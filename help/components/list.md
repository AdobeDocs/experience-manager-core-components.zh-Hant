---
title: 列出元件
description: 核心元件清單元件可讓您輕鬆建立動態和靜態清單。
role: Architect, Developer, Admin, User
exl-id: 662ab508-0253-4d28-b95c-8c4cde8173bd
source-git-commit: af908d77b30b7642b553f38c217136cfd5603108
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 3%

---

# 列出元件{#list-component}

核心元件清單元件可讓您輕鬆建立動態和靜態清單。

## 使用狀況 {#usage}

例如，清單元件可用於建立子頁面的動態清單或任意定義專案的靜態清單。 可用的清單型別和格式設定選項可由範本作者在 [設計對話方塊](#design-dialog). 內容編輯器可以從可用的清單型別以及如何格式化中的清單元素 [編輯對話方塊](#edit-dialog).

## 版本和相容性 {#version-and-compatibility}

清單元件的目前版本是v4，此版本隨2023年2月的核心元件2.22.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v4 | - | 相容 | 相容 |
| [v3](/help/components/v3/list.md) | - | 相容 | 相容 |
| [v2](/help/components/v2/list.md) | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/list-v1.md) | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 清單中的重新導向 {#redirects}

當頁面具有重新導向目標時(無論它指向的是外部URL還是另一個AEM頁面)，則包含指向該點的連結的清單將直接指向重新導向目標的URL。

### 範例 {#redirect-example}

* 建立重新導向至頁面B的頁面A。
* 建立重新導向到的頁面C `https://aemcomponents.dev`
* 在頁面D上，插入包含頁面A和C的清單元件
* 接著產生的個別連結會直接指向頁面B和 `https://aemcomponents.dev`

## 範例元件輸出 {#sample-component-output}

若要體驗清單元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_list).

### 技術細節 {#technical-details}

有關清單元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_list_v3).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者設定清單和清單專案。

### 清單設定標籤 {#list-settings-tab}

清單可透過不同方式建立。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-options)
* [標記](#tags)

無論如何建立清單，都有 [排序和ID選項](#sort-options) 隨時可以設定。

![清單元件的編輯對話方塊](/help/assets/list-edit.png)

視內容作者選擇建立清單的方式而定，其他設定選項將會變更。

#### 子頁面 {#child-pages}

清單可由目前頁面的子頁面或其他頁面建立。

![子頁面選項](/help/assets/list-edit-child-pages.png)

* **父頁面**
   * 其子頁面應產生清單的頁面
   * 留空將使用目前頁面

* **子項深度**
應該使用階層中向下的層級數

#### 固定清單 {#fixed-list}

清單可使用固定專案清單建立。

![固定清單選項](/help/assets/list-edit-fixed.png)

點選或按一下 **新增** 按鈕以將新專案插入至清單。

* 在 **連結** 欄位輸入
   * 完整URL
   * 現有AEM內容的相對URL
      * 您可以使用 **選擇對話方塊** 以從AEM選擇料號。
* 在 **文字** 欄位，輸入清單中連結顯示的文字。
* 如果連結應在新的瀏覽器分頁中開啟，請核取核取方塊

為清單建立多個專案後，您可以排列清單。

* 使用拖曳操作框來重新排列清單中的專案。
* 使用垃圾桶圖示可刪除清單中的專案。

#### 搜尋 {#search-options}

清單可使用搜尋AEM內容的結果來建立。

![搜尋清單選項](/help/assets/list-edit-search.png)

* **搜尋查詢**
執行全文檢索搜尋以產生清單元素的字串
* **搜尋範圍**
應在何處執行搜尋
   * 使用 **選擇對話方塊** 以在AEM中選擇位置
   * 若保留為空白，則使用目前頁面

#### 標記 {#tags}

清單可使用在特定位置下符合特定標籤的頁面來建立。

![標籤清單選項](/help/assets/list-edit-tags.png)

* **上層頁面**
標籤比對應該從哪裡開始
   * 使用 **選擇對話方塊** 以在AEM中選擇位置
   * 若保留為空白，則使用目前頁面
* **標籤**
應該比對哪些標籤
   * 使用 **瀏覽** 對話方塊以選取標籤
* **符合**
定義應使用何種相符專案來限定要包含在清單中的頁面
   * **任何標記**
   * **所有標記**

#### 排序選項 {#sort-options}

無論您選擇如何建立清單，都可隨時定義特定的排序選項。

![排序選項](/help/assets/list-edit-sort-options.png)

* **排序方式**
元素應如何排序
   * **標題**
   * **上次修改日期**
* **排序順序**
專案應排序的順序
   * **升序**
   * **降序**
* **專案數量上限**
清單中顯示的最大專案數。
   * 留空將傳回所有專案。
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 專案設定標籤 {#item-settings-tab}

使用「專案設定」標籤，可以設定清單元素的格式設定。

![專案設定](/help/assets/list-edit-item-settings.png)

* **連結專案**  — 將專案連結至對應的頁面
* **顯示說明**  — 顯示連結專案的說明
* **顯示日期**  — 顯示連結專案的修改日期
* **顯示為Teaser**  — 選取後，專案會顯示為Teaser

### 樣式索引標籤 {#styles-tab-edit}

清單元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling).

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的效果相同。

必須在以下位置為此元件設定樣式： [設計對話方塊](#design-dialog) 讓下拉式功能表可供使用。

![清單元件「編輯」對話方塊的「樣式」索引標籤](/help/assets/list-edit-styles.png)

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義允許內容作者使用的清單型別以及可用的專案設定。

### 清單設定 {#list-settings}

於 **清單設定** 索引標籤中，可以定義日期格式以及在元件中什麼型別的清單可供內容作者使用。

![清單元件的設計對話方塊清單設定](/help/assets/list-design-list-settings.png)

* **日期格式**
用於顯示上次修改日期的格式
* **停用子項**
停用元件中的子清單型別
* **停用靜態**
停用元件中的靜態清單型別
* **停用搜尋**
停用元件中的搜尋清單型別
* **停用標籤**
停用元件中的標籤清單型別

### 項目設定 {#item-settings}

於 **專案設定** 索引標籤上，可以定義在元件中可供內容作者使用的個別清單元素的格式選項。

![清單元件的設計對話方塊專案設定](/help/assets/list-design-item-settings.png)

* **連結專案**
在中啟用連結專案選項 [編輯對話方塊](#edit-dialog)
* **顯示說明**
在中啟用顯示說明選項 [編輯對話方塊](#edit-dialog)
* **顯示日期**
在中啟用顯示日期選項 [編輯對話方塊](#edit-dialog)

### 樣式索引標籤 {#styles-tab}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe使用者端資料層 {#data-layer}

清單元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
