---
title: 核心元件版本
seo-title: 核心元件版本
description: 核心元件發佈為版本，其中可能包含一個以上的相同核心元件版本。本文件說明哪些版本和版本，以及如何瞭解與核心元件和AEM相容。
seo-description: 核心元件發佈為版本，其中可能包含一個以上的相同核心元件版本。本文件說明哪些版本和版本，以及如何瞭解與核心元件和AEM相容。
uuid: a916a923-8c5e-456a-84b5-b52228 e21434
contentOwner: 使用者
content-type: 引用
topic-tags: 簡介
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: a3a98b2f-65bf-4493-82ad-01717938fbc
translation-type: tm+mt
source-git-commit: 40ce01fdb0f22e3ee3b376a3684a766bd7e7bc11

---


# 核心元件版本{#core-components-versions}

目前的核心元件版本為2.4.0，與AEM6.5相容。它於2019年月發行，以小幅更新2.0.0版。版本2.0.0推出新元件以及現有元件的v更新。

如需詳細資訊，請參閱本文件的章節 [發行歷史和相容性](#versions-and-releases) 。

您也可以查看 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library.html)，其中顯示目前版本的核心元件，並提供其使用範例。

## 版本與版本 {#versions-and-releases}

核心元件是透過GitHub分發。這可讓Adobe更快速地新增功能至元件，並允許AEM發行週期以外的社群輸入。

核心元件可透過相容的AEM版本提供。這表示一個AEM版本可能支援多個版本或版本的核心元件。相較於舊版的AEM元件，它提供了更大的彈性。

### 版本 {#versions}

核心元件的主要反覆出現在 **版本**中。每個元件都有一個版本。版本會加上非零的 **v** 表示，正整數(例如v和v2)。版本僅會增加不相容的變更，通常是用於引入新功能和功能的案例。

開發人員和管理員可透過其資源類型路徑中的數字，以及其建置的完全合格Java類別名稱，來識別核心元件的版本。此版本號碼代表一個主要版本，由 [語義版本修訂指引定義](https://semver.org/)。

如需核心元件版本的詳細資訊，請參閱核心元件 [的開發人員文件](guidelines.md)。

### 發行版本 {#releases}

核心元件可 **透過發行版本提供** ， [並代表已發佈在GitHub](https://github.com/adobe/aem-core-wcm-components/releases)上的實際發佈項目。版本以X.Y.Z格式表示，並將所有核心元件一起收集為可傳送套件。

* **主要版本** 可推出新版本的現有元件以及全新元件以及標準錯誤修正。這是由版本號碼X元件的遞增表示。

* **重要版本** 可為現有元件版本提供新功能以及錯誤修正。這由版本號碼Y元件的增量表示。

* **次要版本** 僅包含錯誤修正。這由版本號碼Z元件的增量表示。

>[!NOTE]
>
>版本可以包含相同元件的多個版本。
>
>同一個元件版本可以出現在多個版本中。

## 發行歷史與相容性 {#release-history-and-compatibility}

核心元件最初是使用AEM6.3發行，其設計目的在於靈活彈性並與所有支援的AEM版本相容。因此，元件的版本可以包含相同元件的多個版本。

下表說明核心元件版本與元件版本的相容性。

### 發行歷史記錄與支援的AEM版本 {#release-history-supported-aem-versions}

下表列出GitHub [提供的完整版本詳細資訊](https://github.com/adobe/aem-core-wcm-components/releases)，並概述核心元件版本及其與AEM版本和Java版本的相容性。

| 版本 | 說明 | AEM6.3 | AEM6.4 | AEM6.5 | Java |
|---|---|---|---|---|---|
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本推出內容片段清單元件 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 本版次著重於元件程式庫的調整，但也包含部分的分隔符號元件功能增強功能 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 本版次著重於元件庫，以及新的分隔符號元件，但也包含影像元件的一些功能增強功能 | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 這個版本主要著重於錯誤修正，但也包含一些Carousel元件的功能增強功能 | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 引入標籤和轉盤元件、改善影像、頁面和標題元件以及增強追蹤 | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 摘要元件導入、影像元件改良以及許多錯誤修正 | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Bugfix版本 | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 額外的改良功能、錯誤修正和小改良，包括支援影像翻轉。 | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 大部份的改良功能、錯誤修正，以及對影像、頁面和內容片段元件的一些小幅改良 | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 導覽、語言導覽和快速搜尋元件。適用於所有元件的樣式系統。 | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 實作JSON在所有元件上的Export，引入內容片段元件 | 6.3.1.0 | 6.4.0.0+ | - | 8 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 影像元件的數個修正 | 6.3.0.0+ | 6.4.0.0+ | - | 8 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 頁面元件、影像元件、各種全球修正和改良的修正 | 6.3.0.0+ | 6.4.0.0+ | - | 8 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 影像元件中動畫GIF影像的修正 | 6.3.0.0+ | 6.4.0.0+ | - | 7 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心元件的初始發行 | 6.3.0.0+ | 6.4.0.0+ | - | 7 |

>[!NOTE]
>
>與AEM一樣，Adobe建議開發人員使用可與AEM版本相容的 [最新版本和版本，](https://github.com/adobe/aem-core-wcm-components/releases/latest) 以便從最新的修正和功能中獲益。

### 元件版本與發行{component-versions-and-elease}

下表詳細說明核心元件版本包含哪些元件。

|  | 版本1.0.0-1.0.6 | 版本1.1.0 | 版本2.0.0-2.0.8 | 版本2.1.0 | 版本2.2。-2.2.0 | 2.3.0 |
|---|---|---|---|---|---|---|
| **[頁面](page.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[標題](title.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[影像](image.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[清單](list.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[階層連結](breadcrumb.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[社交媒體分享](sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 |
| **[來自容器](form-container.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[表單文字](form-text.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[表單選項](form-options.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[已隱藏的表單](form-hidden.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[表單按鈕](form-button.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[內容片段](content-fragment-component.md)** | 沙盤 | v1 | v1 | v1 | v1 |
| **[導覽](navigation.md)** | v1 | v1 | v1 | v1 |
| **[語言導覽](language-navigation.md)** | v1 | v1 | v1 | v1 |
| **[快速搜尋](quick-search.md)** | v1 | v1 | v1 | v1 |
| **[Teaser](teaser.md)** | v1 | v1 | v1 |
| **[標籤](tabs.md)** | v1 | v1 |
| **[轉盤](carousel.md)** | v1 | v1 |
| **[分隔符號](separator.md)** | v1 |

## 文件 {#documentation}

[使用核心元件](authoring.md) 編寫，說明核心元件的用法以及內容作者和範本作者的功能。每個元件都會詳細記載。

[元件庫](http://opensource.adobe.com/aem-core-wcm-components/library.html) 是最新版本的核心元件的展示，illustrating如何使用。

[開發核心元件](developing.md) 說明核心元件的技術功能、如何在專案中使用它們、如何自訂和最佳實務。

[核心元件簡介](introduction.md) 概述各個版本、使用案例和支援的核心元件相容性。
