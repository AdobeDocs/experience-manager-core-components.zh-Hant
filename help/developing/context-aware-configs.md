---
title: Sling內容感知設定和核心元件
description: 核心元件針對特定功能運用Sling內容感知設定
role: Architect, Developer, Admin
exl-id: d35210f7-a65d-4768-ab9e-f12ec406da2d
source-git-commit: b72defe1bbe6cb286730ac3f508f7d6c14b3fc33
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---

# Sling內容感知設定和核心元件 {#sling-context-aware-configurations}

內容感知設定是Sling[&#128279;](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)的功能。 這些是與內容資源或資源樹相關的設定，並由核心元件用於允許全網站設定。

## Sling內容感知設定 {#context-aware-configurations}

您的網站可能需要針對不同網站區域進行不同的設定，例如，部分引數可能共用，需要巢狀上下文和全域遞補值的繼承。 AEM運用Sling內容感知設定實現了這種可能性。

如需AEM中設定的詳細資訊，[請參閱設定和設定瀏覽器檔案。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/configurations.html?lang=zh-Hant)

## 在核心元件中使用 {#core-components}

許多核心元件功能採用內容感知設定。 所有這類設定都位於以下節點下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

個別組態取決於特定元件或功能。 使用內容感知設定的核心元件功能包括：

* [頁面元件](https://github.com/adobe/aem-core-wcm-components/tree/main/content/src/content/jcr_root/apps/core/wcm/components/page/v3/page#loading-of-context-aware-cssjs)在呈現`link`、`script`和`meta`標籤時需仰賴內容感知設定。
* [PDF檢視器元件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe使用者端資料層](/help/developing/data-layer/overview.md#installation-activation)
* [AMP支援](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
