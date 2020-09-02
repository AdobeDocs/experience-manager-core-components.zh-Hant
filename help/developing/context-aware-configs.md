---
title: Sling Context-Aware Configurations and Core Components
description: The Core Components運用Sling內容感應組態來處理特定功能
translation-type: tm+mt
source-git-commit: 24a810ff634f8846881dfa0095e879476d0f16f0
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---


# Sling Context-Aware Configurations and Core Components {#sling-context-aware-configurations}

內容感知組態是Sling的功能，是與內容資源或資源樹狀結構相關的組態，並由核心元件運用以允許整個網站的組態。

## Sling Context-Aware Configurations {#context-aware-configurations}

您的網站可能需要不同網站區域的不同設定，例如，某些參數可能是共用的，需要繼承巢狀內容和全域備援值。 Sling上下文感知組態啟用此功能。

如需Sling內容感應組態的完整詳細資訊，請 [參閱Apache檔案。](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)

## 用於核心元件 {#core-components}

許多核心元件功能都採用內容感知組態。 所有此類配置都位於以下節點下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

個別組態取決於特定元件或功能。 使用內容感知組態的核心元件的功能包括：

* [PDF檢視器元件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe用戶端資料層](/help/developing/data-layer/overview.md#installation-activation)
* [AMP支援](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
