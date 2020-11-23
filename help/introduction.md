---
title: 核心元件簡介
description: '核心元件提供強穩且可擴充的基本元件，以最新技術和最佳實務為基礎。 '
translation-type: tm+mt
source-git-commit: 850fbeec3cb31f4ea6873daa2555953684fd5a8d
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 24%

---


# 核心元件簡介{#core-components-introduction}

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。元件向來是 AEM 體驗的基本元素，讓作者可輕鬆建立頁面、功能又強大，而開發人員在開發元件時，也可保有靈活性與擴充空間。

核心元件是一套適用於AEM的標準化網頁內容管理(WCM)元件，可加速開發時間並降低網站的維護成本。

## 資源 {#resources}

* **[元件庫：](https://www.adobe.com/go/aem_cmp_library)** 一組示例，用於查看其各種配置中的元件。
* **元件文檔（本文檔）:** 對於開發人員和作者，請提供每個元件的詳細資訊。
* **[核心元件GitHub儲存庫：](https://github.com/adobe/aem-core-wcm-components)** 如需每個元件和專案下載的開發人員詳細資訊。
* 立即開始:
   * **[核心元件的成功：](/help/developing/success.md)** 在開始使用核心元件的任何專案之前，先考慮的准則。
   * **[WKND教學課程：](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 建立新網站的兩天教學課程。
   * **[峰會教學課程：](https://expleague.azureedge.net/labs/L767/index.html)** 建立新網站的兩小時教學課程（來自2019年美國峰會的實驗室）。
   * **[Gems網路研討會：](https://helpx.adobe.com/tw/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)** 核心元件導覽（2018年12月錄制）。

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 核心元件是28種強穩的元件，經過良好測試、廣泛使用，而且效能良好。 |
| 雲端就緒 | 不論是 [在AEM做為雲端服務](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)、在 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)，或是在內部部署，都只能運作。 |
| 多功能 | 這些元件代表一般概念，作者可用這些概念組合幾乎任何版面。 |
| 可配置 | 範本層級 [的內容原則](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#content-policies) ，定義頁面作者可使用或不可使用的功能。 |
| 可追蹤 | [Adobe用戶端資料層整合](/help/developing/data-layer/overview.md) ，可讓您追蹤訪客體驗的所有方面。 |
| 易於取得 | They comply [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), provide ARIA labels, and support keyboard navigation ([known issues](https://github.com/adobe/aem-core-wcm-components/issues?utf8= ✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)). |
| SEO-Fliendly | The HTML output is semantic and provides [schema.org](https://schema.org) microdata annotations. |
| WebApp-Ready | 簡 [化的JSON輸出](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) ，可讓用戶端轉換，但仍有可 [能進行內容編輯](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。 |
| AMP支援 | 這些元件內建了AMP標 [準支援，可加速您的行動](/help/developing/amp.md) 體驗。 |
| 設計套件 | Adobe XD [的UI套件](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd) ，可讓設計人員建立線框，並視需 [要設定樣式](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_WKND.xd)。 |
| Themeable | The components implement the [Style System](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/style-system.html), and the markup follows [BEM CSS conventions](http://getbem.com/). |
| 可自訂 | 從調整HTML到 [重複使用進階功能](developing/customizing.md)，數種模式都可讓您輕鬆自訂。 |
| 版本設定 | 版 [本修訂政策](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) ，可確保核心元件在改善可能影響您的項目時不會中斷您的網站。 |
| 可本地化 | Smart reference resolution allows certain components to find and [render corresponding localized content automatically](get-started/localization.md). |
| 開放來源 | 如果事情不如預期，請 [改進！](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## 元件 {#the-components}

目前版本的核心元件主打下列元件。

### 範本元件 {#template-components}

* [頁面](components/page.md)
* [導覽](components/navigation.md)
* [語言導覽](components/language-navigation.md)
* [階層連結](components/breadcrumb.md)
* [快速搜尋](components/quick-search.md)

### 頁面編寫元件 {#page-authoring-components}

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
* [社交媒體分享](components/sharing.md)
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
>[開發團隊必須先依照作者的環境整合核心元件](get-started/using.md)，才能將其提供給您。整合後，可透過範本編輯器提供並預先 [設定](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。

>[!NOTE]
>
>某些版本的個別核心元件可能只相容於特定版本的 AEM。
>
>如需特定元件的相容性資訊，請參閱說明頁面 (連結至上一份清單)，或參考[核心元件版本](versions.md)文件以取得詳細資訊。

## 系統需求 {#system-requirements}

| 核心元件 | AEM as a Cloud Service  | AEM 6.5 | AEM 6.4 | Java SE | 馬文 |
|---------|---------|---------|---------|---------|---------|
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | 持續 | 6.5.5.0+ * | 6.4.8.1+ * | 8, 11 | 3.3.9+ |

>[!NOTE]
>
>(*)自2.11.0版起， `org.apache.sling.models.impl` 需要1.4.12版或更新版本(由 [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781))。 這將在未來的Service Pack中針對AEM 6.4和6.5提供。 在此之前，Sling Models套件已包含在套件 `core.wcm.components.all` 中。

如需舊版核心元件的需求，請參閱核 [心元件版本](versions.md)。

核心元件需要使用可編輯的 [範本](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) ，不支援Classic UI或靜態範本。 如有需要，請查看 [AEM現代化工具](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) ，以使用這些現代化AEM功能更新您的專案。

若要設定您的本機開發環境，請 [以Cloud Service SDK的形式查看此AEM概觀](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) ，或以舊 [版AEM的檔案形式查看本檔案](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。
