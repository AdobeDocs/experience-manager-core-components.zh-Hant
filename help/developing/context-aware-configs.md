---
title: Sling Context-Aware Configurations and Core Components
description: The Core Components運用Sling內容感應組態來處理特定功能
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---


# Sling Context-Aware Configurations and Core Components {#sling-context-aware-configurations}

上下文感知組態是Sling](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)的[功能。 它們是與內容資源或資源樹相關的配置，並由核心元件利用這些配置來允許整個站點的配置。

## Sling Context-Aware Configurations {#context-aware-configurations}

您的網站可能需要不同網站區域的不同設定，例如，某些參數可能是共用的，需要繼承巢狀內容和全域備援值。 運AEM用Sling上下文感知組態，可啟用此可能性。

有關中配置的詳AEM細資訊，請參閱配置和配置瀏覽器文檔。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/configurations.html)[

## 在核心元件{#core-components}中使用

許多核心元件功能都採用內容感知組態。 所有此類配置都位於以下節點下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

個別組態取決於特定元件或功能。 使用內容感知組態的核心元件的功能包括：

* [PDF檢視器元件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe客戶端資料層](/help/developing/data-layer/overview.md#installation-activation)
* [AMP支援](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
