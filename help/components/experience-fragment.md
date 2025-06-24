---
title: 體驗片段元件
description: 體驗片段元件可讓內容作者將體驗片段變數新增至頁面。
role: Architect, Developer, Admin, User
exl-id: 103f729a-084d-4b6a-a239-d8ef8902eb95
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 1%

---


# 體驗片段元件{#experience-fragment-component}

核心元件體驗片段元件可讓內容作者在支援當地語系化網站結構時，將體驗片段變數放置在頁面上。

{{traditional-aem}}

## 使用情況 {#usage}

核心元件體驗片段元件可讓內容作者從現有的體驗片段變數中選取，並將其放置在內容頁面上。 體驗片段元件也支援本地化的網站結構。

* 可以在[設定對話方塊](#configure-dialog)中定義元件的屬性。
* 將元件新增至頁面時的預設值可以在[設計對話方塊](#design-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

體驗片段元件的目前版本是v2，此版本隨2022年2月的核心元件發行版本2.18.0的發佈引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v2 | - | 相容 | 相容 | 相容 |
| [v1](v1/experience-fragment.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 當地語系化網站結構支援 {#localized-site-structure}

體驗片段元件可適應本地化的網站結構，並根據頁面的本地化呈現適當的體驗片段。 為此，體驗片段必須滿足以下條件。

* 體驗片段元件已新增至範本。
* 該範本是用來建立新內容頁面，此頁面是`/content/<site>`以下的本地化結構的一部分。
* 在內容頁面上參考的體驗片段屬於`/content/experience-fragments`以下的本地化體驗結構的一部分，遵循與`/content/<site>`以下的網站相同的模式，包括使用相同的元件名稱。

在這種情況下，與目前頁面具有相同本地化（語言、Blueprint或即時副本）的片段將當作範本的一部分呈現。

此行為僅限新增到範本的體驗片段元件。 新增到個別內容頁面的體驗片段元件將轉譯在元件中設定的精確體驗片段轉譯。

* 如需體驗片段元件本地化功能的運作方式範例，請參閱[下節](#example)。
* 如需核心元件的本地化功能如何搭配運作的範例，請參閱核心元件頁面的[本地化功能](/help/get-started/localization.md)。

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

請注意，`/content/experience-fragments/wknd`下的結構會反映`/content/wknd`的結構。

在此案例中，如果體驗片段元件`/content/experience-fragments/wknd/us/en/footerTextXf`放在範本上，根據該範本建立的當地語系化頁面將自動轉譯與當地語系化內容頁面對應的當地語系化體驗片段。

因此，如果您導覽至`/content/wknd/ch/de`底下使用相同範本的內容頁面，將會轉譯`/content/experience-fragments/wknd/ch/de/footerTextXf`而非`/content/experience-fragments/wknd/us/en/footerTextXf`。

### 遞補 {#fallback}

體驗片段元件會嘗試依照以下順序尋找對應的本地化元件。

1. 首先嘗試尋找語言根。
1. 如果未找到，則會嘗試尋找Blueprint。
1. 如果未找到，則會嘗試尋找即時副本。
1. 如果找不到，其預設值為元件中設定的體驗片段。

## 範例元件輸出 {#sample-component-output}

若要體驗體驗體驗片段元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_xf)。

## 技術細節 {#technical-details}

您可以在GitHub](https://adobe.com/go/aem_cmp_tech_xf_v2)上找到體驗片段元件[的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者選取應在頁面上呈現的體驗片段變數。

![體驗片段元件的編輯對話方塊](/help/assets/experience-fragment-edit.png)

使用&#x200B;**開啟選取範圍對話方塊**&#x200B;按鈕開啟元件選擇器，選擇要新增至內容頁面的體驗片段元件變數。

如果您將體驗片段元件新增至範本，請注意，體驗片段一旦本地化，就會自動本地化，因此根據您明確選取的元件，頁面上呈現的內容可能會有所不同。 [如需詳細資訊，請參閱以上範例](#example)。

您也可以定義&#x200B;**ID**。 此選項允許控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。

* 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
* 若指定ID，作者應負責確認該ID為唯一ID。
* 變更ID會對CSS、JS和資料層追蹤造成影響。

### 樣式索引標籤 {#styles-tab-edit}

體驗片段元件](/help/assets/experience-fragment-edit-styles.png)的編輯對話方塊的![樣式索引標籤

體驗片段元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的選取具有相同的效果。

必須在[設計對話方塊](#design-dialog)中為此元件設定樣式，以便下拉式功能表可用。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些選項可供使用體驗片段元件的內容作者使用，以及在放置體驗片段元件時的預設設定。

### 樣式索引標籤 {#styles-tab}

體驗片段元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
