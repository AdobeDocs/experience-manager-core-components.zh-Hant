---
title: 標籤元件
seo-title: 標籤元件
description: 「標籤元件」允許建立多個標籤，以在頁面上排列內容。
seo-description: 「標籤元件」允許建立多個標籤，以在頁面上排列內容。
uuid: 46f71233-8b12-4887-a0c6-ad24dc469cb1
content-type: 引用
topic-tags: 核心元件
discoiquuid: 966d47fb-d35d-4103-b29d-4ef0aa739f24
translation-type: tm+mt
source-git-commit: da404fff6c6e934bbe06a5c4d441d89281ed0c54

---


# 標籤元件

核心元件標籤元件可讓內容組織到多個標籤上。

## 使用狀況 {#usage}

標籤元件可讓內容作者在多個標籤中組織頁面內容。

編輯 [對話方塊](#edit-dialog) ，可讓內容作者定義多個標籤，並設定作用中的標籤。 使用設 [計對話框](#design-dialog)，範本作者可以定義哪些元件可以添加到頁籤並定制樣式。

>[!NOTE]
>
>支援巢狀標籤元件（標籤內的標籤）。
>
>使用內容樹可以定位／選擇簡單（非巢狀）標籤元 [件](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html)，但巢狀標籤不可以。

## 版本與相容性 {#version-and-compatibility}

目前的標籤元件版本為v1，此版本於2018年10月隨核心元件2.2.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗標籤元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](http://opensource.adobe.com/aem-core-wcm-components/library/tabs.html)。

### 技術詳細資訊 {#technical-details}

有關Tabs元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者建立、重新命名和重新排列標籤，並定義作用中的標籤。

### 項目標籤 {#items-tab}

![](assets/screen-shot-2019-08-29-12.28.16.png)

使用「 **新增** 」按鈕開啟元件選擇器，以選擇要新增為標籤的元件。 新增後，會將一個項目新增至清單，其中包含下列欄：

* **表徵圖** -頁籤的元件類型表徵圖，以便在清單中輕鬆標識。 將滑鼠移至上方，以檢視完整元件名稱做為工具提示。
* **說明** -用作標籤文本的說明，預設為為為標籤選擇的元件的名稱。
* **Delete** —— 點選或按一下，從Tab元件中刪除Tab。
* **重新排列** -點選或按一下並拖曳以重新排列標籤的順序。

>[!TIP]
>
>如果頁面的視區被縮小，使編輯對話方塊變成全螢幕，則「新增」 **按鈕** 將會隱藏。 您仍可從元件瀏覽器拖曳至頁面編輯器 [的標籤元件，將元件新增至標籤元件](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)。

### 屬性標籤 {#properties-tab}

![](assets/screen-shot-2019-08-29-12.28.32.png)

在「屬 **性** 」標籤上，內容作者可定義載入頁面時作用中的標籤。 使用「預 **設** 」選項，將選取第一個標籤。

### 「輔助工具」頁籤 {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.28.40.png)

在「協 **助工具** 」標籤上，可為元件的 [](https://www.w3.org/WAI/standards-guidelines/aria/) ARIA協助工具標籤設定值。

* **Label** —— 元件的ARIA label屬性的值

## Select Panel {#select-panel}

內容作者可使用元件工具列上的「選取面板 **** 」選項，變更為不同的面板進行編輯，並輕鬆重新排列標籤順序。

![](assets/screenshot_2018-10-11at165417.png)

在元件工 **具列中選取「選取面板** 」選項後，所設定的標籤會顯示為下拉式清單。

* 清單按指定的制表符排列，並反映在編號中。
* 頁籤的元件類型將首先顯示，然後以更亮的字型顯示頁籤的說明。

![](assets/screenshot_2018-10-11at165154.png)

* 點選或按一下下拉式清單中的項目，將編輯器中的檢視切換至該標籤。
* 通過使用拖曳控制點，可以就地重新排列這些標籤。

>[!NOTE]
>
>作者在「編輯」模式下無法選取標 **簽** 。 使用 [**預覽** (Preview)模式](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) ，或使用「檢視為已發佈」( **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** )選項，以閱讀已發佈內容的方式與標籤互動。

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者定義哪些元件可新增為標籤元件的項目，以及定義哪些自訂樣式可供內容作者使用。

### 允許的元件頁籤 {#allowed-components-tab}

「允 **許的元件** 」標籤用於定義哪些元件可由內容作者新增為標籤元件的項目。

在範本編輯器中定義配置容器的原則和屬性時，「允許的元件」標 [簽的功能與相同名稱的標籤相同。](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### 樣式標籤 {#styles-tab}

「標籤元件」支援AEM [Style系統](authoring.md#component-styling)。
