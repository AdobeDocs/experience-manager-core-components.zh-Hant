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
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# 標籤元件

核心元件標籤元件可讓您將內容組織成多個標籤。

## 使用狀況 {#usage}

標籤元件可讓內容作者組織多個標籤中的頁面內容。

[編輯對話方塊](#edit-dialog) 可讓內容作者定義多個標籤以及設定作用中標籤。Using the [design dialog](#design-dialog), the template author can define which components can be added to tabs and customize the styles.

>[!NOTE]
>
>輔助標籤元件(標籤內的標籤)受到支援。
>
>Simple (non-nested) tab components can be located/selected using the [content tree](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html), however nested tabs can not be.

## Version and Compatibility {#version-and-compatibility}

目前版本的Tab元件是v1，是在2018年10月發行的版本2.2.0推出的v1，本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Tabs Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/tabs.html).

### Technical Details {#technical-details}

The latest technical documentation about the Tabs Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者建立、重新命名和重新排列標籤，以及定義作用中標籤。

### Items Tab {#items-tab}

![](assets/screenshot_2018-10-11at153557.png)

Use the **Add** button to open the component selector to choose which component to add as a tab. 新增後，清單會新增至清單中，其中包含下列欄：

* **圖示** -標籤的元件類型圖示，以方便清單中的識別。將滑鼠移至上方，將完整元件名稱視為工具提示。
* **描述** -作為標籤文字的說明，預設為標籤所選元件的名稱。
* **刪除** -點選或按一下，從標籤元件刪除標籤。
* **重新排列** -點選或按一下並拖曳以重新排列標籤順序。

### Properties Tab {#properties-tab}

![](assets/screenshot_2018-10-19at140646.png)

On the **Properties** tab, the content author can define which tab is active when the page is loaded. With the **Default** option, the first tab will be selected.

## Select Panel {#select-panel}

The content author can use the **Select Panel** option on the component toolbar to change to a different panel for editing as well as to easily rearrange the order of the tabs.

![](assets/screenshot_2018-10-11at165417.png)

Once selecting the **Select Panel** option in the component toolbar, the configured tabs are displayed as a drop-down.

* 清單由標籤的指派排列排列，並反映在編號中。
* 接著會顯示標籤的元件類型，後面接著較淺色的標籤說明。

![](assets/screenshot_2018-10-11at165154.png)

* 點選或按一下下拉式清單中的項目，會將編輯器中的檢視切換為該標籤。
* 您可以使用拖曳控制點，就地重新排列標籤。

>[!NOTE]
>
>Tabs are not selectable by the author when in **Edit** mode. Use [**Preview** mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) or the **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** option to interact with the tabs as a reader of the published content would.

## Design Dialog {#design-dialog}

此設計對話方塊可讓範本作者定義哪些元件可以新增為標籤元件的項目，以及定義內容作者可用的自訂樣式。

### Allowed Components Tab {#allowed-components-tab}

**「允許的元件** 」索引標籤用於定義內容作者可以將哪些元件新增為標籤元件。

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Styles Tab {#styles-tab}

The Tabs Component supports the AEM [Style System](authoring.md#component-styling).