---
title: 列出元件
description: 「核心元件清單元件」可讓您輕鬆建立動態和靜態清單。
role: 架構師、開發人員、管理員、商業從業人員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 4%

---


# 列出元件{#list-component}

「核心元件清單元件」可讓您輕鬆建立動態和靜態清單。

## 使用狀況 {#usage}

「清單元件」可用來建立例如子頁面的動態清單或任意定義項目的靜態清單。 [設計對話框](#design-dialog)中的模板作者可以定義可用清單類型和格式選項。 內容編輯器可從可用的清單類型中選擇，以及如何在[edit對話框](#edit-dialog)中格式化清單元素。

## 版本和相容性{#version-and-compatibility}

目前的清單元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](v1/list-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗「清單元件」，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_list)。

### 技術詳細資訊{#technical-details}

有關List Component [的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_list_v2)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話框{#edit-dialog}

編輯對話框允許內容作者配置清單和清單項。

### 清單設定頁籤{#list-settings-tab}

清單可以以不同的方式建立。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-options)
* [標記](#tags)

無論清單的建立方式為何，都有[排序和ID選項](#sort-options)可隨時設定。

![列出元件的編輯對話框](/help/assets/list-edit.png)

視內容作者選擇如何建立清單而定，其他設定選項將會變更。

#### 子頁面 {#child-pages}

清單可由目前頁面或其他頁面的子頁面建立。

![子頁面選項](/help/assets/list-edit-child-pages.png)

* **父頁面**
   * 其子頁面應該列出的頁面
   * 保留空白以使用目前頁面

* **子級深**
度階層中應使用多少層級

#### 修正清單{#fixed-list}

清單可使用固定的項目清單來建立。

![修正清單選項](/help/assets/list-edit-fixed.png)

點選或按一下「新增&#x200B;****」按鈕，將新項目插入清單。

* 在清單中輸入項的文本，或使用&#x200B;**選擇對話框**&#x200B;從中選擇項AEM。
* 使用拖動控制滑塊重新排列清單中的項目。
* 使用垃圾桶圖示來刪除清單中的項目。

#### 搜尋 {#search-options}

您可使用內容搜尋結果來建立清AEM單。

![搜尋清單選項](/help/assets/list-edit-search.png)

* **搜**
尋查詢要執行全文搜尋以產生清單元素的字串
* **搜**
尋應在何處執行搜尋
   * 使用&#x200B;**選擇對話框**&#x200B;選擇位AEM置
   * 如果保留空白，請使用目前頁面

#### 標記 {#tags}

清單可使用與特定位置下的特定標籤相符的頁面來建立。

![標籤清單選項](/help/assets/list-edit-tags.png)

* **上層頁**
面標籤符合的起始位置
   * 使用&#x200B;**選擇對話框**&#x200B;選擇位AEM置
   * 如果保留空白，請使用目前頁面
* **標**
記哪些標籤應符合
   * 使用&#x200B;**Browse**&#x200B;對話方塊來選取標籤
* **比**
對定義哪些比對類型可限定要包含在清單中的頁面
   * **任何標記**
   * **所有標記**

#### 排序選項{#sort-options}

無論您選擇如何建立清單，都有某些排序選項可隨時定義。

![排序選項](/help/assets/list-edit-sort-options.png)

* **依**
據如何排序元素
   * **標題**
   * **上次修改日期**
* **排序**
順序項目排序順序
   * **升序**
   * **降序**
* **最大**
項目清單中顯示的項目數上限。
   * 留空以傳回所有項目。
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

### 項目設定頁籤{#item-settings-tab}

使用「項目設定」標籤，可以設定清單元素的格式。

![項目設定](/help/assets/list-edit-items.png)

* **連結**
項目連結項目至對應頁面
* **顯示**
說明顯示連結項目的說明
* **顯示**
日期顯示連結項目的修改日期

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義內容作者應允許的清單類型以及可用的項目設定。

### 清單設定 {#list-settings}

在&#x200B;**清單設定**&#x200B;標籤上，可以定義日期格式，以及內容作者應在元件中使用哪些類型的清單。

![列出元件的設計對話框清單設定](/help/assets/list-design-list-settings.png)

* **顯示**
上次修改日期的DateFormatFormat
* **禁用**
子代禁用元件中的子代清單類型
* **禁用**
靜態禁用元件中的靜態清單類型
* **禁用**
搜索禁用元件中的搜索清單類型
* **停用**
標籤停用元件中的標籤清單類型

### 項目設定 {#item-settings}

在&#x200B;**項目設定**&#x200B;標籤上，可以定義內容作者在元件中應使用的個別清單元素的格式選項。

![列出元件的設計對話框項設定](/help/assets/list-design-item-settings.png)

* **連結**
項目在編輯對話方塊中啟用連結 [項目選項](#edit-dialog)
* **顯示**
說明在編輯對話方塊中啟用顯示 [說明選項](#edit-dialog)
* **在編輯**
對話方塊中顯示日期啟用顯 [示日期選項](#edit-dialog)

### 樣式標籤{#styles-tab}

映像元件支AEM持[樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層{#data-layer}

清單元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
