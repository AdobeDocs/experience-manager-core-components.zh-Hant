---
title: 核心元件版本
description: 核心元件會發佈為可能包含相同核心元件之多個版本的發行版本。 本檔案說明哪些版本和版本，以及如何瞭解與核心元件和AEM的相容性。
translation-type: tm+mt
source-git-commit: 2f3d2499e9f6c88453b633c20e49703eac25eff4
workflow-type: tm+mt
source-wordcount: '1870'
ht-degree: 21%

---


# 核心元件版本 {#core-components-versions}

目前的核心元件版本是2.12.1，並與 [AEM（雲端服務）和內部部](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) 署AEM安裝相容 [](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html) 。 它於2020年11月發行，作為2.12.0的修補程式版本。2.12.0版針對表單、中繼資料和資料層引入了數種新功能。

## 發行記錄與相容性 {#release-history-and-compatibility}

核心元件設計為彈性且與所有支援的AEM版本相容。 因此，某個版本的元件可以包含相同元件的多個版本。

下表說明了核心元件版本的相容性以及包含哪些版本的元件版本。

### 發行記錄與需求 {#release-history-requirements}

下表提供完整版本詳細資 [訊的GitHub內容](https://github.com/adobe/aem-core-wcm-components/releases)，其中概述核心元件的發行版本及其與AEM版本和Java版本的相容性。

| 發行 | 說明 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  | Java | 發行日期 |
|---|---|---|---|---|---|---|
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | 這是2.12.0的修補程式版本，包括次要修正。 | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年11月11日 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | 這是2.12.0的修補程式版本，已修正影像元件中的 [主要錯誤。](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年11月5日 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | 本版次推出 [新的POST表單處理程式；](/help/components/forms/form-container.md#post-data) 透過內容感知組態，包含自訂CSS、Javascript [和中繼資料標籤；](/help/developing/including-clientlibs.md#context-aware-loading) 以及簡化 `DataLayerBuilder` 自訂元 [件中資料層整合的公用程式。](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年10月29日 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | 此版本推出 [AMP支援。](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持續 | 8, 11 | 2020年7月20日 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | 本版次推出 [PDF檢視器元件。](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | 持續 | 8, 11 | 2020年6月17日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | 此版本可讓您與 [Adobe用戶端資料層整合](/help/developing/data-layer/overview.md) ，並引入 [進度列元件。](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | 持續 | 8, 11 | 2020年5月29日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此版本的重點是修正及小型增強功能。 | 6.4.4.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019年12月5日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 本版次推出新的 [Embed元件。](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019年9月25日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 本版次推出新的 [Experience Fragment元件。](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019年9月6日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 本版次引進了新 [的Accordion、](/help/components/accordion.md)[Button](/help/components/button.md) 、 [Container](/help/components/container.md) 和Download [元件。](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019年6月25日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本引入了「內 [容片段清單」元件。](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | 持續 | 8, 11 | 2019年5月7日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此版本主要針對元件庫 [的調整](https://aemcomponents.dev) ，但也包含分隔符號元件的一 [些增強功能。](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | 持續 | 8 | 2019年3月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此版本主要針對元 [件庫](https://aemcomponents.dev) ，並推出新的 [Separator元件，但也包含影像元件的一些功](/help/components/separator.md)[能增強。](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 2019年2月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要針對錯誤修正，但也包含轉盤元件的一些功 [能增強。](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 本版次引入了 [Tabs Component](/help/components/tabs.md) 、 [Carousel Component](/help/components/carousel.md) ，以及 [Image Component、](/help/components/image.md) Page Component、 [](/help/components/page.md)[](/help/components/title.md) And Title Component和Carousel Component的改進，並增強了跟蹤功能。 | 6.4.2.0+ | - | - | 8 | 2018年10月16日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 本版次推出 [Teaser元件](/help/components/teaser.md) ，以及影像元件 [的改良功能](/help/components/image.md) ，以及許多錯誤修正。 | 6.4.2.0+ | - | - | 8 | 2018年7月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 這是錯誤修正版本。 | 6.4.0.0+ | - | - | 8 | 2018年6月12日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 此版本新增了內在改良功能、錯誤修正和小幅改良功能，包括支援影像元件中的 [影像翻轉。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2018年4月11日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 此版本主要著重於內容改良、錯誤修正，以及 [Image Component、](/help/components/image.md)[Page Component和](/help/components/page.md) Content Fragment Component的一 [些微幅改良。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2018年3月7日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 此版本引入導 [覽元件、語言導覽元](/help/components/navigation.md) 件和快速搜尋元件，並針對所 [有元件實作Style System System](/help/components/language-navigation.md)[](/help/components/quick-search.md)[](/help/get-started/authoring.md#component-styling) 。 | 6.4.0.0+ | - | - | 8 | 2018年1月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 此發行版本會在所有元件上實作JSON匯出，並引入內 [容片段元件。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2017年10月10日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 此版本新增數項影像元件 [修正。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2017年8月4日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 此版本新增了頁面元 [件、影像元件](/help/components/page.md)[的修正，](/help/components/image.md) 以及各種全域修正與改進。 | 6.4.0.0+ | - | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 此版本新增影像元件中GIF動畫影像 [的修正。](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 2017年3月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心元件的初次發行。 | 6.4.0.0+ | - | - | 7 | 2017年3月20日 |

>[!NOTE]
>
>(*)自2.11.0版起， `org.apache.sling.models.impl` 需要1.4.12版或更新版本(由 [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781))。 這將在未來的Service Pack中針對AEM 6.4和6.5提供。 在此之前，Sling Models套件已包含在套件 `core.wcm.components.all` 中。

>[!TIP]
>
>和AEM一樣，Adobe建議開發人員使用最新版本和可用的核心元件版本 [](https://github.com/adobe/aem-core-wcm-components/releases/latest) ，這些版本可與執行中的AEM版本相容，以便從最新的修正和功能中獲益。

### 元件版本與發行 {#component-versions-and-releases}

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

## 版本與發行 {#versions-and-releases}

核心元件是透過GitHub散發。 這可讓Adobe更快速地將功能新增至元件，也允許在AEM發行週期之外輸入社群。

「核心元件」可與已定義的AEM版本搭配使用，這些版本與之相容。 這表示一個AEM版本可能支援多個版本或核心元件版本。 這提供了比先前與特定AEM版本相連結的Foundation Components更大的彈性。

### 版本 {#versions}

核心元件的主要小版本是 **版本**。 每個元件都有一個版本。 版本會以 **v** 附加非零正整數（例如v1和v2）表示。 版本只會針對不向後相容的變更而增加，這通常是新功能的引入。

開發人員和管理員可在其資源類型路徑中，以及其實作的完全限定Java類別名稱中，依數字識別核心元件的版本。 此版本號表示由語義版本修訂指導所定義的 [主要版本](https://semver.org/)。

如需核心元件版本的詳細資訊，請參 [閱核心元件的開發人員檔案](developing/guidelines.md)。

### 發行 {#releases}

核心元件可透過發行 **提供** , [並代表GitHub上的實際已發佈對象](https://github.com/adobe/aem-core-wcm-components/releases)。 版本以X.Y.Z格式的十進位數字表示，並將所有核心元件作為交付件包一起收集。

* **主要版本** ，可推出新版本的現有元件以及全新的元件以及標準錯誤修正。 這由釋放編號的X元件中的增量表示。
* **重要版本** ，可在現有元件版本中新增功能，並修正錯誤。 這由釋放編號的Y元件中的增量表示。
* **次要版本** ，僅包含錯誤修正。 這由釋放號的Z分量中的增量表示。

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

Adobe的開發重點已轉移到核心元件，並將繼續新增新功能。

[幾乎所有的Foundation Components都已在AEM 6.5中停用](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) ，而且未來Foundation Components只會考慮主要的錯誤修正。
