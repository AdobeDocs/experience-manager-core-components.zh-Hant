---
title: 核心元件簡介
description: '核心元件提供強穩且可擴充的基本元件，以最新技術和最佳實務為基礎。 '
translation-type: tm+mt
source-git-commit: defc6f2cf4cac817577f3e74372da5e420a45ead
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 24%

---


# 核心元件簡介{#core-components-introduction}

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。元件向來是 AEM 體驗的基本元素，讓作者可輕鬆建立頁面、功能又強大，而開發人員在開發元件時，也可保有靈活性與擴充空間。

核心元件是一套適用於AEM的標準化網頁內容管理(WCM)元件，可加速開發時間並降低網站的維護成本。

## 資源 {#resources}

* **[元件庫：](https://www.adobe.com/go/aem_cmp_library)** 在各種組態中檢視元件的範例集合。
* **元件檔案（本檔案）：對於開** 發人員和作者，請提供每個元件的詳細資訊。
* **[核心元件GitHub存放庫：如需每](https://github.com/adobe/aem-core-wcm-components)** 個元件和專案下載的開發人員詳細資訊。
* 立即開始:
   * **[核心元件的成功：](/help/developing/success.md)** 在開始使用核心元件的專案之前，先考慮相關准則。
   * **[WKND教學課](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 程：建立新網站的兩天教學課程。
   * **[峰會教學課](https://expleague.azureedge.net/labs/L767/index.html)** 程：建立新網站的兩小時教學課程（來自2019年美國峰會的實驗室）。
   * **[Gems網路研討會：](https://helpx.adobe.com/tw/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)** 核心元件導覽（於2018年12月錄制）。

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 核心元件是28種強穩的元件，經過良好測試、廣泛使用，而且效能良好。 |
| 雲端就緒 | 不論是在[AEM當做雲端服務](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)、在[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署中，都只能運作。 |
| 多功能 | 這些元件代表一般概念，作者可用這些概念組合幾乎任何版面。 |
| 可配置 | 範本層級[內容原則](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#content-policies)定義頁面作者可使用或不使用的功能。 |
| 可追蹤 | [Adobe用戶端資料層整合](/help/developing/data-layer/overview.md)可追蹤訪客體驗的所有方面。 |
| 易於取得 | 它們符合[WCAG 2.1標準](https://www.w3.org/TR/WCAG21/)，提供ARIA標籤，並支援鍵盤導覽（[已知問題](https://github.com/adobe/aem-core-wcm-components/issues?utf8= ✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)）。 |
| SEO-Fliendly | HTML輸出是語義的，提供[schema.org](https://schema.org)微資料注釋。 |
| WebApp-Ready | [簡化的JSON輸出](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html)允許用戶端轉譯，但仍有[內容內容編輯](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)的可能。 |
| AMP支援 | 這些元件內建[支援AMP標準，](/help/developing/amp.md)可加速您的行動體驗。 |
| 設計套件 | Adobe XD的[UI套件可讓設計人員建立線框，然後視需要[樣式](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd)。](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd) |
| Themeable | 元件實施[樣式系統](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/style-system.html)，標籤遵循[BEM CSS約定](http://getbem.com/)。 |
| 可自訂 | 從調整HTML到進階功能的重複使用，有幾種模式可讓[輕鬆自訂](developing/customizing.md)。 |
| 版本設定 | [版本控制原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)可確保核心元件在改善可能影響您的項目時不會中斷您的網站。 |
| 可本地化 | 智慧型參考解析度可讓特定元件自動尋找及[轉換對應的本地化內容。](get-started/localization.md) |
| 開放來源 | 如果某些項目不如預期，[會提供您的改進！](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## 元件 {#the-components}

目前版本的核心元件主打下列元件。

### 範本元件{#template-components}

* [頁面](components/page.md)
* [導覽](components/navigation.md)
* [語言導覽](components/language-navigation.md)
* [階層連結](components/breadcrumb.md)
* [快速搜尋](components/quick-search.md)

### 頁面編寫元件{#page-authoring-components}

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

### 容器元件{#container-components}

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
>[開發團隊必須先依照作者的環境整合核心元件](get-started/using.md)，才能將其提供給您。整合後，可透過[範本編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)使它們可用並預先設定。

>[!NOTE]
>
>某些版本的個別核心元件可能只相容於特定版本的 AEM。
>
>如需特定元件的相容性資訊，請參閱說明頁面 (連結至上一份清單)，或參考[核心元件版本](versions.md)文件以取得詳細資訊。

## 系統要求{#system-requirements}

| 核心元件 | AEM as a Cloud Service  | AEM 6.5 | AEM 6.4 | Java SE | 馬文 |
|---------|---------|---------|---------|---------|---------|
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | 持續 | 6.5.5.0+ * | 6.4.8.1+ * | 8, 11 | 3.3.9+ |

>[!NOTE]
>
>(*)自2.11.0版起，需要`org.apache.sling.models.impl` 1.4.12版或更新版本（由於[SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)）。 這將在未來的Service Pack中針對AEM 6.4和6.5提供。 在此之前，Sling Models組合包會包含在`core.wcm.components.all`套件中。

如需舊版核心元件的需求，請參閱[核心元件版本](versions.md)。

核心元件需要使用[可編輯的範本](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，且不支援Classic UI或靜態範本。 視需要查看[AEM Meduration Tools](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html)，以使用這些現代化的AEM功能更新您的專案。

若要設定您的本機開發環境，請參閱[本AEM的Cloud Service SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)概觀，或本檔案[中較舊版本的AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。
