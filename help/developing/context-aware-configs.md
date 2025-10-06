---
title: Sling 內容感知設定和核心元件
description: 核心元件將 Sling 內容感知設定用於特定功能
role: Architect, Developer, Admin
exl-id: d35210f7-a65d-4768-ab9e-f12ec406da2d
source-git-commit: b72defe1bbe6cb286730ac3f508f7d6c14b3fc33
workflow-type: ht
source-wordcount: '174'
ht-degree: 100%

---

# Sling 內容感知設定和核心元件 {#sling-context-aware-configurations}

內容感知設定是 [Sling 功能](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)。這些是與內容資源或資源樹相關的設定，並由核心元件用於允許全網站設定。

## Sling 內容感知設定 {#context-aware-configurations}

您的網站可能需要針對不同網站區域進行不同的設定，例如，部分參數可能共用，需要巢狀內容和全域遞補值的繼承。AEM 利用 Sling 內容感知設定實現了這種可能性。

如需 AEM 中設定的詳細資訊，[請參閱設定和設定瀏覽器文件。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/configurations.html)

## 在核心元件中使用 {#core-components}

許多核心元件功能採用內容感知設定。所有這類設定都位於以下節點下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

個別設定取決於特定元件或功能。使用內容感知設定的核心元件功能包括：

* [頁面元件](https://github.com/adobe/aem-core-wcm-components/tree/main/content/src/content/jcr_root/apps/core/wcm/components/page/v3/page#loading-of-context-aware-cssjs)在呈現 `link`、`script` 和 `meta` 索引標籤時需仰賴內容感知設定。
* [PDF 檢視器元件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe Client Data Layer](/help/developing/data-layer/overview.md#installation-activation)
* [AMP 支援](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
