---
title: 清單元件(v2)
description: 核心元件清單元件允許輕鬆建立動態清單和靜態清單。
role: Architect, Developer, Admin, User
exl-id: fa34be64-b345-45cd-baf3-571973414852
source-git-commit: 241c86240377858a73f4a022368d428da9c11100
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 2%

---

# 清單元件(v2) {#list-component}

核心元件清單元件允許輕鬆建立動態清單和靜態清單。

## 使用狀況 {#usage}

「清單元件」可用於建立子頁的動態清單或任意定義項的靜態清單。 可用清單類型和格式選項可由模板作者在 [設計對話框](#design-dialog)。 內容編輯器可以從可用清單類型中選擇以及如何格式化清單中的清單元素 [編輯對話框](#edit-dialog)。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了2018年1月隨核心元件2.0.0版而推出的清單元件v1。

>[!CAUTION]
>
>本文檔介紹了清單元件的v2。
>
>有關清單元件當前版本的詳細資訊，請參閱 [清單元件](/help/components/list.md) 的子菜單。

## 清單重定向 {#redirects}

當頁面具有重定向目標(無論它指向外部URL還是指向另一頁AEM)時，則包含指向該指向重定向目標的URL的連結的清單。

### 範例 {#redirect-example}

* 建立重定向到B頁的A頁。
* 建立重定向到 `https://aemcomponents.dev`
* 在頁D上，插入包含頁A和頁C的清單元件
* 然後生成的各個連結直接指向B頁和 `https://aemcomponents.dev`

## 元件輸出示例 {#sample-component-output}

要體驗清單元件，並查看其配置選項示例以及HTML和JSON輸出，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_list)。

### 技術詳細資訊 {#technical-details}

有關清單元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_list_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者配置清單和清單項。

### 清單設定頁籤 {#list-settings-tab}

清單可以用不同的方式構建。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-options)
* [標記](#tags)

無論清單是如何構建的， [排序和ID選項](#sort-options) 可以始終進行配置。

![列出元件的編輯對話框](/help/assets/v2/list-edit.png)

根據內容作者選擇構建清單的方式，其他配置選項將發生更改。

#### 子頁面 {#child-pages}

該清單可由當前頁面或其他頁面的子頁面生成。

![子頁面選項](/help/assets/v2/list-edit-child-pages.png)

* **父頁面**
   * 其子頁應生成清單的頁
   * 留空以使用當前頁

* **子深度**
應使用層次結構中的下層層數

#### 固定清單 {#fixed-list}

可以使用固定的項目清單生成清單。

![固定清單選項](/help/assets/v2/list-edit-fixed-list.png)

點擊或按一下 **添加** 按鈕

* 輸入清單中項的文本或使用 **選擇對話框** 的子例AEM行。
* 使用拖動控制滑塊重新排列清單中的項目。
* 使用垃圾桶表徵圖刪除清單中的項目。

#### 搜尋 {#search-options}

可以使用內容搜索的結果來構建列AEM表。

![搜索清單選項](/help/assets/v2/list-edit-search.png)

* **搜索查詢**
將運行全文搜索以生成清單元素的字串
* **搜索範圍**
應在何處運行搜索
   * 使用 **選擇對話框** 以選擇AEM
   * 如果留空，則使用當前頁

#### 標記 {#tags}

可以使用與特定位置下的某些標籤相匹配的頁面來構建清單。

![標籤清單選項](/help/assets/v2/list-edit-tags.png)

* **父頁**
標籤匹配應從何處開始
   * 使用 **選擇對話框** 以選擇AEM
   * 如果留空，則使用當前頁
* **標籤**
應匹配哪些標籤
   * 使用 **瀏覽** 對話框，以選擇標籤
* **匹配**
定義哪些類型的匹配應限定清單中要包含的頁面
   * **任何標記**
   * **所有標記**

#### 排序選項 {#sort-options}

無論您選擇如何構建清單，總是可以定義某些排序選項。

![排序選項](/help/assets/v2/list-edit-sort-options.png)

* **排序依據**
元素的排序方式
   * **標題**
   * **上次修改日期**
* **排序順序**
物料的排序順序
   * **升序**
   * **降序**
* **最大項**
清單中顯示的最大項數。
   * 留空以返回所有項目。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

### 項目設定頁籤 {#item-settings-tab}

使用「項目設定」頁籤，可以配置清單元素的格式。

![項設定](/help/assets/v2/list-edit-item-settings.png)

* **連結項**
將項連結到相應頁
* **顯示說明**
顯示連結項的說明
* **顯示日期**
顯示連結項的修改日期

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者應允許的清單類型以及可用的項目設定。

### 清單設定 {#list-settings}

在 **清單設定** 頁籤中，可以定義日期格式以及元件中的內容作者應使用的清單類型。

![列出元件的設計對話框清單設定](/help/assets/v2/list-design-list-settings.png)

* **日期格式**
用於顯示上次修改日期的格式
* **禁用子項**
禁用元件中的子清單類型
* **禁用靜態**
禁用元件中的靜態清單類型
* **禁用搜索**
禁用元件中的搜索清單類型
* **禁用標籤**
禁用元件中的標籤清單類型

### 項目設定 {#item-settings}

在 **項設定** 頁籤中，可以定義內容作者的元件中應提供的單個清單元素的格式選項。

![列出元件的設計對話框項設定](/help/assets/v2/list-design-item-settings.png)

* **連結項**
在中啟用連結項選項 [編輯對話框](#edit-dialog)
* **顯示說明**
在中啟用「顯示說明」選項 [編輯對話框](#edit-dialog)
* **顯示日期**
在中啟用「顯示日期」選項 [編輯對話框](#edit-dialog)

### 樣式頁籤 {#styles-tab}

映像元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

清單元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
