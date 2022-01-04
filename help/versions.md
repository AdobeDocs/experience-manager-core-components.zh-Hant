---
title: 核心元件版本
description: 核心元件會發佈為發行版本，其中可能包含相同核心元件的多個版本。 本檔案說明哪些版本和版本，以及如何了解與核心元件和AEM的相容性。
role: Architect, Developer, Admin, User
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: ef18f65be72295f7886a132a26bdd4f8bc2fbd50
workflow-type: tm+mt
source-wordcount: '2318'
ht-degree: 20%

---

# 核心元件版本 {#core-components-versions}

核心元件的最新版本為2.17.14，與 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 和 [內部部署AEM](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html) 安裝。

## 版本記錄和相容性 {#release-history-and-compatibility}

核心元件的設計靈活且與所有支援的AEM版本相容。 因此，元件的版本可包含相同元件的多個版本。

下表說明核心元件版本的相容性，以及包含哪些版本的元件版本。

### 發行記錄和需求 {#release-history-requirements}

下表為 [在GitHub上提供完整發行詳細資訊](https://github.com/adobe/aem-core-wcm-components/releases)，提供核心元件版本的概觀，及其與AEM版本和Java版本的相容性。

| 發行 | 說明 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  | Java | 發行日期 |
|---|---|---|---|---|---|---|
| [2.17.14](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | 此為修補程式版本。 | 6.4.8.4+ * | 6.5.6.0+ * | 持續 | 8, 11 | 2021 年 12 月 13 日 |
| [2.17.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | 此修補程式版本修正了先前版本引入的回歸。 | 6.4.8.4+ * | 6.5.6.0+ * | 持續 | 8, 11 | 2021年10月1日 |
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | 此修補程式可增強 [清單](/help/components/list.md) 和 [導覽](/help/components/navigation.md) 元件來顯示重新導向目標的外部URL，會為即將推出的v2啟用頁面影像繼承 [Teaser](/help/components/teaser.md) 元件，並包含其他錯誤修正。 | 6.4.8.4+ * | 6.5.6.0+ * | 持續 | 8, 11 | 2021年8月31日 |
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | 此修補程式版本此為修補程式版本，用於修正先前引入的不相容反向變更。 | 6.4.8.4+ * | 6.5.6.0+ * | 持續 | 8, 11 | 2021年8月2日 |
| [2.17.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.6) | 此修補程式版本新增了對頁面網站地圖的支援，並包含各種協助工具改善。 | 6.4.8.4+ * | 6.5.6.0+ * | 持續 | 8, 11 | 2021年7月29日 |
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | 此修補程式版本包含 [資料層](/help/developing/data-layer/overview.md) 無法與AEMaaCS搭配使用。 | 6.4.8.4+ * | 6.5.6.0+ * | 持續 | 8, 11 | 2021年7月8日 |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | 此版本包含許多支援連結處理常式功能的新元件版本的技術預覽，以及 [頁面元件。](/help/components/page.md) 也包含數項錯誤修正。 | 6.4.8.4+ * | 6.5.6.0+ * | 持續 | 8, 11 | 2021年6月16日 |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | 此為修正新連結處理常式問題的修補程式版本。 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2021年5月19日 |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | 此為修補程式版本，主要修正新連結處理常式的問題，並新增了支援多頁應用程式的增強功能 [PWA。](/help/components/page.md#pwa-support) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2021年5月15日 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | 此版本著重於協助工具的改善，以及將新的連結處理常式引入現有元件。 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2021年4月22日 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | 此修補程式版本主要修正 [資料層](/help/developing/data-layer/overview.md) 向後相容性和IT測試在某些情況下失敗。 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2021 年 3 月 16 日 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | 此版本包含 [頁面元件中的漸進式網頁應用程式(PWA)](/help/components/page.md#pwa-support) 並支援2.0.0版 [Adobe資料層。](/help/developing/data-layer/overview.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2021年2月23日 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | 此版本包含 [內嵌元件](/help/components/embed.md) 並於 [頁面](/help/components/page.md) 並解決許多問題。 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2021年2月9日 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | 此為修補程式版本，可解決在AEMaaCS上使用RTE時的問題 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年12月16日 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | 此版本包含適用於 [影像元件。](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年12月4日 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | 此為2.12.0的修補程式版本，包含微幅修正。 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年11月11日 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | 此為2.12.0的修補程式版本，修正 [影像元件。](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年11月5日 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | 此版本已推出 [新的POST表單處理程式；](/help/components/forms/form-container.md#post-data) 包含自訂CSS、Javascript和中繼資料的功能 [標籤；](/help/developing/including-clientlibs.md#context-aware-loading) 和 `DataLayerBuilder` 實用程式 [簡化自訂元件中的資料層整合。](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年10月29日 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | 此版本已推出 [AMP支援。](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年7月20日 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | 此版本推出 [PDF檢視器元件。](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | 持續 | 8, 11 | 2020年6月17日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | 此版本啟用與 [Adobe用戶端資料層](/help/developing/data-layer/overview.md) 並介紹 [進度欄元件。](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | 持續 | 8, 11 | 2020年5月29日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此版本專注於修正微幅增強功能。 | 6.4.4.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019年12月5日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 此版本推出 [內嵌元件。](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此版本推出 [體驗片段元件。](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此版本推出 [折疊式功能表，](/help/components/accordion.md) [按鈕，](/help/components/button.md) [容器，](/help/components/container.md) 和 [下載元件。](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019年6月25日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本推出 [內容片段清單元件。](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019年5月7日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此版本專注於 [元件庫、](https://aemcomponents.dev) 也包含 [分隔符元件。](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | 持續 | 8 | 2019年3月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此版本專注於 [元件庫](https://aemcomponents.dev) 以及介紹 [分隔符元件，](/help/components/separator.md) 也包含 [影像元件。](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 2019年2月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要著重於錯誤修正，但也包含 [輪播元件。](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 此版本推出 [制表符元件](/help/components/tabs.md) 和 [轉盤元件](/help/components/carousel.md) 以及 [影像元件、](/help/components/image.md) [頁面元件、](/help/components/page.md) 和 [標題元件](/help/components/title.md) 以及更強的追蹤功能。 | 6.4.2.0+ | - | - | 8 | 2018 年 10 月 16 日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 此版本推出 [Teaser元件](/help/components/teaser.md) 以及 [影像元件](/help/components/image.md) 以及多項錯誤修正。 | 6.4.2.0+ | - | - | 8 | 2018年7月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 這是錯誤修正版本。 | 6.4.0.0+ | - | - | 8 | 2018 年 6 月 12 日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 此版本新增了機殼下的改善功能、錯誤修正和小幅改善功能，包括支援在 [影像元件。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2018 年 4 月 11 日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 此版本主要著重於機下改善、錯誤修正，以及 [影像元件、](/help/components/image.md) [頁面元件、](/help/components/page.md) 和 [內容片段元件。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2018年3月7日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 此版本推出 [導覽元件、](/help/components/navigation.md) [語言導航元件、](/help/components/language-navigation.md) 和 [快速搜尋元件](/help/components/quick-search.md) 並實施 [樣式系統](/help/get-started/authoring.md#component-styling) 適用於所有元件。 | 6.4.0.0+ | - | - | 8 | 2018年1月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 此版本會對所有元件實作JSON匯出，並導入 [內容片段元件。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2017年10月10日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 此版本新增了數項 [影像元件。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2017年8月4日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 此版本新增 [頁面元件、](/help/components/page.md) [影像元件、](/help/components/image.md) 以及各種全域修正和改善。 | 6.4.0.0+ | - | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 此版本新增了動畫GIF影像的修正，位於 [影像元件。](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 2017年3月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心元件初次發行。 | 6.4.0.0+ | - | - | 7 | 2017年3月20日 |

>[!NOTE]
>
>(*)自2.11.0版起， `org.apache.sling.models.impl` 需要1.4.12版或更新版本(由於 [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781))。 這將在未來的Service Pack中提供給AEM 6.4和6.5。 在此之前，Sling模型套件組合會包含在 `core.wcm.components.all` 包。

>[!TIP]
>
>如同AEM,Adobe建議開發人員使用 [核心元件的最新版本和版本](https://github.com/adobe/aem-core-wcm-components/releases/latest) 可與其執行的AEM版本相容，以受益於最新的修正和功能。

### 元件版本與發行 {#component-versions-and-releases}

下表詳細說明核心元件發行包含哪些元件版本。

|  | 版本1.0.0 - 1.0.6 | 版本1.1.0 | 版本2.0.0 - 2.0.8 | 版本2.1.0 | 版本2.2.0-2.2.0 | 版本2.3.0-2.3.2 | 版本2.4.0 | 版本2.5.0 | 版本2.6.0 | 版本2.7.0-2.8.0 | 版本2.9.0+ |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **[頁面](components/page.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[標題](components/title.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[影像](components/image.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[清單](components/list.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[階層連結](components/breadcrumb.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[社交媒體分享](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[來自容器](components/forms/form-container.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[表單文字](components/forms/form-text.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[表單選項](components/forms/form-options.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[已隱藏的表單](components/forms/form-hidden.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[表單按鈕](components/forms/form-button.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[內容片段](components/content-fragment-component.md)** |  | 沙盤 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 |
| **[導覽](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[語言導覽](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[快速搜尋](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[索引標籤](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[傳送](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[分隔符號](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[內容片段清單](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[折疊式面板](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[按鈕](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[容器](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[下載](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[體驗片段](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[內嵌](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 |
| **[進度列](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 |
| **[PDF 檢視器](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 |

## 版本和版本 {#versions-and-releases}

核心元件可透過GitHub發佈。 這可讓Adobe更快速地將功能新增至元件，也允許在AEM發行週期之外輸入社群。

核心元件可與已定義且相容的AEM版本搭配使用。 這表示一個AEM版本可能支援多個核心元件版本。 這比舊版Foundation元件(系結至特定版本的AEM)更具彈性。

### 版本 {#versions}

核心元件的主要小版本為 **版本**. 每個元件都有一個版本。 版本的表示方式為 **v** 附加非零的正整數，例如v1和v2。 版本僅會針對不向後相容的變更而遞增，這通常是導入新功能的情況。

開發人員和管理員可在其資源類型路徑和實作的完全限定Java類別名稱中，依數字識別核心元件的版本。 此版本編號代表定義的主要版本 [語義版本化准則](https://semver.org/).

如需核心元件版本的詳細資訊，請參閱 [核心元件的開發人員檔案](developing/guidelines.md).

### 版本 {#releases}

核心元件可透過 **發行** 和 [代表GitHub上可用的實際已發佈成品](https://github.com/adobe/aem-core-wcm-components/releases). 發行版本的表示格式為X.Y.Z的十進位數，並將所有核心元件作為交付件包一起收集。

* **主要版本** 可導入新版本的現有元件，以及全新元件和標準錯誤修正。 這由發行編號的X元件中的增量表示。
* **重要發行** 可對現有版本的元件導入新功能並修正錯誤。 這由發行編號的Y元件中的增量表示。
* **次要版本** 僅包含錯誤修正。 這由發行編號的Z元件中的增量表示。

>[!NOTE]
>
>版本可包含相同元件的多個版本。
>
>多個版本中可能會顯示相同版本的元件。

## 核心元件支援 {#core-components-support}

核心元件是 AEM 不可或缺的一部分，並依照與 Quickstart 所提供相同的條款與條件給予支援。

就如同其他產品的功能，其生命週期結束的通則是:

* 移除元件前，將先公告該元件已被取代
* 最快將於公告後釋出的 AEM 版本中移除這些項目。

這可讓客戶在支援結束前，至少有一個版本的週期可移至新版本的元件。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

如需支援自訂元件的詳細資訊，請參閱[自訂核心元件](developing/customizing.md)頁面瞭解相關的核心元件版本。

## 基礎元件支援 {#foundation-component-support}

Adobe的開發重點已轉向核心元件，而新功能將繼續增加。

[幾乎所有基礎元件已於AEM 6.5中淘汰](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html) 未來基礎元件將僅考慮重大錯誤修正。
