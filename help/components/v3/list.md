---
title: 清單元件(v3)
description: 核心元件清單元件(v3)可輕鬆建立動態及靜態清單。
role: Architect, Developer, Admin, User
source-git-commit: af908d77b30b7642b553f38c217136cfd5603108
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 3%

---


# 清單元件(v3) {#list-component}

核心元件清單元件(v3)可輕鬆建立動態及靜態清單。

## 使用狀況 {#usage}

清單元件(v3)可用來建立子頁面的動態清單或任意定義項目的靜態清單。 可用清單類型和格式選項可由範本作者在 [設計對話](#design-dialog). 內容編輯器可從可用的清單類型中選取，以及如何將清單元素的格式設為 [編輯對話框](#edit-dialog).

## 版本與相容性 {#version-and-compatibility}

本檔案說明2022年2月2.18.0版核心元件導入的清單元件v3。

>[!CAUTION]
>
>本文檔介紹清單元件的v3。
>
>如需目前版本清單元件的詳細資訊，請參閱 [清單元件](/help/components/list.md) 檔案。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| [v4](/help/components/list.md) | - | 相容 | 相容 |
| v3 | - | 相容 | 相容 |
| [v2](/help/components/v2/list.md) | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/list-v1.md) | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱本檔案 [核心元件版本](/help/versions.md).

## 清單中的重新導向 {#redirects}

當頁面具有重定向目標時(無論它指向的是外部URL還是指向另一個AEM頁面)，則包含指向該指向重定向目標的URL的連結的清單。

### 範例 {#redirect-example}

* 建立重新導向至頁面B的頁面A。
* 建立可重新導向至 `https://aemcomponents.dev`
* 在頁面D上，插入包含頁面A和C的清單元件
* 接著，產生的個別連結會直接指向頁面B和 `https://aemcomponents.dev`

## 範例元件輸出 {#sample-component-output}

若要體驗清單元件以及查看其設定選項的範例，以及HTML和JSON輸出，請造訪 [元件庫](https://adobe.com/go/aem_cmp_library_list).

### 技術詳細資訊 {#technical-details}

清單元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_list_v3).

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者設定清單和清單項目。

### 清單設定索引標籤 {#list-settings-tab}

清單可以以不同的方式建置。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-options)
* [標記](#tags)

無論清單的建立方式為何，都有 [排序和ID選項](#sort-options) 一律可設定。

![清單元件的編輯對話框](/help/assets/v3/list-edit.png)

視內容作者選擇如何建立清單而定，其他設定選項將會變更。

#### 子頁面 {#child-pages}

清單可由目前頁面或其他頁面的子頁面建立。

![子頁面選項](/help/assets/v3/list-edit-child-pages.png)

* **父頁面**
   * 應建立其子頁清單的頁
   * 留空即可使用目前頁面

* **子深度**
應使用階層中的下層數

#### 固定清單 {#fixed-list}

可使用固定的項目清單來建立清單。

![修正清單選項](/help/assets/v3/list-edit-fixed.png)

點選或按一下 **新增** 按鈕將新項插入清單。

* 在清單中輸入項的文本，或使用 **選擇對話框** 從AEM中選擇項目。
* 使用拖動控點重新排列清單中的項目。
* 使用垃圾桶圖示來刪除清單中的項目。

#### 搜尋 {#search-options}

可使用搜尋AEM內容的結果來建立清單。

![搜尋清單選項](/help/assets/v3/list-edit-search.png)

* **搜尋查詢**
將運行全文搜索以生成清單元素的字串
* **在中搜尋**
應執行搜尋的位置
   * 使用 **選擇對話框** 在AEM中選擇位置
   * 留空時，請使用目前頁面

#### 標記 {#tags}

清單可以使用在特定位置下符合特定標籤的頁面來建立。

![標籤清單選項](/help/assets/v3/list-edit-tags.png)

* **上層頁面**
標籤比對的開始位置
   * 使用 **選擇對話框** 在AEM中選擇位置
   * 留空時，請使用目前頁面
* **標籤**
哪些標籤應符合
   * 使用 **瀏覽** 對話框，選擇標籤
* **符合**
定義哪些符合類型應會讓頁面有資格納入清單中
   * **任何標記**
   * **所有標記**

#### 排序選項 {#sort-options}

無論您選擇以何種方式建立清單，都有可一律定義的特定排序選項。

![排序選項](/help/assets/v3/list-edit-sort-options.png)

* **訂購依據**
元素的順序
   * **標題**
   * **上次修改日期**
* **排序順序**
物料的排序順序
   * **升序**
   * **降序**
* **項目數上限**
清單中顯示的項目數上限。
   * 保留為空以傳回所有項目。
* **ID**  — 此選項可控制HTML中和 [資料層](/help/developing/data-layer/overview.md).
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

### 項目設定標籤 {#item-settings-tab}

使用「項目設定」頁簽，可以配置清單元素的格式。

![項目設定](/help/assets/v3/list-edit-items.png)

* **連結項目**  — 將項目連結至對應的頁面
* **顯示說明**  — 顯示連結項目的說明
* **顯示日期**  — 顯示連結項目的修改日期
* **顯示為預告**  — 勾選後，項目會顯示為預告

### 樣式標籤 {#styles-tab-edit}

清單元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling).

使用下拉式清單選取您要套用至元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須針對此元件在 [設計對話](#design-dialog) 讓下拉式功能表可供使用。

![清單元件的編輯對話框的樣式頁簽](/help/assets/v3/list-edit-styles.png)

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者應允許的清單類型以及可用的項目設定。

### 清單設定 {#list-settings}

在 **清單設定** 索引標籤，可定義日期格式，以及內容作者可在元件中使用的清單類型。

![清單元件的設計對話框清單設定](/help/assets/v3/list-design-list-settings.png)

* **日期格式**
用於顯示上次修改日期的格式
* **禁用子項**
在元件中禁用子清單類型
* **停用靜態**
停用元件中的靜態清單類型
* **禁用搜索**
禁用元件中的搜索清單類型
* **停用標籤**
在元件中禁用標籤清單類型

### 項目設定 {#item-settings}

在 **項目設定** 索引標籤，則可定義內容作者元件中應提供的個別清單元素的格式選項。

![列出元件的設計對話框項設定](/help/assets/v3/list-design-item-settings.png)

* **連結項目**
在 [編輯對話框](#edit-dialog)
* **顯示說明**
在 [編輯對話框](#edit-dialog)
* **顯示日期**
在 [編輯對話框](#edit-dialog)

### 樣式標籤 {#styles-tab}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe用戶端資料層 {#data-layer}

清單元件支援 [Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
