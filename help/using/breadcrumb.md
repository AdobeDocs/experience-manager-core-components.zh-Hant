---
title: 階層連結元件
seo-title: 階層連結元件
description: 'null'
seo-description: 核心元件階層連結元件是一個導覽元件，可根據頁面的內容階層中的位置建立連結的導覽路徑標示。
uuid: 13e858d5-24ad-4144-adc4-0fa1 ffd257 c1
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: dd237df-08b8-4deb-9881-66a1f0d65ef3
modalsize: 426x240
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Breadcrumb Component{#breadcrumb-component}

核心元件階層連結元件是一個導覽元件，可根據頁面的內容階層中的位置建立連結的導覽路徑標示。

## 使用狀況 {#usage}

階層連結元件會顯示網站階層內目前頁面的位置，讓頁面訪客可從其目前位置導覽頁面階層。這通常會與頁首或頁尾整合。

Available options, such as the default navigation level and the ability to show the current page or hidden pages, can be defined by the template author in the [design dialog](#design-dialog). The content editor can then choose if hidden pages should be shown or not and the actual navigation level for the component in the [edit dialog](#edit-dialog).

## Version and Compatibility {#version-and-compatibility}

The current version of the Breadcrumb Component is v2，that which was be intenducated with the release2.0.0of the Core Components in18，and is described in this document.

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](breadcrumb-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Breadcrumb Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/breadcrumb/hidden/level-1/level-2/breadcrumb.html).

>[!NOTE]
>
>As of Core Components release 2.1.0, the Breadcrumb Component supports [schema.org microdata](https://schema.org/BreadcrumbList).

## Technical Details {#technical-details}

The latest technical documentation about the Breadcrumb Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者抑制網站導覽路徑標示中隱藏和作用中頁面，以及應顯示階層中的深度。

![](assets/screen_shot_2018-01-12at124250.png)

* **導覽開始層級** -階層中的階層連結元件應該開始向下移至目前頁面。例如在我們的零售業：

   * 0 starts at `/content`

   * 1 starts at `/content/we-retail`
   * 2 starts at `/content/we-retail/<country>`

* **顯示隱藏導覽項目** -顯示標示為隱藏在導覽路徑標示中的頁面(依預設不會顯示)
* **隱藏目前頁面**-抑制目前頁面中的目前頁面(依預設會顯示)

## Design Dialog {#design-dialog}

The design dialog allows the template author to define what the default value are for the options tocre抑制hideo and active page in the breadcrumbs and should should should shown.

### Main Tab {#main-tab}

![](assets/screen_shot_2018-01-12at124437.png)

* **導覽開始層級** -定義階層中階層連結元件在新增至頁面時應該開始至目前頁面的預設值。
* **顯示隱藏的導覽項目** -在頁面新增階層連結元件至頁面時，定義 **「顯示隱藏導覽項目** 」選項的預設值。

   * 它不會啓用或停用作者的選項。它只會設定預設值。

* **隱藏目前頁面**-在頁面新增階層連結元件至頁面時，定義 **「隱藏目前頁面** 」選項的預設值。

   * 它不會啓用或停用作者的選項。它只會設定預設值。

### Styles Tab {#styles-tab}

The Breadcrumb Component supports the AEM [Style System](authoring.md#component-styling).