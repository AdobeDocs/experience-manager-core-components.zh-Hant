---
title: 導覽元件(v1)
description: 導覽元件可讓使用者輕鬆導覽全域化的網站結構。
role: Architect, Developer, Admin, User
exl-id: 0b7de79a-e0c7-4cf9-b5a9-c78cbc3ecd2f
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 0%

---


# 導覽元件(v1) {#navigation-component}

導覽元件可讓使用者輕鬆導覽全域化的網站結構。

## 使用情況 {#usage}

導覽元件會列出頁面的樹狀結構，讓網站的使用者可以輕鬆導覽網站結構。

導覽元件可以自動偵測您網站的全域化網站結構，並[自動適應本地化的頁面。](#localized-site-structure)此外，它可以使用[陰影重新導向頁面](#shadow-structure)支援任意網站結構，以代表您主要內容結構以外的其他結構。

[編輯對話方塊](#edit-dialog)可讓內容作者定義導覽根頁面以及導覽深度。 [設計對話方塊](#design-dialog)允許範本作者定義導覽根目錄和深度的預設值。

## 版本和相容性 {#version-and-compatibility}

本檔案說明導覽元件v1，此版本隨2018年1月的核心元件發行版本2.0.0的發佈引入。

>[!CAUTION]
>
>本檔案說明導覽元件v1。
>
>如需目前版本的導覽元件詳細資訊，請參閱[導覽元件](/help/components/navigation.md)檔案。

## 當地語系化網站結構支援 {#localized-site-structure}

網站通常以多種語言提供給不同地區。 通常，每個本地化的頁面都會包含導覽元素，這些元素會包含在頁面範本中。 導覽元件可讓您針對網站的所有頁面在範本上放置一次，然後根據您的全域化網站結構自動針對個別本地化頁面進行調整。

* 如需導覽元件本地化功能的運作方式範例，請參閱下方[一節](#example-localization)。
* 如需核心元件的本地化功能如何搭配運作的範例，請參閱核心元件頁面的[本地化功能](/help/get-started/localization.md)。

### 範例 {#example-localization}

假設您的內容看起來像這樣：

```
/content
+-- wknd
   +-- language-masters
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- es
      +-- fr
      \-- it
   +-- us
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      \-- es
   \-- ch
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

對於網站WKND，您可能想要將導覽元件放置在頁面範本上作為標頭的一部分。 一旦成為範本的一部分，您可以將元件的&#x200B;**導覽根目錄**&#x200B;設定為`/content/wknd/language-masters/en`，因為這是您網站的主要內容開始的位置。 您可能也會想要將&#x200B;**導覽結構深度**&#x200B;設為`2`，因為您可能不希望元件顯示整個內容樹狀結構，而是隻顯示前兩個層級，以做為概觀。

透過&#x200B;**導覽根**&#x200B;值，導覽元件會知道在`/content/wknd/language-masters/en`之後，導覽開始，而且可以向下遞回網站的結構兩個層級（如&#x200B;**導覽結構深度**&#x200B;值所定義）來產生導覽選項。

無論使用者檢視哪個當地語系化頁面，導覽元件都可藉由知道目前頁面的位置、回溯至根目錄，然後前進至對應頁面來尋找對應的當地語系化頁面。

因此，如果訪客檢視`/content/ch/de/experience/arctic-surfing-in-lofoten`，元件就會知道根據`/content/wknd/language-masters/de`產生導覽結構。 同樣地，如果訪客檢視`/content/us/en/experience/arctic-surfing-in-lofoten`，元件就會知道根據`/content/wknd/language-masters/en`產生導覽結構。

## 陰影網站結構支援 {#shadow-structure}

有時候，需要為訪客建立與實際網站結構不同的導覽功能表。 或許促銷活動應藉由重新排列內容清單的方式，在功能表中反白顯示特定內容。 使用僅僅重新導向至其他內容頁面的陰影頁面，導覽元件可以產生任何必要的任意導覽結構。

若要這麼做，您需要：

1. 建立影子頁面作為代表您所需網站結構的空白頁面。 這通常稱為陰影網站結構。
1. 在這些頁面的頁面屬性中設定&#x200B;**重新導向**&#x200B;值，以指向實際內容頁面。
1. 在陰影頁面的頁面屬性中，設定&#x200B;**在導覽中隱藏**&#x200B;選項。
1. 將導覽元件的&#x200B;**導覽根**&#x200B;值設定為指向新陰影網站結構的根。

接著，導覽元件會根據陰影網站結構來轉譯功能表。 元件轉譯的連結會指向陰影頁面重新導向到的實際內容頁面，而不是陰影頁面本身。 此外，元件會顯示實際頁面的名稱，並正確地反白顯示作用中的頁面，即使導覽是以陰影頁面為基礎。 導覽元件可讓陰影頁面有效地對訪客完全透明。

>[!NOTE]
>陰影頁面可讓您的導覽選項更具彈性，但請記住，此結構的維護是完全手動的。 如果您重新排列實際的網站內容或新增/移除內容，則必須視需要手動更新陰影結構。

>[!NOTE]
>轉譯陰影網站結構時，導覽邏輯只會遞回陰影頁面。 此邏輯不會遞回重新導向目的地的結構。

## 導覽中的重新導向 {#redirects}

當頁面具有重新導向目標時(無論它指向的是外部URL還是另一個AEM頁面)，則包含該點連結的導覽元件會直接指向重新導向目標的URL。

### 範例 {#redirect-example}

* 建立重新導向至頁面B的頁面A。
* 建立重新導向至`https://aemcomponents.dev`的頁面C
* 在頁面D上，插入包含頁面A和C的或導覽元件
* 接著產生的個別連結會直接指向頁面B和`https://aemcomponents.dev`

## 範例元件輸出 {#sample-component-output}

若要體驗導覽元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_navigation_tw)。

## 技術細節 {#technical-details}

在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_navigation_v1_tw)上可找到有關導覽元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

>[!NOTE]
>
>截至核心元件2.1.0版，導覽元件支援[schema.org微資料](https://schema.org)。

## 編輯對話方塊 {#edit-dialog}

在編輯對話方塊中，內容作者可以定義導覽的根頁面，以及導覽結構的深度。

### 屬性標籤 {#properties-tab}

![導覽元件的編輯對話方塊屬性索引標籤](/help/assets/navigation-edit-properties.png)

* **導覽根** — 根頁面，將用來產生導覽樹狀結構。
* **排除根層級** — 通常根層級不應該包含在導覽中。 此選項可讓您指定從根開始往上，要排除多少個層級。 例如：
   * 0 =顯示根層級
   * 1 =排除根層級
   * 2 =排除根以及往上的1層
   * 等等。
* **收集所有子頁面** — 收集屬於導覽根目錄子系的所有頁面。
* **導覽結構深度** — 定義元件在導覽樹狀結構中應相對於導覽根目錄向下顯示多少層級（僅在未選取&#x200B;**收集所有子頁面**&#x200B;時可用）。
* **停用陰影** — 如果階層中的頁面是重新導向，將顯示重新導向頁面的名稱而非目標。 如需詳細資訊，請參閱[陰影網站結構支援](#shadow-structure)。
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 協助工具標籤 {#accessibility-tab}

![導覽元件的編輯對話方塊協助工具索引標籤](/help/assets/navigation-edit-accessibility.png)

在&#x200B;**協助工具**&#x200B;標籤上，可以為元件設定[ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤的值。

* **標籤** — 元件的ARIA標籤屬性值

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者設定向內容作者顯示的導覽根頁面和導覽深度的預設值。

### 屬性標籤 {#properties-tab-design}

![導覽元件的設計對話方塊](/help/assets/navigation-design.png)

* **導覽根目錄** — 導覽結構根目錄的預設值，將會用來產生導覽樹狀目錄，並在內容作者將元件新增至頁面時進行預設。
* **排除根層級** — 通常根層級不應該包含在導覽中。 此選項可讓您指定從根開始往上，要排除多少層級的預設值。 例如：
   * 0 =顯示根層級
   * 1 =排除根層級
   * 2 =排除根以及往上的1層
   * 等等。
* **收集所有子頁面** — 選項的預設值，用來收集屬於導覽根目錄子系的所有頁面。
* **導覽結構深度** — 導覽結構深度的預設值。
* **停用陰影** — 新增導覽元件時是否應停用陰影的預設值

### 樣式索引標籤 {#styles-tab}

導覽元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

導覽元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
