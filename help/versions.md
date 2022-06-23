---
title: 核心元件版本
description: 核心元件作為可能包含多個相同核心元件版本的版本發佈。 本文檔介紹哪些版本和版本以及如何瞭解與核心元件和的相容AEM性。
role: Architect, Developer, Admin, User
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: 0e00de5d566143258f3b0ad573681806ce35d1af
workflow-type: tm+mt
source-wordcount: '2599'
ht-degree: 19%

---

# 核心元件版本 {#core-components-versions}

核心元件的當前版本為2.20.0，與 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 和 [本AEM地](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html) 安裝。

## 發佈歷史記錄和相容性 {#release-history-and-compatibility}

核心元件設計為靈活且與所有受支援版本兼AEM容。 因此，元件版本可以包含同一元件的多個版本。

下表說明了核心元件版本與其中包含哪些元件版本的相容性。

### 發佈歷史記錄和要求 {#release-history-requirements}

下表，其內容 [在GitHub上提供，並提供完整版詳細資訊](https://github.com/adobe/aem-core-wcm-components/releases)，概述核心元件的版本及其與版本和Java版本AEM的相容性。

| 發行 | 說明 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  | Java | 發行日期 |
|---|---|---|---|---|---|---|
| [2.20.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.0) | 此版本新增了 [目錄元件](/help/components/tableofcontents.md) 包括錯誤修復。 | - | 6.5.10.0+ * | 連續 | 8、11 | 2022年6月23日 |
| [2.19.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.19.0) | 此版本將新版本添加到 [搜索元件](/help/components/quick-search.md) 和 [按鈕元件](/help/components/button.md) 以及許多輔助功能改進和錯誤修復。 | - | 6.5.10.0+ * | 連續 | 8、11 | 2022年4月7日 |
| [2.18.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.8) | 此版本修復了AEMaaCS的問題。 | - | 6.5.10.0+ * | 連續 | 8、11 | 2022年3月17日 |
| [2.18.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.6) | 這是修補程式版本。 | - | 6.5.10.0+ * | 連續 | 8、11 | 2022年3月3日 |
| [2.18.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.0) | 此主要版本的核心元件將在多個元件的新版本中引入新的連結處理程式，並提供許多輔助功能改進和錯誤修復。 | - | 6.5.10.0+ * | 連續 | 8、11 | 2022年2月16日 |
| [2.17.14](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | 這是修補程式版本。 | 6.4.8.4+ * | 6.5.6.0+ * | 連續 | 8、11 | 2021 年 12 月 13 日 |
| [2.17.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | 這是修補程式版本，它修復了上一版本引入的回歸。 | 6.4.8.4+ * | 6.5.6.0+ * | 連續 | 8、11 | 2021年10月1日 |
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | 此修補程式可增強 [清單](/help/components/list.md) 和 [導航](/help/components/navigation.md) 顯示重定向目標的外部URL的元件，為即將到來的v2啟用頁面影像繼承 [預告](/help/components/teaser.md) 元件，並包含其他錯誤修復。 | 6.4.8.4+ * | 6.5.6.0+ * | 連續 | 8、11 | 2021年8月31日 |
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | 此修補程式版本這是一個修補程式版本，用於修復以前引入的向後不相容的更改。 | 6.4.8.4+ * | 6.5.6.0+ * | 連續 | 8、11 | 2021年8月2日 |
| [2.17.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.6) | 此修補程式版本增加了對頁面站點映射的支援，並包括各種輔助功能改進。 | 6.4.8.4+ * | 6.5.6.0+ * | 連續 | 8、11 | 2021年7月29日 |
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | 此修補程式版本包括 [資料層](/help/developing/data-layer/overview.md) 不與AEMaCS一起工作。 | 6.4.8.4+ * | 6.5.6.0+ * | 連續 | 8、11 | 2021年7月8日 |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | 此版本包括許多支援連結處理程式功能的新元件版本的技術預覽，以及針對 [頁面元件。](/help/components/page.md) 還包括若干錯誤修復。 | 6.4.8.4+ * | 6.5.6.0+ * | 連續 | 8、11 | 2021年6月16日 |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | 這是用於修復新連結處理程式問題的修補程式版本。 | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2021年5月19日 |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | 這是一個修補程式版本，主要解決新連結處理程式的問題，並添加了一個增強功能，以支援多頁應用程式 [PWA。](/help/components/page.md#pwa-support) | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2021年5月15日 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | 此版本側重於輔助功能改進以及向現有元件引入新的連結處理程式。 | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2021年4月22日 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | 這是修補程式版本，主要解決 [資料層](/help/developing/data-layer/overview.md) 向後相容性和ITtest在某些情況下失敗。 | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2021 年 3 月 16 日 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | 此版本包括對 [頁面元件中的漸進式Web應用(PWA)](/help/components/page.md#pwa-support) 支援2.0.0版 [Adobe資料層。](/help/developing/data-layer/overview.md) | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2021年2月23日 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | 此版本包括 [嵌入元件](/help/components/embed.md) 並介紹品牌策略 [頁](/help/components/page.md) 解決許多問題。 | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2021年2月9日 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | 這是一個修補程式版本，用於解決在AEMaaCS上使用RTE時的問題 | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2020年12月16日 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | 此版本包括用於 [影像元件。](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2020年12月4日 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | 這是2.12.0的修補程式版本，包括次要修復。 | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2020年11月11日 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | 這是2.12.0的修補程式版本，用於修復 [影像元件。](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2020年11月5日 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | 此版本已發佈 [新的POST表格處理程式；](/help/components/forms/form-container.md#post-data) 能夠包括自定義CSS、Javascript和元資料 [標籤通過上下文感知配置；](/help/developing/including-clientlibs.md#context-aware-loading) 和 `DataLayerBuilder` 實用程式 [簡化定製元件中的資料層整合。](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2020年10月29日 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | 此版本已發佈 [AMP支援。](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | 連續 | 8、11 | 2020年7月20日 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | 此版本介紹 [PDF查看器元件。](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | 連續 | 8、11 | 2020年6月17日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | 此版本支援與 [Adobe客戶端資料層](/help/developing/data-layer/overview.md) 並介紹 [進度欄元件。](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | 連續 | 8、11 | 2020年5月29日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此版本側重於具有小型增強功能的修復。 | 6.4.4.0+ | 6.5.0.0+ | 連續 | 8、11 | 2019年12月5日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 此版本引入了 [嵌入元件。](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | 連續 | 8、11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此版本引入了 [體驗片段元件。](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | 連續 | 8、11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此版本引入了 [手風琴，](/help/components/accordion.md) [按鈕，](/help/components/button.md) [容器，](/help/components/container.md) 和 [下載元件。](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | 連續 | 8、11 | 2019年6月25日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本介紹 [內容片段清單元件。](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | 連續 | 8、11 | 2019年5月7日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 本版本側重於對 [元件庫，](https://aemcomponents.dev) 還包含一些功能增強 [分隔符元件。](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | 連續 | 8 | 2019年3月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 本新聞稿的重點 [元件庫](https://aemcomponents.dev) 以及介紹 [分隔符元件，](/help/components/separator.md) 還包含一些功能增強 [影像元件。](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 2019年2月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要側重於錯誤修復，但還包含一些功能增強 [旋轉軸元件。](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 此版本介紹 [制表符元件](/help/components/tabs.md) 和 [旋轉木馬元件](/help/components/carousel.md) 以及對 [影像元件，](/help/components/image.md) [頁面元件，](/help/components/page.md) 和 [標題元件](/help/components/title.md) 並加強跟蹤。 | 6.4.2.0+ | - | - | 8 | 2018 年 10 月 16 日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 此版本介紹 [預告元件](/help/components/teaser.md) 以及 [影像元件](/help/components/image.md) 和大量錯誤修復。 | 6.4.2.0+ | - | - | 8 | 2018年7月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 這是個錯誤的解決方案。 | 6.4.0.0+ | - | - | 8 | 2018年6月12日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 此版本增加了機尾改進、錯誤修復和小的改進，包括支援在 [影像元件。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2018 年 4 月 11 日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 本版本主要側重於在機尾下的改進、錯誤修復，以及對 [影像元件，](/help/components/image.md) [頁面元件，](/help/components/page.md) 和 [內容片段元件。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2018年3月7日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 此版本介紹 [導航元件，](/help/components/navigation.md) [語言導航元件，](/help/components/language-navigation.md) 和 [快速搜索元件](/help/components/quick-search.md) 並實施 [樣式系統](/help/get-started/authoring.md#component-styling) 的下界。 | 6.4.0.0+ | - | - | 8 | 2018年1月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 此版本在所有元件上實現JSON導出，並引入 [內容片段元件。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2017年10月10日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 此版本為 [影像元件。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2017年8月4日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 此版本為 [頁面元件，](/help/components/page.md) [影像元件，](/help/components/image.md) 以及各種全球性的修復和改進。 | 6.4.0.0+ | - | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 此版本將在中添加動畫GIF影像的修復 [影像元件。](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 2017年3月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心元件的初始版本。 | 6.4.0.0+ | - | - | 7 | 2017年3月20日 |

>[!NOTE]
>
>(*)自2.11.0版以來， `org.apache.sling.models.impl` 1.4.12版或更高版本(由於 [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781))。 這將在將AEM來的Service Pack中為6.4和6.5提供。 在此之前，「吊具模型」捆綁包包含在 `core.wcm.components.all` 檔案。

>[!TIP]
>
>與一AEM樣，Adobe建議開發人員 [核心元件的最新版本和版本](https://github.com/adobe/aem-core-wcm-components/releases/latest) 可用，它與運行AEM的版本相容，以便從最新的修復和功能中獲益。

### 元件版本和版本 {#component-versions-and-releases}

下表詳細說明了哪些版本的元件包含哪些核心元件版本。

|  | 1.0.0版 — 1.0.6 | 1.1.0版 | 2.0.0版 — 2.0.8 | 2.1.0版 | 2.2.0-2.2.0版 | 2.3.0-2.3.2版 | 2.4.0版 | 2.5.0版 | 2.6.0版 | 2.7.0-2.8.0版 | 2.9.0-2.17.14版 | 2.18.0版 | 2.19.0版 | 版本2.20.0+ |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **[Page](components/page.md)** | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 、 v3 | v1 、 v2 、 v3 | v1 、 v2 、 v3 |
| **[標題](components/title.md)** | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 、 v3 | v1 、 v2 、 v3 | v1 、 v2 、 v3 |
| **[影像](components/image.md)** | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 、 v3 | v1 、 v2 、 v3 | v1 、 v2 、 v3 |
| **[清單](components/list.md)** | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 、 v3 | v1 、 v2 、 v3 | v1 、 v2 、 v3 |
| **[階層連結](components/breadcrumb.md)** | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 、 v3 | v1 、 v2 、 v3 | v1 、 v2 、 v3 |
| **[社交媒體分享](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[來自容器](components/forms/form-container.md)** | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[表單文字](components/forms/form-text.md)** | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[表單選項](components/forms/form-options.md)** | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[已隱藏的表單](components/forms/form-hidden.md)** | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[表單按鈕](components/forms/form-button.md)** | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[內容片段](components/content-fragment-component.md)** |  | 沙盤 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[導覽](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[語言導覽](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[快速搜尋](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 、 v2 | v1 、 v2 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[索引標籤](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[傳送](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[分隔符號](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[內容片段清單](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[折疊式面板](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[按鈕](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[容器](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[下載](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[體驗片段](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[內嵌](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 、 v2 | v1 、 v2 | v1 、 v2 |
| **[進度列](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[PDF 檢視器](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[目錄](components/tableofcontents.md)** |  |  |  |  |  |  |  |  |  |  |  |  |  | v1 |

## 版本和版本 {#versions-and-releases}

核心元件通過GitHub分發。 這允許Adobe更快地向元件添加功能，並允許在發佈週期之外進AEM行社區輸入。

「核心元件」可在與其相容的AEM已定義版本中使用。 這意味著一個AEM版本可能支援核心元件的多個版本或版本。

### 版本 {#versions}

核心元件的主要迭代是 **版本**。 每個元件都有一個版本。 版本用 **v** 附加了非零正整數，如v1和v2。 版本僅對不向後相容的更改遞增，通常引入新特性和功能時是這樣。

開發人員和管理員可以通過其資源類型路徑中的數字以及其實現的完全限定的Java類名稱來識別核心元件的版本。 此版本號表示由定義的主要版本 [語義版本指導](https://semver.org/)。

有關核心元件版本的詳細資訊，請參閱 [核心元件的開發人員文檔](developing/guidelines.md)。

### 發行 {#releases}

核心元件可通過 **釋放** 和 [表示GitHub上可用的實際已發佈對象](https://github.com/adobe/aem-core-wcm-components/releases)。 版本以格式的十進位數表示 `X.Y.Z` 並將所有核心元件作為交付件包一起收集。

* **主要版本** 引入全新元件、對現有版本元件的改進以及標準錯誤修復。 此值由 `X` 版本號的元件。
* **次要版本** 為現有版本的元件引入新元件、新功能以及錯誤修復。 此值由 `Y` 版本號的元件。
* **修補程式版本** 僅包含錯誤修復。 此值由 `Z` 版本號的元件。

>[!NOTE]
>
>版本可以包含同一元件的多個版本。
>
>同一版本的元件可以出現在多個版本中。

## 核心元件支援 {#core-components-support}

核心元件是Quickstart的一AEM個組成部分，它們受到的條款和條件相同的支援，與作為Quickstart的一部分提供的條款和條件相同。

就如同其他產品的功能，其生命週期結束的通則是:

* 移除元件前，將先公告該元件已被取代
* 最快將於公告後釋出的 AEM 版本中移除這些項目。

這可讓客戶在支援結束前，至少有一個版本的週期可移至新版本的元件。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

如需支援自訂元件的詳細資訊，請參閱[自訂核心元件](developing/customizing.md)頁面瞭解相關的核心元件版本。

## 基礎元件支援 {#foundation-component-support}

Adobe的發展重點已轉向核心元件，並將繼續增加新功能。

[幾乎所有Foundation Components都已棄用，AEM帶有6.5](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html) 而且，今後將只考慮對Foundation Components進行主要的錯誤修復。
