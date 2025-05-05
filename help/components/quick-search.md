---
title: 快速搜尋元件
description: 快速搜尋元件提供對網站的搜尋功能並顯示搜尋結果，讓訪客可以搜尋網站並篩選結果。
role: Architect, Developer, Admin, User
exl-id: fc40ce1d-e69a-4a40-853e-67a37228271b
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 1%

---

# 快速搜尋元件 {#quick-search-component}

快速搜尋元件提供對網站的搜尋功能並顯示搜尋結果，讓訪客可輕鬆找到相符內容並檢視結果。

## 使用情況 {#usage}

快速搜尋元件讓網站訪客能夠搜尋內容、就地檢視結果，並輕鬆導覽至相符頁面。 使用者捲動搜尋結果時，會動態擷取新結果。

[編輯對話方塊](#edit-dialog)可讓內容作者定義內容樹狀結構中開始搜尋的位置。 使用[設計對話方塊](#design-dialog)，範本作者可以設定內容樹狀結構中開始搜尋的位置的預設值，以及最大結果集大小和最小搜尋字詞長度。

## 版本和相容性 {#version-and-compatibility}

快速搜尋元件目前的版本是v2，此版本隨2018年1月的核心元件發行版本2.18.0的發佈引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|--- |--- |--- |---|---|
| v2 | - | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/quick-search.md) | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | - | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

### 技術細節 {#technical-details}

>[!NOTE]
>
>保護搜尋元件或任何AEM型應用程式免受DOS攻擊應在較高層級實作，例如透過在Dispatcher上使用`mod_security`。

在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_search_v2_tw)上可找到有關快速搜尋元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者定義內容樹中開始搜尋的位置。

![快速搜尋元件的編輯對話方塊](/help/assets/quick-search-edit.png)

**搜尋根** — 開始搜尋的根頁面。 搜尋根可以是Blueprint主版、語言主版或一般頁面。
* **ID** — 此選項允許控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

>[!NOTE]
>
>如果&#x200B;**搜尋根**&#x200B;未設定或無法解析，則快速搜尋預設為搜尋目前頁面下方。

## 設計對話方塊 {#design-dialog}

使用「設計」對話方塊，範本作者可以設定內容樹狀結構中開始搜尋的位置的預設值，以及最大結果集大小和最小搜尋字詞長度。「設計」對話方塊可讓範本作者定義哪些文字格式選項可供內容作者使用。

### 屬性標籤 {#properties-tab}

![快速搜尋元件的設計對話方塊](/help/assets/quick-search-design.png)

* **搜尋根目錄**
內容作者在內容頁面上放置快速搜尋元件時搜尋根的預設值
* **個結果大小**
搜尋請求可擷取的最大結果數量
* **搜尋字詞最小長度**
開始搜尋的搜尋字詞最小長度

>[!NOTE]
>
>**結果大小**&#x200B;和&#x200B;**搜尋字詞最小長度**&#x200B;只能在設計模式中設定，因此只能在範本層級，這表示內容作者無法修改這些值。

>[!CAUTION]
>
>**結果大小**&#x200B;和&#x200B;**搜尋字詞最小長度**&#x200B;如果分別設定得太高或太低，可能會影響效能。

### 樣式索引標籤 {#styles-tab}

快速搜尋元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
