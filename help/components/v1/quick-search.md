---
title: 快速搜尋元件(v1)
description: 快速搜尋元件提供對網站的搜尋功能並顯示搜尋結果，以便訪客可以搜尋網站並篩選結果。
role: Architect, Developer, Admin, User
exl-id: 60a043b7-d82c-4bc1-b91a-b77f748f7bc2
source-git-commit: ae2e1d0aaadbc0ad04847ce9aecb382e10cbedf1
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# 快速搜尋元件(v1) {#quick-search-component}

快速搜尋元件提供對網站的搜尋功能並顯示搜尋結果，讓訪客可輕鬆找到相符的內容並檢視結果。

## 使用狀況 {#usage}

快速搜尋元件讓網站訪客能夠搜尋內容、就地檢視結果，以及輕鬆導覽至相符頁面。 使用者捲動搜尋結果時，會動態擷取新結果。

此 [編輯對話方塊](#edit-dialog) 可讓內容作者定義內容樹狀結構中開始搜尋的位置。 使用 [設計對話方塊](#design-dialog)，範本作者可以設定內容樹狀結構中開始搜尋的位置的預設值，以及最大結果集大小和最小搜尋詞長度。

## 版本和相容性 {#version-and-compatibility}

快速搜尋元件的目前版本是v1，此版本隨2018年1月的核心元件2.0.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容於<br>[版本2.17.4](/help/versions.md) 和先前的 | 相容 | 相容 |

>[!CAUTION]
>
>本檔案說明快速搜尋元件v1。
>如需目前版本的「快速搜尋」元件的詳細資訊，請參閱 [快速搜尋元件](/help/components/quick-search.md) 檔案。

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

### 技術細節 {#technical-details}

>[!NOTE]
>
>保護搜尋元件或任何以AEM為基礎的應用程式免受DOS攻擊應在較高層級實作，例如透過使用 `mod_security` 在Dispatcher上。

有關快速搜尋元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_search_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者定義內容樹狀結構中開始搜尋的位置。

![快速搜尋元件的「編輯」對話方塊](/help/assets/quick-search-edit.png)

**搜尋根目錄**  — 開始搜尋的根目錄頁面。 「搜尋根目錄」可以是Blueprint主版、語言主版或一般頁面。
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層。](/help/developing/data-layer/overview.md)
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

>[!NOTE]
>
>如果 **搜尋根目錄** 未設定或無法解析，「快速搜尋」預設為搜尋目前頁面下方。

## 設計對話方塊 {#design-dialog}

使用「設計」對話方塊，範本作者可以設定內容樹狀結構中開始搜尋的位置的預設值，以及最大結果集大小和最小搜尋字詞長度。「設計」對話方塊可讓範本作者定義哪些文字格式選項可供內容作者使用。

### 屬性標籤 {#properties-tab}

![快速搜尋元件的設計對話方塊](/help/assets/quick-search-design.png)

* **搜尋根目錄**
內容作者在內容頁面上放置快速搜尋元件時搜尋根的預設值
* **結果大小**
搜尋要求擷取的結果數量上限
* **搜尋字詞最小長度**
開始搜尋的搜尋字詞最小長度

>[!NOTE]
>
>**結果大小** 和 **搜尋字詞最小長度** 只能在設計模式中設定，因此只能在範本層級，這表示內容作者無法修改這些值。

>[!CAUTION]
>
>**結果大小** 和 **搜尋字詞最小長度** 如果設定得太高或太低，可能會影響效能。

### 樣式索引標籤 {#styles-tab}

快速搜尋元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
