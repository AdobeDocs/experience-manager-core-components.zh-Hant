---
title: 吊具上下文感知配置和核心元件
description: 核心元件利用吊具上下文感知配置來實現某些功能
role: Architect, Developer, Admin
exl-id: d35210f7-a65d-4768-ab9e-f12ec406da2d
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---

# 吊具上下文感知配置和核心元件 {#sling-context-aware-configurations}

上下文感知配置是 [吊具的特徵](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)。 它們是與內容資源或資源樹相關的配置，核心元件利用它們來允許站點範圍的配置。

## 吊帶上下文感知配置 {#context-aware-configurations}

您的站點可能需要不同站點區域的不同配置，例如，某些參數可能是共用的，需要繼承嵌套上下文和全局回退值。 利AEM用Sling上下文感知配置，從而實現這一可能性。

有關中的配置的詳細信AEM息， [請參閱配置和配置瀏覽器文檔。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/configurations.html)

## 在核心元件中使用 {#core-components}

許多核心元件功能利用上下文感知配置。 所有此類配置都位於以下節點下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

單個配置取決於特定的元件或功能。 使用上下文感知配置的核心元件的功能包括：

* [PDF查看器元件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe客戶端資料層](/help/developing/data-layer/overview.md#installation-activation)
* [AMP支援](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
