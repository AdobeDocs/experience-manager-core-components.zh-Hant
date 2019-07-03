---
title: 轉盤元件
seo-title: 轉盤元件
description: 'null'
seo-description: 轉盤元件可讓內容作者在旋轉轉盤中呈現內容。
uuid: 3493491-bd85-4f1 e-ae22-bb48 ed4 dbd5 c
content-type: 引用
topic-tags: 核心元件
discoiquuid: 3510812b-9d3e-40Fe-b986-0f15 d40 b42廣告
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
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Carousel Component{#carousel-component}

核心元件轉盤元件可讓內容作者在導覽轉盤中呈現內容。

## 使用狀況 {#usage}

使用轉盤元件，內容作者可在投影片旋轉轉盤中組織內容。

[編輯對話方塊](#edit-dialog) 可讓內容作者建立、命名和排序多張投影片，並啓用延遲自動轉場。Using the [design dialog](#design-dialog), the template author can define which components can be added to the carousel, enable or disable automatic transitions, and customize the styles.

## Version and Compatibility {#version-and-compatibility}

目前版本的Carousel Component is v1，它是在2018年10月發行的版本2.2.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Carousel Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/carousel.html).

### Technical Details {#technical-details}

The latest technical documentation about the Carousel Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者新增、重新命名和重新排列投影片，以及定義自動轉場設定。

### Items Tab {#items-tab}

![](assets/screenshot_2018-10-12at102451.png)

Use the **Add** button to open the component selector to choose which component to add as a tab. 新增後，清單會新增至清單中，其中包含下列欄：

* **圖示** -標籤的元件類型圖示，以方便清單中的識別。將滑鼠移至上方，將完整元件名稱視為工具提示。
* **描述** -作為標籤文字的說明，預設為標籤所選元件的名稱。
* **刪除** -點選或按一下，從標籤元件刪除標籤。
* **重新排序** -點選或點選並拖曳以訂購標籤。

### Properties Tab {#properties-tab}

![](assets/screenshot_2018-11-28at141054.png)

On the **Properties** tab, the content author can set the slides to automatically transition.

* **自動轉換投影片** -當作用中時，元件會自動前進至下一張投影片，然後再指定延遲。
* **轉換延遲** -當選取自動轉場投影片時，此值可用來定義轉場之間的延遲(以毫秒為單位)。
* **在滑鼠停留** 時停用自動暫停-當選取 **自動轉場投影片** 時，轉盤轉場會在游標停留在轉盤上時自動暫停。選取此選項，讓轉場不會暫停。

>[!NOTE]
>
>The slide advance controls are not enabled when in **Edit** mode. Use [**Preview** mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) or the **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** option to interact with the carousel as a reader of the published content would.
>
>**在編輯** 模式中，未啓用自動進階功能。Use **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** option to see the auto-advance feature as a reader of the published content would.

## Select Panel {#select-panel}

The content author can use the **Select Panel** option on the component toolbar to change to a different slide for editing as well as to easily rearrange the order of the slides.

![](assets/screenshot_2018-10-11at165417.png)

Once selecting the **Select Panel** option in the component toolbar, the configured slides are displayed as a drop-down.

* 清單是依投影片的指派排列排列，並反映在編號中。
* 投影片的元件類型會先顯示，後面接著投影片的說明。

![](assets/opera_snapshot_2018-11-28141537localhost.png)

* 點選或按一下下拉式清單中的項目，會將編輯器中的檢視切換為該投影片。
* 您可以使用拖曳控制點，就地排序投影片。

## Design Dialog {#design-dialog}

此設計對話方塊可讓範本作者定義哪些元件可加入至轉盤元件，以及定義自動轉場預設值，以及內容作者可用的自訂樣式。

### Properties Tab {#properties-tab-1}

**「屬性** 」索引標籤可用來定義當內容作者新增轉盤元件至頁面時，投影片轉場的預設設定。

![](assets/screenshot_2018-11-28at141824.png)

* **自動轉換投影片** -定義當內容作者將轉盤元件新增至頁面時，預設會啓用自動前進轉盤至下一張投影片的選項。
* **轉換延遲** -定義內容作者將轉盤元件加入頁面時，投影片之間轉場延遲的預設值(以毫秒為單位)。
* **在滑鼠停留** 時停用自動暫停-定義預設情況下，當內容作者選取 **自動轉場投影片** 時，會啓用自動投影片暫停選項。

### Allowed Components Tab {#allowed-components-tab}

**「允許的元件** 」索引標籤用於定義內容作者可以新增哪些元件做為投影片至「轉盤元件」。

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Styles Tab {#styles-tab}

The Carousel Component supports the AEM [Style System](authoring.md#component-styling).