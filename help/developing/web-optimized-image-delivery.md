---
title: 網頁最佳化的影像交付
description: 瞭解核心元件如何運用AEMas a Cloud Service的網頁最佳化影像傳送功能，以更有效率地傳送影像。
role: Architect, Developer, Admin, User
exl-id: 6080ab8b-f53c-4d5e-812e-16889da4d7de
source-git-commit: d8c8f4c3395313b21f56fd7d98175924287c367c
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 0%

---

# 網頁最佳化的影像交付 {#web-optimized-image-delivery}

瞭解核心元件如何運用AEMas a Cloud Service的網頁最佳化影像傳送功能，以更有效率地傳送影像。

## 概觀 {#overview}

AEM as a Cloud Service的網頁最佳化影像傳送功能可從以下位置傳送來自DAM的影像資產： [WebP格式。](https://developers.google.com/speed/webp) WebP平均可將影像的下載大小縮減約25%，進而加快頁面載入速度。

在核心元件中啟用網頁最佳化的影像傳遞很簡單，而且由於所有常見瀏覽器都支援WebP，因此體驗對一般使用者而言是透明的。 他們會注意到的唯一差異是內容載入速度更快！

## 啟用核心元件的Web最佳化影像傳送 {#activating}

若要啟用Web最佳化的影像傳送，請編輯頁面範本並直接啟動選項 **啟用Web最佳化的影像** 在「 」的「設計」對話方塊中 [影像元件。](/help/components/image.md#design-dialog) 此選項適用於影像元件的v1、v2和v3。

如果您不熟悉設計對話方塊和AEM頁面範本， [請檢閱此檔案。](/help/get-started/authoring.md#pre-configuring-core-components)

![在設計對話方塊中啟用Web最佳化影像傳送](/help/assets/web-optimized-image-delivery.png)

就是這樣！影像現在由影像元件以WebP格式傳送。

在啟用網頁最佳化的影像傳送後，您可能也想要檢查您的Dispatcher設定，以確認其不會封鎖對影像服務的請求。 此服務的URL採用以下形式。

```text
/adobe/dynamicmedia/deliver/dm-aid--741ed388-d5f8-4797-8095-10c896dc9f1d/skitouring.jpg?quality=80&preferwebp=true
```

這可以用此規則運算式來推廣。

```text
\/adobe\/dynamicmedia\/deliver\/([^:[]|*\/])\/([\w-])\.(gif|png|png8|jpg|pjpg|bjpg|webp|webpll|webply)(?[a-z0-9=&]*)?
```

## 驗證WebP傳遞 {#verifying}

網頁最佳化的影像傳送對內容的消費者是透明的，不會影響標籤。 一般使用者只會注意到載入時間變快。

因此，若要觀察行為的實際變更，您必須檢視頁面來源。

1. 在AEM中，編輯以範本為基礎的頁面，您可以 [已啟動網頁最佳化的影像傳遞](#activating) 用於影像元件。
1. 在頁面編輯器中，選取 **頁面資訊** 左上角的按鈕，然後 **以發佈的形式檢視**.
1. 使用您的瀏覽器開發工具，檢視頁面來源並檢視呈現的標籤如何保持不變，但影像在 `src` 屬性指向 [新影像服務的URL。](#activating)

## 當Web最佳化的影像傳送無法使用時 {#fallback}

網頁最佳化的影像傳遞僅適用於AEMas a Cloud Service。 如果無法使用該功能(例如在內部部署或本機開發執行個體上執行AEM 6.5)，則影像傳送會退回使用 [自我調整影像Servlet。](/help/developing/adaptive-image-servlet.md)

正如啟用Web最佳化的影像傳送不會影響標籤一樣，退回撥適型影像Servlet也不會影響標籤，因為只有 `src` 的屬性 `img` 元素已變更。

## 常見問題 {#faq}

### 為什麼在我的環境中沒有啟用Web最佳化影像的選項？ {#missing-option}

此功能僅適用於AEMas a Cloud Service。 在本機或內部部署（影像元件）執行AEM [回覆](#fallback) 以使用最適化影像Servlet。

### 此服務為何無法搭配本機SDK運作？ {#local-sdk}

在上使用AEM SDK時 `localhost`，影像服務無法使用，且影像演算 [回覆](#fallback) 以使用最適化影像Servlet。

若要使用Web最佳化的影像傳送服務，請將專案部署到AEMaaCS開發環境，以便能夠精確測試影像服務與影像服務的行為方式。

### 為什麼該服務無法用於我頁面上的某些影像？ {#some-images}

影像服務僅適用於下的資產 `/content/dam` 對於直接上傳至頁面並儲存在下的影像則無法運作。 `cq:Page` 物件。 這類資產仍會以自適應影像Servlet的身分傳遞 [遞補內容。](#fallback)

### 為什麼此服務會顯示品質較差的影像或限制影像大小？ {#quality}

網頁最佳化的影像服務會考量所有2048畫素和更小的影像轉譯，並挑選最大的影像轉譯作為套用請求之設定（寬度、裁切、格式、品質等）的基礎。

影像服務絕對不會放大影像。 因此，這些轉譯會定義影像服務能夠傳送的最佳大小和品質。 因此，請確定您的資產都有2048畫素的縮放轉譯，如果沒有，請重新處理。

### 我的影像URL仍以.PNG或。JPG結尾，而非.WEBP，而且沒有SRCSET屬性或PICTURE元素。 這真的使用最佳化的網頁格式嗎？ {#content-negotiation}

為了傳遞WebP格式，網頁最佳化的影像傳遞服務使用稱為「內容交涉」的技術。 這包括傳回WebP檔案格式，即使在請求JPG或PNG副檔名時也是如此，但僅當發出請求的瀏覽器提供 `image/webp` HTTP接受標頭。 支援此技術的瀏覽器就可以提供此標題，而較舊的瀏覽器仍會取得JPG或PNG檔案格式。

此技巧的優點在於 `img` 元素及其屬性可以維持不變，這將為現有網站帶來最佳相容性，並確保以最順暢的方式過渡到網頁最佳化的影像傳送。

### 我可以搭配自己的元件使用Web最佳化的影像傳送嗎？

可以，自訂元件可使用網頁最佳化的影像傳送服務。 Adobe建議 [擴充影像元件](/help/developing/customizing.md) 在此案例中。

以下服務介面可用於協助產生資產URL。

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

**請注意，如果體驗不是透過在AEM Sites CS上執行的核心元件所建置，則直接URL會違反Media Library授權條款。**

### 新影像服務所傳送的影像URL為何？ {#url}

請參閱上一節 [啟用核心元件的Web最佳化影像傳送](#activating) 例如URL和規則運算式。

### 啟用Web最佳化的影像後，影像是否會無法顯示？

不，這絕不應該發生。

* 在HTML中，啟用Web最佳化影像時，標籤不會變更，只有影像元素上SRC屬性的值會變更。
* 每當新的影像服務無法使用或無法處理所需的影像時，產生的URL將 [後援至最適化影像Servlet。](#fallback)
* Dispatcher規則可能會封鎖網頁最佳化的影像服務，並且 [啟動功能時應該勾選。](#activating)
