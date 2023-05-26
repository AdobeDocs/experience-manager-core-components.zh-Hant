---
title: 導覽元件(v1)
description: 導覽元件可讓使用者輕鬆導覽全域化的網站結構。
role: Architect, Developer, Admin, User
exl-id: 0b7de79a-e0c7-4cf9-b5a9-c78cbc3ecd2f
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 0%

---

# 導覽元件(v1) {#navigation-component}

導覽元件可讓使用者輕鬆導覽全域化的網站結構。

## 使用狀況 {#usage}

導覽元件會列出頁面的樹狀結構，方便網站的使用者導覽網站結構。

導覽元件可以自動偵測網站的全域化網站結構，並且 [自動調整以符合當地語系化的頁面。](#localized-site-structure) 此外，它可以使用支援任何任意網站結構 [陰影重新導向頁面](#shadow-structure) 以代表您的主要內容結構以外的其他結構。

此 [編輯對話方塊](#edit-dialog) 允許內容作者定義導覽根頁面以及導覽深度。 此 [設計對話方塊](#design-dialog) 可讓範本作者定義導覽根目錄和深度的預設值。

## 版本和相容性 {#version-and-compatibility}

本檔案說明導覽元件v1，此版本隨2018年1月的核心元件發行版本2.0.0的發佈引入。

>[!CAUTION]
>
>本檔案說明導覽元件v1。
>
>如需目前版本的導覽元件詳細資訊，請參閱 [導覽元件](/help/components/navigation.md) 檔案。

## 當地語系化網站結構支援 {#localized-site-structure}

網站通常以多種語言提供給不同地區。 通常，每個本地化的頁面都會包含導覽元素，此元素會包含在頁面範本中。 導覽元件可讓您將它放在網站所有頁面的範本上一次，然後它就會根據您的全域化網站結構自動適應個別本地化的頁面。

* 如需導覽元件本地化功能運作方式的範例，請參閱 [下節](#example-localization).
* 如需核心元件的本地化功能如何搭配運作的範例，請參閱 [核心元件頁面的本地化功能](/help/get-started/localization.md).

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

對於網站WKND，您可能想要將導覽元件放在頁面範本上作為標頭的一部分。 一旦成為範本的一部分，您就可以將 **導覽根目錄** 的元件至 `/content/wknd/language-masters/en` 因為這是您網站主要內容的開始位置。 您可能也想要設定 **導覽結構深度** 成為 `2` 因為您可能不希望元件顯示整個內容樹狀結構，而是隻顯示前兩個層級，以做為概觀。

使用 **導覽根目錄** 值，則導覽元件會在下列步驟後得知該 `/content/wknd/language-masters/en` 開始導覽，並向下遞回網站的結構兩級（如下列定義），即可產生導覽選項： **導覽結構深度** 值)。

無論使用者檢視哪個當地語系化頁面，導覽元件都可藉由知道目前頁面的位置、向後查詢到根目錄，然後前進到對應的頁面，來找到對應的當地語系化頁面。

因此，如果訪客正在檢視 `/content/ch/de/experience/arctic-surfing-in-lofoten`，元件就會知道要根據以下專案產生導覽結構： `/content/wknd/language-masters/de`. 同樣地，如果訪客正在檢視 `/content/us/en/experience/arctic-surfing-in-lofoten`，元件就會知道要根據以下專案產生導覽結構： `/content/wknd/language-masters/en`.

## 陰影網站結構支援 {#shadow-structure}

有時候，需要為訪客建立與實際網站結構不同的導覽功能表。 也許促銷活動應透過重新排列內容清單來反白選單中的某些內容。 使用陰影頁面（只是重新導向至其他內容頁面），導覽元件可產生任何必要的任意導覽結構。

若要這麼做，您需要：

1. 將陰影頁面建立為代表您所需網站結構的空白頁面。 這通常稱為陰影網站結構。
1. 設定 **重新導向** 這些頁面上頁面屬性中的值，以指向實際內容頁面。
1. 設定 **在導覽中隱藏** 陰影頁面的頁面屬性中的選項。
1. 設定 **導覽根目錄** 「導覽元件」的值，指向新陰影網站結構的根目錄。

接著，導覽元件會根據陰影網站結構來轉譯功能表。 元件轉譯的連結會指向陰影頁面重新導向到的實際內容頁面，而不是陰影頁面本身。 此外，元件會顯示實際頁面的名稱，並正確地反白顯示作用中頁面，即使導覽是以陰影頁面為基礎。 導覽元件有效地讓陰影頁面對訪客完全透明。

>[!NOTE]
>陰影頁面可讓導覽選項更具彈性，但請記住，此結構的維護是全手動的。 如果您重新排列實際的網站內容或新增/移除內容，則必須視需要手動更新陰影結構。

>[!NOTE]
>轉譯陰影網站結構時，導覽邏輯只會遞回陰影頁面。 此邏輯不會遞回重新導向目的地的結構。

## 導覽中的重新導向 {#redirects}

當頁面具有重新導向目標時(無論它指向的是外部URL還是另一個AEM頁面)，則包含指向該點的連結的導覽元件會直接指向重新導向目標的URL。

### 範例 {#redirect-example}

* 建立重新導向至頁面B的頁面A。
* 建立重新導向到的頁面C `https://aemcomponents.dev`
* 在頁面D上，插入或包含頁面A和C的導覽元件
* 接著產生的個別連結會直接指向頁面B和 `https://aemcomponents.dev`

## 範例元件輸出 {#sample-component-output}

若要體驗導覽元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_navigation).

## 技術細節 {#technical-details}

有關導覽元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_navigation_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

>[!NOTE]
>
>截至核心元件2.1.0版，導覽元件支援 [schema.org microdata](https://schema.org).

## 編輯對話方塊 {#edit-dialog}

在編輯對話方塊中，內容作者可以定義導覽的根頁面和導覽結構的深度。

### 屬性標籤 {#properties-tab}

![導覽元件的「編輯」對話方塊屬性標籤](/help/assets/navigation-edit-properties.png)

* **導覽根目錄**  — 根頁面，將用於產生導覽樹狀結構。
* **排除根層級**  — 通常根目錄不應包含在導覽中。 此選項可讓您指定從根開始往上，要排除多少個層級。 例如：
   * 0 =顯示根層級
   * 1 =排除根層級
   * 2 =排除根以及往上1層
   * 等
* **收集所有子頁面**  — 收集屬於導覽根目錄子系的所有頁面。
* **導覽結構深度**  — 定義在導覽樹狀結構下方，元件應相對於導覽根目錄顯示多少層（僅在以下情況下可用） **收集所有子頁面** 未選取)。
* **停用陰影**  — 如果階層中的頁面是重新導向，將顯示重新導向頁面的名稱而非目標。 請參閱 [陰影網站結構支援](#shadow-structure) 以取得詳細資訊。
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 協助工具標籤 {#accessibility-tab}

![導覽元件的「編輯」對話方塊輔助功能索引標籤](/help/assets/navigation-edit-accessibility.png)

於 **協助工具** 標籤，可設定的值 [ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性值

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者設定向內容作者顯示的導覽根頁面和導覽深度的預設值。

### 屬性標籤 {#properties-tab-design}

![導覽元件的設計對話方塊](/help/assets/navigation-design.png)

* **導覽根目錄**  — 導覽結構的根頁面預設值，將用於產生導覽樹狀結構，並在內容作者將元件新增至頁面時預設該值。
* **排除根層級**  — 通常根目錄不應包含在導覽中。 此選項可讓您指定從根開始往上，要排除多少層級的預設值。 例如：
   * 0 =顯示根層級
   * 1 =排除根層級
   * 2 =排除根以及往上1層
   * 等
* **收集所有子頁面**  — 選項的預設值，用來收集屬於導覽根目錄子系的所有頁面。
* **導覽結構深度**  — 導覽結構深度的預設值。
* **停用陰影**  — 新增導覽元件時是否應停用陰影的預設值

### 樣式索引標籤 {#styles-tab}

導覽元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe使用者端資料層 {#data-layer}

導覽元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
