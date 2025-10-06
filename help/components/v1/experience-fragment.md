---
title: 體驗片段元件 (v1)
description: 透過體驗片段元件，內容作者可將體驗片段變化版本新增至頁面。
role: Architect, Developer, Admin, User
exl-id: 42230a7b-6feb-4535-baf9-b8fc06978d98
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '770'
ht-degree: 100%

---


# 體驗片段元件 (v1) {#experience-fragment-component}

透過核心元件體驗片段元件，內容作者可於頁面上放置體驗片段變化版本，同時支援本地化網站架構。

## 用途 {#usage}

透過核心元件體驗片段元件，內容作者可從現有的體驗片段變化版本中選取，並將其放置在內容頁面上。體驗片段元件同樣支援本地化網站結構。

* 該元件的屬性可在[設定對話框](#configure-dialog)中定義。
* 將元件新增至頁面時，可在[設計對話框](#design-dialog)中定義預設值。

## 版本和相容性 {#version-and-compatibility}

本文件說明體驗片段元件 v1，最初於 2019 年 9 月隨著核心元件 2.6.0 版發行導入。

>[!CAUTION]
>
>本文件說明體驗片段元件 v1。
>
>如需體驗片段元件目前版本的詳細資訊，請參閱[體驗片段元件](/help/components/experience-fragment.md)文件。

## 本地化網站結構支援 {#localized-site-structure}

體驗片段元件可適應本地化的網站結構，並根據頁面的本地化呈現適當的體驗片段。為此，體驗片段必須符合以下條件。

* 體驗片段元件已新增至範本。
* 該範本用於建立新內容頁面，此頁面是 `/content/<site>` 以下的本地化結構的一部分。
* 在內容頁面上參考的體驗片段屬於 `/content/experience-fragments` 以下的本地化體驗結構的一部分，遵循與 `/content/<site>` 以下的網站相同的模式，包括使用相同的元件名稱。

在這種情況下，與目前頁面具有相同本地化 (語言、Blueprint 或即時副本) 的片段將當作範本的一部分呈現。

此行為僅限新增至範本的體驗片段元件。新增到個別內容頁面的體驗片段元件將轉譯在元件中設定的精確體驗片段轉譯。

* 如需體驗片段元件本地化功能的運作方式範例，請參閱[下一章節](#example)。
* 如需核心元件的本地化功能如何搭配運作的範例，請參閱[核心元件頁面的本地化功能](/help/get-started/localization.md)。

### 範例 {#example}

假設您的內容看起來像這樣：

```
/content
+-- experience-fragments
   \-- wknd
      +-- language-masters
      +-- us
         +-- en
            +-- footerTextXf
            \-- headerTextXf
         \-- es
            +-- footerTextXf
            \-- headerTextXf
      \-- ch
         +-- de
            +-- footerTextXf
            \-- headerTextXf
         +-- fr
            +-- footerTextXf
            \-- headerTextXf
         \-- it
            +-- footerTextXf
            \-- headerTextXf
+-- wknd
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

請注意，`/content/experience-fragments/wknd` 下的結構會反映 `/content/wknd` 的結構。

在此案例中，如果體驗片段元件 `/content/experience-fragments/wknd/us/en/footerTextXf` 放置在範本上，根據該範本建立的本地化頁面將自動轉譯與本地化內容頁面對應的本地化體驗片段。

因此，如果您導覽至 `/content/wknd/ch/de` 底下使用相同範本的內容頁面，將會轉譯 `/content/experience-fragments/wknd/ch/de/footerTextXf` 而非 `/content/experience-fragments/wknd/us/en/footerTextXf`。

### 遞補 {#fallback}

體驗片段元件會嘗試依照以下順序尋找對應的本地化元件。

1. 首先嘗試尋找語言根。
1. 如果未找到，則會嘗試尋找 Blueprint。
1. 如果未找到，則會嘗試尋找即時副本。
1. 如果找不到，則預設為元件中設定的體驗片段。

## 範例元件輸出 {#sample-component-output}

若要體驗「體驗片段元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_xf)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_xf_v1_tw)有關體驗片段元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，內容作者可選取應在頁面上轉譯的體驗片段變化版本。

![體驗片段元件的編輯對話框](/help/assets/experience-fragment-edit.png)

使用&#x200B;**開啟選取對話框**&#x200B;按鈕開啟元件選擇器，選擇要新增至內容頁面的體驗片段元件變化版本。

如果您將體驗片段元件新增至範本，請注意，只要體驗片段完成本地化，該元件便會自動進行本地化，因此在頁面呈現的內容可能與您明確選取的元件有所差異。如需詳細資訊，[請參閱以上範例](#example)。

您也可以定義 **ID**。此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。

* 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
* 若已指定 ID，則作者應確保其為唯一識別碼。
* 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可為使用體驗片段元件的內容作者定義可用選項，以及在放置體驗片段元件時所設定的預設值。

### 樣式索引標籤 {#styles-tab}

體驗片段元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
