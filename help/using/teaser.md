---
title: 摘要元件
seo-title: 摘要元件
description: 摘要元件可顯示影像、標題、豐富文字，並可選擇性地連結至其他內容。
seo-description: 摘要元件可顯示影像、標題、豐富文字，並可選擇性地連結至其他內容。
uuid: 46989314-df37-448b-8562-c707043 f2160
contentOwner: bohnert
content-type: 引用
topic-tags: 核心元件
discoiquuid: e597c18e-3643-41be-9878-4a7872f1ab90
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Teaser Component{#teaser-component}

核心元件摘要元件可顯示影像、標題、豐富文字，並可選擇性地連結至其他內容。

## 使用狀況 {#usage}

Teaser Component可讓內容作者使用影像、標題或豐富文字，並連結到更進一步的內容或其他動作，輕鬆製作出更進一步的內容。

The template author can use the [design dialog](#design-dialog) to define if the options to create call-to-actions and add links are available as well as disabling various display options. The content author can use the [configure dialog](#configure-dialog) to set an image, define CTAs, set titles and descriptions, and configure links to the individual teaser. The [edit dialog](image.md#edit-dialog) of the [Image Component](image.md) can be accessed to modify the teaser image.

## Version and Compatibility {#version-and-compatibility}

目前的Teaser元件版本是v1，它是在2018年月發行的版本2.1.0版中推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|---|---|---|---|
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

## Sample Component Output {#sample-component-output}

To experience the Teaser Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/teaser.html).

### Technical Details {#technical-details}

The latest technical documentation about the Teaser Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Configure Dialog {#configure-dialog}

內容作者可以使用設定對話方塊來定義個別摘要的屬性。There is also an [edit dialog](#edit-dialog) to modify the teaser image if one is selected.

### 影像 {#image}

![](assets/screen_shot_2018-07-03at104125.png)

* **影像資產**
   * Drop an asset from the [asset browser](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) or tap the **browse** option to upload from a local file system.
   * Tap or click **Clear** to de-select the currently selected image.
   * Tap or click **Edit** to [mange the renditions of the asset](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) in the asset editor.

### 文字 {#text}

![](assets/screen_shot_2018-07-03at104138.png)

* **標題** 定義標題，以做為摘要的標題。
* **從連結頁面** 取得標題時，此標題會填入連結頁面的標題。
* **說明** 定義要顯示為摘要子標題的說明。
* **從連結頁面** 取得描述時，此說明會填入連結頁面的說明。

### Links &amp; Actions {#links-actions}

![](assets/screen_shot_2018-07-03at104146.png)

* **套用至摘要的連結** 連結。使用路徑瀏覽器來選取連結目標。
* **啓用呼叫動作：** 勾選時，啓用「呼叫動作」的定義。清單中的第一個「呼叫對動作」連結會用作其他摘要元素的連結。

## Edit Dialog {#edit-dialog}

The Teaser Component delegates image rendering to the [Image Component](image.md). Therefore the [edit dialog](image.md#edit-dialog of the Image Component is available to the content author to manipulate the teaser image.

## Design Dialog {#design-dialog}

設計對話方塊可讓範本作者定義使用此元件時，內容作者所擁有的摘要選項。

### Teaser Tab {#teaser-tab}

![](assets/screen_shot_2018-07-03at105958.png)

* **呼叫動作**
   * **停用呼叫動作** 隱藏內容作者 **的呼叫動作動作** 選項
* **元素**
   * **隱藏標題**
      * Hides the **Title** option for content authors
      * When selected the **Title Type** is hidden
   * **隱藏說明** 隱藏內容作者 **的描述** 選項
* **標題類型** 定義摘要標題要使用的H標記。
* **連結**
   * **未連結影像** 時，選取的摘要影像未連結
   * **不連結標題** 時，選取的摘要標題不會連結

### Styles Tab {#styles-tab}

The Teaser Component supports the AEM [Style System](authoring.md#component-styling).
