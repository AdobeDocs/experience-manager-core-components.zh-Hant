---
title: 標題元件
seo-title: 標題元件
description: 'null'
seo-description: 核心元件標題元件是一個區段標題元件，具備就地編輯功能。
uuid: cf190861-e5 cd-42b8-9193-842b8 df8 c5 c6
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 243efc75-fcf9-427d-9303-9642b0602991
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# 標題元件{#title-component}

核心元件標題元件是一個區段標題元件，具備就地編輯功能。

## 使用狀況 {#usage}

「標題元件」旨在做為內容區段的標題或標題。The available heading levels can be defined by the template author in the [design dialog](#design-dialog). The content editor can select from available headings levels in the [edit dialog](#edit-dialog). 為方便您加入，也提供簡單的標題文字就地編輯功能。

## Version and Compatibility {#version-and-compatibility}

目前版本的Title Component is v2，它是在2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|---|---|---|---|
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](title-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Title Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/title.html).

### Technical Details {#technical-details}

The latest technical documentation about the Title Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者定義標題文字，並選取標題層級。

* **標題** -如果將頁面標題空白，則會使用
* **類型/大小** -定義標題的標題層級
* **連結** -定義標題將會連結的內容。這可以是內容頁面、外部URL或頁面錨點的路徑。

![](assets/screenshot_2018-10-19at110055.png)

>[!CAUTION]
>
>The ability to define a link for the title is delated with the release2.2.0of the Core Components.

原地編輯器也可以用來編輯標題元件的文字。

![](assets/chlimage_1-37.png)

## Design Dialog {#design-dialog}

此設計對話方塊可讓範本作者定義內容作者建立時，標題元件將擁有的預設標題層級。

### Sizes Tab {#sizes-tab}

![](assets/screenshot_2018-10-19at110120.png)

* **適用於作者的允許類型/大小** -啓用或停用內容作者使用標題元件時將可使用的標題類型。
* **預設類型/大小**-定義當內容作者新增「標題元件」至頁面時，自動指派的標題類型。
* **停用連結**-停用標題元件中的連結支援，以避免內容作者從標題連結。

>[!CAUTION]
>
>The ability to define a link for the title is delated with the release2.2.0of the Core Components.

### Styles Tab {#styles-tab}

The Title Component supports the AEM [Style System](authoring.md#component-styling).