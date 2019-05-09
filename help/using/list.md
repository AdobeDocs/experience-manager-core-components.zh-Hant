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
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 列出元件{#list-component}

核心元件清單元件可讓您輕鬆建立動態和靜態清單。

## 使用狀況 {#usage}

清單元件可用來建立子頁面的動態清單或任意定義項目的靜態清單。可用清單類型和格式選項可由 [設計對話方塊中的範本作者定義](#design-dialog)。內容編輯器可以從可用的清單類型中選取，以及如何在 [編輯對話方塊中格式化清單元素](#edit-dialog)。

## 版本與相容性 {#version-and-compatibility}

目前版本的清單元件是v2，它是在2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](list-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/screen_shot_2018-01-12at105924.png)

### 元件庫

若要體驗清單元件，以及查看其組態選項以及HTML和JSON輸出的範例，請造訪 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library/list.html)。

### 技術細節 {#technical-details}

有關List Component [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者設定清單和清單項目。

### 清單設定標籤 {#list-settings-tab}

清單可以以不同的方式建立。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-options)
* [標記](#tags)

不論清單是如何建立的，都有 [可隨時設定的「排序選項](#sort-options) 」。

![](assets/chlimage_1-38.png)

視內容作者選擇要如何建立清單而定，其他設定選項將會變更。

#### 子頁面 {#child-pages}

可建立目前頁面或其他頁面的子頁面。

![](assets/chlimage_1-39.png)

* **父頁面**
   * 子系頁面應製作清單的頁面
   * 保留空白以使用目前頁面

* **子深度：**階層中應使用多少層級

#### 固定清單 {#fixed-list}

您可以使用固定清單來建立清單。

![](assets/chlimage_1-40.png)

點選或按一下「 **新增** 」按鈕，將新項目嵌入清單中。

* 輸入清單中項目的文字，或使用 **「選擇對話方塊** 」從AEM選擇項目。
* 使用拖曳控制點重新排列清單中的項目。
* 使用垃圾筒圖示可刪除清單中的項目。

#### 搜尋 {#search-options}

您可以使用搜尋AEM內容的搜尋結果來建立清單。

![](assets/chlimage_1-41.png)

* **搜尋查詢**將執行全文搜尋的字串，產生清單元素
* **搜尋應執行的搜尋**位置
   * 使用 **「選取對話方塊** 」選擇AEM中的位置
   * 如果留空，請使用目前頁面

#### 標記 {#tags}

您可以使用符合特定位置標記的頁面來建立清單。

![](assets/chlimage_1-42.png)

* **上層頁面**應啓動的標籤符合
   * 使用 **「選取對話方塊** 」選擇AEM中的位置
   * 如果留空，請使用目前頁面
* **標記**應符合的標籤
   * 使用 **「瀏覽** 」對話方塊選取標記
* **符合**定義哪種符合應符合清單中要包含的頁面
   * **任何標記**
   * **所有標記**

#### 排序選項 {#sort-options}

無論您選擇如何建立清單，都有一些可隨時定義的排序選項。

![](assets/chlimage_1-43.png)

* **訂購如何**訂購元素
   * **標題**
   * **上次修改日期**
* **排序順序：**應訂購項目的順序
   * **升序**
   * **降序**
* **最大項目**：清單中顯示的項目上限。
   * 保留空白以傳回所有項目。

### 項目設定標籤 {#item-settings-tab}

使用「項目設定」標籤，可以設定清單元素的格式。

![](assets/chlimage_1-44.png)

* **連結項目**連結項目至對應頁面
* **顯示說明**顯示連結項目的說明
* **顯示連結項目的日期**顯示修改日期

## 設計對話方塊 {#design-dialog}

此設計對話方塊可讓範本作者定義應允許的清單類型，以及可用項目設定。

### 清單設定 {#list-settings}

在 **「清單設定** 」標籤上，可以定義日期格式，以及元件中應該提供何種清單類型給內容作者。

![](assets/chlimage_1-45.png)

* **用於顯示上次修改日期之顯示的日期格式**格式
* **停用子項**停用元件中的子清單類型
* **停用靜態**停用元件中的靜態清單類型
* **停用搜尋**停用元件中的搜尋清單類型
* **停用標記**停用元件中的標籤清單類型

### 項目設定 {#item-settings}

在 **「項目設定** 」標籤上，可以定義內容作者的元件中應該提供的個別清單元素格式選項。

![](assets/chlimage_1-46.png)

* **編輯對話方塊中的連結項目**啓用連結 [項目選項](#edit-dialog)
* **在編輯對話方塊中顯示說明**[說明選項](#edit-dialog)
* **在編輯對話方塊中顯示「**啓用顯示 [日期」選項](#edit-dialog)

### 樣式標籤 {#styles-tab}

Image Component支援AEM [Style System](authoring.md#component-styling)。