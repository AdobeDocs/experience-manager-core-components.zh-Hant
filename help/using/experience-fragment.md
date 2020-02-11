---
title: 體驗片段元件
description: 體驗片段元件可讓內容作者將體驗片段變數新增至頁面。
translation-type: tm+mt
source-git-commit: 65f900ad6759206a13f2bda6169900f62d968d8d

---


# 體驗片段元件{#experience-fragment-component}

核心元件體驗片段元件可讓內容作者在支援本地化網站結構的同時，將體驗片段變更置於頁面上。

## 使用狀況 {#usage}

核心元件體驗片段元件可讓內容作者從現有體驗片段變化中選取，並將一個片段放在內容頁面上。 「體驗片段」元件也支援本地化的網站結構。

* 可在「配置」對話框中定義元件的 [屬性](#configure-dialog)。
* 將元件新增至頁面時的預設值，可在設計對話方塊中 [定義](#design-dialog)。

## 本地化網站結構支援 {#localized-site-structure}

「體驗片段元件」可自適應本地化網站結構，並根據頁面的本地化呈現適當的體驗片段。 若要這麼做，體驗片段必須符合下列條件。

* 體驗片段元件會新增至範本。
* 該範本可用來建立新內容頁面，此頁面為下方本地化結構的一部分 `/content/<site>`。
* 內容頁面上參考的體驗片段是下方本地化體驗片段結構的一部分，其模式與 `/content/experience-fragments` 下方的網站相同， `/content/<site>` 包括使用相同的元件名稱。

在此情況下，與目前頁面具有相同本地化（語言、藍圖或即時副本）的片段會呈現為範本的一部分。

此行為僅限於新增至範本的體驗片段元件。 新增至個別內容頁面的體驗片段元件，將會呈現元件內所設定的確切體驗片段轉譯。

* 如需體驗片段元件的本地化功能如何運作的範例，請參 [閱下節](#example)。
* 如需核心元件的本地化功能如何搭配運作的範例，請參閱核 [心元件的本地化功能頁面](localization.md)。

### 例如 {#example}

假設您的內容看起來像這樣：

```
/content
+-- experience-fragments
   \-- we-retail
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
+-- we-retail
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

請注意，下面的 `/content/experience-fragments/we-retail` 結構與的結構相 `/content/we-retail`反。

在此例中，如果「體驗片段」元 `/content/experience-fragments/we-retail/us/en/footerTextXf` 件放置在範本上，則根據該範本建立的本地化頁面會自動呈現與本地化內容頁面相對應的本地化體驗片段。

因此，如果您導覽至使用相同范 `/content/we-retail/ch/de` 本之下的內容頁面，將 `/content/experience-fragments/we-retail/ch/de/footerTextXf` 會呈現而非呈現 `/content/experience-fragments/we-retail/us/en/footerTextXf`。

### 備援 {#fallback}

體驗片段元件會嘗試依下列順序尋找對應的本地化元件。

1. 首先，它會嘗試尋找語言根。
1. 如果找不到，它會嘗試尋找藍圖。
1. 如果找不到，則會嘗試尋找即時副本。
1. 如果找不到，則預設為元件中設定的體驗片段。

## 版本與相容性 {#version-and-compatibility}

Experience Fragment元件的目前版本為v1，此版本於2019年9月隨核心元件2.6.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM As a Cloud Service |
|--- |--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 | 相容 |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗「體驗片段元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](https://adobe.com/go/aem_cmp_library_xf)。

## 技術詳細資訊 {#technical-details}

有關Experience Fragment元件的最新技術文 [件，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_xf_v1)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者選取應在頁面上呈現的體驗片段變數。

![](assets/screen-shot-2019-08-23-10.49.21.png)

使用「開 **啟選擇對話方塊** 」按鈕，開啟元件選擇器以選擇要新增至內容頁面的體驗片段元件變數。

如果您將體驗片段元件新增至範本，請注意，如果體驗片段已本地化，則會自動本地化，因此頁面上呈現的內容可能會與您明確選取的元件有所不同。 [如需詳細資訊](#example) ，請參閱上述範例。

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者可用的選項，內容作者使用體驗片段元件，以及放置體驗片段元件時設定的預設值。

![](assets/screen-shot-2019-08-23-10.48.36.png)

「體驗片段」元件支援AEM [Style系統](authoring.md#component-styling)。
