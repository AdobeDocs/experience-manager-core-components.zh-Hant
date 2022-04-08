---
title: 快速搜索元件(v1)
description: 快速搜索元件為網站提供搜索功能並顯示搜索結果，以便訪問者可以搜索網站並過濾結果。
role: Architect, Developer, Admin, User
exl-id: 60a043b7-d82c-4bc1-b91a-b77f748f7bc2
source-git-commit: ae2e1d0aaadbc0ad04847ce9aecb382e10cbedf1
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# 快速搜索元件(v1) {#quick-search-component}

快速搜索元件為網站提供搜索功能並顯示搜索結果，以便訪問者可以輕鬆查找匹配的內容和查看結果。

## 使用狀況 {#usage}

「快速搜索」元件使站點訪問者能夠搜索內容、將結果就地查看，並輕鬆導航到匹配的頁面。 當用戶滾動搜索結果時，將動態獲取新結果。

的 [編輯對話框](#edit-dialog) 允許內容作者在內容樹中定義搜索的起始位置。 使用 [設計對話框](#design-dialog)，模板作者可以設定內容樹中搜索應開始的位置的預設值以及最大結果集大小和最小搜索術語長度。

## 版本和相容性 {#version-and-compatibility}

快速搜索元件的當前版本為v1，該版本於2018年1月隨核心元件2.0.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |

>[!CAUTION]
>
>本文檔介紹快速搜索元件的v1。
>有關快速搜索元件當前版本的詳細資訊，請參閱 [快速搜索元件](/help/components/quick-search.md) 的子菜單。

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

### 技術詳細資訊 {#technical-details}

>[!NOTE]
>
>保護搜索元件或任何基AEM於DOS的應用程式免受DOS攻擊應在更高級別實施，例如，使用 `mod_security` 調度員的電話。

有關快速搜索元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_search_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者定義搜索在內容樹中的起始位置。

![快速搜索元件的編輯對話框](/help/assets/quick-search-edit.png)

**搜索根**  — 從何處開始搜索的根頁。 「搜索根」可以是藍圖首頁、語言首頁或常規頁。
* **ID**  — 此選項允許控制HTML和 [資料層。](/help/developing/data-layer/overview.md)
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

>[!NOTE]
>
>如果 **搜索根** 未配置或無法解析，「快速搜索」預設為在當前頁面下進行搜索。

## 設計對話框 {#design-dialog}

使用「設計」對話框，模板作者可以設定內容樹中搜索應開始的位置的預設值以及最大結果集大小和最小搜索術語長度。「設計」對話框允許模板作者定義哪些文本格式選項可供內容作者使用。

### 屬性頁籤 {#properties-tab}

![「快速搜索元件的設計」對話框](/help/assets/quick-search-design.png)

* **搜索根**
當內容作者將快速搜索元件放置在內容頁面上時搜索根的預設值
* **結果大小**
搜索請求獲取的最大結果數
* **搜索術語最小長度**
開始搜索的搜索項的最小長度

>[!NOTE]
>
>**結果大小** 和 **搜索術語最小長度** 只能在設計模式下設定，因此只能在模板級別設定，這意味著內容作者無法修改這些值。

>[!CAUTION]
>
>**結果大小** 和 **搜索術語最小長度** 分別設定得過高或過低時，可能會對效能產生影響。

### 樣式頁籤 {#styles-tab}

快速搜索元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
