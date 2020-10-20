---
title: Sling Context-Aware Configurations and Core Components
description: The Core Components運用Sling內容感應組態來處理特定功能
translation-type: tm+mt
source-git-commit: 11e2c6da0fa93084b601437fd45fd65dd8d73231
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%

---


# Sling Context-Aware Configurations and Core Components {#sling-context-aware-configurations}

內容感知組態是Sling的功能，是與內容資源或資源樹狀結構相關的組態，並由核心元件運用以允許整個網站的組態。

## Sling Context-Aware Configurations {#context-aware-configurations}

您的網站可能需要不同網站區域的不同設定，例如，某些參數可能是共用的，需要繼承巢狀內容和全域備援值。 AEM運用Sling內容感應組態，可啟用此可能性。

如需AEM中設定的詳細資訊，請 [參閱「設定與設定瀏覽器」檔案。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/configurations.html)

## 用於核心元件 {#core-components}

許多核心元件功能都採用內容感知組態。 所有此類配置都位於以下節點下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

個別組態取決於特定元件或功能。 使用內容感知組態的核心元件的功能包括：

* [PDF檢視器元件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe用戶端資料層](/help/developing/data-layer/overview.md#installation-activation)
* [AMP支援](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
