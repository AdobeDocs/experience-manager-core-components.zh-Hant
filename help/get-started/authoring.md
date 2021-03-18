---
title: 使用核心元件編寫
description: 在中AEM，元件是構成所製作頁面內容的結構元素——核心元件提供有彈性且功能豐富的製作功能。
role: 架構師、開發人員、管理員、商業從業人員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 8%

---


# 使用核心元件製作

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。

核心元件提供有彈性且功能豐富的製作功能。 [WKND參考網站](https://wknd.site)及其說明如何使用核心元件來建置豐富的網站體驗。

若要體驗核心元件並檢視其設定選項以及HTML和JSON輸出的範例，請造訪[元件庫](https://adobe.com/go/aem_cmp_library)。

如需更深入、以開發人員為導向的簡介，以介紹如何使用[AEM Project Archetype](/help/developing/archetype/overview.md)查看[ WKND教學課程，在專案上實作核心元件。](https://docs.adobe.com/content/help/zh-Hant/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>[開發團隊必須先依照作者的環境整合核心元件](/help/get-started/using.md)，才能將其提供給您。整合後，可透過[範本編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)使它們可用並預先設定。

>[!CAUTION]
>
>核心元件[需要AEM6.4或更高版本](/help/versions.md)，並需要使用[可編輯的範本](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。 它們不適用於Classic UI，也不適用於靜態範本。

## 使用核心元件編寫 {#authoring-with-core-components}

身為作者，您會注意到核心元件的幾項優點，包括：

* 使用簡單，並與[頁面編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)緊密整合

* 功能豐富，可容納許多使用案例，如[WKND參考網站](https://wknd.site)以及[元件庫](https://adobe.com/go/aem_cmp_library)中所示

* [預先設](#pre-configuring-core-components) 定可透過範本編輯器定義頁面作者可使用的 [功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

* 以[協助工具指南](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)為基礎

* 內建以支援[回應式版面](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* 內建以支援[簡易本地化](localization.md)

當[編輯頁面](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)時，頁面編輯器側面板的&#x200B;**「元件」(Components)**&#x200B;標籤上提供元件。

元件會根據稱為元件群組的類別分組，以輕鬆組織和篩選元件。 元件組名稱與元件一起顯示在[元件瀏覽器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)中，還可以按組進行篩選，以便輕鬆找到正確的元件。

>[!NOTE]
>
>「核心元件」預設為隱藏群組的一部分，在元件瀏覽器中不可見。
>
>將所需元件新增至可見群組，或自訂供作者使用。

## 預配置核心元件{#pre-configuring-core-components}

設定基礎元件是開發人員的工作。 不過，有了核心元件，範本作者現在可以透過範本編輯器設定許多功能。

例如，如果影像元件不應允許從檔案系統上傳影像，或者文字元件僅允許特定段落格式，只要按一下滑鼠，就可以啟用或停用這些功能。

如需詳細資訊，請參閱[建立頁面範本](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。

### 編輯和設計對話框{#edit-and-design-dialogs}

由於範本作者可預先設定核心元件，以定義範本中允許的選項，然後頁面作者進一步設定以定義實際的頁面內容，因此每個元件可在兩個不同的對話方塊中提供選項。

|  | 說明 | 控制項 | 範例 |
|--- |--- |--- |--- |
| **編輯對話框** | **頁面作者**&#x200B;可在置入元件的正常頁面編輯期間修改的選項 | 元件顯示的內容，以及它最終在頁面上的顯示方式。 | 格式化內容文字，在頁面上旋轉影像 |
| **設計對話框** | 設定頁面範本時，**範本作者**&#x200B;可修改的選項。 | 頁面作者在編輯元件時可使用哪些選項 | 哪些文字格式選項可用，哪些影像就地選項可用 |

### 元件樣式{#component-styling}

大部分核心元件的樣式都可使用樣式系統來AEM定義。

* 範本作者可以定義哪些樣式可用於該元件的「設計對話框」中的特定元件。
* 然後，內容作者可以選擇在新增元件和建立內容時要套用的樣式。

有關詳細資訊，請參閱[Style System](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html)文檔。

## 開發人員資源 {#developer-resources}

有關核心元件的技術資訊，請參閱[開發核心元件](/help/developing/overview.md)開發人員文檔。
