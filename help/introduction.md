---
title: 核心元件簡介
description: '核心元件提供強大且可擴充的基本元件，以最新技術和最佳實務為基礎。 '
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: cc8c3275bf251b4c390ee66588f34bac7c0ec218
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 25%

---

# 核心元件簡介{#core-components-introduction}

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。元件向來是 AEM 體驗的基本元素，讓作者可輕鬆建立頁面、功能又強大，而開發人員在開發元件時，也可保有靈活性與擴充空間。

核心元件是一套適用於AEM的標準化網頁內容管理(WCM)元件，可縮短開發時間並降低網站的維護成本。

## 資源 {#resources}

* **[元件程式庫：](https://www.adobe.com/go/aem_cmp_library)** 檢視其各種設定中元件的範例集合。
* **元件檔案（本檔案）:** 適用於開發人員和作者，提供每個元件的詳細資訊。
* **[核心元件GitHub存放庫：](https://github.com/adobe/aem-core-wcm-components)** 如需每個元件和專案下載的開發人員詳細資訊。
* 立即開始:
   * **[成功運用核心元件：](/help/developing/success.md)** 准則可在使用核心元件的任何專案開始前先行考慮。
   * **[WKND教學課程：](https://docs.adobe.com/content/help/zh-Hant/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 建置新網站的兩天教學課程。
   * **[Summit教學課程：](https://expleague.azureedge.net/labs/L767/index.html)** 建置新網站的兩小時教學課程（來自2019年US Summit的Lab）。
   * **[Gems網路研討會：](https://helpx.adobe.com/tw/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)** 核心元件導覽（2018年12月錄制）。

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 核心元件有28種強大元件，經過良好測試、廣泛使用且效能良好。 |
| 雲就緒 | 無論是在[AEM as aCloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)、在[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署上，都只能運作。 |
| 多功能 | 元件代表一般概念，作者可以用這些概念組合幾乎任何版面。 |
| 可設定 | 範本層級[內容原則](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#content-policies)定義頁面作者可以使用或不使用的功能。 |
| 可追蹤 | [Adobe用戶端資料層整合](/help/developing/data-layer/overview.md)可追蹤訪客體驗的所有方面。 |
| 易於取得 | 它們符合[WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/)、提供ARIA標籤，以及支援鍵盤導覽（[已知問題](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)）。 |
| SEO友善 | HTML輸出為語意，提供[schema.org](https://schema.org)微資料注釋。 |
| WebApp-Ready | [簡化的JSON輸出](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html)允許用戶端轉譯，但仍可能進行[內容內編輯](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。 |
| AMP支援 | 這些元件已內建[支援AMP標準，](/help/developing/amp.md)加速您的行動體驗。 |
| Design Kit | 適用於Adobe XD的[UI套件](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)可讓設計人員建立線框，然後他們可以根據需要[樣式](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd)。 |
| 表 | 元件實作[樣式系統](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/style-system.html)，標籤遵循[BEM CSS慣例](http://getbem.com/)。 |
| 可自訂 | 有幾種模式可讓[輕鬆自訂](developing/customizing.md)，從調整HTML到重新使用進階功能。 |
| 版本設定 | [版本化原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)可確保核心元件在改善可能影響您的項目時不會破壞您的網站。 |
| 可本地化 | 智慧型參考解析度可讓特定元件自動尋找和[轉譯對應的本地化內容](get-started/localization.md)。 |
| 開放來源 | 如果某個項目不如預期，[會提供您的改善！](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## 元件 {#the-components}

目前版本的核心元件主打下列元件。

### 範本元件 {#template-components}

* [頁面](components/page.md)
* [導覽](components/navigation.md)
* [語言導覽](components/language-navigation.md)
* [階層連結](components/breadcrumb.md)
* [快速搜尋](components/quick-search.md)

### 頁面製作元件 {#page-authoring-components}

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
>[開發團隊必須先依照作者的環境整合核心元件](get-started/using.md)，才能將其提供給您。整合後，可透過[範本編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)使用並預先設定。

>[!NOTE]
>
>某些版本的個別核心元件可能只相容於特定版本的 AEM。
>
>如需特定元件的相容性資訊，請參閱說明頁面 (連結至上一份清單)，或參考[核心元件版本](versions.md)文件以取得詳細資訊。

## 系統需求 {#system-requirements}

| 核心元件 | AEM as a Cloud Service  | AEM 6.5 | AEM 6.4 | Java SE | 馬文 |
|---------|---------|---------|---------|---------|---------|
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | 持續 | 6.5.6.0+ * | 6.4.8.4+ * | 8, 11 | 3.3.9+ |

>[!NOTE]
>
>(*)自2.11.0版起，需要`org.apache.sling.models.impl` 1.4.12版或更新版本（因為[SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)）。 這將在未來的Service Pack中提供給AEM 6.4和6.5。 在此之前，Sling模型套件組合會包含在`core.wcm.components.all`套件中。

如需舊版核心元件的需求，請參閱[核心元件版本](versions.md)。

核心元件需要使用[可編輯的範本](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，且不支援傳統UI或靜態範本。 如有需要，請查看[AEM現代化工具](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html)，以使用這些現代化的AEM功能更新您的專案。

若要設定您的本機開發環境，請查看[本AEM as aCloud ServiceSDK](https://docs.adobe.com/content/help/zh-Hant/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)概覽，或本檔案[以了解舊版AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。

>[!TIP]
>
>核心元件會自動成為AEMCloud Service的一部分，而且您一律有最新版的核心元件。
>
>如需如何在AEMaaCS和內部部署中開始使用核心元件的詳細資訊，請參閱[使用核心元件](/help/get-started/using.md)檔案。
