---
title: 列出元件
seo-title: 列出元件
description: 'null'
seo-description: 核心元件清單元件可讓您輕鬆建立動態和靜態清單。
uuid: 50a572e8-b444-4f7 d-82bc-5a93 eb4 be95
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 89053323-621-46ed-896a-31a-31c55282e
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


# 列出元件{#list-component}

核心元件清單元件可讓您輕鬆建立動態和靜態清單。

## 使用狀況 {#usage}

清單元件可用來建立子頁面的動態清單或任意定義項目的靜態清單。The type of lists available and formatting options can be defined by the template author in the [design dialog](#design-dialog). The content editor can select from available list types and how to format the list elements in the [edit dialog](#edit-dialog).

## Version and Compatibility {#version-and-compatibility}

目前版本的清單元件是v2，它是在2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](list-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the List Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/list.html).

### Technical Details {#technical-details}

The latest technical documentation about the List Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者設定清單和清單項目。

### List Settings Tab {#list-settings-tab}

清單可以以不同的方式建立。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-options)
* [標記](#tags)

Regardless of how the list is built, there are [Sort Options](#sort-options) that can always be configured.

![](assets/chlimage_1-38.png)

視內容作者選擇要如何建立清單而定，其他設定選項將會變更。

#### 子頁面 {#child-pages}

可建立目前頁面或其他頁面的子頁面。

![](assets/chlimage_1-39.png)

* **父頁面**
   * 子系頁面應製作清單的頁面
   * 保留空白以使用目前頁面

* **子深度：** 階層中應使用多少層級

#### Fixed List {#fixed-list}

您可以使用固定清單來建立清單。

![](assets/chlimage_1-40.png)

Tap or click the **Add** button to inset a new item to the list.

* Enter text for the item in the list or use the **Selection Dialog** to choose an item from AEM.
* 使用拖曳控制點重新排列清單中的項目。
* 使用垃圾筒圖示可刪除清單中的項目。

#### 搜尋 {#search-options}

您可以使用搜尋AEM內容的搜尋結果來建立清單。

![](assets/chlimage_1-41.png)

* **搜尋查詢** 將執行全文搜尋的字串，產生清單元素
* **搜尋應執行的搜尋** 位置
   * Use the **Selection Dialog** to choose the location in AEM
   * 如果留空，請使用目前頁面

#### 標記 {#tags}

您可以使用符合特定位置標記的頁面來建立清單。

![](assets/chlimage_1-42.png)

* **上層頁面** 應啓動的標籤符合
   * Use the **Selection Dialog** to choose the location in AEM
   * 如果留空，請使用目前頁面
* **標記** 應符合的標籤
   * Use the **Browse** dialog to select the tags
* **符合** 定義哪種符合應符合清單中要包含的頁面
   * **任何標記**
   * **所有標記**

#### Sort Options {#sort-options}

無論您選擇如何建立清單，都有一些可隨時定義的排序選項。

![](assets/chlimage_1-43.png)

* **訂購如何** 訂購元素
   * **標題**
   * **上次修改日期**
* **排序順序：** 應訂購項目的順序
   * **升序**
   * **降序**
* **最大項目**：清單中顯示的項目上限。
   * 保留空白以傳回所有項目。

### Item Settings Tab {#item-settings-tab}

使用「項目設定」標籤，可以設定清單元素的格式。

![](assets/chlimage_1-44.png)

* **連結項目** 連結項目至對應頁面
* **顯示說明** 顯示連結項目的說明
* **顯示連結項目的日期** 顯示修改日期

## Design Dialog {#design-dialog}

此設計對話方塊可讓範本作者定義應允許的清單類型，以及可用項目設定。

### 清單設定 {#list-settings}

On the **List Settings** tab, the date format can be defined as well as what type of lists should be available in the component to the content authors.

![](assets/chlimage_1-45.png)

* **用於顯示上次修改日期之顯示的日期格式** 格式
* **停用子項** 停用元件中的子清單類型
* **停用靜態** 停用元件中的靜態清單類型
* **停用搜尋** 停用元件中的搜尋清單類型
* **停用標記** 停用元件中的標籤清單類型

### 項目設定 {#item-settings}

On the **Item Settings** tab, the formatting options for the individual list elements that should be available in the component for the content authors can be defined.

![](assets/chlimage_1-46.png)

* **編輯對話方塊中的連結項目** 啓用連結 [項目選項](#edit-dialog)
* **在編輯對話方塊中顯示說明**[說明選項](#edit-dialog)
* **在編輯對話方塊中顯示「** 啓用顯示 [日期」選項](#edit-dialog)

### Styles Tab {#styles-tab}

The Image Component supports the AEM [Style System](authoring.md#component-styling).