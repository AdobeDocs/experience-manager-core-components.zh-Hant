---
title: 核心元件簡介
description: 取得核心元件問題的解決方案，並允許其他人在 AEM 中製作元素。
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: b6b850237bdab1cb59a81c3162182e5b25fbdb68
workflow-type: ht
source-wordcount: '836'
ht-degree: 100%

---


# 核心元件簡介{#core-components-introduction}

{{traditional-aem}}

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。元件向來是 AEM 體驗的基本元素，讓作者可輕鬆建立頁面、功能又強大，而開發人員在開發元件時，也可保有靈活性與擴充空間。

核心元件是一組適用於 AEM 的標準化網站內容管理 (WCM) 元件，可加快開發時間並降低網站的維護成本。

## 資源 {#resources}

* **[元件庫：](https://www.adobe.com/go/aem_cmp_library)**&#x200B;檢視元件的各種設定範例集合。
* **元件文件 (本文件)：**&#x200B;適用於開發人員和作者，提供各元件的詳細資訊。
* **[核心元件 GitHub 存放庫：](https://github.com/adobe/aem-core-wcm-components)**&#x200B;用於各元件和專案下載的開發人員詳細資訊。
* 開始使用：
   * **[成功使用核心元件：](/help/developing/success.md)**&#x200B;在任何將使用核心元件的專案開始之前要考慮的指導方針。
   * **[WKND 教學課程：](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**&#x200B;有關建置新網站的兩天教學課程。
   * **[Summit 教學課程：](https://expleague.azureedge.net/labs/L767/index.html)**&#x200B;有關建置新網站的兩小時教學課程 (出自美國 Summit 2019 的實驗室)。
   * **[Gems 網路研討會：](https://helpx.adobe.com/tw/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)**&#x200B;核心元件的導覽 (於 2018 年 12 月錄製)。

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 核心元件是 30 種經過充分測試、廣泛使用且效能出色的強大 WCM 元件。 |
| 雲端就緒 | 無論是在 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 上、在 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 還是內部部署，這些元件都能運作。 |
| 多功能 | 這些元件代表作者可用來組裝幾乎任何版面的一般概念。 |
| 可設定 | 範本層級[內容原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies) 定義頁面作者可以使用或無法使用的功能。 |
| [回應式](responsive.md) | 所有「核心元件」都設計為可充分回應，確保裝置間的順暢體驗 |
| 可追蹤 | [Adobe Client Data Layer 整合](/help/developing/data-layer/overview.md)允許追蹤訪客體驗的各個層面。 |
| 易於存取 | 元件符合 [WCAG 2.1 標準](https://www.w3.org/TR/WCAG21/)，提供 ARIA 標籤，並支援鍵盤導覽 ([已知問題](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle))。 |
| SEO 友善 | HTML 可輸出語義，並提供 [schema.org](https://schema.org) 結構化資料標記。 |
| WebApp 就緒 | [簡化的 JSON 輸出](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/develop-sling-model-exporter.html)允許用戶端轉譯，仍可進行[情境式編輯](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。 |
| AMP 支援 | 元件已內建 [AMP 標準支援](/help/developing/amp.md)，可加速您的行動體驗。 |
| 設計套件 | [Adobe XD 的 UI 套件](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)可讓設計人員建立透視效果，然後[根據需要設定樣式](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd)。 |
| 可主題化 | 元件實施[樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)，標記語言也遵循 [BEM CSS 慣例](https://getbem.com/)。 |
| 可自訂 | 數個模式允許[輕鬆自訂](developing/customizing.md)，涵蓋從調整 HTML 到進階功能重複使用。 |
| 版本設定 | [版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)可確保核心元件在改善可能影響您的內容時，不會破壞您的網站。 |
| 可本地化 | 智慧型參考解決方案可讓特定元件自動尋找並[自動轉譯為對應的本地化內容](get-started/localization.md)。 |
| 開放原始碼 | 如果發現錯誤，請[協助我們改進！](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |


## WCM 元件 {#the-wcm-components}

目前版本的核心元件具備下列元件。

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
* [社交媒體分享](components/sharing.md) (已棄用)
* [分隔符號](components/separator.md)
* [進度列](components/progress-bar.md)
* [PDF 檢視器](components/pdf-viewer.md)

### 容器元件 {#container-components}

* [容器](components/container.md)
* [輪播](components/carousel.md)
* [索引標籤](components/tabs.md)
* [摺疊面板](components/accordion.md)

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

## 系統要求 {#system-requirements}

| 核心元件發行版本 | AEM as a Cloud Service | AEM 6.5 LTS | AEM 6.5 | Java SE 版本 | Maven 版本 |
|---|---|---|---|---|---|
| [2.30.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.30.0) | 持續 | 6.5 LTS 正式發佈版 | 6.5.21.0+ | 8、11 | 3.3.9+ |

針對舊版核心元件的要求，請參閱[核心元件版本](versions.md)。

核心元件需要使用[可編輯範本](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) ，而且不支援傳統 UI 或靜態範本。如有需要，請檢視 [AEM 現代化工具](https://opensource.adobe.com/aem-modernize-tools/)，使用這些現代化 AEM 功能更新您的專案。

若要設定您的本機開發環境，請檢視 [AEM as a Cloud Service SDK 概觀](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)或[舊版 AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html) 的文件。

>[!TIP]
>
>核心元件會自動成為 AEM as a Cloud Service 的一部分，且您隨時會擁有最新版本的核心元件。
>
>如需有關如何在 AEMaaCS 和內部部署中開始使用核心元件的詳細資訊，請參閱[使用核心元件](/help/get-started/using.md)文件。

## 其他元件 {#other-components}

AEM 作者可以使用以核心元件為基礎的其他元件。

* [電子郵件核心元件](/help/email/introduction.md) - 探索建置在核心元件之上，並專門用於 Adobe Campaign 的元件。
* [自適應表單核心元件](/help/adaptive-forms/introduction.md) - 在 Adobe Experience Manager 中使用自適應表單核心元件，可以建立吸引人的註冊體驗。
