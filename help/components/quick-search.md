---
title: 快速搜尋元件
description: 「快速搜尋」元件提供網站的搜尋功能，並提供搜尋結果，讓訪客可以搜尋網站並篩選結果。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: fc40ce1d-e69a-4a40-853e-67a37228271b
translation-type: tm+mt
source-git-commit: 6eff0c8584605e034fc6516416783715fce10095
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 1%

---

# 快速搜尋元件{#quick-search-component}

「快速搜尋」元件提供網站的搜尋功能，並提供搜尋結果，讓訪客可以輕鬆找到符合的內容並檢視結果。

## 使用狀況 {#usage}

「快速搜尋」元件讓網站訪客能夠搜尋內容、就地檢視結果，並輕鬆導覽至相符的頁面。 當使用者捲動搜尋結果時，會動態擷取新結果。

[edit dialog](#edit-dialog)可讓內容作者定義內容樹中應開始搜索的位置。 使用[設計對話框](#design-dialog)，模板作者可以設定內容樹中應開始搜索的位置的預設值以及最大結果集大小和最小搜索詞長度。

## 版本和相容性{#version-and-compatibility}

目前的快速搜尋元件版本為v1，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

### 技術詳細資訊{#technical-details}

>[!NOTE]
>
>保護搜索元件或任何基AEM於DOS的應用程式免受DOS攻擊的保護應該在更高級別上實施，例如在調度器上使用`mod_security`。

有關快速搜索元件[的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_search_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者定義搜尋應在內容樹狀結構中的位置。

![快速搜尋元件的編輯對話方塊](/help/assets/quick-search-edit.png)

**搜索根** -從何處開始搜索的根頁。「搜尋根」可以是Blueprint主版、語言主版或一般頁面。
* **ID**  —— 此選項可讓您控制HTML和資料層中元件的唯 [一識別碼。](/help/developing/data-layer/overview.md)
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

>[!NOTE]
>
>如果&#x200B;**Search Root**&#x200B;未配置或無法解析，則「快速搜索」預設為在當前頁面下進行搜索。

## 設計對話框{#design-dialog}

使用設計對話框，模板作者可以設定內容樹中搜索應開始的位置的預設值以及最大結果集大小和最小搜索詞長度。設計對話框允許模板作者定義哪些文本格式選項可供內容作者使用。

### 屬性頁籤{#properties-tab}

![快速搜尋元件的設計對話方塊](/help/assets/quick-search-design.png)

* **搜尋**
根內容作者將快速搜尋元件置於內容頁面時的搜尋根的預設值
* **結果**
大小搜尋請求擷取的結果數上限
* **搜尋詞最小**
長度開始搜尋的搜尋詞最小長度

>[!NOTE]
>
>**結果** 大小和 **搜尋詞最小** 長度只能在設計模式中設定，因此只能在範本層級設定，這表示內容作者無法修改這些值。

>[!CAUTION]
>
>**結果** 大小和 **搜索詞最小長** 度分別設定為過高或過低時，可能會對效能產生影響。

### 樣式標籤{#styles-tab}

快速搜索元件AEM支援[樣式系統](/help/get-started/authoring.md#component-styling)。
