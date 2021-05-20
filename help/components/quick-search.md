---
title: 快速搜尋元件
description: 「快速搜尋元件」提供網站的搜尋功能，並顯示搜尋結果，讓訪客可以搜尋網站並篩選結果。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: fc40ce1d-e69a-4a40-853e-67a37228271b
source-git-commit: 6eff0c8584605e034fc6516416783715fce10095
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 1%

---

# 快速搜索元件{#quick-search-component}

「快速搜尋元件」可為網站提供搜尋功能，並顯示搜尋結果，讓訪客可輕鬆找到相符的內容和檢視結果。

## 使用狀況 {#usage}

「快速搜尋」元件讓網站訪客能夠搜尋內容、就地檢視結果，以及輕鬆導覽至相符的頁面。 當使用者捲動搜尋結果時，會動態擷取新結果。

[edit dialog](#edit-dialog)可讓內容作者定義內容樹狀結構中應開始搜尋的位置。 使用[design對話框](#design-dialog)，模板作者可以為內容樹中應該開始搜索的位置設定預設值，以及最大結果集大小和最小搜索詞長度。

## 版本和相容性{#version-and-compatibility}

快速搜尋元件的目前版本為v1，此版本於2018年1月隨核心元件2.0.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

### 技術詳細資訊{#technical-details}

>[!NOTE]
>
>保護搜尋元件或任何AEM型應用程式，使其免受DOS攻擊，應在較高層級實作，例如在Dispatcher上使用`mod_security`。

如需快速搜尋元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_search_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者定義內容樹狀結構中應開始搜尋的位置。

![快速搜索元件的編輯對話框](/help/assets/quick-search-edit.png)

**搜尋根**  — 要開始搜尋的根頁面。「搜尋根」可以是Blueprint主版、語言主版或一般頁面。
* **ID**  — 此選項可讓您控制HTML和資料層中元件的唯一 [識別碼。](/help/developing/data-layer/overview.md)
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

>[!NOTE]
>
>如果未配置或無法解析&#x200B;**搜索根**，則「快速搜索」預設為當前頁下的搜索。

## 設計對話框{#design-dialog}

使用設計對話框，模板作者可以為內容樹中應開始搜索的位置設定預設值，以及最大結果集大小和最小搜索詞長度。設計對話框允許模板作者定義哪些文本格式選項可供內容作者使用。

### 屬性頁簽{#properties-tab}

![快速搜索元件的設計對話框](/help/assets/quick-search-design.png)

* **搜**
尋根內容作者將快速搜尋元件置於內容頁面時的搜尋根的預設值
* **結**
果大小搜索請求獲取的最大結果數
* **搜尋詞最小**
長度要開始搜尋的搜尋詞的最小長度

>[!NOTE]
>
>**「結** 果大 **小」和「** 搜索詞最小長度」只能在設計模式中設定，因此只能在模板級別設定，這意味著內容作者無法修改這些值。

>[!CAUTION]
>
>**結果** 大小和 **搜索詞最小** 長度如果分別設定為過高或過低，則可能會產生效能影響。

### 樣式標籤{#styles-tab}

快速搜索元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
