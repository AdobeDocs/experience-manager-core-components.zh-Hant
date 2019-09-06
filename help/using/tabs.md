---
title: 標籤元件
seo-title: 標籤元件
description: 標籤元件可讓您建立多個標籤，以在頁面上排列內容。
seo-description: 標籤元件可讓您建立多個標籤，以在頁面上排列內容。
uuid: 46f71233-8b12-4887-a0 c6-ad24 dc469 cb1
content-type: 引用
topic-tags: 核心元件
discoiquuid: 966d47fb-d35 d-4103-b29 d-4ef0 aua739 f24
translation-type: tm+mt
source-git-commit: 48d23edbcdf4c4ed70d590cf6c6e4ac1db14f852

---


# 標籤元件

核心元件標籤元件可讓您將內容組織成多個標籤。

## 使用狀況 {#usage}

標籤元件可讓內容作者組織多個標籤中的頁面內容。

[編輯對話方塊](#edit-dialog) 可讓內容作者定義多個標籤以及設定作用中標籤。範本作者可以使用 [設計對話方塊](#design-dialog)，定義哪些元件可以新增至標籤並自訂樣式。

>[!NOTE]
>
>輔助標籤元件(標籤內的標籤)受到支援。
>
>您可以使用 [內容樹狀目錄來放置/選取簡單(非巢狀)標籤元件](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html)，不過巢狀索引標籤不能。

## 版本與相容性 {#version-and-compatibility}

目前版本的Tab元件是v1，是在2018年10月發行的版本2.2.0推出的v1，本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

若要體驗標籤元件，以及查看其組態選項以及HTML和JSON輸出的範例，請造訪 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library/tabs.html)。

### 技術細節 {#technical-details}

有關標籤元件的 [最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者建立、重新命名和重新排列標籤，以及定義作用中標籤。

### 項目標籤 {#items-tab}

![](assets/screen-shot-2019-08-29-12.28.16.png)

使用 **「新增** 」按鈕開啓元件選擇器，以選擇要新增為標籤的元件。新增後，清單會新增至清單中，其中包含下列欄：

* **圖示** -標籤的元件類型圖示，以方便清單中的識別。將滑鼠移至上方，將完整元件名稱視為工具提示。
* **描述** -作為標籤文字的說明，預設為標籤所選元件的名稱。
* **刪除** -點選或按一下，從標籤元件刪除標籤。
* **重新排列** -點選或按一下並拖曳以重新排列標籤順序。

### 屬性索引標籤 {#properties-tab}

![](assets/screen-shot-2019-08-29-12.28.32.png)

在 **「屬性** 」索引標籤上，內容作者可以定義載入頁面時的作用中標籤。使用 **預設** 選項，將會選取第一個標籤。

### 協助工具標籤 {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.28.40.png)

在 **「協助工具** 」索引標籤上，可為元件設定 [AIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 標籤的值。

* **標籤** -元件的AIA標籤屬性值

## Select Panel {#select-panel}

內容作者可以使用元件工具列上的 **「選取面板** 」選項，變更為不同的面板進行編輯，並輕鬆重新排列標籤順序。

![](assets/screenshot_2018-10-11at165417.png)

選取元件工具列中的 **「選取面板** 」選項後，設定的標籤會顯示為下拉式清單。

* 清單由標籤的指派排列排列，並反映在編號中。
* 接著會顯示標籤的元件類型，後面接著較淺色的標籤說明。

![](assets/screenshot_2018-10-11at165154.png)

* 點選或按一下下拉式清單中的項目，會將編輯器中的檢視切換為該標籤。
* 您可以使用拖曳控制點，就地重新排列標籤。

>[!NOTE]
>
>在 **編輯** 模式中，作者無法選取標籤。使用 [**「預覽** 」模式](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) 或 **[「檢視為已發佈](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** 」選項，將標籤與已發佈內容的讀者互動。

## 設計對話方塊 {#design-dialog}

此設計對話方塊可讓範本作者定義哪些元件可以新增為標籤元件的項目，以及定義內容作者可用的自訂樣式。

### 允許的元件標籤 {#allowed-components-tab}

**「允許的元件** 」索引標籤用於定義內容作者可以將哪些元件新增為標籤元件。

在「範本編輯器」 [中定義「配置容器」的原則和屬性時，「允許元件」索引標籤的功能與相同名稱的標籤相同。](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### 樣式標籤 {#styles-tab}

標籤元件支援AEM [樣式系統](authoring.md#component-styling)。
