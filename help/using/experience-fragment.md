---
title: 體驗片段元件
seo-title: 體驗片段元件
description: 「體驗片段元件」可讓內容作者新增體驗片段變數至頁面。
seo-description: 「體驗片段元件」可讓內容作者新增體驗片段變數至頁面。
content-type: 引用
topic-tags: 核心元件
index: y
internal: n
translation-type: tm+mt
source-git-commit: c0827595a594779f48ba5e8770b804e574346647

---

# 體驗片段元件{#experience-fragment-component}

核心元件體驗片段元件可讓內容作者在頁面上放置體驗片段變數，同時支援本地化的網站結構。

## 使用狀況 {#usage}

核心元件體驗片段元件可讓內容作者從現有體驗片段驗證中選取，並將之放置在內容頁面上。Experience片段元件也支援本地化的網站結構。

* 您可以在 [設定對話方塊中定義元件的屬性](#configure-dialog)。
* 將元件新增至頁面時的預設值可在 [設計對話方塊中定義](#design-dialog)。

## 本地化的網站結構支援 {#localized-site-structure}

Experience片段元件可調整為本地化的網站結構，並根據頁面本土化產生適當的體驗片段。若要這麼做，體驗片段必須符合下列條件。

* Experience片段元件會新增至範本。
* 該範本可用來建立新內容頁面，此頁面屬於下方結構的一部分 `/content/<site>`。
* 內容頁面上引用的體驗片段屬於下方體驗片段結構的一部分， `/content/experience-fragments` 下方採用與下列相同的模式， `/content/<site>` 包含相同的元件名稱。

在這種情況下，會將具有相同本地化(語言、藍圖或即時副本)的片段轉換為範本的一部分。

此行為僅限於新增至範本的Experience片段元件。新增至個別內容頁面的體驗片段元件將會呈現在元件內設定的精確體驗片段轉譯。

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

請注意，以下結構 `/content/experience-fragments/we-retail` 反映了結構的鏡像 `/content/we-retail`。

在這種情況下，如果將Experience片段元件 `/content/experience-fragments/we-retail/us/en/footerTextXf` 放置在範本上，根據該範本建立的本地化頁面會自動呈現對應於本地化內容頁面的本地化體驗片段。

因此，如果您導覽至使用相同範本的 `/content/we-retail/ch/de` 內容頁面，將 `/content/experience-fragments/we-retail/ch/de/footerTextXf` 會顯示而非 `/content/experience-fragments/we-retail/us/en/footerTextXf`顯示。

### 後援 {#fallback}

體驗片段元件會嘗試以下列順序尋找對應的本地化元件。

1. First會嘗試尋找語言根目錄。
1. 如果找不到，則會嘗試尋找藍圖。
1. 如果找不到，則會嘗試尋找即時副本。
1. 如果找不到，則會預設為元件中設定的體驗片段。

## 版本與相容性 {#version-and-compatibility}

目前版本的Experience片段元件是v1，是於2019年月發行的版本2.6.0推出，並於本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |---|
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

若要體驗Experience片段元件，以及查看其組態選項以及HTML和JSON輸出的範例，請造訪 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library/experience-fragment.html)。

## 技術細節 {#technical-details}

有關Experience片段元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/experience-fragment/v1/experience-fragment)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者選取應在頁面上轉換的體驗片段變數。

![](assets/screen-shot-2019-08-23-10.49.21.png)

使用 **「開啓選擇對話方塊** 」按鈕開啓元件選擇器，以選擇要新增至內容頁面的體驗片段元件變數。

如果您將Experience片段元件新增至範本，請注意，當Experience片段已本地化時，它會自動本地化，因此在頁面上演算的內容可能會與您明確選取的元件不同。[如需詳細資訊，請參閱上述](#example) 範例。

## 設計對話方塊 {#design-dialog}

此設計對話方塊可讓範本作者定義使用Experience片段元件和置入Experience片段元件時預設集的內容作者可用選項。

![](assets/screen-shot-2019-08-23-10.48.36.png)

體驗片段元件支援AEM [樣式系統](authoring.md#component-styling)。
