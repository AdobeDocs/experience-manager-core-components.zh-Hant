---
title: 自適應影像Servlet
description: 瞭解核心元件如何使用自適應映像Servlet進行映像傳送，以及如何優化其使用。
role: Architect, Developer, Admin, User
exl-id: d9199d51-6f09-4000-9525-afc30474437e
source-git-commit: 420e6085da57e5dc6deb670a5f0498b018441cb8
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# 自適應影像Servlet {#adaptive-image-servlet}

瞭解核心元件如何使用自適應映像Servlet進行映像傳送，以及如何優化其使用。

## 自適應影像伺服器還是Web優化影像傳送？ {#options}

影像核心元件可以使用兩種方法傳送影像。

* 預設為Adaptive Image Servlet。
* [Web優化的影像傳送](/help/developing/web-optimized-image-delivery.md) AEMaaCS可用，平均下載量減少25%。

本文檔介紹預設的Adaptive Image Servlet。

## 概觀 {#overview}

預設情況下，映像元件使用核心元件的自適應映像Servlet傳送映像。 [自適應映像Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) 負責影像處理和流式處理，開發人員可以利用 [核心元件的自定義](/help/developing/customizing.md)。

## 格式副本選擇 {#rendition-selection}

Adaptive Image Servlet將根據顯示該格式的容器的大小自動選擇要顯示的最合適的格式副本。 格式副本選擇過程如下所示。

1. Adaptive Image Servlet會查看影像資產的所有可用格式副本。
1. 它只選擇那些具有原始引用資產的相同MIME/類型的資產。
   * 例如，如果原始資產是PNG，則它將只考慮PNG格式副本。
1. 其中，格式副本會考慮尺寸，並將它們與應在其中顯示影像的容器的大小進行比較。
   1. 如果格式副本為>=容器大小，則會將其添加到候選格式副本清單中。
   1. 如果格式副本為&lt;容器大小，則不會考慮它。
   1. 這些標準確保不會對格式副本進行上調，這會影響影像質量。
1. 然後，Adaptive Image Servlet從候選清單中選取檔案大小最小的格式副本。

## 優化格式副本選擇 {#optimizing-rendition-selection}

Adaptive Image Servlet將嘗試根據請求的影像大小和類型選擇最佳格式副本。 建議同步定義DAM格式副本和影像元件允許的寬度，以便Adaptive Image Servlet盡可能少地處理。

這將提高效能，並避免某些影像無法被底層影像處理庫正確處理。

## 使用上次修改的標頭 {#last-modified}

通過 `Last-Modified` 頭由Adaptive Image Servlet支援，但快取的 `Last-Modified` 標題 [需要在Dispatcher中啟用](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#caching-http-response-headers)。

[項AEM目原型](/help/developing/archetype/overview.md)的Dispatcher配置示例已包含此配置。
