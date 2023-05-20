---
title: 使用核心元件編寫
description: 在中AEM，元件是構成正在創作的頁面內容的結構元素 — 核心元件提供靈活且功能豐富的創作功能。
role: Architect, Developer, Admin, User
exl-id: 56e58303-a178-45ab-b59d-e374c9cf90cf
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 8%

---

# 使用核心元件

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。

核心元件提供靈活且功能豐富的創作功能。 的 [WKND參考站點](https://wknd.site) 並說明了如何利用核心元件來實現豐富的網站體驗。

要體驗核心元件並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library)。

有關在項目上通過使用 [項AEM目原型](/help/developing/archetype/overview.md) 簽出 [WKND教程。](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hant)

>[!NOTE]
>
>[開發團隊必須先依照作者的環境整合核心元件](/help/get-started/using.md)，才能將其提供給您。整合後，可通過 [模板編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)。

>[!CAUTION]
>
>核心元件 [要求AEM6.4或更高版本](/help/versions.md) 並要求 [可編輯模板](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)。 它們不與Classic UI或靜態模板一起使用。

## 使用核心元件編寫 {#authoring-with-core-components}

作為作者，您將注意到核心元件的幾個優點，包括：

* 易於使用，與 [頁面編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* 功能豐富，可容納許多使用情形，如 [WKND參考站點](https://wknd.site) 以及 [元件庫](https://adobe.com/go/aem_cmp_library)

* [預配置](#pre-configuring-core-components) 定義頁面作者可通過 [模板編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

* 圍繞 [輔助性指導](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

* 構建為支援 [響應佈局](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* 構建為支援 [易定位](localization.md)

元件在 **元件** 的子菜單。 [編輯頁面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)。

元件按稱為元件組的類別進行分組，以便輕鬆地組織和過濾元件。 元件組名隨元件在 [元件瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html) 也可以按組過濾，方便地找到正確的元件。

>[!NOTE]
>
>預設情況下，「核心元件」是隱藏組的一部分，在元件瀏覽器中不可見。
>
>將所需元件添加到可見組或自定義它們，以便作者可以使用這些元件。

## 預配置核心元件 {#pre-configuring-core-components}

配置基礎元件是開發人員的作業。 但是，使用核心元件，模板作者現在可以通過模板編輯器配置許多功能。

例如，如果影像元件不應允許從檔案系統上載影像，或者文本元件應僅允許某些段落格式設定，則只需按一下一下即可啟用或禁用這些功能。

請參閱 [建立頁面模板](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 的子菜單。

### 編輯和設計對話框 {#edit-and-design-dialogs}

由於核心元件可由模板作者預先配置，以定義允許哪些選項作為模板的一部分，然後由頁面作者進一步配置以定義實際頁面內容，因此每個元件可以在兩個不同的對話框中具有選項。

|  | 說明 | 它控制的內容 | 範例 |
|--- |--- |--- |--- |
| **編輯對話框** | 選項 **頁面作者** 可在對放置的元件進行常規頁面編輯期間進行修改 | 元件顯示的內容及其最終在頁面上的顯示方式。 | 格式化內容文本，在頁面上旋轉影像 |
| **設計對話框** | 選項 **模板作者** 可以在配置頁面模板時進行修改。 | 編輯元件時頁面作者可用的選項 | 哪些文本格式選項可用，哪些影像就地選項可用 |

### 元件樣式 {#component-styling}

大多數「核心元件」的樣式都可使用樣式系AEM統定義。

* 模板作者可以定義哪些樣式可用於該元件的「設計」對話框中的特定元件。
* 然後，內容作者可以選擇添加元件和建立內容時應用的樣式。

有關詳細資訊，請參閱 [樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html) 文檔。

## 開發人員資源 {#developer-resources}

查看 [開發核心元件](/help/developing/overview.md) 有關核心元件的技術資訊的開發人員文檔。
