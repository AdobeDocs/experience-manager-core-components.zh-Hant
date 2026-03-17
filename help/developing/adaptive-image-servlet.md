---
title: 最適化影像 Servlet
description: 了解「核心元件」如何使用「最適化影像 Servlet」傳遞影像，以及如何最佳化其使用。
role: Developer, Admin, User
exl-id: d9199d51-6f09-4000-9525-afc30474437e
source-git-commit: 7ba1374bd64686c2e7ac44398d77fb187ff60949
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 89%

---

# 最適化影像 Servlet {#adaptive-image-servlet}

了解「核心元件」如何使用「最適化影像 Servlet」傳遞影像，以及如何最佳化其使用。

>[!WARNING]
>
>基於效能考量，強烈建議將影像儲存在 DAM 中，並使用網頁最佳化的影像傳遞。
>
>將影像直接儲存在元件節點下只適用於偶爾使用。 無法利用 DAM 轉譯減少在「最適化影像 Servlet」中的處理，且不允許網頁最佳化影像傳遞的效能優勢，因此可能會導致效能問題。

## 最適化影像 Servlet 或網頁最佳化影像傳遞？ {#options}

「影像核心元件」可使用兩種方法來傳遞影像。

* 預設為「最適化影像 Servlet」。
* [網頁最佳化影像傳遞](/help/developing/web-optimized-image-delivery.md)適用於 AEMaaCS，平均減少 25% 的下載大小。

本文件說明預設的「最適化影像 Servlet」。

## 概觀 {#overview}

依預設，影像元件會使用核心元件的調適型影像Servlet來傳送影像。[最適化影像Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet)負責影像處理和串流，可由開發人員在其[核心元件的自訂中](/help/developing/customizing.md)運用。

## 轉譯選取 {#rendition-selection}

「最適化影像 Servlet」會根據顯示容器的大小，自動選取最適合的轉譯顯示。 轉譯選取過程如下。

1. 「最適化影像 Servlet」檢閱影像資產的所有可用轉譯。
1. 它只會選取與原始參考資產具有相同 MIME/類型的資產。
   * E.g. 如果原始資產是PNG，則只會考慮PNG轉譯。
1. 在這些轉譯中，會考量尺寸，並將尺寸與應顯示影像的容器大小進行比較。
1. 如果轉譯大於或等於容器大小，則會將其新增至候選轉譯清單。
1. 如果轉譯小於容器大小，則會忽略該轉譯。
1. 這些條件可確保轉譯不會放大，進而影響影像品質。
1. 接著，「最適化影像 Servlet」會從候選清單中挑選檔案大小最小的轉譯。

## 最佳化轉譯選取 {#optimizing-rendition-selection}

「最適化影像 Servlet」會嘗試根據所要求的影像大小和類型，挑選最佳轉譯。 建議同步定義 DAM 轉譯和影像元件允許的寬度，盡可能減少「最適化影像 Servlet」的處理量。

這將提升效能，並避免基礎影像處理程式庫無法正確處理某些影像。

## 使用 Last-Modified 頁首 {#last-modified}

「最適化影像 Servlet」支援透過 `Last-Modified` 頁首的條件式要求，但[必須在 Dispatcher 中啟用 &#x200B;](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=zh-hant#caching-http-response-headers) `Last-Modified` 頁首的快取。

[AEM 專案原型的](/help/developing/archetype/overview.md)範例 Dispatcher 設定已包含此設定。
