---
title: 自適應影像Servlet
description: 瞭解核心元件如何使用自適應映像Servlet進行映像傳送，以及如何優化其使用。
role: Architect, Developer, Admin, User
source-git-commit: 3ff1343ab4ef7a52f910984a0bcd8fc4201441bf
workflow-type: tm+mt
source-wordcount: '254'
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

## 優化格式副本選擇 {#optimizing-rendition-selection}

Adaptive Image Servlet將嘗試根據請求的影像大小和類型選擇最佳格式副本。 建議同步定義DAM格式副本和影像元件允許的寬度，以便Adaptive Image Servlet盡可能少地處理。

這將提高效能，並避免某些影像無法被底層影像處理庫正確處理。

## 使用上次修改的標頭 {#last-modified}

通過 `Last-Modified` 頭由Adaptive Image Servlet支援，但快取的 `Last-Modified` 標題 [需要在Dispatcher中啟用](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#caching-http-response-headers)。

[項AEM目原型](/help/developing/archetype/overview.md)的Dispatcher配置示例已包含此配置。
