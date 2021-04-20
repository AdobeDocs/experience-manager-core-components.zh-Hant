---
title: Accordion元件
description: 核心元件Accordion元件允許建立在頁面上以accordion排列的面板集合。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 0%

---


# Accordion Component{#accordion-component}

核心元件Accordion元件允許建立在頁面上以accordion排列的面板集合。

## 使用狀況 {#usage}

核心元件Accordion元件允許建立元件集合，這些元件以面板形式構成，並排列在頁面上的accordion中，類似於[標籤元件](tabs.md)，但允許展開和折疊面板。

* accordion的屬性可在[configure dialog](#configure-dialog)中定義。
* accordion面板的順序可在「設定」對話方塊以及[選擇面板快顯](#select-panel-popover)中定義。
* 將Accordion元件添加到頁面時的預設值可在[設計對話框](#design-dialog)中定義。

## 面板{#deep-linking}的深層連結

Accordion和[Tabs Components](tabs.md)支援直接連結至元件內的面板。

要執行此操作：

1. 使用頁面編輯器中的&#x200B;**[「檢視為已發佈」選項，檢視包含元件的頁面。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**
1. Inspect網頁內容，並識別面板的ID。
   * 例如`id="accordion-86196c94d3-item-ca319dbb0b"`
1. 此ID會成為您可使用雜湊(`#`)附加至URL的錨點。
   * 例如`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

瀏覽至以面板ID為錨點的URL時，瀏覽器會直接捲動至特定元件並顯示指定的面板。 如果面板配置為預設不展開，則會自動展開。

## 版本和相容性{#version-and-compatibility}

Accordion元件的目前版本為v1，此版本於2019年6月隨核心元件2.5.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗Accordion元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_accordion)。

## 技術詳細資訊{#technical-details}

有關Accordion元件[的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_accordion_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

設定對話方塊可讓內容作者定義accordion項目、其面板，以及該項目的行為和顯示方式，讓頁面的訪客檢視。

### 項目標籤{#items-tab}

![Accordion元件的編輯對話框的「項」頁籤](/help/assets/accordion-edit-items.png)

使用&#x200B;**Add**&#x200B;按鈕來開啟元件選擇器，以選擇要新增為面板的元件。 新增後，會將一個項目新增至清單，其中包含下列欄：

* **圖示** -面板的元件類型表徵圖，以便在清單中輕鬆標識。將滑鼠移至上方，以檢視完整元件名稱做為工具提示。
* **說明** -用作面板文本的說明，預設為為為面板選擇的元件的名稱。
* **刪除** -點選或按一下，從accordion元件中刪除面板。
* **重新排列** -點選或按一下並拖曳以重新排列面板的順序。

>[!TIP]
>
>如果頁面的視區被縮小，使編輯對話框變為全屏，則&#x200B;**添加**&#x200B;按鈕將隱藏。 從元件瀏覽器拖曳並拖曳至頁面編輯器中的Accordion元件，仍可將元件添加到Accordion元件中。[](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)

### 屬性頁籤{#properties-tab}

![Accordion元件的編輯對話框的屬性頁籤](/help/assets/accordion-edit-properties.png)

* **單一項目擴展** -選擇此選項後，將強制一次擴展單個accordion項目。展開一個項目將會收合所有其他項目。
* **展開的項目** -此選項定義在載入頁面時依預設展開的項目。
   * 選擇&#x200B;**單項擴展**&#x200B;時，必須選擇一個面板。 依預設會選取第一個面板。
   * 如果未選擇&#x200B;**單個項目擴展**，此選項是多選項，是可選的。
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

## 選擇「面板」 「沿面{#select-panel-popover}」

內容作者可使用元件工具列上的「選取面板」(**Select Panel**)選項，變更為不同的面板進行編輯，並輕鬆重新排列accordion中面板的順序。

![選取面板圖示](/help/assets/select-panel-icon.png)

在元件工具列中選取「選取面板」(**Select Panel)**&#x200B;選項後，所設定的accordion面板會顯示為下拉式清單。

![選取面板快顯視窗](/help/assets/select-panel-popover.png)

* 該清單按所指定的面板排列排序，並反映在編號中。
* 首先顯示面板的元件類型，然後以更亮的字型說明面板。
* 點選或按一下下拉式清單中的項目，將編輯器中的檢視切換至該面板。
* 通過使用拖曳控點，可以就地重新排列面板。

## 設計對話框{#design-dialog}

設計對話框允許模板作者定義內容作者可用的選項，內容作者使用Accordion元件，並在放置Accordion元件時設定預設值。

### 屬性頁籤{#properties-tab-design}

![「設計」對話框屬性頁籤](/help/assets/accordion-design-properties.png)

* **允許的標題元素** -此多選下拉式清單定義作者允許選取的accordion項目標題HTML元素。
* **預設標題元素** -此下拉式清單定義預設的accordion項目標題HTML元素。

### 允許的元件頁籤{#allowed-components-tab}

**允許的元件**&#x200B;標籤用於定義內容作者可將哪些元件新增為Accordion元件中的面板項目。

當[在範本編輯器中定義版面容器的原則和屬性時，「允許的元件」標籤的運作方式與相同名稱的標籤相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### 樣式標籤{#styles-tab}

Accordion元件支AEM持[Style System](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層{#data-layer}

Accordion元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
