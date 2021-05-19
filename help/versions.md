---
title: 核心元件版本
description: 核心元件會發佈為可能包含相同核心元件之多個版本的發行版本。 本檔案說明哪些版本和版本，以及如何瞭解與核心元件和的相容AEM性。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: 6dc5c5959410f643ff169989d4d98c6f65f98076
workflow-type: tm+mt
source-wordcount: '2072'
ht-degree: 21%

---

# 核心元件版本 {#core-components-versions}

核心元件的當前版本為2.16.2，與[作AEM為Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)和[內部部署AEM](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html)安裝相容。

## 發行歷史記錄與相容性{#release-history-and-compatibility}

核心元件設計為具有彈性且與所有支援版本相容AEM。 因此，某個版本的元件可以包含相同元件的多個版本。

下表說明了核心元件版本的相容性以及包含哪些版本的元件版本。

### 發行記錄與要求{#release-history-requirements}

下表提供完整版本詳細資訊](https://github.com/adobe/aem-core-wcm-components/releases)的[在GitHub上提供的內容，概述核心元件的版本及其與版本和Java版本AEM的相容性。

| 發行 | 說明 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  | Java | 發行日期 |
|---|---|---|---|---|---|---|
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | 此修補程式版本主要修正新連結處理常式的問題，並新增增強功能，以支援[PWA的多頁應用程式。](/help/components/page.md#pwa-support) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2021年5月15日 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | 此版本著重於協助工具改良功能，並為現有元件引進新的連結處理常式。 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2021年4月22日 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | 此修補程式版本主要修正[資料層](/help/developing/data-layer/overview.md)向後相容性和IT測試在某些情況下失敗的問題。 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2021 年 3 月 16 日 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | 此版本包含對頁面元件](/help/components/page.md#pwa-support)中[漸進式網頁應用程式(PWA)的支援，並支援[Adobe資料層2.0.0版。](/help/developing/data-layer/overview.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2021年2月23日 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | 此版本包含[內嵌元件](/help/components/embed.md)的新選項，並在[page](/help/components/page.md)層級推出品牌印刷邊界，並解決許多問題。 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2021年2月9日 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | 這是修補程式版本，可解決RTE在AEMaaCS上使用時的問題 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年12月16日 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | 此版本包含[影像元件的Dynamic Media新功能。](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年12月4日 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | 這是2.12.0的修補程式版本，包括次要修正。 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年11月11日 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | 這是2.12.0的修補程式版本，已修正[影像元件中的主要錯誤。](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年11月5日 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | 此版本引入[新的POST表單處理常式；](/help/components/forms/form-container.md#post-data)透過內容感知組態加入自訂CSS、Javascript和中繼資料[標籤；](/help/developing/including-clientlibs.md#context-aware-loading)和`DataLayerBuilder`公用程式，以簡化自訂元件中的資料層整合。](/help/developing/data-layer/integrations.md#enabling-custom-components)[ | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年10月29日 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | 此版本引入了[AMP支援。](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年7月20日 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | 此版本推出[PDF檢視器元件。](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | 持續 | 8, 11 | 2020年6月17日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | 此版本支援與[Adobe客戶端資料層](/help/developing/data-layer/overview.md)的整合，並引入了[進度欄元件。](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | 持續 | 8, 11 | 2020年5月29日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此版本的重點是修正及小型增強功能。 | 6.4.4.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019年12月5日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 此版本引入了新的[Embed元件。](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此版本引入新的[體驗片段元件。](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 本版次推出新的[Accordion、](/help/components/accordion.md)[Button、](/help/components/button.md)[Container、](/help/components/container.md)和[下載元件。](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019年6月25日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本引入了[內容片段清單元件。](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019年5月7日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此版本主要針對[元件庫](https://aemcomponents.dev)的調整，但也包含[分隔元件的某些功能增強功能。](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | 持續 | 8 | 2019年3月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 本版本主要介紹[元件庫](https://aemcomponents.dev)，並介紹新的[分隔元件](/help/components/separator.md)，但也包含一些[影像元件的增強功能。](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 2019年2月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要針對錯誤修正，但也包含[轉盤元件的一些功能增強功能。](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 本版次推出[標籤元件](/help/components/tabs.md)和[轉盤元件](/help/components/carousel.md)，以及[影像元件、](/help/components/image.md)[頁面元件、](/help/components/page.md)和[標題元件](/help/components/title.md)的增強追蹤功能。 | 6.4.2.0+ | - | - | 8 | 2018 年 10 月 16 日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 本版次推出[摘要元件](/help/components/teaser.md)，以及[影像元件](/help/components/image.md)的增強功能和許多錯誤修正。 | 6.4.2.0+ | - | - | 8 | 2018年7月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 這是錯誤修正版本。 | 6.4.0.0+ | - | - | 8 | 2018 年 6 月 12 日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 此版本新增了外觀改良功能、錯誤修正和小幅改良功能，包括[影像元件中支援影像翻轉。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2018 年 4 月 11 日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 此版本主要著重於機殼下的改良、錯誤修正，以及對[影像元件、](/help/components/image.md)[頁面元件、](/help/components/page.md)和[內容片段元件的一些微幅改良。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2018年3月7日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 本版次推出[導覽元件、](/help/components/navigation.md) [語言導覽元件、](/help/components/language-navigation.md)和[快速搜尋元件，並針對所有元件實作[樣式系統](/help/get-started/authoring.md#component-styling)。](/help/components/quick-search.md) | 6.4.0.0+ | - | - | 8 | 2018年1月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 此發行版本會在所有元件上實作JSON匯出，並推出[內容片段元件。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2017年10月10日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 此版本新增了[影像元件的數項修正。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2017年8月4日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 此版本新增了[頁面元件、](/help/components/page.md)[影像元件、](/help/components/image.md)的修正，以及各種全域修正與改進。 | 6.4.0.0+ | - | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 此版本新增了[影像元件中GIF動畫影像的修正。](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 2017年3月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心元件的初次發行。 | 6.4.0.0+ | - | - | 7 | 2017年3月20日 |

>[!NOTE]
>
>(*)自2.11.0版起，需要`org.apache.sling.models.impl` 1.4.12版或更新版本（由於[SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)）。 這將在未AEM來的Service Pack中提供6.4和6.5版。 在此之前，Sling Models組合包會包含在`core.wcm.components.all`套件中。

>[!TIP]
>
>與AEM同時，Adobe建議開發人員使用與所執行版本相容的[最新版核心元件&lt;a1/AEM>版本，以運用最新的修正和功能。](https://github.com/adobe/aem-core-wcm-components/releases/latest)

### 元件版本和版本{#component-versions-and-releases}

下表詳細說明核心元件的發行版本中包含哪些元件版本。

|  | 版本1.0.0 - 1.0.6 | 版本1.1.0 | 版本2.0.0 - 2.0.8 | 版本2.1.0 | 版本2.2.0-2.2.0 | 版本2.3.0-2.3.2 | 版本2.4.0 | 版本2.5.0 | 版本2.6.0 | 版本2.7.0-2.8.0 | 版本2.9.0+ |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **[頁面](components/page.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[標題](components/title.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[影像](components/image.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[清單](components/list.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[階層連結](components/breadcrumb.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[社交媒體分享](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[來自容器](components/forms/form-container.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[表單文字](components/forms/form-text.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[表單選項](components/forms/form-options.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[已隱藏的表單](components/forms/form-hidden.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[表單按鈕](components/forms/form-button.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[內容片段](components/content-fragment-component.md)** |  | 沙盤 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1,v2 | v1,v2 |
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

## 版本與版本{#versions-and-releases}

核心元件是透過GitHub散發。 這可讓Adobe更快速地將功能新增至元件，並允許在發行週期之外提供社群AEM輸入。

核心元件可與其相容的AEM已定義版本搭配使用。 這表示一AEM個版本可支援核心元件的多個版本或版本。 這提供了比先前與特定版本的Foundation Components更大的彈性AEM。

### 版本 {#versions}

核心元件的主要小版本是&#x200B;**版本**。 每個元件都有一個版本。 版本以&#x200B;**v**&#x200B;表示，並附加非零的正整數，如v1和v2。 版本只會針對不向後相容的變更而增加，這通常是新功能的引入。

開發人員和管理員可在其資源類型路徑中，以及其實作的完全限定Java類別名稱中，依數字識別核心元件的版本。 此版本號表示[語義版本控制指南](https://semver.org/)定義的主要版本。

如需核心元件版本的詳細資訊，請參閱核心元件](developing/guidelines.md)的[開發人員檔案。

### 發行 {#releases}

核心元件通過&#x200B;**版本**&#x200B;和[表示GitHub](https://github.com/adobe/aem-core-wcm-components/releases)上可用的實際發佈對象。 版本以X.Y.Z格式的十進位數字表示，並將所有核心元件作為交付件包一起收集。

* **主要** 版本可推出新版本的現有元件，以及全新的元件和標準錯誤修正。這由釋放編號的X元件中的增量表示。
* **重要** 版本可將新功能與錯誤修正一併引入現有元件版本。這由釋放編號的Y元件中的增量表示。
* **次要** 版本僅包含錯誤修正。這由釋放號的Z分量中的增量表示。

>[!NOTE]
>
>版本可包含相同元件的多個版本。
>
>同一版本的元件可以出現在多個版本中。

## 核心元件支援 {#core-components-support}

核心元件是 AEM 不可或缺的一部分，並依照與 Quickstart 所提供相同的條款與條件給予支援。

就如同其他產品的功能，其生命週期結束的通則是:

* 移除元件前，將先公告該元件已被取代
* 最快將於公告後釋出的 AEM 版本中移除這些項目。

這可讓客戶在支援結束前，至少有一個版本的週期可移至新版本的元件。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

如需支援自訂元件的詳細資訊，請參閱[自訂核心元件](developing/customizing.md)頁面瞭解相關的核心元件版本。

## 基礎元件支援 {#foundation-component-support}

Adobe公司的開發重點已轉向核心元件，並將繼續增加新功能。

[幾乎所有的Foundation Components都已在6.5AEM中過時，今後Foundation Components只會考慮](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) 重大的錯誤修正。
