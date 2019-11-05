---
title: Accordion元件
seo-title: Accordion元件
description: 'null'
seo-description: 核心元件Accordion元件允許建立在頁面上以accordion排列的面板集合。
uuid: ec807de9-f76c-4850-9ece-c3e439a1d626
contentOwner: 使用者
content-type: 參考
topic-tags: 編寫
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: f093f58e-9755-4a4f-803a-ab93a50e6870
translation-type: tm+mt
source-git-commit: da404fff6c6e934bbe06a5c4d441d89281ed0c54

---


# Accordion元件{#accordion-component}

核心元件Accordion元件允許建立在頁面上以accordion排列的面板集合。

## 使用狀況 {#usage}

核心元件Accordion元件可建立元件集合，以面板形式組成，並排列在頁面上的accordion中，類似於 [Tabs元件](tabs.md)，但允許展開和收合面板。

* accordion的屬性可在「設定」對話 [方塊中定義](#configure-dialog)。
* accordion面板的順序可在「設定」對話方塊和「選取」面板快 [顯視窗中定義](#select-planel.md)。
* 將Accordion元件新增至頁面時的預設值，可在設計對話方塊中 [定義](#design-dialog)。

## 版本與相容性 {#version-and-compatibility}

Accordion元件的目前版本為v1，此版本於2019年6月隨核心元件2.5.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗Accordion元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](http://opensource.adobe.com/aem-core-wcm-components/library/accordion.html)。

## 技術詳細資訊 {#technical-details}

有關Accordion元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/accordion/v1/accordion)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## 配置對話框 {#configure-dialog}

設定對話方塊可讓內容作者定義accordion項目、其面板，以及該項目的行為和顯示方式，讓頁面的訪客檢視。

### 項目標籤 {#items-tab}

![](assets/screen-shot-2019-06-21-08.26.38.png)

使用「 **新增** 」按鈕開啟元件選擇器，以選擇要新增為面板的元件。 新增後，會將一個項目新增至清單，其中包含下列欄：

* **圖示** -面板的元件類型表徵圖，以便在清單中輕鬆標識。 將滑鼠移至上方，以檢視完整元件名稱做為工具提示。
* **說明** -用作面板文本的說明，預設為為為面板選擇的元件的名稱。
* **刪除** -點選或按一下，從accordion元件中刪除面板。
* **重新排列** -點選或按一下並拖曳以重新排列面板的順序。

### 屬性標籤 {#properties-tab}

![](assets/screen-shot-2019-06-21-08.26.53.png)

* **單一項目擴展** -選擇此選項後，將強制一次擴展單個accordion項目。 展開一個項目將會收合所有其他項目。
* **展開的項目** -此選項定義在載入頁面時依預設展開的項目。
   * 選取「 **單一項目展開** 」時，必須選取一個面板。 依預設會選取第一個面板。
   * 如果未 **選取「單一項目展開** 」，此選項為多選項，且為可選項。

>[!TIP]
>
>如果頁面的視區被縮小，使編輯對話方塊變成全螢幕，則「新增」 **按鈕** 將會隱藏。 您仍可從元件瀏覽器拖曳至頁面編輯器 [中的Accordion元件，將元件新增至Accordion元件](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)。

## 選取面板快顯 {#seelct-panel-popover}

內容作者可使用元件工具列上的「選取面板 **** 」選項，變更為不同的面板進行編輯，並輕鬆重新排列accordion中面板的順序。

![](assets/screen-shot-2019-06-21-08.49.36.png)

在元件工 **具列中選取「選取面板** 」選項後，所設定的accordion面板會顯示為下拉式清單。

![](assets/screen-shot-2019-06-21-08.52.14.png)

* 該清單按所指定的面板排列排序，並反映在編號中。
* 首先顯示面板的元件類型，然後以更亮的字型說明面板。
* 點選或按一下下拉式清單中的項目，將編輯器中的檢視切換至該面板。
* 通過使用拖曳控點，可以就地重新排列面板。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者可用的選項，內容作者使用Accordion元件，並在放置Accordion元件時設定預設值。

### 屬性標籤 {#properties-tab-design}

![](assets/screen-shot-2019-06-21-08.58.11.png)

* **允許的標題元素** -此多選下拉式清單定義作者允許選取的accordion項目標題HTML元素。
* **預設標題元素** -此下拉式清單定義預設的accordion項目標題HTML元素。

### 允許的元件頁籤 {#allowed-components-tab}

「允 **許的元件** 」索引標籤可用來定義哪些元件可由內容作者新增為Accordion元件的面板項目。

在範本編輯器中定義配置容器的原則和屬性時，「允許的元件」標 [簽的功能與相同名稱的標籤相同。](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### 樣式標籤 {#styles-tab}

Accordion元件支援AEM [Style系統](authoring.md#component-styling)。
