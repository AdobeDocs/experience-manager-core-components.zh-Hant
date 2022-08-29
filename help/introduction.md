---
title: 核心元件簡介
description: '獲取核心元件問題的解決方案，並允許其他人在中建立元AEM素。 '
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: 12fef6732ba53beeb7b3354335005f459321da96
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 23%

---

# 核心元件簡介{#core-components-introduction}

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。元件向來是 AEM 體驗的基本元素，讓作者可輕鬆建立頁面、功能又強大，而開發人員在開發元件時，也可保有靈活性與擴充空間。

核心元件是一組標準化的Web內容管理(WCM)元件AEM，用於加快開發時間並降低網站的維護成本。

## 資源 {#resources}

* **[元件庫：](https://www.adobe.com/go/aem_cmp_library)** 一組示例，用於查看各種配置中的元件。
* **元件文檔（本文檔）:** 對於開發人員和作者，提供有關每個元件的詳細資訊。
* **[核心元件GitHub儲存庫：](https://github.com/adobe/aem-core-wcm-components)** 有關每個元件和項目下載的開發人員詳細資訊。
* 立即開始:
   * **[核心元件成功：](/help/developing/success.md)** 在使用核心元件的任何項目開始之前考慮的准則。
   * **[WKND教程：](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 用於構建新站點的兩天教程。
   * **[峰會教程：](https://expleague.azureedge.net/labs/L767/index.html)** 一個兩小時的教程，用於構建新站點（來自2019年美國峰會實驗室）。
   * **[Gems網路研討會：](https://helpx.adobe.com/tw/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)** 核心元件指導教程（2018年12月錄制）。

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 核心元件是30個強健的元件，經過良好測試、廣泛使用，效能良好。 |
| 雲就緒 | 是否開啟 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html)。 [Adobe托管服務](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或者在內部，它們只是起作用。 |
| 多功能 | 這些元件代表一般概念，作者可以用這些概念裝配幾乎任何佈局。 |
| 可配置 | 模板級 [內容策略](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies) 定義允許頁作者使用或不使用的功能。 |
| 可跟蹤 | 的 [Adobe客戶端資料層整合](/help/developing/data-layer/overview.md) 允許跟蹤訪問者體驗的所有方面。 |
| 易於取得 | 他們遵守 [WCAG 2.1標準](https://www.w3.org/TR/WCAG21/)，提供ARIA標籤和支援鍵盤導航([已知問題](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+輔助功能+in%3Atitle))。 |
| SEO友好 | HTML輸出是語義的，並提供 [架構.org](https://schema.org) 微資料注釋。 |
| WebApp就緒 | 的 [精簡的JSON輸出](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) 允許客戶端呈現，但仍有可能 [上下文編輯](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。 |
| AMP支援 | 這些元件內置了 [支援AMP標準，](/help/developing/amp.md) 加速移動體驗。 |
| 設計套件 | A [用於Adobe XD的UI套件](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd) 允許設計人員建立線框，然後 [根據需要的樣式](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd)。 |
| 泰默 | 元件實現 [樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)的 [BEM CSS約定](http://getbem.com/)。 |
| 可定製 | 幾種模式允許 [輕鬆定制](developing/customizing.md)，從調整HTML到高級功能重用。 |
| 版本設定 | 的 [版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) 確保核心元件在改進可能影響您的內容時不會中斷您的站點。 |
| 可本地化 | 智慧參考解析度允許某些元件查找和 [自動呈現相應的本地化內容](get-started/localization.md)。 |
| 開源 | 如果事情不如預期， [幫你改進！](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## 元件 {#the-components}

目前版本的核心元件主打下列元件。

### 模板元件 {#template-components}

* [Page](components/page.md)
* [導覽](components/navigation.md)
* [語言導覽](components/language-navigation.md)
* [階層連結](components/breadcrumb.md)
* [快速搜尋](components/quick-search.md)
* [目錄](components/tableofcontents.md)

### 頁面創作元件 {#page-authoring-components}

* [標題](components/title.md)
* [文字](components/text.md)
* [影像](components/image.md)
* [按鈕](components/button.md)
* [Teaser](components/teaser.md)
* [下載](components/download.md)
* [清單](components/list.md)
* [體驗片段](components/experience-fragment.md)
* [內容片段](components/content-fragment-component.md)
* [內容片段清單](components/content-fragment-list.md)
* [內嵌](components/embed.md)
* [社交媒體共用](components/sharing.md) （不建議使用）
* [分隔符號](components/separator.md)
* [進度列](components/progress-bar.md)
* [PDF 檢視器](components/pdf-viewer.md)

### 容器元件 {#container-components}

* [容器](components/container.md)
* [傳送](components/carousel.md)
* [索引標籤](components/tabs.md)
* [折疊式面板](components/accordion.md)

### 表單元件 {#form-components}

* [來自容器](components/forms/form-container.md)
* [表單文字](components/forms/form-text.md)
* [表單選項](components/forms/form-options.md)
* [已隱藏的表單](components/forms/form-hidden.md)
* [表單按鈕](components/forms/form-button.md)

>[!NOTE]
>
>[開發團隊必須先依照作者的環境整合核心元件](get-started/using.md)，才能將其提供給您。整合後，可通過 [模板編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)。

>[!NOTE]
>
>某些版本的個別核心元件可能只相容於特定版本的 AEM。
>
>如需特定元件的相容性資訊，請參閱說明頁面 (連結至上一份清單)，或參考[核心元件版本](versions.md)文件以取得詳細資訊。

## 系統要求 {#system-requirements}

| 核心元件 版 | AEM as a Cloud Service  | AEM 6.5修補程式級別 | Java SE版本 | 馬文版本 |
|---------|---------|---------|---------|---------|
| [2.20.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.6) | 連續 | 6.5.13.0+ * | 8、11 | 3.3.9+ |

>[!NOTE]
>
>(*)自2.11.0版以來， `org.apache.sling.models.impl` 1.4.12版或更高版本(由於 [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781))。 這將在將AEM來的Service Pack中為6.4和6.5提供。 在此之前，「吊具模型」捆綁包包含在 `core.wcm.components.all` 檔案。

有關以前核心元件版本的要求，請參閱 [核心元件版本](versions.md)。

核心元件要求 [可編輯模板](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) 不支援Classic UI和靜態模板。 如果需要，請查看 [現代化AEM工具](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) 用這些現代功能更新您的AEM項目。

要設定本地開發環境，請簽出 [as a Cloud ServiceSDK的AEM本概述](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) 或 [對於舊版本AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。

>[!TIP]
>
>核心元件自動是AEMas a Cloud Service的一部分，並且您始終擁有最新版本的核心元件。
>
>查看 [使用核心元件](/help/get-started/using.md) 文檔，瞭解有關如何在AEMaaCS和內部部署中開始使用核心元件的詳細資訊。
