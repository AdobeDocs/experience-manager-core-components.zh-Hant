---
title: 網頁最佳化影像傳遞
description: 了解核心元件如何運用 AEM as a Cloud Service 的網頁最佳化影像傳遞功能，更有效率地傳遞影像。
role: Architect, Developer, Admin, User
exl-id: 6080ab8b-f53c-4d5e-812e-16889da4d7de
source-git-commit: eb1822cb41a849695afb5125745ed5f78e3e70a4
workflow-type: ht
source-wordcount: '1061'
ht-degree: 100%

---

# 網頁最佳化影像傳遞 {#web-optimized-image-delivery}

了解核心元件如何運用 AEM as a Cloud Service 的網頁最佳化影像傳遞功能，更有效率地傳遞影像。

## 概觀 {#overview}

AEM as a Cloud Service 的網頁最佳化影像傳遞功能會以 [WebP 格式從 DAM 傳遞影像資產。](https://developers.google.com/speed/webp)WebP 平均可將影像的下載大小縮減約 25%，進而加快頁面載入速度。

在核心元件中啟用網頁最佳化影像傳遞很簡單，而且由於所有常見瀏覽器都支援 WebP，因此一般使用者並不會感受到變化。他們會注意到的唯一差異是內容載入速度更快！

## 啟用核心元件的網頁最佳化影像傳遞 {#activating}

若要啟用網頁最佳化影像傳遞，請編輯頁面範本，然後在[影像元件的設計對話框內啟用&#x200B;**啟用網頁最佳化影像**&#x200B;選項即可。](/help/components/image.md#design-dialog)此選項適用於影像元件的 v1、v2 和 v3。

如果您不熟悉設計對話框和 AEM 頁面範本，[請檢視此文件。](/help/get-started/authoring.md#pre-configuring-core-components)

![在設計對話框中啟用網頁最佳化影像傳遞](/help/assets/web-optimized-image-delivery.png)

就是這樣！影像現在由影像元件以 WebP 格式傳遞。

啟用網頁最佳化影像傳遞後，您可以檢查 Dispatcher 設定，確認其不會封鎖對影像傳送服務的請求。如需詳細資訊，請參閱[常見問題集的此項目](#failure-to-deliver)。

## 驗證 WebP 傳遞 {#verifying}

網頁最佳化影像傳遞對內容使用者來說是說是無感的。一般使用者只會注意到載入時間變快。因此，若要觀察行為的任何實際變更，您必須檢查瀏覽器中呈現後影像的內容類型。現今所有瀏覽器都支援 WebP。如需瀏覽器支援的詳細資訊，請參閱[本網站](https://caniuse.com/webp) 。

1. 在 AEM 中，編輯以範本為基礎的頁面，您在該範本中已為影像元件[啟動網頁最佳化影像傳遞](#activating)。
1. 在頁面編輯器中，選取左上方的「**頁面資訊**」按鈕，然後選取「**以發佈頁面形式檢視**」。
1. 開啟瀏覽器的開發人員工具，然後選取「網路」索引標籤。
1. 重新載入頁面，並尋找載入影像的 HTTP 請求，然後檢查瀏覽器收到的影像內容類型。

## 當網頁最佳化影像傳遞無法使用時 {#fallback}

網頁最佳化影像傳遞僅適用於 AEM as a Cloud Service。如果無法使用該功能 (例如在內部部署或本機開發執行個體上執行 AEM 6.5)，則影像傳遞將使用[最適化影像 Servlet](/help/developing/adaptive-image-servlet.md) 進行遞補。

使用最適化影像 Servlet 進行遞補時，會變更頁面原始碼中 `img` 元素的 `src` 屬性。

## 常見問題 {#faq}

### 為什麼在我的環境中沒有啟用網頁最佳化影像的選項？ {#missing-option}

此功能僅適用於 AEM as a Cloud Service。在本機或內部部署執行 AEM 時，影像元件將使用最適化影像 Servlet 進行[遞補](#fallback)。

### 此服務為何無法搭配本機 SDK 運作？ {#local-sdk}

在 `localhost` 上使用 AEM SDK 時，影像服務無法使用，影像轉譯將使用最適化影像 Servlet 進行[遞補](#fallback)。

若要使用網頁最佳化影像傳遞服務，請將專案部署到 AEMaaCS 開發環境，以便能夠精確測試影像服務與影像服務的行為方式。

### 為什麼該服務無法用於我頁面上的某些影像？ {#some-images}

影像服務僅適用於位於 `/content/dam` 下的資產，不適用於直接上傳至頁面並儲存在 `cq:Page` 物件下的影像。此類資產仍會透過最適化影像 Servlet 以[遞補](#fallback)內容的形式傳遞。

### 為什麼此服務會顯示品質較差的影像或限制影像大小？ {#quality}

處理 `/content/dam` 下的影像資產時，AEM as a Cloud Service 環境會產生不同維度的最佳化轉譯。網頁最佳化影像服務會分析影像核心元件要求的寬度、考量原始影像及所有 2048 像素或以下的轉譯，並挑選影像服務可以處理的最大值 (在大小和維度限制內，目前為 50 MB 和 `12k`x`12k`) 作為套用所要求設定 (寬度、裁切、格式、品質等) 的基礎。

為了保留輸出的逼真度，影像服務不會放大影像。上述轉譯定義了影像服務能夠傳遞的最佳品質。由於您通常無法影響原始影像資產的大小和/或尺寸，請確定您的影像資產都有 2048 像素的縮放轉譯，如果沒有，請重新處理。

### 我的影像 URL 仍以 .JPG 或 .PNG 結尾，而非 .WEBP，而且沒有 SRCSET 屬性或 PICTURE 元素。這真的使用了最佳化的網頁格式嗎？ {#content-negotiation}

為了傳遞 WebP 格式，網頁最佳化的影像傳遞服務會執行[伺服器驅動的內容交涉。](https://developer.mozilla.org/en-US/docs/Web/HTTP/Content_negotiation#server-driven_content_negotiation)這有助於根據用戶端廣告功能選擇影像的最佳輸出格式，讓影像傳遞服務忽略副檔名。

運用內容交涉的優點在於，即使瀏覽器未宣告支援 WebP 格式，仍可取得 JPG 或 PNG 檔案格式，而不需要變更頁面標記。這樣可為現有網站提供最佳相容性，並確保以最順暢的方式過渡到網頁最佳化影像傳遞。

### 我可以搭配自己的元件使用網頁最佳化影像傳遞嗎？

可以，自訂元件可以使用網頁最佳化影像傳遞服務，只要這些元件是藉由[擴充影像元件](/help/developing/customizing.md)所建置。

以下服務介面可用於協助產生資產 URL。

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

>[!WARNING]
>
>非透過上述 SPI (可在 AEM as a Cloud Service 網站上取得) 建置的體驗中的直接 URL 內嵌違反[媒體庫使用條款](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/admin/medialibrary.html?lang=zh-hant#use-media-library)。

### 啟用網頁最佳化影像後，影像是否會無法顯示？ {#failure-to-deliver}

否，由於下列原因，此情況絕不應該發生。

* 在 HTML 中，啟用網頁最佳化影像時，標記不會變更，只有影像元素上的 `src` 屬性值會變更。
* 每當新的影像服務無法使用或無法處理所需的影像時，產生的 URL 將[遞補為最適化影像 Servlet。](#fallback)

不過，Dispatcher 規則可能會封鎖網頁最佳化影像傳遞服務。影像傳遞服務的 URL 以 `/adobe` 開頭，並依照[此處所述](https://experienceleague.adobe.com/docs/experience-manager-learn/ams/dispatcher/common-logs.html?lang=zh-Hant#filter-rejects)檢查 Dispatcher 記錄檔以找出拒絕的請求，應該有助於疑難排解將影像傳遞至瀏覽器時遇到的所有失敗。
