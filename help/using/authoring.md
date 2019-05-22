---
title: 使用核心元件編寫
seo-title: 使用核心元件編寫
description: 在AEM中，元件是構成所編寫頁面內容的結構元素-核心元件提供有彈性且功能豐富的編寫功能。
seo-description: 在AEM中，元件是構成所編寫頁面內容的結構元素-核心元件提供有彈性且功能豐富的編寫功能。
uuid: 4a54cd4c-3d89-4683-8301-bc1 e633436 e3
content-type: 引用
topic-tags: 製作
discoiquuid: 8751e490-d427-44f2-b767-51935afda988
translation-type: tm+mt
source-git-commit: 632d6abb1f13667cc0457152268d50af3bfabfc4

---


# 使用核心元件製作

在Adobe Experience Manager中，元件是構成所編寫頁面內容的結構元素。本節涵蓋核心元件，其中提供建立頁面的基本內容類型。

核心元件提供有彈性且功能豐富的編寫功能。[We. Retail參考網站](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) 說明如何使用核心元件。

若要體驗核心元件並查看其組態選項以及HTML和JSON輸出的範例，請造訪 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)。

>[!NOTE]
>
>無法立即將核心元件用於作者， [開發團隊必須先將它們整合至您的環境](using.md)。整合後，即可透過 [範本編輯器提供並預先設定](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)。

>[!CAUTION]
>
>核心元件 [需要AEM6.3或更新版本](versions.md) ，而且需要使用 [可編輯的範本](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)。無法使用Classic UI或靜態範本。

## 使用核心元件編寫 {#authoring-with-core-components}

身為作者，您會注意到核心元件的幾項優點，包括：

* 簡單易用並與 [頁面編輯器整合](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)

* 功能豐富的功能，可容納許多使用案例，如 [我們在零售和](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)[元件庫中所說明](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)

* [預先設定](#pre-configuring-core-components) ，可定義哪些功能可透過 [範本編輯器提供給頁面作者](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

* 圍繞 [協助工具方針建立](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

* 建立以支援 [互動式版面配置](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)

編輯頁面時，頁面編輯器側面板的 **「元件** 」索引標籤上 [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)會提供元件。

元件會根據稱為元件群組的類別分組，以輕鬆組織和篩選元件。元件群組名稱會與 [元件瀏覽器中的元件一起顯示](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) ，而且也可以依群組篩選，輕鬆找到正確的元件。

>[!NOTE]
>
>核心元件依隱藏群組的預設部分而非顯示在元件瀏覽器中。
>
>將必要元件新增至可見群組，或自訂它們供作者使用。

## 預先設定核心元件 {#pre-configuring-core-components}

設定Foundation元件是開發人員的工作。不過，有了核心元件，範本作者現在可以透過範本編輯器來設定一些功能。

例如，如果影像元件不允許從檔案系統上傳影像，或文字元件只允許某些段落格式設定，則只需按一下即可啓用或停用這些功能。

如需詳細資訊，請參閱 [建立頁面範本](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) 。

### 編輯與設計對話方塊 {#edit-and-design-dialogs}

由於核心元件可由範本作者預先設定，定義哪些選項可作為範本的一部分，然後再由頁面作者進一步設定，以定義實際的頁面內容，因此每個元件都可以在兩個不同的對話方塊中提供選項。

|  | 說明 | 控制項 | 範例 |
|--- |--- |--- |--- |
| **編輯對話方塊** | **頁面作者** 在正常頁面編輯期間可修改置入元件的選項 | 元件顯示的內容及其最終顯示在頁面上的方式。 | 格式化內容文字，在頁面上旋轉影像 |
| **設計對話方塊** | **範本作者** 在設定頁面範本時可修改的選項。 | 編輯元件時，頁面作者可用的選項 | 提供哪些文字格式選項，可使用哪些影像就地選項 |

### 元件樣式 {#component-styling}

大部分核心元件的樣式都可以使用AEM樣式系統來定義。

* 範本作者可以定義該元件的「設計對話方塊」中特定元件可用的樣式。
* 然後內容作者可以選擇在新增元件和建立內容時套用哪些樣式。

如需詳細資訊，請參閱 [樣式系統](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) 文件。

>[!NOTE]
>
>在AEM6.3中，必須使用Service Pack2(6.3.2.0)或更新版本才能啓用樣式系統功能。

## 可用核心元件清單 {#list-of-core-components-available}

以下為可用核心元件清單，連結至說明其編輯和設計對話方塊功能的頁面。

目前版本的核心元件包含下列元件。

* [階層連結](breadcrumb.md)
* [表單按鈕](form-button.md)
* [傳送](carousel.md)
* [來自容器](form-container.md)
* [內容片段](content-fragment-component.md)
* [內容片段清單](content-fragment-list.md)
* [已隱藏的表單](form-hidden.md)
* [表單選項](form-options.md)
* [表單文字](form-text.md)
* [影像](image.md)
* [語言導覽](language-navigation.md)
* [清單](list.md)
* [導覽](navigation.md)
* [頁面](page.md)
* [快速搜尋](quick-search.md)
* [分隔符號](separator.md)
* [社交媒體分享](sharing.md)
* [Teaser](teaser.md)
* [文字](text.md)
* [標題](title.md)

>[!CAUTION]
>
>某些版本的個別核心元件僅能與某些版本的AEM相容。
>
>如需相容性資訊的詳細資訊，請參閱特定元件的個別說明頁面(連結至上一份清單)，或參考 [核心元件版本](versions.md) 文件。

>[!NOTE]
>
>視您的實例而定，您可能已針對您的需求明確開發自訂元件。這些元件甚至可能與此處討論的部分元件名稱相同。
>表單核心元件與AEM Forms無關。

## 開發人員資源 {#developer-resources}

有關核心元件的技術資訊，請參閱 [開發核心元件](developing.md) 開發人員文件。
