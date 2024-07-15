---
title: 自我調整影像Servlet
description: 瞭解核心元件如何使用最適化影像Servlet來傳送影像，以及如何最佳化其使用。
role: Architect, Developer, Admin, User
exl-id: d9199d51-6f09-4000-9525-afc30474437e
source-git-commit: 785aa82930e3bcf6ef16d7a1cdc614d230e8daa8
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# 自我調整影像Servlet {#adaptive-image-servlet}

瞭解核心元件如何使用最適化影像Servlet來傳送影像，以及如何最佳化其使用。

## 最適化影像Servlet或網頁最佳化的影像傳送？ {#options}

影像核心元件可使用兩種方法來傳送影像。

* 預設為最適化影像Servlet。
* [網頁最佳化的影像傳遞](/help/developing/web-optimized-image-delivery.md)可供AEMaaCS使用，平均將下載大小減少25%。

本檔案說明預設的最適化影像Servlet。

## 概觀 {#overview}

依預設，影像元件會使用核心元件的調適型影像Servlet來傳送影像。 [最適化影像Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet)負責影像處理和串流，可由開發人員在其[核心元件的自訂中](/help/developing/customizing.md)運用。

## 轉譯選擇 {#rendition-selection}

「自我調整影像Servlet」會根據顯示所在的容器大小，自動選取最適合的轉譯。 轉譯選取程式如下。

1. 最適化影像Servlet會檢閱影像資產的所有可用轉譯。
1. 它只會選取與原始參考資產具有相同mime/型別的資產。
   * 例如，如果原始資產是PNG，則只會考慮PNG轉譯。
1. 在這些轉譯中，會考量尺寸，並將尺寸與應顯示影像的容器大小進行比較。
   1. 如果轉譯大於=容器大小，則會將其新增至候選轉譯清單。
   1. 如果轉譯小於容器大小，則忽略該轉譯。
   1. 這些條件可確保轉譯不會放大，進而影響影像品質。
1. 最適化影像Servlet接著會從候選清單中挑選檔案大小最小的轉譯。

## 最佳化轉譯選擇 {#optimizing-rendition-selection}

最適化影像Servlet會嘗試針對請求的影像大小和型別挑選最佳轉譯。 我們建議同步定義DAM轉譯和影像元件允許的寬度，好讓最適化影像Servlet執行儘可能少的處理工作。

這將改善效能，並避免基礎影像處理程式庫無法正確處理某些影像。

## 使用上次修改的標頭 {#last-modified}

最適化影像Servlet支援透過`Last-Modified`標頭進行條件式要求，但是必須在Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#caching-http-response-headers)中啟用`Last-Modified`標頭[的快取。

[AEM專案原型](/help/developing/archetype/overview.md)的範例Dispatcher設定已包含此設定。
