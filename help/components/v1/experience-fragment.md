---
title: 體驗片段元件(v1)
description: 體驗片段元件可讓內容作者將體驗片段變數新增至頁面。
role: Architect, Developer, Admin, User
exl-id: 42230a7b-6feb-4535-baf9-b8fc06978d98
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 0%

---

# 體驗片段元件(v1) {#experience-fragment-component}

核心元件體驗片段元件可讓內容作者在支援當地語系化網站結構的同時，將體驗片段變數放置在頁面上。

## 使用狀況 {#usage}

核心元件體驗片段元件可讓內容作者從現有的體驗片段變數中選取，並將其放在內容頁面上。 體驗片段元件也支援本地化的網站結構。

* 元件的屬性可在 [設定對話方塊](#configure-dialog).
* 將元件新增至頁面時的元件預設值可在下列位置定義： [設計對話方塊](#design-dialog).

## 版本和相容性 {#version-and-compatibility}

本檔案說明體驗片段元件v1，此版本隨2019年9月的核心元件2.6.0版引入。

>[!CAUTION]
>
>本檔案說明體驗片段元件v1。
>
>如需目前版本的體驗片段元件的詳細資訊，請參閱 [體驗片段元件](/help/components/experience-fragment.md) 檔案。

## 當地語系化網站結構支援 {#localized-site-structure}

體驗片段元件可適應本地化的網站結構，並根據頁面的本地化呈現適當的體驗片段。 為此，體驗片段必須滿足以下條件。

* 體驗片段元件已新增至範本。
* 該範本用於建立屬於以下本地化結構一部分的新內容頁面 `/content/<site>`.
* 在內容頁面上參考的體驗片段是以下本地化體驗片段結構的一部分 `/content/experience-fragments` 遵循與以下網站相同的模式 `/content/<site>` 包括使用相同的元件名稱。

在此情況下，與目前頁面具有相同本地化（語言、Blueprint或即時副本）的片段將會在範本中轉譯。

此行為僅限於新增至範本的體驗片段元件。 新增到個別內容頁面的體驗片段元件將轉譯在元件中設定的確切體驗片段轉譯。

* 如需體驗片段元件本地化功能運作方式的範例，請參閱 [下節](#example).
* 如需核心元件的本地化功能如何搭配運作的範例，請參閱 [核心元件頁面的本地化功能](/help/get-started/localization.md).

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

請注意，下列結構 `/content/experience-fragments/wknd` 映象結構 `/content/wknd`.

在此情況下，如果體驗片段元件 `/content/experience-fragments/wknd/us/en/footerTextXf` 放在範本上，根據該範本建立的本地化頁面將自動轉譯與本地化內容頁面對應的本地化體驗片段。

因此，如果您導覽至 `/content/wknd/ch/de` 使用相同範本的檔案， `/content/experience-fragments/wknd/ch/de/footerTextXf` 將轉譯而不是 `/content/experience-fragments/wknd/us/en/footerTextXf`.

### 遞補內容 {#fallback}

體驗片段元件會嘗試依照以下順序尋找對應的本地化元件。

1. 首先嘗試尋找語言根。
1. 如果找不到，它會嘗試尋找Blueprint。
1. 如果找不到，會嘗試尋找即時副本。
1. 如果找不到，則預設為元件中設定的體驗片段。

## 範例元件輸出 {#sample-component-output}

若要體驗體驗片段元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_xf).

## 技術細節 {#technical-details}

有關體驗片段元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_xf_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者選取應呈現在頁面上的體驗片段變數。

![體驗片段元件的「編輯」對話方塊](/help/assets/experience-fragment-edit.png)

使用 **開啟選取範圍對話方塊** 按鈕來開啟元件選擇器，以選擇要新增至內容頁面的體驗片段元件變數。

如果您將體驗片段元件新增至範本，請注意，體驗片段一旦本地化，就會自動本地化，因此根據您明確選取的元件，頁面上呈現的內容可能會有所不同。 [請參閱上述範例](#example) 以取得詳細資訊。

您也可以定義 **ID**. 此選項可讓您控制HTML和中的元件的唯一識別碼 [資料層](/help/developing/data-layer/overview.md).

* 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
* 若指定ID，作者應負責確認該ID是唯一的。
* 變更ID會對CSS、JS和資料層追蹤造成影響。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些選項可供使用體驗片段元件的內容作者使用，以及在放置體驗片段元件時的預設值。

### 樣式索引標籤 {#styles-tab}

體驗片段元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
