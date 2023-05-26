---
title: Sling內容感知設定和核心元件
description: 核心元件針對特定功能運用Sling內容感知設定
role: Architect, Developer, Admin
exl-id: d35210f7-a65d-4768-ab9e-f12ec406da2d
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---

# Sling內容感知設定和核心元件 {#sling-context-aware-configurations}

內容感知設定是 [Sling功能](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html). 這些是與內容資源或資源樹相關的設定，並由核心元件用於允許全網站設定。

## Sling內容感知設定 {#context-aware-configurations}

您的網站可能需要針對不同網站區域進行不同的設定，例如，某些可能共用的引數需要巢狀上下文和全域後援值的繼承。 AEM運用Sling內容感知設定來啟用此可能性。

如需AEM設定的詳細資訊， [請參閱設定和設定瀏覽器檔案。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/configurations.html)

## 用於核心元件 {#core-components}

許多核心元件功能會運用內容感知設定。 所有這類設定都位於下列節點下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

個別組態視特定元件或功能而定。 使用內容感知設定的核心元件功能包括：

* [PDF檢視器元件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe使用者端資料層](/help/developing/data-layer/overview.md#installation-activation)
* [AMP支援](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
