---
title: Sling內容感知組態與核心元件
description: 核心元件針對特定功能運用Sling內容感知設定
role: Architect, Developer, Admin
exl-id: d35210f7-a65d-4768-ab9e-f12ec406da2d
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---

# Sling內容感知組態與核心元件 {#sling-context-aware-configurations}

內容感知設定是Sling](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)的[功能。 這些設定與內容資源或資源樹相關，並由核心元件運用以允許全網站設定。

## Sling內容感知設定 {#context-aware-configurations}

您的網站可能需要針對不同網站區域進行不同設定，例如某些參數可能會共用，而巢狀內容和全域後援值需要繼承。 AEM採用Sling內容感知設定，因此可能。

有關AEM中配置的詳細資訊，請[參閱配置和配置瀏覽器文檔。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/configurations.html)

## 用於核心元件 {#core-components}

許多核心元件功能採用內容感知設定。 所有此類配置都位於以下節點下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

個別設定取決於特定元件或功能。 使用內容感知設定的核心元件功能包括：

* [PDF Viewer元件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe用戶端資料層](/help/developing/data-layer/overview.md#installation-activation)
* [AMP支援](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
