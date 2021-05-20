---
title: 列出元件
description: 核心元件清單元件可輕鬆建立動態及靜態清單。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 662ab508-0253-4d28-b95c-8c4cde8173bd
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 4%

---

# 列出元件{#list-component}

核心元件清單元件可輕鬆建立動態及靜態清單。

## 使用狀況 {#usage}

清單元件可用於建立子頁的動態清單或任意定義項的靜態清單。 可用清單類型和格式選項可由範本作者在[設計對話方塊](#design-dialog)中定義。 內容編輯器可以從可用的清單類型中選擇，以及如何在[edit對話框](#edit-dialog)中格式化清單元素。

## 版本和相容性{#version-and-compatibility}

目前的清單元件版本為v2，已於2018年1月隨核心元件2.0.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](v1/list-v1.md) | 相容 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗清單元件以及查看其設定選項的範例以及HTML和JSON輸出，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_list)。

### 技術詳細資訊{#technical-details}

如需清單元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_list_v2)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者設定清單和清單項目。

### 清單設定頁簽{#list-settings-tab}

清單可以以不同的方式建置。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-options)
* [標記](#tags)

無論清單是如何建立的，都有可始終配置的[排序和ID選項](#sort-options)。

![清單元件的編輯對話框](/help/assets/list-edit.png)

視內容作者選擇如何建立清單而定，其他設定選項將會變更。

#### 子頁面 {#child-pages}

清單可由目前頁面或其他頁面的子頁面建立。

![子頁面選項](/help/assets/list-edit-child-pages.png)

* **父頁面**
   * 應建立其子頁清單的頁
   * 留空即可使用目前頁面

* **子級深**
度應使用層次中向下多少個級別

#### 固定清單{#fixed-list}

可使用固定的項目清單來建立清單。

![修正清單選項](/help/assets/list-edit-fixed.png)

點選或按一下&#x200B;**Add**&#x200B;按鈕，將新項目插入清單。

* 在清單中輸入項的文本，或使用&#x200B;**選擇對話框**&#x200B;從AEM中選擇項。
* 使用拖動控點重新排列清單中的項目。
* 使用垃圾桶圖示來刪除清單中的項目。

#### 搜尋 {#search-options}

可使用搜尋AEM內容的結果來建立清單。

![搜尋清單選項](/help/assets/list-edit-search.png)

* **搜**
索查詢將運行全文搜索以生成清單元素的字串
* **在中**
搜索應該運行搜索的位置
   * 使用&#x200B;**選擇對話框**&#x200B;選擇AEM中的位置
   * 留空時，請使用目前頁面

#### 標記 {#tags}

清單可以使用在特定位置下符合特定標籤的頁面來建立。

![標籤清單選項](/help/assets/list-edit-tags.png)

* **上層**
頁面標籤相符的開始位置
   * 使用&#x200B;**選擇對話框**&#x200B;選擇AEM中的位置
   * 留空時，請使用目前頁面
* ****
標籤應符合的標籤
   * 使用&#x200B;**Browse**&#x200B;對話方塊來選取標籤
* ****
符合定義哪些符合類型應該允許將頁面包含在清單中
   * **任何標記**
   * **所有標記**

#### 排序選項{#sort-options}

無論您選擇以何種方式建立清單，都有可一律定義的特定排序選項。

![排序選項](/help/assets/list-edit-sort-options.png)

* **依**
順序元素的順序
   * **標題**
   * **上次修改日期**
* **排**
序順序應排序項的順序
   * **升序**
   * **降序**
* **最大**
項目數清單中顯示的項目數上限。
   * 保留為空以傳回所有項目。
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

### 項目設定頁簽{#item-settings-tab}

使用「項目設定」頁簽，可以配置清單元素的格式。

![項目設定](/help/assets/list-edit-items.png)

* **連結**
項目連結項目至對應的頁面
* **顯示**
說明顯示連結項目的說明
* **顯示**
連結項目的DateShow修改日期

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義內容作者應允許的清單類型以及可用的項目設定。

### 清單設定 {#list-settings}

在&#x200B;**清單設定**&#x200B;標籤中，可定義日期格式，以及內容作者可在元件中使用哪些類型的清單。

![清單元件的設計對話框清單設定](/help/assets/list-design-list-settings.png)

* **用**
於顯示上次修改日期的Date Format
* **禁用**
子項禁用元件中的子項清單類型
* **停**
用靜態禁用元件中的靜態清單類型
* **禁用**
搜索禁用元件中的搜索清單類型
* **停用**
標籤禁用元件中的標籤清單類型

### 項目設定 {#item-settings}

在&#x200B;**項目設定**&#x200B;標籤中，可以定義內容作者應在元件中可用的個別清單元素的格式選項。

![列出元件的設計對話框項設定](/help/assets/list-design-item-settings.png)

* **連結**
項目在編輯對話方塊中啟用連結 [項目選項](#edit-dialog)
* **顯示**
說明在編輯對話方塊中啟用顯示說 [明選項](#edit-dialog)
* **在編**
輯對話方塊中顯示日期啟用顯 [示日期選項](#edit-dialog)

### 樣式標籤{#styles-tab}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層{#data-layer}

清單元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
