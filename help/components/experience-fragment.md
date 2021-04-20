---
title: 體驗片段元件
description: 體驗片段元件可讓內容作者將體驗片段變數新增至頁面。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 1%

---


# 體驗片段元件{#experience-fragment-component}

核心元件體驗片段元件可讓內容作者在支援本地化網站結構的同時，將體驗片段變更置於頁面上。

## 使用狀況 {#usage}

核心元件體驗片段元件可讓內容作者從現有體驗片段變化中選取，並將一個片段放在內容頁面上。 「體驗片段」元件也支援本地化的網站結構。

* 在[configure dialog](#configure-dialog)中可定義元件的屬性。
* 將元件添加到頁面時的預設值可在[設計對話框](#design-dialog)中定義。

## 本地化網站結構支援{#localized-site-structure}

「體驗片段元件」可自適應本地化網站結構，並根據頁面的本地化呈現適當的體驗片段。 若要這麼做，體驗片段必須符合下列條件。

* 體驗片段元件會新增至範本。
* 該範本用於建立新內容頁面，此頁面屬於`/content/<site>`下方的本地化結構。
* 內容頁面上參考的體驗片段是`/content/experience-fragments`下方本地化的體驗片段結構的一部分，其模式與`/content/<site>`下方的網站相同，包括使用相同的元件名稱。

在此情況下，與目前頁面具有相同本地化（語言、藍圖或即時副本）的片段會呈現為範本的一部分。

此行為僅限於新增至範本的體驗片段元件。 新增至個別內容頁面的體驗片段元件，將會呈現元件內所設定的確切體驗片段轉譯。

* 如需體驗片段元件的本地化功能如何運作的範例，請參閱[下方的](#example)一節。
* 有關核心元件的本地化功能如何協同工作的示例，請參閱核心元件的[本地化功能頁](/help/get-started/localization.md)。

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

請注意，`/content/experience-fragments/wknd`下方的結構反映`/content/wknd`的結構。

在這種情況下，如果「體驗片段」元件`/content/experience-fragments/wknd/us/en/footerTextXf`放置在範本上，根據該範本建立的本地化頁面會自動呈現與本地化內容頁面相對應的本地化體驗片段。

因此，如果導覽至使用相同範本的`/content/wknd/ch/de`下方的內容頁面，將會呈現`/content/experience-fragments/wknd/ch/de/footerTextXf`，而非`/content/experience-fragments/wknd/us/en/footerTextXf`。

### 備援{#fallback}

體驗片段元件會嘗試依下列順序尋找對應的本地化元件。

1. 首先，它會嘗試尋找語言根。
1. 如果找不到，它會嘗試尋找藍圖。
1. 如果找不到，則會嘗試尋找即時副本。
1. 如果找不到，則預設為元件中設定的體驗片段。

## 版本和相容性{#version-and-compatibility}

Experience Fragment元件的目前版本為v1，此版本於2019年9月隨核心元件2.6.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗「體驗片段元件」，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_xf)。

## 技術詳細資訊{#technical-details}

有關體驗片段元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_xf_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

「設定」對話方塊可讓內容作者選取應在頁面上呈現的體驗片段變數。

![體驗片段元件的編輯對話方塊](/help/assets/experience-fragment-edit.png)

使用&#x200B;**開啟選擇對話方塊**&#x200B;按鈕，開啟元件選擇器以選擇要新增至內容頁面的體驗片段元件變數。

如果您將體驗片段元件新增至範本，請注意，如果體驗片段已本地化，則會自動本地化，因此頁面上呈現的內容可能會與您明確選取的元件有所不同。 [如需詳細資](#example) 訊，請參閱上述範例。

您也可以定義&#x200B;**ID**。 此選項可控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。

* 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
* 如果指定ID，則作者有責任確保其唯一性。
* 變更ID可能會影響CSS、JS和資料圖層追蹤。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義內容作者可用的選項，內容作者使用體驗片段元件，以及放置體驗片段元件時設定的預設值。

### 樣式標籤{#styles-tab}

體驗片段元AEM件支援[Style System](/help/get-started/authoring.md#component-styling)。
