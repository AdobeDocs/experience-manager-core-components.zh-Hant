---
title: 標題元件 (v2)
description: 核心元件標題元件是區段標題元件，具備就地編輯的功能。
role: Architect, Developer, Admin, User
exl-id: f853ec46-19fd-4569-a9d3-5c376d2a2101
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '521'
ht-degree: 100%

---


# 標題元件 (v2) {#title-component}

核心元件標題元件是區段標題元件，具備就地編輯的功能。

## 用途 {#usage}

標題元件用作內容的主標題或區段的標題。可用的標題層級可由範本作者在[設計對話框](#design-dialog)中定義。內容編輯者可在[編輯對話框](#edit-dialog)中選取可用的標題層級。為了增加便利性，也可以簡單地就地編輯標題文字。

## 版本和相容性 {#version-and-compatibility}

本文件說明標題元件 v2，最初於 2018 年 1 月隨著核心元件 2.0.0 版發行導入。

>[!CAUTION]
>
>本文件說明標題元件 v2。
>
>如需標題元件目前版本的詳細資訊，請參閱[標題元件](/help/components/title.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「標題元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_title_tw)」。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_title_v2_tw)有關標題元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框可讓內容作者定義標題文字並選取標題層級。

* **標題** - 如果空白，則使用頁面標題
* **類型/大小** - 定義標題的標題層級
* **連結** - 定義標題將連結的內容。這可以是內容頁面的路徑、外部 URL 或頁面錨點。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

![標題元件的編輯對話框](/help/assets/title-edit.png)

>[!NOTE]
>
>定義標題連結的功能已在核心元件發行版本 2.2.0 中導入。

也可以使用就地編輯器來編輯標題元件的文字。

![標題元件的就地編輯](/help/assets/title-edit-inline.png)

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義內容作者建立標題元件時應具備的預設標題層級。

### 尺寸索引標籤 {#sizes-tab}

![標題元件的設計對話框](/help/assets/title-design.png)

* **允許作者使用的類型/大小** - 啟用或停用內容作者在使用標題元件時可用的標題類型。
* **預設類型/大小** - 定義內容作者將標題元件新增至頁面時，將自動指派的標題類型。
* **停用連結** - 停用標題元件中連結的支援，不允許內容作者從標題連結。

>[!NOTE]
>
>定義標題連結的功能已在核心元件發行版本 2.2.0 中導入。

### 樣式索引標籤 {#styles-tab}

標題元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「標題元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
