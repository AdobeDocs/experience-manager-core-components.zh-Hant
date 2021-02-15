---
title: 轉盤元件
description: 「轉盤元件」可讓內容作者在旋轉轉盤中呈現內容。
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 0%

---


# 轉盤元件{#carousel-component}

核心元件轉盤元件可讓內容作者在可導覽轉盤中呈現內容。

## 使用狀況 {#usage}

內容作者使用轉盤元件，在旋轉的投影片轉盤中組織內容。

[edit dialog](#edit-dialog)可讓內容作者建立、命名和排序多張投影片，並啟用延遲的自動轉換。 使用[設計對話方塊](#design-dialog)，範本作者可以定義哪些元件可以加入轉盤、啟用或停用自動轉場效果，以及自訂樣式。

## 版本和相容性{#version-and-compatibility}

目前的轉盤元件版本為v1，此版本於2018年10月隨核心元件2.2.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗轉盤元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_carousel)。

### 技術詳細資訊{#technical-details}

有關轉盤元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者新增、重新命名和重新排列投影片，並定義自動轉場設定。

### 項目標籤{#items-tab}

![「轉盤元件」的編輯對話方塊的「項目」標籤](/help/assets/carousel-edit-items.png)

使用&#x200B;**Add**&#x200B;按鈕來開啟元件選擇器，以選擇要新增為標籤的元件。 新增後，會將一個項目新增至清單，其中包含下列欄：

* **表徵圖** -頁籤的元件類型表徵圖，以便在清單中輕鬆標識。將滑鼠移至上方，以檢視完整元件名稱做為工具提示。
* **說明** -用作標籤文本的說明，預設為為標籤選擇的元件的名稱。
* **刪除** -點選或按一下以從頁籤元件中刪除頁籤。
* **重新排序** -點選或按一下並拖曳以排序標籤。

>[!TIP]
>
>如果頁面的視區被縮小，使編輯對話框變為全屏，則&#x200B;**添加**&#x200B;按鈕將隱藏。 您仍可從元件瀏覽器拖曳至頁面編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser)中的轉盤元件，將元件新增至轉盤元件。[

### 屬性頁籤{#properties-tab}

![「轉盤元件」的編輯對話方塊的屬性標籤](/help/assets/carousel-edit-properties.png)

在&#x200B;**屬性**&#x200B;標籤上，內容作者可將投影片設定為自動轉換。

* **自動轉換投影片** -在作用中時，元件會在指定延遲後自動前進至下一張投影片。
* **轉場延遲** -選取「自動轉場」投影片時，此值會用來定義轉場之間的延遲（以毫秒為單位）。
* **停用暫留時的自動暫停** -選取「自 **動轉** 場」投影片時，每當游標暫留在轉盤上時，轉盤轉場會自動暫停。選取此選項，讓轉場不會暫停。
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

>[!NOTE]
>
>在&#x200B;**Edit**&#x200B;模式下，不會啟用投影片進階控制。 使用&#x200B;[**預覽**&#x200B;模式](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)或&#x200B;**[檢視為發佈](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;選項，以閱讀發佈內容的方式與轉盤互動。
>
>在&#x200B;**Edit**&#x200B;模式下，自動進階功能不會啟用。 使用「以發佈方式檢視」選項，將自動進階功能視為發佈內容的讀者。**[](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**

### 輔助功能頁籤{#accessibility-tab}

![轉盤元件編輯對話方塊的協助工具標籤](/help/assets/carousel-edit-accessibility.png)

在&#x200B;**Accessibility**&#x200B;標籤上，可為元件的[ARIA accessibility](https://www.w3.org/WAI/standards-guidelines/aria/)標籤設定值。

* **Label**  —— 元件的ARIA label屬性的值

## 選擇面板{#select-panel}

內容作者可使用元件工具列上的「選取面板」(**Select Panel)**&#x200B;選項，變更為不同的投影片以進行編輯，並輕鬆重新排列投影片順序。

![選取面板圖示](/help/assets/select-panel-icon.png)

在元件工具列中選取「選取面板」(**Select Panel)**&#x200B;選項後，所設定的投影片會顯示為下拉式清單。

* 清單按幻燈片的指定排列排序，並反映在編號中。
* 首先顯示幻燈片的元件類型，然後以更亮的字型說明幻燈片。

![選取面板](/help/assets/select-panel-popover.png)

* 點選或按一下下拉式清單中的項目，將編輯器中的檢視切換至該投影片。
* 使用拖曳控點，即可就地重新排序投影片。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義哪些元件可新增為浮動切換元件的投影片，以及定義自動轉換預設值以及哪些自訂樣式可供內容作者使用。

### 屬性頁籤{#properties-tab-1}

**Properties**&#x200B;標籤用於定義內容作者將轉盤元件新增至頁面時投影片轉場的預設設定。

![轉盤元件的設計對話方塊](/help/assets/carousel-design.png)

* **自動轉換投影片** -定義內容作者將轉盤元件新增至頁面時，預設會啟用自動將轉盤移至下一張投影片的選項。
* **轉場延遲** -定義內容作者將轉盤元件新增至頁面時，投影片之間轉場延遲的預設值（以毫秒為單位）。
* **停用暫留時的自動暫停** -定義內容作者選取的「自動轉場投影片」時，預設會啟用停用自動投影片暫停 **** 的選項。

### 允許的元件頁籤{#allowed-components-tab}

**允許的元件**&#x200B;標籤用於定義內容作者可將哪些元件新增為投影片至轉盤元件。

當[在範本編輯器中定義版面容器的原則和屬性時，「允許的元件」標籤的運作方式與相同名稱的標籤相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式標籤{#styles-tab}

轉盤元件支援AEM [Style System](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層{#data-layer}

轉盤元件支援[Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
