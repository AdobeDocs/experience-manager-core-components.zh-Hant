---
title: 使用核心元件編寫
description: 在AEM中，元件是構成所撰寫頁面內容的結構元素——核心元件提供有彈性且功能豐富的製作功能。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 使用核心元件製作

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。

核心元件提供有彈性且功能豐富的製作功能。 WKND參 [考網站](https://wknd.site) 及其說明如何使用核心元件來建置豐富的網站體驗。

若要體驗核心元件並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](https://adobe.com/go/aem_cmp_library)。

如需在AEM專案上實作核心元件(使用 [AEM Project Archetype)的深入、以開發人員為導向的簡介，請參閱](/help/developing/archetype/overview.md) WKND教學課程 [。](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>[開發團隊必須先依照作者的環境整合核心元件](/help/get-started/using.md)，才能將其提供給您。整合後，可透過範本編輯器提供並預先 [設定](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。

>[!CAUTION]
>
>核心元 [件需要AEM 6.3或更新版本](/help/versions.md) ，而且需要使用可編 [輯的範本](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。 它們不適用於Classic UI，也不適用於靜態範本。

## 使用核心元件編寫 {#authoring-with-core-components}

身為作者，您會注意到核心元件的幾項優點，包括：

* 簡單易用且與頁面編輯器完 [整整合](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* 功能豐富，可容納 [WKND參考網站](https://wknd.site) ，以及元件庫中的許 [多使用案例](https://adobe.com/go/aem_cmp_library)

* [預先設定](#pre-configuring-core-components) ，以定義哪些功能可透過範本編輯器提供給頁 [面作者](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

* 以協助工具指 [南為基礎](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

* 專為支援互動式版 [面設計](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* 專為支援輕鬆本 [地化而設](localization.md)

在編輯頁面時，可 **在頁面編輯器側面板的「元件** 」(Components)選 [項卡上使用元件](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)。

元件會根據稱為元件群組的類別分組，以輕鬆組織和篩選元件。 元件群組名稱會與元件一起顯示在元 [件瀏覽器中](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html) ，您也可以依群組篩選，輕鬆找到正確的元件。

>[!NOTE]
>
>「核心元件」預設為隱藏群組的一部分，在元件瀏覽器中不可見。
>
>將所需元件新增至可見群組，或自訂供作者使用。

## 預先設定核心元件 {#pre-configuring-core-components}

設定基礎元件是開發人員的工作。 不過，有了核心元件，範本作者現在可以透過範本編輯器設定許多功能。

例如，如果影像元件不應允許從檔案系統上傳影像，或者文字元件僅允許特定段落格式，只要按一下滑鼠，就可以啟用或停用這些功能。

如需詳 [細資訊，請參閱](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) 「建立頁面範本」。

### 編輯和設計對話框 {#edit-and-design-dialogs}

由於範本作者可預先設定核心元件，以定義範本中允許的選項，然後頁面作者進一步設定以定義實際的頁面內容，因此每個元件可以在兩個不同的對話方塊中有選項。

|  | 說明 | 控制項 | 範例 |
|--- |--- |--- |--- |
| **編輯對話框** | 頁面作者 **在正常頁面編輯** ，對置入的元件進行修改的選項 | 元件顯示的內容，以及它最終在頁面上的顯示方式。 | 格式化內容文字，在頁面上旋轉影像 |
| **設計對話框** | 設定頁面范 **本時** ，範本作者可修改的選項。 | 頁面作者在編輯元件時可使用哪些選項 | 哪些文字格式選項可用，哪些影像就地選項可用 |

### 元件樣式 {#component-styling}

大部分核心元件的樣式都可使用AEM樣式系統來定義。

* 範本作者可以定義哪些樣式可用於該元件的「設計對話框」中的特定元件。
* 然後，內容作者可以選擇在新增元件和建立內容時要套用的樣式。

有關詳細資訊，請參 [閱Style System](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html) 文檔。

>[!NOTE]
>
>在AEM 6.3中，必須有Service Pack 2(6.3.2.0)或更新版本才能啟用樣式系統功能。

## 可用核心元件清單 {#list-of-core-components-available}

以下是連結至頁面的可用核心元件清單，詳細說明其編輯與設計對話方塊功能。

目前版本的核心元件主打下列元件。

* [折疊式面板](/help/components/accordion.md)
* [階層連結](/help/components/breadcrumb.md)
* [按鈕](/help/components/button.md)
* [容器](/help/components/container.md)
* [傳送](/help/components/carousel.md)
* [內容片段](/help/components/content-fragment-component.md)
* [內容片段清單](/help/components/content-fragment-list.md)
* [下載](/help/components/download.md)
* [內嵌](/help/components/embed.md)
* [體驗片段](/help/components/experience-fragment.md)
* [表單按鈕](/help/components/forms/form-button.md)
* [來自容器](/help/components/forms/form-container.md)
* [已隱藏的表單](/help/components/forms/form-hidden.md)
* [表單選項](/help/components/forms/form-options.md)
* [表單文字](/help/components/forms/form-text.md)
* [影像](/help/components/image.md)
* [語言導覽](/help/components/language-navigation.md)
* [清單](/help/components/list.md)
* [導覽](/help/components/navigation.md)
* [頁面](/help/components/page.md)
* [快速搜尋](/help/components/quick-search.md)
* [分隔符號](/help/components/separator.md)
* [社交媒體分享](/help/components/sharing.md)
* [索引標籤](/help/components/tabs.md)
* [文字](/help/components/text.md)
* [標題](/help/components/title.md)

>[!CAUTION]
>
>某些版本的個別核心元件可能只相容於特定版本的 AEM。
>
>如需特定元件的相容性資訊，請參閱說明頁面 (連結至上一份清單)，或參考[核心元件版本](/help/versions.md)文件以取得詳細資訊。

>[!NOTE]
>
>視您的例項而定，您可能已針對您的需求明確開發自訂元件。 這些元件甚至可能與此處討論的某些元件名稱相同。
>表單核心元件與AEM Forms無關。

## 開發人員資源 {#developer-resources}

如需核心 [元件的技術資訊](/help/developing/overview.md) ，請參閱開發核心元件開發人員檔案。