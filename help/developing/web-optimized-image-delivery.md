---
title: Web優化的映像交付
description: 瞭解核心元件如何AEM利用as a Cloud Service的Web優化映像交付功能更高效地提供映像。
role: Architect, Developer, Admin, User
exl-id: 6080ab8b-f53c-4d5e-812e-16889da4d7de
source-git-commit: df0ae972ca698e809a5cb8a5ad2d41ad89c2db8e
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 0%

---

# Web優化的映像交付 {#web-optimized-image-delivery}

瞭解核心元件如何AEM利用as a Cloud Service的Web優化映像交付功能更高效地提供映像。

>[!NOTE]
>
>Web優化映像交付服務是預發佈功能，2022年6月發佈的AEMas a Cloud Service預計將於7月正式發佈。
>
>有關AEMaaCS的預發行功能的詳細資訊，請參閱文檔 [Adobe Experience Manager as a Cloud Service預發行頻道](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html)

##  概觀 {#overview}

作為雲服務的Web優化AEM的映像交付功能可從 [WebP格式。](https://developers.google.com/speed/webp) WebP平均可將影像的下載大小減少約25%，從而加快頁面載入。

在核心元件中激活Web優化影像傳輸非常簡單，而且由於所有常用瀏覽器都支援WebP，因此體驗對最終用戶是透明的。 他們會注意到的唯一區別是內容載入速度更快！

## 激活核心元件的Web優化影像傳送 {#activating}

要啟用Web優化的影像傳送，請編輯頁面模板，然後只需激活選項 **啟用Web優化映像** 在 [影像元件。](/help/components/image.md#design-dialog) 此選項可用於映像元件的v1 、 v2和v3。

如果您不熟悉設計對話框和頁AEM面模板， [請查看此文檔。](/help/get-started/authoring.md#pre-configuring-core-components)

![在設計對話框中啟用Web優化的影像傳遞](/help/assets/web-optimized-image-delivery.png)

就這樣！ 影像現在由WebP格式的影像元件傳送。

激活Web優化的映像傳送後，您可能還希望檢查調度程式配置以驗證它是否不會阻止對映像服務的請求。 此服務的URL採用以下形式。

```text
/adobe/dynamicmedia/deliver/dm-aid--741ed388-d5f8-4797-8095-10c896dc9f1d/skitouring.jpg?quality=80&preferwebp=true
```

這可以用這個規則運算式來推廣。

```text
\/adobe\/dynamicmedia\/deliver\/([^:[]|*\/])\/([\w-])\.(gif|png|png8|jpg|pjpg|bjpg|webp|webpll|webply)(?[a-z0-9=&]*)?
```

## 驗證WebP傳遞 {#verifying}

Web優化的影像傳遞對內容的使用者是透明的，並且不影響標籤。 最終用戶唯一注意到的是加快載入時間。

因此，要觀察實際行為的變化，必須查看頁面源。

1. 在AEM中，編輯基於您所在的模板的頁面 [激活的Web優化影像傳送](#activating) 表徵圖。
1. 在頁面編輯器中，選擇 **頁面資訊** 按鈕 **查看為已發佈**。
1. 使用瀏覽器開發工具，查看頁面的源，並查看呈現的標籤如何保持不變，但是影像在 `src` 屬性點到 [新映像服務的URL。](#activating)

## 當Web優化映像交付不可用時 {#fallback}

Web優化的影像傳送僅在AEMas a Cloud Service。 如果無法使用，例如在AEM本地或本地開發實例上運行6.5 ，則映像交付將退回到使用 [自適應映像Servlet。](/help/developing/adaptive-image-servlet.md)

正如啟用Web優化影像傳遞不會影響標籤一樣，回退到Adaptive Image Servlet對標籤也沒有影響，因為只有URL位於 `src` 屬性 `img` 元素。

## 常見問題 {#faq}

### 為什麼在我的環境中沒有啟用Web優化映像的此類選項？ {#missing-option}

該功能僅在AEMas a Cloud Service上可用。 本地AEM或本地運行映像元件 [倒](#fallback) 到使用Adaptive Image Servlet。

### 為什麼服務不與本地SDK配合使用？ {#local-sdk}

使用AEMSDK時 `localhost`，影像服務不可用，影像呈現 [倒](#fallback) 到使用Adaptive Image Servlet。

要使用Web優化的映像傳遞服務，請將項目部署到AEMaaCS開發環境，以便能夠準確test映像服務與映像服務的行為方式。

### 為什麼服務不適用於我頁面上的某些影像？ {#some-images}

映像服務僅適用於位於 `/content/dam` 它不適用於直接上載到頁面並儲存在 `cq:Page` 的雙曲餘切值。 此類資產仍將與Adaptive Image Servlet一起作為 [回退。](#fallback)

### 為什麼服務顯示質量較差的影像或限制影像大小？ {#quality}

Web優化影像服務將所有2048px和更小的影像呈現形式都考慮在內，並選取其中最大的格式副本作為應用所請求設定的基礎（寬度、裁剪、格式、質量等）。

影像服務永遠不會升級影像。 因此，這些格式副本定義了映像服務能夠提供的最佳大小和質量。 因此，請確保您的資產都具有2048px縮放格式副本，如果它們沒有，則重新處理它們。

### 我的影像的URL仍以。JPG或.PNG結尾，而不是.WEBP，並且沒有SRCSET屬性或PICTURE元素。 這是否真的在使用優化的Web格式？ {#content-negotiation}

為了提供WebP格式，Web優化影像傳輸服務使用一種稱為「內容協商」的技術。 這包括返回WebP檔案格式，即使當請求JPG或PNG檔案副檔名時，也是如此，但僅當發出請求的瀏覽器提供 `image/webp` HTTP接受標頭。 然後，支援此技術的瀏覽器可以提供此標題，而較舊的瀏覽器仍將獲得JPG或PNG檔案格式。

這種技術的優點是 `img` 元素及其屬性可以保持不變，這將導致現有站點的最佳相容性，並確保向web優化映像交付過渡的最平滑的可能路徑。

### 是否可以將Web優化的映像交付與自己的元件一起使用？

是的，Web優化映像交付服務可供自定義元件使用。 Adobe建議 [擴展影像元件](/help/developing/customizing.md) 在這個例子中。

以下是服務介面，可用於幫助生成資產URL。

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

此服務將資產資源作為強制的第一個參數，並可以為要應用的所需映像轉換建立可選映射，該映射可包含以下參數。

* `path`  — 要交付的資產ID必須為模式 `([^:\[\]\|\*\/]+)` (例如： `unicorn–1234`)
* `seoname`  — 要附加到影像URL的以用戶定義、以SEO為中心的名稱，可能包含連字元，必須為模式 `([\w-]+)` (例如： `my-friend-the-unicorn`)
* `format`  — 所需的影像格式可 `gif`。 `png`。 `png8`。 `jpg`。 `pjpg`。 `bjpg`。 `webp`。 `webpll`。 `webply` (例如： `webp`)
* `preferwebp`  — 如果可能，傳遞WebP輸出，忽略 `format` 參數([請參閱有關內容協商的常見問題](#content-negotiation))，布爾值(例如： `true`)
* `width`  — 所需的影像解析度（以像素為單位）必須大於1(例如： `400`)
* `quality`  — 所需的壓縮，介於 `1` 和 `100` (例如： `75`)
* `c`  — 所需的影像裁剪坐標，逗號分隔的像素值(例如： `100,100,400,200`)
* `r`  — 所需的影像旋轉，可以 `90`。 `180`。 `270` (例如： `90`)
* `flip`  — 所需的影像翻轉，可 `h`。 `v`。 `hv` (例如： `h`)

### 新映像服務傳遞的映像的URL是什麼？ {#url}

請參閱上一節 [激活核心元件的Web優化影像傳送](#activating) 例如URL和規則運算式。

### 啟用Web優化映像後，映像是否無法顯示？

不，這不該發生。

* 在HTML中，啟用Web優化影像時，標籤不會更改，只會更改影像元素上SRC屬性的值。
* 當新映像服務不可用或無法處理所需映像時，生成的URL將 [回退到Adaptive Image Servlet。](#fallback)
* 調度器規則可以阻止網路優化的影像服務和 [激活特徵時應檢查。](#activating)
