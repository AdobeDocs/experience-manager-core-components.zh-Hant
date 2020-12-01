---
title: 標籤元件
description: 「標籤元件」允許建立多個標籤，以在頁面上排列內容。
translation-type: tm+mt
source-git-commit: 2926c51c2ab97b50b9ec4942cd5415c15a1411b6
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 0%

---


# 標籤元件{#tabs-component}

核心元件標籤元件可讓內容組織到多個標籤上。

## 使用狀況 {#usage}

標籤元件可讓內容作者在多個標籤中組織頁面內容。

[edit dialog](#edit-dialog)可讓內容作者定義多個標籤並設定作用中的標籤。 使用[設計對話框](#design-dialog)，模板作者可以定義哪些元件可以添加到頁籤並自定義樣式。

>[!TIP]
>
>支援巢狀標籤元件（標籤內的標籤）。
>
>使用[內容樹](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree)可以定位／選擇簡單（非巢狀）標籤元件，但嵌套標籤不可以。

## 面板{#deep-linking}的深層連結

標籤和[Accordion元件](accordion.md)支援直接連結至元件內的面板。

要執行此操作：

1. 使用頁面編輯器中的&#x200B;**[「檢視為已發佈」選項，檢視包含元件的頁面。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**
1. 檢查頁面內容並識別面板的ID。
   * 例如`id="accordion-86196c94d3-item-ca319dbb0b"`
1. 此ID會成為您可使用雜湊(`#`)附加至URL的錨點。
   * 例如`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

瀏覽至以面板ID為錨點的URL時，瀏覽器會直接捲動至特定元件並顯示指定的面板。 如果面板配置為預設不展開，則會自動展開。

## 版本和相容性{#version-and-compatibility}

目前的標籤元件版本為v1，此版本於2018年10月隨核心元件2.2.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗標籤元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_tabs)。

### 技術詳細資訊{#technical-details}

有關Tabs Component [的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_tabs_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者建立、重新命名和重新排列標籤，並定義作用中的標籤。

### 項目標籤{#items-tab}

![頁籤元件的編輯對話框項頁籤](/help/assets/tabs-edit-items.png)

使用&#x200B;**Add**&#x200B;按鈕來開啟元件選擇器，以選擇要新增為標籤的元件。 新增後，會將一個項目新增至清單，其中包含下列欄：

* **表徵圖** -頁籤的元件類型表徵圖，以便在清單中輕鬆標識。將滑鼠移至上方，以檢視完整元件名稱做為工具提示。
* **說明** -用作標籤文本的說明，預設為為標籤選擇的元件的名稱。
* **Delete**  —— 點選或按一下，從Tab元件中刪除Tab。
* **重新排列** -點選或按一下並拖曳以重新排列標籤的順序。

>[!TIP]
>
>如果頁面的視區被縮小，使編輯對話框變為全屏，則&#x200B;**添加**&#x200B;按鈕將隱藏。 您仍可從元件瀏覽器拖曳至頁面編輯器[中的標籤元件，將元件新增至標籤元件。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)

### 屬性頁籤{#properties-tab}

![頁籤元件的編輯對話框屬性頁籤](/help/assets/tabs-edit-properties.png)

* **作用中項目** -內容作者可以定義載入頁面時作用中的標籤。
   * 使用&#x200B;**Default**&#x200B;選項，將選擇第一個頁籤。
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

### 輔助功能頁籤{#accessibility-tab}

![頁籤元件的編輯對話框輔助功能頁籤](/help/assets/tabs-edit-accessibility.png)

在&#x200B;**Accessibility**&#x200B;標籤上，可為元件的[ARIA accessibility](https://www.w3.org/WAI/standards-guidelines/aria/)標籤設定值。

* **Label**  —— 元件的ARIA label屬性的值

## 選擇面板{#select-panel}

內容作者可使用元件工具列上的「選取面板」(**Select Panel)**&#x200B;選項，變更為不同的面板進行編輯，並輕鬆重新排列標籤順序。

![選取面板圖示](/help/assets/select-panel-icon.png)

在元件工具欄中選擇&#x200B;**選擇面板**&#x200B;選項後，將顯示已配置的頁籤作為下拉式頁籤。

* 清單按指定的制表符排列，並反映在編號中。
* 頁籤的元件類型將首先顯示，然後以更亮的字型顯示頁籤的說明。

![選取面板快顯視窗](/help/assets/select-panel-popover.png)

* 點選或按一下下拉式清單中的項目，將編輯器中的檢視切換至該標籤。
* 通過使用拖曳控制點，可以就地重新排列這些標籤。

>[!NOTE]
>
>作者在&#x200B;**Edit**&#x200B;模式下無法選取標籤。 使用&#x200B;**[預覽](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)**&#x200B;模式或&#x200B;**[檢視為發佈](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;選項，與標籤互動，以做為發佈內容的讀者。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義哪些元件可新增為標籤元件的項目，以及定義哪些自訂樣式可供內容作者使用。

### 允許的元件頁籤{#allowed-components-tab}

**允許的元件**&#x200B;標籤用於定義內容作者可以將哪些元件新增為標籤元件的項目。

當[在範本編輯器中定義版面容器的原則和屬性時，「允許的元件」標籤的運作方式與相同名稱的標籤相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式標籤{#styles-tab}

Tabs Component支援AEM [Style System](/help/get-started/authoring.md#component-styling)。
