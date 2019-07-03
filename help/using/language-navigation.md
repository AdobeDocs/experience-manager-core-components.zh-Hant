---
title: 語言導覽元件
seo-title: 語言導覽元件
description: 'null'
seo-description: 語言導覽元件提供網站的語言/國家導覽，讓訪客能夠在不同地區中導覽至相同的頁面。
uuid: ce73458-1cdf-4bc2-b90 f-9c5 a62 fe1 ca0
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 8f232eb0-65d5-4075-8668-75f1366882c8
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


# Language Navigation Component{#language-navigation-component}

語言導覽元件提供網站的語言/國家導覽，讓訪客能夠在不同地區中導覽至相同的頁面。

## 使用狀況 {#usage}

通常不同地區的網站提供多種語言版本。語言導覽元件可讓訪客以不同語言/地區設定檢視相同頁面。

[編輯對話方塊](#edit-dialog) 可讓您定義全域網站導覽根目錄，以及導覽應前往的結構深度。Using the [design dialog](#design-dialog), the template author can set the default values for the same options.

## Version and Compatibility {#version-and-compatibility}

目前版本的語言導覽元件是v1，它是在2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |


For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Language Navigation Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/language-navigation/language-structure/us/en/language-navigation.html).

## Technical Details {#technical-details}

The latest technical documentation about the Language Navigation Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓您定義全域網站導覽根目錄，以及導覽應前往的結構深度。

![](assets/screen_shot_2018-01-12at133353.png)

* **導覽根目錄** 定義導覽結構的根頁面。
   * Use the **Open Selection Dialog** button to easily navigate the content structure and select the root.
* **語言結構深度** 深度：相對於導覽根目錄的全域語言結構深度。

## Design Dialog {#design-dialog}

範本作者可使用設計對話方塊，為編輯對話方塊中可用的相同選項設定預設值。

### Properties Tab {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **導覽根目錄的「導覽根目錄** 預設值」當內容作者將「語言切換器元件」置於內容頁面時
* **語言結構深度**：內容作者將語言切換元件置於內容頁面上時，語言結構深度的預設值

### Styles Tab {#styles-tab}

The Language Navigation Component supports the AEM [Style System](authoring.md#component-styling).