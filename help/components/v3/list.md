---
title: 清單元件 (v3)
description: 核心元件清單元件 (v3) 可讓您輕鬆建立動態和靜態清單。
role: Architect, Developer, Admin, User
exl-id: 4aefce2e-9c22-4c6d-869e-aaa8c246b073
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '1168'
ht-degree: 100%

---


# 清單元件 (v3) {#list-component}

核心元件清單元件 (v3) 可讓您輕鬆建立動態和靜態清單。

## 用途 {#usage}

清單元件 (v3) 可用於建立下層頁面的動態清單或任意定義項目的靜態清單。範本作者可在[設計對話框](#design-dialog)中定義可用的清單類型和格式選項。內容編輯者可以在[編輯對話框](#edit-dialog)中，從可用的清單類型以及如何格式化清單元素中選取。

## 版本和相容性 {#version-and-compatibility}

本文件說明清單元件 v3，最初於 2022 年 2 月隨著核心元件 2.18.0 版發行導入。

>[!CAUTION]
>
>本文件說明清單元件 v3。
>
>如需清單元件目前版本的詳細資訊，請參閱[清單元件](/help/components/list.md)文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| [v4](/help/components/list.md) | - | 相容 | 相容 |
| v3 | - | 相容 | 相容 |
| [v2](/help/components/v2/list.md) | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/list-v1.md) | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 清單中的重新導向 {#redirects}

當頁面具有重新導向目標時 (無論它指向的是外部 URL 還是另一個 AEM 頁面)，則包含其連結的清單會直接指向重新導向目標的 URL。

### 範例 {#redirect-example}

* 建立重新導向至頁面 B 的頁面 A。
* 建立重新導向至 `https://aemcomponents.dev` 的頁面 C
* 在頁面 D 上，插入包含頁面 A 和 C 的清單元件
* 接著產生的個別連結會直接指向頁面 B 和 `https://aemcomponents.dev`

## 範例元件輸出 {#sample-component-output}

若要體驗「清單元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_list_tw)」。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_list_v3_tw)有關清單元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框可讓內容作者設定清單和清單項目。

### 清單設定索引標籤 {#list-settings-tab}

清單可透過不同方式建置。

* [下層頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-options)
* [標記](#tags)

無論清單的建置方式為何，一律可以設定[排序和 ID 選項](#sort-options)。

![清單元件的編輯對話框](/help/assets/v3/list-edit.png)

根據內容作者選擇建置清單的方式而定，其他設定選項將會變更。

#### 下層頁面 {#child-pages}

清單可由目前頁面或其他頁面的下層頁面建置。

![下層頁面選項](/help/assets/v3/list-edit-child-pages.png)

* **上層頁面**
   * 其下層頁面應該產生清單的頁面
   * 留空將使用目前頁面

* **下層深度**
要向下使用階層中的多少個層級

#### 固定清單 {#fixed-list}

清單可使用固定項目清單建立。

![固定清單選項](/help/assets/v3/list-edit-fixed.png)

點選或按一下&#x200B;**新增**&#x200B;按鈕，將新項目插入清單。

* 在清單中輸入項目的文字，或使用&#x200B;**選取對話框**&#x200B;從 AEM 中選擇項目。
* 使用拖曳控點來重新排列清單中的項目。
* 使用垃圾桶圖示可刪除清單中的項目。

#### 搜尋 {#search-options}

清單可使用搜尋 AEM 內容的結果來建立。

![搜尋清單選項](/help/assets/v3/list-edit-search.png)

* **搜尋查詢**
執行全文搜尋以產生清單元素的字串
* **搜尋位置**
應在何處執行搜尋
   * 使用&#x200B;**選取對話框**&#x200B;在 AEM 中選擇位置
   * 如果留空則使用目前頁面

#### 標記 {#tags}

清單可使用在特定位置下符合特定標記的頁面來建立。

![標記清單選項](/help/assets/v3/list-edit-tags.png)

* **上層頁面**
應開始標記比對的位置
   * 使用&#x200B;**選取對話框**&#x200B;在 AEM 中選擇位置
   * 如果留空則使用目前頁面
* **標記**
應該比對哪些標記
   * 使用&#x200B;**瀏覽**&#x200B;對話框來選取標記
* **符合**
定義用什麼相符類型來限定要包含在清單中的頁面
   * **任何標記**
   * **所有標記**

#### 排序選項 {#sort-options}

無論您選擇如何建置清單，都可隨時定義特定的排序選項。

![排序選項](/help/assets/v3/list-edit-sort-options.png)

* **排序依據**
應該如何排序元素
   * **標題**
   * **上次修改日期**
* **排序順序**
項目應排序的順序
   * **升序**
   * **降序**
* **最大項目**
在清單中顯示的最大項目數。
   * 留空將傳回所有項目。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

### 項目設定索引標籤 {#item-settings-tab}

使用項目設定索引標籤，可設定清單元素的格式。

![項目設定](/help/assets/v3/list-edit-items.png)

* **連結項目** - 連結項目至相應頁面
* **顯示說明** - 顯示連結項目的說明
* **顯示日期** - 顯示連結項目修改日期
* **顯示為 Teaser** - 勾選後，項目會顯示為 Teaser

### 樣式索引標籤 {#styles-tab-edit}

清單元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取想要套用至元件的樣式。在編輯對話框中所做的選取，與從元件工具列中選擇具有相同效果。

元件樣式必須在[設計對話框](#design-dialog)中設定，才能使用該下拉式清單。

![清單元件編輯對話框的樣式索引標籤](/help/assets/v3/list-edit-styles.png)

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義應允許內容作者使用的清單類型，以及可用的項目設定。

### 清單設定 {#list-settings}

在&#x200B;**清單設定**&#x200B;索引標籤上，可以定義日期格式以及在元件中什麼類型的清單可供內容作者使用。

![清單元件的設計對話框清單設定](/help/assets/v3/list-design-list-settings.png)

* **日期格式**
用於顯示上次修改日期的格式
* **停用下層**
停用元件中的下層清單類型
* **停用靜態**
停用元件中的靜態清單類型
* **停用搜尋**
停用元件中的搜尋清單類型
* **停用標記**
停用元件中的標記清單類型

### 項目設定 {#item-settings}

在&#x200B;**項目設定**&#x200B;索引標籤上，可以定義在元件中可供內容作者使用的個別清單元素的格式選項。

![清單元件的設計對話框項目設定](/help/assets/v3/list-design-item-settings.png)

* **連結項目**
在[編輯對話框](#edit-dialog)中啟用連結項目選項
* **顯示說明**
在[編輯對話框](#edit-dialog)中啟用顯示說明選項
* **顯示日期**
在[編輯對話框](#edit-dialog)中啟用顯示日期選項

### 樣式索引標籤 {#styles-tab}

影像元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「清單元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
