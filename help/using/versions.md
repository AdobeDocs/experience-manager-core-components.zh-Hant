---
title: 核心元件版本
seo-title: 核心元件版本
description: 核心元件會發佈為可能包含相同核心元件之多個版本的發行版本。 本檔案說明哪些版本和版本，以及如何瞭解與核心元件和AEM的相容性。
seo-description: 核心元件會發佈為可能包含相同核心元件之多個版本的發行版本。 本檔案說明哪些版本和版本，以及如何瞭解與核心元件和AEM的相容性。
uuid: a916a923-8c5e-456a-84b5-b52228e21434
contentOwner: 使用者
content-type: 引用
topic-tags: 簡介
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新功能
discoiquuid: a3a98b2f-65bf-4493-82ad-01717938fdbc
translation-type: tm+mt
source-git-commit: 97f1461b57079806f9f96d325d9b763538e32127

---


# 核心元件版本{#core-components-versions}

目前的核心元件版本是2.7.0，並與AEM 6.5相容。它已於2019年9月發行，作為2.0.0版的重要更新。2.0.0版推出新元件，並更新現有元件的v2版。

如需詳細資 [訊，請參閱本檔案的發行記錄](#versions-and-releases) 和相容性一節。

您也可以檢視元件 [庫](http://opensource.adobe.com/aem-core-wcm-components/library.html)，其中會顯示核心元件的目前版本，並提供其使用範例。

## 版本與發行 {#versions-and-releases}

核心元件是透過GitHub散發。 這可讓Adobe更快速地將功能新增至元件，也允許在AEM發行週期之外輸入社群。

「核心元件」可與已定義的AEM版本搭配使用，這些版本與之相容。 這表示一個AEM版本可能支援多個版本或核心元件版本。 這提供了比先前與特定AEM版本相連結的Foundation Components更大的彈性。

### 版本 {#versions}

核心元件的主要小版本是 **版本**。 每個元件都有一個版本。 版本會以 **v** 附加非零正整數（例如v1和v2）表示。 版本只會針對不向後相容的變更而增加，這通常是新功能的引入。

Developers and administrators can recognize versions of the core components by a number in their resource type paths, and in the fully qualified Java class names of their implementations. This version number represents a major version as defined by semantic versioning guidelines.[](https://semver.org/)

For more details about core component versions, see the developer documentation of the Core Components.[](guidelines.md)

### Releases {#releases}

The core components are made available through releases and represent the actual published artifacts available on GitHub. ****[](https://github.com/adobe/aem-core-wcm-components/releases)Releases are denoted with a decimal number of the format X.Y.Z and collect all core components together as a deliverable package.

* **Major releases can introduce new versions of existing components along with entirely new components as well as standard bug fixes.** This is represented by an increment in the X component of the release number.
* **Important releases can introduce new functionality to existing versions of components along with bug fixes.** This is represented by an increment in the Y component of the release number.
* **Minor releases contain only bug fixes.** This is represented by an increment in the Z component of the release number.

>[!NOTE]
>
>Releases can contain multiple versions of the same component.
>
>The same version of a component can appear in multiple releases.

## 發行記錄與相容性 {#release-history-and-compatibility}

The Core Components were first released with AEM 6.3 and are designed to be flexible and compatible with all supported AEM versions. 因此，某個版本的元件可以包含相同元件的多個版本。

下表說明了核心元件版本的相容性以及包含哪些版本的元件版本。

### 發行記錄與支援的AEM版本 {#release-history-supported-aem-versions}

下表提供完整版本詳細資 [訊的GitHub內容](https://github.com/adobe/aem-core-wcm-components/releases)，其中概述核心元件的發行版本及其與AEM版本和Java版本的相容性。

| 發行 | 說明 | AEM 6.3 | AEM 6.4 | AEM 6.5 | Java | 發行日期 |
|---|---|---|---|---|---|---|
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 本版次推出新的內嵌元件 | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | 8, 11 | 2019年9月25日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此版本推出新的Experience Fragment元件 | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | 8, 11 | 2019年9月6日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此版本引進了新的Accordion、Button、Container和Download元件。 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 2019年6月25日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本引入內容片段清單元件 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 2019年5月7日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此版本主要針對元件庫的調整，但也包含分隔符號元件的一些功能增強功能 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8 | 2019年3月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此版本主要針對元件庫以及新的分隔元件，但也包含一些影像元件的增強功能 | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 2019年2月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要針對錯誤修正，但也包含Carousel元件的一些功能增強功能 | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 引入標籤和轉盤元件、影像、頁面和標題元件的改進，以及增強的追蹤功能 | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 2018年10月16日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 引入摘要元件、影像元件改良和許多錯誤修正 | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 2018年7月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 錯誤修正版本 | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 2018年6月12日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 其他幕後改良功能、錯誤修正和小幅改良功能，包括支援影像翻轉。 | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 2018年4月11日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Mostly under-the-hood improvements, bug fixes, plus some minor improvements to the Image, Page, and Content Fragment Components | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 7 March 2018 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 引入導覽、語言導覽和快速搜尋元件。 Style system implemented for all components. | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 16 January 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Implementation of JSON export on all components, introduction of the Content Fragment component | 6.3.1.0 | 6.4.0.0+ | - | 8 | 10 October 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Several fixes for the Image component | 6.3.0.0+ | 6.4.0.0+ | - | 8 | 4 August 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Fixes of Page Component, Image Component, various global fixes and improvements | 6.3.0.0+ | 6.4.0.0+ | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 影像元件中GIF動畫影像的修正 | 6.3.0.0+ | 6.4.0.0+ | - | 7 | 2017年3月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心元件的初次發行 | 6.3.0.0+ | 6.4.0.0+ | - | 7 | 2017年3月20日 |

>[!NOTE]
>
>和AEM一樣，Adobe建議開發人員使用最新版本和可用的核心元件版本 [](https://github.com/adobe/aem-core-wcm-components/releases/latest) ，這些版本可與執行中的AEM版本相容，以便從最新的修正和功能中獲益。

### 元件版本與發行 {#component-versions-and-releases}

下表詳細說明核心元件的發行版本中包含哪些元件版本。

|  | 版本1.0.0 - 1.0.6 | 版本1.1.0 | 版本2.0.0 - 2.0.8 | 版本2.1.0 | 版本2.2.0-2.2.0 | 版本2.3.0-2.3.2 | 版本2.4.0 | 版本2.5.0 | 版本2.6.0 | 版本2.7.0+ |
|---|---|---|---|---|---|---|---|---|---|---|
| **[頁面](page.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[標題](title.md)** | v1 | v1 | v1,v2 | v1,v2 | v1, v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[影像](image.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[清單](list.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[階層連結](breadcrumb.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[社交媒體分享](sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[來自容器](form-container.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[表單文字](form-text.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[表單選項](form-options.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[已隱藏的表單](form-hidden.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[表單按鈕](form-button.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[內容片段](content-fragment-component.md)** |  | 沙盤 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[導覽](navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[語言導覽](language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[快速搜尋](quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[摘要](teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[標籤](tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Carousel](carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Separator](separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[內容片段清單](content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Accordion](accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Button](button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Container](separator.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Download](separator.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[體驗片段](separator.md)** |  |  |  |  |  |  |  |  | v1 | v1 |
| **[Embed](separator.md)** |  |  |  |  |  |  |  |  |  | v1 |

## 文件 {#documentation}

[使用核心元件撰寫](authoring.md) ，說明核心元件的使用方式，以及內容作者和範本作者所公開的功能。 每個元件都有詳細的說明。

[元件庫](http://opensource.adobe.com/aem-core-wcm-components/library.html) (Component Library)是大部分核心元件目前版本的展示，說明如何使用這些元件。

[開發核心元件](developing.md) (Developing Core Components)說明核心元件的技術功能、如何在專案中使用這些元件、如何自訂以及最佳實務。

[核心元件簡介](introduction.md) (Core Components Introduction)概述各版本、使用案例和支援的核心元件相容性。

[WKND教學課程](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) ，是針對AEM進行開發（包括使用核心元件）的絕佳逐步簡介。
