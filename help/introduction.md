---
title: 核心元件簡介
description: 取得核心元件問題的解決方案，並允許其他人在AEM中編寫元素。
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: 7b618358ca4689cb496fec7db6a6ec7cecbc8fdc
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 23%

---


# 核心元件簡介{#core-components-introduction}

>[!TIP]
>
>**您是否考慮過為AEM使用Edge Delivery Services？**
>
>您可以繼續使用本檔案所述的方法處理現有專案。 不過，若是新專案，Adobe建議使用[Edge Delivery Services.](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/edge-delivery/overview)

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。元件向來是 AEM 體驗的基本元素，讓作者可輕鬆建立頁面、功能又強大，而開發人員在開發元件時，也可保有靈活性與擴充空間。

核心元件是適用於AEM的一組標準化網站內容管理(WCM)元件，可加快開發時間並降低網站的維護成本。

## 資源 {#resources}

* **[元件庫：](https://www.adobe.com/go/aem_cmp_library)**&#x200B;檢視各種組態中元件的範例集合。
* **元件檔案（本檔案）：**&#x200B;對於開發人員和作者，包含每個元件的詳細資訊。
* **[核心元件GitHub存放庫：](https://github.com/adobe/aem-core-wcm-components)**&#x200B;如需每個元件和專案下載的開發人員詳細資訊。
* 開始使用：
   * **[使用核心元件成功：](/help/developing/success.md)**&#x200B;在任何將使用核心元件的專案開始之前要考慮的准則。
   * **[WKND教學課程：](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**&#x200B;有關建立新網站的兩天教學課程。
   * **[Summit教學課程：](https://expleague.azureedge.net/labs/L767/index.html)**&#x200B;有關建立新網站的兩小時教學課程（來自US Summit 2019的實驗室）。
   * **[Gems網路研討會：](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)**&#x200B;核心元件的導覽（於2018年12月錄製）。

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 核心元件是30種經過充分測試、廣泛使用且效能出色的強大WCM元件。 |
| 雲端就緒 | 無論是在[AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html)、[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)還是內部部署，這些元件都能運作。 |
| 多功能 | 這些元件代表作者可用來組裝幾乎任何版面的一般概念。 |
| 可設定 | 範本層級[內容原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies)定義頁面作者可以使用或不使用的功能。 |
| [回應式](responsive.md) | 所有核心元件的設計都可充分回應，確保裝置間的順暢體驗 |
| 可追蹤 | [Adobe Client Data Layer整合](/help/developing/data-layer/overview.md)允許追蹤訪客體驗的各個層面。 |
| 易於取得 | 它們符合[WCAG 2.1標準](https://www.w3.org/TR/WCAG21/)，提供ARIA標籤，並支援鍵盤導覽（[已知問題](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)）。 |
| SEO友善 | HTML輸出是語意且提供[schema.org](https://schema.org)微資料註解。 |
| WebApp就緒 | [簡化的JSON輸出](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/develop-sling-model-exporter.html)允許使用者端轉譯，仍可進行[內容內編輯](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。 |
| AMP支援 | 元件已內建[AMP標準支援，](/help/developing/amp.md)可加速您的行動體驗。 |
| 設計套件 | Adobe XD[&#128279;](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)的UI套件可讓設計人員建立線框，然後視需要[設定樣式](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd)。 |
| 可主題化 | 元件實作[樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)，標籤遵循[BEM CSS慣例](https://getbem.com/)。 |
| 可自訂 | 數個模式可讓[輕鬆自訂](developing/customizing.md)，從調整HTML到進階功能重複使用。 |
| 版本設定 | [版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)可確保核心元件在改善可能影響您的內容時，不會中斷您的網站。 |
| 可本地化 | 智慧型參考解析可讓特定元件自動尋找及[轉譯對應的本地化內容](get-started/localization.md)。 |
| 開放來源 | 如果有出錯的地方，請[貢獻您的改善專案！](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |


## WCM元件 {#the-wcm-components}

目前版本的核心元件主打下列元件。

### 範本元件 {#template-components}

* [頁面](components/page.md)
* [導覽](components/navigation.md)
* [語言導覽](components/language-navigation.md)
* [階層連結](components/breadcrumb.md)
* [快速搜尋](components/quick-search.md)
* [目錄](components/tableofcontents.md)

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
* [嵌入](components/embed.md)
* [社群媒體共用](components/sharing.md) （已棄用）
* [分隔符號](components/separator.md)
* [進度列](components/progress-bar.md)
* [PDF 檢視器](components/pdf-viewer.md)

### 容器元件 {#container-components}

* [容器](components/container.md)
* [傳送](components/carousel.md)
* [標籤](components/tabs.md)
* [折疊面板](components/accordion.md)

### 表單元件 {#form-components}

* [表單容器](components/forms/form-container.md)
* [表單文字](components/forms/form-text.md)
* [表單選項](components/forms/form-options.md)
* [已隱藏的表單](components/forms/form-hidden.md)
* [表單按鈕](components/forms/form-button.md)

>[!NOTE]
>
>[開發團隊必須先依照作者的環境整合核心元件](get-started/using.md)，才能將其提供給您。整合後，可透過[範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)使用及預先設定。

>[!NOTE]
>
>某些版本的個別核心元件可能只相容於特定版本的 AEM。
>
>如需特定元件的相容性資訊，請參閱說明頁面 (連結至上一份清單)，或參考[核心元件版本](versions.md)文件以取得詳細資訊。

## 系統需求 {#system-requirements}

| 核心元件發行版本 | AEM as a Cloud Service | AEM 6.5 LTS | AEM 6.5 | Java SE版本 | Maven版本 |
|---|---|---|---|---|---|
| [2.28.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.28.0) | 持續 | 6.5 LTS GA | 6.5.21.0+ | 8， 11 | 3.3.9+ |

如需舊版核心元件的需求，請參閱[核心元件版本](versions.md)。

核心元件需要使用[可編輯的範本](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，而且不支援傳統UI或靜態範本。 如有需要，請檢視[AEM現代化工具](https://opensource.adobe.com/aem-modernize-tools/)，以使用這些現代化AEM功能更新您的專案。

若要設定您的本機開發環境，請檢視[此AEM as a Cloud Service SDK概觀](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)或此檔案[舊版AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。

>[!TIP]
>
>核心元件會自動成為AEM as a Cloud Service的一部分，且您隨時會擁有最新版本的核心元件。
>
>如需如何在AEMaaCS和內部部署中開始使用核心元件的詳細資訊，請參閱[使用核心元件](/help/get-started/using.md)檔案。

## 其他元件 {#other-components}

AEM作者可以使用以核心元件為基礎的其他元件。

* [電子郵件核心元件](/help/email/introduction.md) — 探索建置在核心元件之上並專門用於Adobe Campaign的元件。
