---
title: 轉盤元件
seo-title: 轉盤元件
description: 'null'
seo-description: 「轉盤元件」可讓內容作者在旋轉轉盤中呈現內容。
uuid: 34934491-bd85-4f1e-ae22-bb48ed4dbd5c
content-type: 引用
topic-tags: 核心元件
discoiquuid: 3510812b-9d3e-40fe-b986-0f15d40b42ad
disttype: dist5
gnavtheme: 淺色
groupsectionnavitems: 否
hidemerchandisingbar: 繼承
hidepromocomponent: 繼承
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: da404fff6c6e934bbe06a5c4d441d89281ed0c54

---


# 轉盤元件{#carousel-component}

核心元件轉盤元件可讓內容作者在可導覽轉盤中呈現內容。

## 使用狀況 {#usage}

內容作者使用轉盤元件，在旋轉的投影片轉盤中組織內容。

編輯 [對話方塊](#edit-dialog) ，可讓內容作者建立、命名和排序多張投影片，並可延遲自動轉換。 使用設 [計對話方塊](#design-dialog)，範本作者可以定義哪些元件可以加入轉盤、啟用或停用自動轉場效果，以及自訂樣式。

## 版本與相容性 {#version-and-compatibility}

目前的轉盤元件版本為v1，此版本於2018年10月隨核心元件2.2.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗「轉盤元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](http://opensource.adobe.com/aem-core-wcm-components/library/carousel.html)。

### 技術詳細資訊 {#technical-details}

有關轉盤元件的最新技術檔案 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者新增、重新命名和重新排列投影片，並定義自動轉場設定。

### 項目標籤 {#items-tab}

![](assets/screen-shot-2019-08-29-12.01.39.png)

使用「 **新增** 」按鈕開啟元件選擇器，以選擇要新增為標籤的元件。 新增後，會將一個項目新增至清單，其中包含下列欄：

* **表徵圖** -頁籤的元件類型表徵圖，以便在清單中輕鬆標識。 將滑鼠移至上方，以檢視完整元件名稱做為工具提示。
* **說明** -用作標籤文本的說明，預設為為為標籤選擇的元件的名稱。
* **Delete** —— 點選或按一下可從頁籤元件中刪除頁籤。
* **重新排序** -點選或按一下並拖曳以排序標籤。

>[!TIP]
>
>如果頁面的視區被縮小，使編輯對話方塊變成全螢幕，則「新增」 **按鈕** 將會隱藏。 您仍可從元件瀏覽器拖曳至頁面編輯器 [中的轉盤元件，將元件新增至轉盤元件](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)。

### 屬性標籤 {#properties-tab}

![](assets/screen-shot-2019-08-29-12.01.57.png)

在「屬 **性** 」標籤上，內容作者可將投影片設定為自動轉場。

* **自動轉換投影片** -在作用中時，元件會在指定延遲後自動前進至下一張投影片。
* **轉場延遲** -選取「自動轉場」投影片時，此值用於定義轉場之間的延遲（以毫秒為單位）。
* **停用暫留時的自動暫停** -選取「自動 **轉場」投影片** ，每當游標停留在轉盤上時，轉盤轉場會自動暫停。 選取此選項，讓轉場不會暫停。

>[!NOTE]
>
>在「編輯」模式下，不會啟用投影片 **進階控** 制項。 使用 [**預覽** (Preview)模式](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) ，或使用「檢視為已發佈」( **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** )選項，以閱讀已發佈內容的方式與轉盤互動。
>
>在「編輯」模式下，自動進階功能 **未啟用** 。 使用 **[「檢視為已發佈](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** 」選項，將自動進階功能視為已發佈內容的讀者。

### 「輔助工具」頁籤 {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.02.22.png)

在「協 **助工具** 」標籤上，可為元件的 [](https://www.w3.org/WAI/standards-guidelines/aria/) ARIA協助工具標籤設定值。

* **Label** —— 元件的ARIA label屬性的值

## Select Panel {#select-panel}

內容作者可使用元件工具列上的「選取面板 **** 」選項，變更為不同的投影片以進行編輯，並輕鬆重新排列投影片順序。

![](assets/screenshot_2018-10-11at165417.png)

在元件工 **具列中選取「選取面板** 」選項後，所設定的投影片會顯示為下拉式清單。

* 清單按幻燈片的指定排列排序，並反映在編號中。
* 首先顯示幻燈片的元件類型，然後以更亮的字型說明幻燈片。

![](assets/opera_snapshot_2018-11-28141537localhost.png)

* 點選或按一下下拉式清單中的項目，將編輯器中的檢視切換至該投影片。
* 使用拖曳控點，即可就地重新排序投影片。

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者定義哪些元件可新增為浮動切換元件的投影片，以及定義自動轉換預設值以及哪些自訂樣式可供內容作者使用。

### 屬性標籤 {#properties-tab-1}

當內 **容作者將轉盤元件新增至頁面時，「屬性** 」標籤可用來定義投影片轉場的預設設定。

![](assets/screenshot_2018-11-28at141824.png)

* **自動轉場投影片** -定義內容作者將轉盤元件新增至頁面時，預設會啟用自動將轉盤移至下一張投影片的選項。
* **轉場延遲** -定義內容作者將轉盤元件新增至頁面時，投影片之間轉場延遲的預設值（以毫秒為單位）。
* **停用暫留時的自動暫停** -定義內容作者選取「自動轉場投影片 **** 」時，預設會啟用停用自動投影片暫停的選項。

### 允許的元件頁籤 {#allowed-components-tab}

「允 **許的元件** 」標籤用於定義哪些元件可由內容作者新增為投影片至「轉盤元件」。

在範本編輯器中定義配置容器的原則和屬性時，「允許的元件」標 [簽的功能與相同名稱的標籤相同。](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### 樣式標籤 {#styles-tab}

「轉盤元件」支援AEM [Style系統](authoring.md#component-styling)。
