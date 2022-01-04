---
title: 核心元件簡介
description: '核心元件提供強大且可擴充的基本元件，以最新技術和最佳實務為基礎。 '
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: ef18f65be72295f7886a132a26bdd4f8bc2fbd50
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 23%

---

# 核心元件簡介{#core-components-introduction}

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。元件向來是 AEM 體驗的基本元素，讓作者可輕鬆建立頁面、功能又強大，而開發人員在開發元件時，也可保有靈活性與擴充空間。

核心元件是一套適用於AEM的標準化網頁內容管理(WCM)元件，可縮短開發時間並降低網站的維護成本。

## 資源 {#resources}

* **[元件庫：](https://www.adobe.com/go/aem_cmp_library)** 檢視其各種設定中元件的範例集合。
* **元件文檔（本文檔）:** 針對開發人員和作者，提供每個元件的詳細資訊。
* **[核心元件GitHub存放庫：](https://github.com/adobe/aem-core-wcm-components)** 如需每個元件和專案下載的開發人員詳細資訊。
* 立即開始:
   * **[成功運用核心元件：](/help/developing/success.md)** 在使用核心元件的專案開始前，請先詳加考慮的准則。
   * **[WKND教學課程：](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 建立新網站的為期兩天的教學課程。
   * **[Summit教學課程：](https://expleague.azureedge.net/labs/L767/index.html)** 建立新網站的兩小時教學課程（來自2019年US Summit的Lab）。
   * **[Gems網路研討會：](https://helpx.adobe.com/tw/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)** 核心元件的導覽（2018年12月錄制）。

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 核心元件有28種強大元件，經過良好測試、廣泛使用且效能良好。 |
| 雲就緒 | 是否開啟 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html)，在 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)，或內部部署，這些功能只能運作。 |
| 多功能 | 元件代表一般概念，作者可以用這些概念組合幾乎任何版面。 |
| 可設定 | 範本層級 [內容原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/components-templates/templates.html#content-policies) 定義頁面作者可使用或不可使用的功能。 |
| 可追蹤 | 此 [Adobe用戶端資料層整合](/help/developing/data-layer/overview.md) 可追蹤訪客體驗的所有方面。 |
| 易於取得 | 他們遵守 [WCAG 2.1標準](https://www.w3.org/TR/WCAG21/)，提供ARIA標籤，並支援鍵盤導覽([已知問題](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle))。 |
| SEO友善 | HTML輸出是語義的，提供 [schema.org](https://schema.org) 微資料註解。 |
| WebApp-Ready | 此 [精簡的JSON輸出](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) 允許用戶端轉譯，但仍有可能 [內容內編輯](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html). |
| AMP支援 | 元件已內建 [支援AMP標準，](/help/developing/amp.md) 加速您的行動體驗。 |
| Design Kit | A [適用於Adobe XD的UI套件](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd) 允許設計人員建立線框，然後他們就可以 [視需要設定樣式](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd). |
| 表 | 元件會實作 [樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/components-templates/style-system.html)，標籤如下 [BEM CSS慣例](http://getbem.com/). |
| 可自訂 | 數個模式允許 [輕鬆定制](developing/customizing.md)，從調整HTML到重新使用進階功能。 |
| 版本設定 | 此 [版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) 確保核心元件在改善可能影響您的項目時不會破壞您的網站。 |
| 可本地化 | 智慧型參考解析度可讓特定元件尋找和 [自動呈現對應的本地化內容](get-started/localization.md). |
| 開放來源 | 如果事情不如預期， [貢獻您的改善功能！](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

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
>[開發團隊必須先依照作者的環境整合核心元件](get-started/using.md)，才能將其提供給您。整合後，可透過 [範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>某些版本的個別核心元件可能只相容於特定版本的 AEM。
>
>如需特定元件的相容性資訊，請參閱說明頁面 (連結至上一份清單)，或參考[核心元件版本](versions.md)文件以取得詳細資訊。

## 系統需求 {#system-requirements}

| 核心元件 | AEM as a Cloud Service  | AEM 6.5 | AEM 6.4 | Java SE | 馬文 |
|---------|---------|---------|---------|---------|---------|
| [2.17.14](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.14) | 持續 | 6.5.6.0+ * | 6.4.8.4+ * | 8, 11 | 3.3.9+ |

>[!NOTE]
>
>(*)自2.11.0版起， `org.apache.sling.models.impl` 需要1.4.12版或更新版本(由於 [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781))。 這將在未來的Service Pack中提供給AEM 6.4和6.5。 在此之前，Sling模型套件組合會包含在 `core.wcm.components.all` 包。

如需先前核心元件版本的需求，請參閱 [核心元件版本](versions.md).

核心元件需使用 [可編輯的範本](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) 不支援傳統UI或靜態範本。 如有需要，請查看 [AEM現代化工具](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) 使用這些現代化的AEM功能更新專案。

若要設定本機開發環境，請簽出 [此AEMas a Cloud ServiceSDK概述](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) 或此文檔 [適用於舊版AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

>[!TIP]
>
>核心元件會自動成為AEMas a Cloud Service的一部分，且您一律會有最新版的核心元件。
>
>請參閱 [使用核心元件](/help/get-started/using.md) 如需如何在AEMaCS和內部部署中開始使用核心元件的詳細資訊，請參閱檔案。
