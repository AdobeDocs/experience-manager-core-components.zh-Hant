---
title: 快速搜尋元件 (v1)
description: 「快速搜尋元件」提供網站搜尋功能，並會顯示搜尋結果，讓訪客可搜尋該網站並篩選結果。
role: Architect, Developer, Admin, User
exl-id: 60a043b7-d82c-4bc1-b91a-b77f748f7bc2
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '646'
ht-degree: 100%

---


# 快速搜尋元件 (v1) {#quick-search-component}

「快速搜尋元件」提供網站搜尋功能，並會顯示搜尋結果，讓訪客可輕鬆找到相符的內容並檢視結果。

## 用途 {#usage}

「快速搜尋元件」可讓網站訪客搜尋內容、就地檢視結果，並可輕鬆瀏覽至相符的頁面。當使用者捲動搜尋結果時，則會動態擷取新的結果。

透過[編輯對話框](#edit-dialog)，內容作者可定義在內容樹狀結構中搜尋的開始位置。使用[設計對話框](#design-dialog)，範本作者可設定在內容樹狀結構中搜尋的開始位置預設值，以及最大結果集大小和最小搜尋字詞長度。

## 版本和相容性 {#version-and-compatibility}

「快速搜尋元件」的目前版本為 v1，此版本於 2018 年 1 月隨著「核心元件」2.0.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 |

>[!CAUTION]
>
>本文件說明快速搜尋元件 v1。
>>如需「快速搜尋元件」目前版本的詳細資訊，請參閱[快速搜尋元件](/help/components/quick-search.md)文件。

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

### 技術詳細資訊 {#technical-details}

>[!NOTE]
>
>若要保護「搜尋元件」或任何以 AEM 為基礎的應用程式免受 DOS 攻擊，應在較高層級實施，例如透過在 Dispatcher 上使用 `mod_security` 。

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_search_v1)有關「快速搜尋元件」的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

透過編輯對話框，內容作者可定義在內容樹狀結構中搜尋的開始位置。

![快速搜尋元件的編輯對話框](/help/assets/quick-search-edit.png)

**搜尋根目錄** - 搜尋開始位置的根頁面。「搜尋根目錄」可以是 Blueprint 主版頁面、語言主版頁面或一般頁面。
* **ID** - 此選項可讓您控制 HTML 和「[資料層](/help/developing/data-layer/overview.md)」中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

>[!NOTE]
>
>如果&#x200B;**搜尋根目錄**&#x200B;未設定或無法解析，則「快速搜尋」會預設為在目前頁面之下搜尋。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可以設定在內容樹狀結構中搜尋的開始位置預設值，以及最大結果集大小和最小搜尋字詞長度。設計對話框可讓範本作者定義可供內容作者使用的文字格式選項。

### 屬性索引標籤 {#properties-tab}

![快速搜尋元件的設計對話框](/help/assets/quick-search-design.png)

* **搜尋根目錄**
內容作者在內容頁面上放置「快速搜尋元件」時，搜尋根目錄的預設值
* **結果大小**
搜尋要求擷取的最大結果數量
* **搜尋字詞最小長度**
開始搜尋時，搜尋字詞的最小長度

>[!NOTE]
>
>**結果大小**&#x200B;和&#x200B;**搜尋字詞最小長度**&#x200B;只能在設計模式下設定，因此僅限於範本層級，這表示內容作者無法修改這些值。

>[!CAUTION]
>
>**結果大小**&#x200B;和&#x200B;**搜尋字詞最小長度**&#x200B;如果分別設定得太高或太低，可能會影響效能。

### 樣式索引標籤 {#styles-tab}

「快速搜尋元件」支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
