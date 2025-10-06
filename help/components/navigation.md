---
title: 導覽元件
description: 導覽元件可讓使用者輕鬆導覽全域化網站結構。
role: Architect, Developer, Admin, User
exl-id: 9154f2a3-3d1e-4865-a413-298748fa66d3
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '1544'
ht-degree: 100%

---


# 導覽元件{#navigation-component}

導覽元件可讓使用者輕鬆導覽全域化網站結構。

{{traditional-aem}}

## 用途 {#usage}

導覽元件會列出頁面的樹狀結構，讓網站的使用者可以輕鬆導覽網站結構。

導覽元件可以自動偵測您網站的全域化網站結構，並[自動調整至本地化的頁面。](#localized-site-structure)此外，它可以使用[影子重新導向頁面](#shadow-structure)支援任意網站結構，以代表您主要內容結構以外的其他結構。

透過[編輯對話框](#edit-dialog)，內容作者可定義導覽根頁面以及導覽深度。透過[設計對話框](#design-dialog)，範本作者可定義導覽根目錄和深度的預設值。

## 版本和相容性 {#version-and-compatibility}

導覽元件的目前版本為 v2，此版本於 2022 年 2 月隨著核心元件 2.18.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v2 | - | 相容 | 相容 | 相容 |
| [v1](v1/navigation.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 本地化網站結構支援 {#localized-site-structure}

網站通常以多種語言提供給不同地區。通常，每個本地化的頁面都會包含導覽元素，這些元素會包含在頁面範本中。透過導覽元件，您只需在範本上放置一次，即可套用至網站的所有頁面，並根據您的全域化網站結構，為個別的本地化頁面自動進行調整。

* 如需導覽元件本地化功能的運作方式範例，請參閱[下方章節](#example-localization)。
* 如需核心元件的本地化功能如何搭配運作的範例，請參閱[核心元件頁面的本地化功能](/help/get-started/localization.md)。

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

對於網站 WKND，您可能想要將導覽元件放置在頁面範本上作為頁首的一部分。一旦成為範本的一部分，您可以將元件的&#x200B;**導覽根目錄**&#x200B;設定為 `/content/wknd/language-masters/en`，因為這是您網站的主要內容開始的位置。您可能也會想要將&#x200B;**導覽結構深度**&#x200B;設為 `2`，因為您可能不希望元件顯示整個內容樹狀結構，而是只顯示前兩個層級，以做為概觀。

透過&#x200B;**導覽根目錄**&#x200B;值，導覽元件會知道在 `/content/wknd/language-masters/en` 之後為導覽開始位置，而且可以向下遞迴網站的結構兩個層級 (由&#x200B;**導覽結構深度**&#x200B;值所定義) 來產生導覽選項。

無論使用者檢視哪個本地化頁面，導覽元件都可藉由掌握目前頁面的位置，先回溯至根目錄，然後前進至對應頁面來尋找對應的本地化頁面。

因此，當訪客檢視 `/content/ch/de/experience/arctic-surfing-in-lofoten` 時，元件就會根據 `/content/wknd/language-masters/de` 產生導覽結構。同樣地，當訪客檢視 `/content/us/en/experience/arctic-surfing-in-lofoten` 時，元件就會根據 `/content/wknd/language-masters/en` 產生導覽結構。

## 影子網站結構支援 {#shadow-structure}

有時候，為訪客建立與實際網站結構不同的導覽功能表有其必要性。譬如在促銷活動中，也許需要重新排列內容清單來凸顯功能表中的特定內容。利用影子頁面只會重新導向至其他內容頁面的功能，導覽元件可以產生任何必要的任意導覽結構。

若要完成此操作，您需要：

1. 建立影子頁面作為代表您所需網站結構的空白頁面。這通常稱為影子網站結構。
1. 在這些頁面的頁面屬性中設定&#x200B;**重新導向**&#x200B;值，以指向實際內容頁面。
1. 在影子頁面的頁面屬性中，設定&#x200B;**在導覽中隱藏**&#x200B;選項。
1. 設定導覽元件的&#x200B;**導覽根目錄**&#x200B;值，以指向新影子網站結構的根。

接著，導覽元件會根據影子網站結構來轉譯功能表。元件轉譯的連結會指向影子頁面重新導向到的實際內容頁面，而不是影子頁面本身。此外，元件會顯示實際頁面的名稱，並正確地凸顯作用中的頁面，即使導覽是以影子頁面為基礎。導覽元件能有效地使訪客完全不會察覺到影子頁面。

>[!NOTE]
>影子頁面可讓您的導覽選項更具彈性，但請記住，此結構的維護是完全手動的。如果您重新排列實際的網站內容或新增/移除內容，則必須視需要手動更新影子結構。

>[!NOTE]
>轉譯影子網站結構時，導覽邏輯只會遞迴影子頁面。此邏輯不會遞迴重新導向目的地的結構。

## 導覽中的重新導向 {#redirects}

當頁面具有重新導向目標時 (無論它指向的是外部 URL 還是另一個 AEM 頁面)，則包含其連結的導覽元件會直接指向重新導向目標的 URL。

### 範例 {#redirect-example}

* 建立重新導向至頁面 B 的頁面 A。
* 建立重新導向至`https://aemcomponents.dev` 的頁面 C
* 在頁面 D 上，插入包含頁面 A 和 C 的導覽元件
* 接著產生的個別連結會直接指向頁面 B 和 `https://aemcomponents.dev`

## 範例元件輸出 {#sample-component-output}

若要體驗「導覽元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_navigation)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_navigation_v2)有關導覽元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

>[!NOTE]
>
>截至「核心元件」2.1.0 版，「導覽元件」支援 [schema.org 結構化資料](https://schema.org)。

## 編輯對話框 {#edit-dialog}

在編輯對話框中，內容作者可以定義導覽的根頁面，以及導覽結構的深度。

### 屬性索引標籤 {#properties-tab}

![導覽元件的編輯對話框屬性索引標籤](/help/assets/navigation-edit-properties.png)

* **導覽根目錄** - 根頁面，用於產生導覽樹狀結構。
* **排除根層級** - 通常根層級不應該包含在導覽中。此選項可讓您指定要從根目錄向上排除多少層級。例如：
   * 0 = 顯示根層級
   * 1 = 排除根層級
   * 2 = 排除根以及往上的 1 層
   * 以此類推
* **收集所有下層頁面** - 收集屬於導覽根目錄下層的所有頁面。
* **導覽結構深度** - 定義元件在導覽樹狀結構中應相對於導覽根目錄向下顯示多少層級 (僅在未選取&#x200B;**收集所有下層頁面**&#x200B;時可用)。
* **停用影子** - 如果階層中的頁面是重新導向，將顯示重新導向頁面的名稱而非目標。如需詳細資訊，請參閱[影子網站結構支援](#shadow-structure)。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

### 協助工具索引標籤 {#accessibility-tab}

![導覽元件的編輯對話框協助工具索引標籤](/help/assets/navigation-edit-accessibility.png)

在&#x200B;**協助工具**&#x200B;索引標籤上，可以設定元件的 [ARIA 協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤值。

* **標籤** - 元件的 ARIA 標籤屬性值

### 樣式索引標籤 {#styles-tab-edit}

導覽元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取想要套用至元件的樣式。在編輯對話框中所做的選取，與從元件工具列中選擇具有相同效果。

元件樣式必須在[設計對話框](#design-dialog)中設定，才能使用該下拉式選單。

![導覽元件編輯對話框的樣式索引標籤](/help/assets/navigation-edit-styles.png)

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可設定對內容作者呈現的導覽根頁面和導覽深度的預設值。

### 屬性索引標籤 {#properties-tab-design}

![導覽元件的設計對話框](/help/assets/navigation-design.png)

* **導覽根目錄** - 導覽結構根頁面的預設值，用於產生導覽樹狀結構，並在內容作者將元件新增至頁面時進行預設。
* **排除根層級** - 通常根層級不應該包含在導覽中。此選項可讓您指定要從根目錄向上排除多少層級的預設值。例如：
   * 0 = 顯示根層級
   * 1 = 排除根層級
   * 2 = 排除根以及往上的 1 層
   * 以此類推
* **收集所有下層頁面** - 該選項的預設值，用來收集屬於導覽根目錄下層的所有頁面。
* **導覽結構深度** - 導覽結構深度的預設值。
* **停用影子** - 新增導覽元件時是否應停用影子功能的預設值

### 樣式索引標籤 {#styles-tab}

導覽元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「導覽元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
