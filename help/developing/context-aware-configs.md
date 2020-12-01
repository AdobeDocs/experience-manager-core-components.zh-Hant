---
title: Sling Context-Aware Configurations and Core Components
description: The Core Components運用Sling內容感應組態來處理特定功能
translation-type: tm+mt
source-git-commit: aff9046008dcea6c0cbda4b3de400df77a507097
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---


# Sling Context-Aware Configurations and Core Components {#sling-context-aware-configurations}

上下文感知組態是Sling](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)的[功能。 它們是與內容資源或資源樹相關的配置，並由核心元件利用這些配置來允許整個站點的配置。

## Sling Context-Aware Configurations {#context-aware-configurations}

您的網站可能需要不同網站區域的不同設定，例如，某些參數可能是共用的，需要繼承巢狀內容和全域備援值。 AEM運用Sling內容感應組態，可啟用此可能性。

如需AEM中設定的詳細資訊，請參閱「設定與設定瀏覽器」檔案。[](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/configurations.html)

## 在核心元件{#core-components}中使用

許多核心元件功能都採用內容感知組態。 所有此類配置都位於以下節點下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

個別組態取決於特定元件或功能。 使用內容感知組態的核心元件的功能包括：

* [PDF檢視器元件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe用戶端資料層](/help/developing/data-layer/overview.md#installation-activation)
* [AMP支援](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
