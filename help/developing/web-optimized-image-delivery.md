---
title: 網頁最佳化的影像交付
description: 瞭解核心元件如何運用AEMas a Cloud Service的網頁最佳化影像傳送功能，以更有效率地傳送影像。
role: Architect, Developer, Admin, User
exl-id: 6080ab8b-f53c-4d5e-812e-16889da4d7de
source-git-commit: eb1822cb41a849695afb5125745ed5f78e3e70a4
workflow-type: tm+mt
source-wordcount: '1061'
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

啟用網頁最佳化的影像傳送後，您可以檢查Dispatcher設定，確認其不會封鎖對影像傳送服務的請求。 請參閱 [此常見問題集專案](#failure-to-deliver) 以取得詳細資訊。

## 驗證WebP傳遞 {#verifying}

網頁最佳化的影像傳送對內容的消費者而言是透明的。 一般使用者只會注意到載入時間變快。 因此，若要觀察行為的任何實際變更，您必須檢查瀏覽器中演算後影像的內容型別。 所有現代瀏覽器都支援WebP。 您可參閱 [此網站](https://caniuse.com/webp) 以取得瀏覽器支援的詳細資訊。

1. 在AEM中，編輯以範本為基礎的頁面，您可以 [已啟動網頁最佳化的影像傳遞](#activating) 用於影像元件。
1. 在頁面編輯器中，選取 **頁面資訊** 左上角的按鈕，然後 **以發佈的形式檢視**.
1. 開啟瀏覽器的開發人員工具，然後選取「網路」標籤。
1. 重新載入頁面，並尋找載入影像的HTTP請求，然後檢查瀏覽器收到的影像內容型別。

## 當Web最佳化的影像傳送無法使用時 {#fallback}

網頁最佳化的影像傳遞僅適用於AEMas a Cloud Service。 如果無法使用該功能(例如在內部部署或本機開發執行個體上執行AEM 6.5)，則影像傳送會退回使用 [自我調整影像Servlet。](/help/developing/adaptive-image-servlet.md)

遞補為最適化影像Servlet會變更 `src` 的屬性 `img` 頁面來源中的元素。

## 常見問題 {#faq}

### 為什麼在我的環境中沒有啟用Web最佳化影像的選項？ {#missing-option}

此功能僅適用於AEMas a Cloud Service。 在本機或內部部署（影像元件）執行AEM [回覆](#fallback) 以使用最適化影像Servlet。

### 此服務為何無法搭配本機SDK運作？ {#local-sdk}

在上使用AEM SDK時 `localhost`，影像服務無法使用，且影像演算 [回覆](#fallback) 以使用最適化影像Servlet。

若要使用Web最佳化的影像傳送服務，請將專案部署到AEMaaCS開發環境，以便能夠精確測試影像服務與影像服務的行為方式。

### 為什麼該服務無法用於我頁面上的某些影像？ {#some-images}

影像服務僅適用於下的資產 `/content/dam` 對於直接上傳至頁面並儲存在下的影像則無法運作。 `cq:Page` 物件。 這類資產仍會以自適應影像Servlet的身分傳遞 [遞補內容。](#fallback)

### 為什麼此服務會顯示品質較差的影像或限制影像大小？ {#quality}

當影像資產位於 `/content/dam` 都會處理，AEMas a Cloud Service的環境會產生不同維度的最佳化轉譯。 網頁最佳化的影像服務會分析影像核心元件要求的寬度，考量原始影像及所有2048畫素或以下大小的轉譯，並挑選影像服務可處理的最大值(在大小和維度限制內，目前為50 MB， `12k`x`12k`)作為套用請求之設定（寬度、裁切、格式、品質等）的基礎。

為了保留輸出的逼真度，影像服務不會放大影像。 上述轉譯定義了影像服務能夠提供的最佳品質。 由於您通常無法影響原始影像資產的大小和/或尺寸，請確定您的影像資產都有2048畫素的縮放轉譯，如果沒有，請重新處理。

### 我的影像URL仍以.PNG或。JPG結尾，而非.WEBP，而且沒有SRCSET屬性或PICTURE元素。 這真的使用最佳化的網頁格式嗎？ {#content-negotiation}

為了傳遞WebP格式，網頁最佳化的影像傳遞服務會執行 [伺服器驅動的內容交涉。](https://developer.mozilla.org/en-US/docs/Web/HTTP/Content_negotiation#server-driven_content_negotiation) 這有助於根據使用者端廣告功能選擇影像的最佳輸出格式，讓影像傳送服務可忽略副檔名。

運用內容交涉的優點在於，未廣告支援WebP的瀏覽器仍會取得JPG或PNG檔案格式，而不需要變更頁面的標籤。 這樣可為現有網站提供最佳相容性，並確保以最順暢的方式過渡到網頁最佳化的影像傳送。

### 我可以搭配自己的元件使用Web最佳化的影像傳送嗎？

可以，自訂元件可使用網頁最佳化的影像傳送服務，建立者為 [擴充影像元件，](/help/developing/customizing.md)

以下服務介面可用於協助產生資產URL。

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

>[!WARNING]
>
>非透過上述SPI (可在AEMas a Cloud Service網站上取得)建立的體驗中的直接URL嵌入違反了 [Media Library使用條款](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/admin/medialibrary.html?lang=en#use-media-library).

### 啟用Web最佳化的影像後，影像是否會無法顯示？ {#failure-to-deliver}

否，由於下列原因，此情況絕不應該發生。

* 在HTML中，啟用Web最佳化影像時，標籤不會變更，只會變更 `src` 影像元素上的屬性會變更。
* 每當新的影像服務無法使用或無法處理所需的影像時，產生的URL將 [後援至最適化影像Servlet。](#fallback)

不過，Dispatcher規則可能會封鎖網頁最佳化的影像傳送服務。 影像傳遞服務的URL開頭為 `/adobe`，並檢查Dispatcher記錄檔中拒絕的請求 [此處說明](https://experienceleague.adobe.com/docs/experience-manager-learn/ams/dispatcher/common-logs.html#filter-rejects) 應該有助於疑難排解將影像傳送至瀏覽器期間所遇到的任何問題。
