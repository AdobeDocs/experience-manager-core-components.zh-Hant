---
title: 導覽元件
description: 導覽元件可讓使用者輕鬆導覽全球化網站結構。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '1387'
ht-degree: 1%

---


# 導覽元件{#navigation-component}

導覽元件可讓使用者輕鬆導覽全球化網站結構。

## 使用狀況 {#usage}

導覽元件會列出頁面樹狀結構，讓網站的使用者可輕鬆導覽網站結構。

導覽元件可自動偵測您網站的全球化網站結構，並且[可自動調整至本地化頁面。](#localized-site-structure) 此外，它可支援任何任意的網站結構，方 [法是使用](#shadow-structure) 陰影重新導向頁面來表示主要內容結構以外的其他結構。

[edit dialog](#edit-dialog)可讓內容作者定義導覽根頁面以及導覽深度。 [design對話框](#design-dialog)允許模板作者定義導航根和深度的預設值。

## 本地化網站結構支援{#localized-site-structure}

網站通常針對不同地區提供多種語言版本。 通常，每個本地化頁面都會包含作為頁面範本一部分的導覽元素。 「導覽元件」可讓您將它放置在網站所有頁面的範本上一次，然後它會根據您的全球化網站結構自動調整個別本地化頁面。

* 如需導覽元件本地化功能如何運作的範例，請參閱[下方的](#example-localization)一節。
* 有關核心元件的本地化功能如何協同工作的示例，請參閱核心元件的[本地化功能頁](/help/get-started/localization.md)。

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

對於網站WKND，您可能想要將導覽元件置於頁面範本上，做為頁首的一部分。 在範本中加入後，您就可將元件的&#x200B;**導覽根**&#x200B;設為`/content/wknd/language-masters/en`，因為這是該網站的主要內容的開始位置。 您可能也想將&#x200B;**導覽結構深度**&#x200B;設為`2`，因為您可能不希望元件顯示整個內容樹狀結構，而是前兩個層級，以做為總覽。

使用&#x200B;**導覽根**&#x200B;值，導覽元件會知道在`/content/wknd/language-masters/en`開始導覽後，它可以透過向下遞回網站結構兩個層級（如&#x200B;**導覽結構深度**&#x200B;值所定義）來產生導覽選項。

無論使用者檢視的是哪個本地化頁面，Navigation元件都能透過知道目前頁面的位置、向後工作至根目錄，然後轉送至對應的頁面，來尋找對應的本地化頁面。

因此，如果訪客檢視`/content/ch/de/experience/arctic-surfing-in-lofoten`，元件會知道根據`/content/wknd/language-masters/de`產生導覽結構。 同樣地，如果訪客檢視`/content/us/en/experience/arctic-surfing-in-lofoten`，元件會知道根據`/content/wknd/language-masters/en`產生導覽結構。

## 陰影網站結構支援{#shadow-structure}

有時，必須為訪客建立不同於實際網站結構的導覽功能表。 或許促銷活動應重新排列內容清單，以反白顯示功能表中的特定內容。 使用陰影頁面（只會重新導向至其他內容頁面），導覽元件可產生任何必要的任意導覽結構。

若要這麼做，您必須：

1. 將陰影頁面建立為代表您所需網站結構的空白頁面。 這通常稱為陰影網站結構。
1. 在這些頁面的頁面屬性中設定&#x200B;**Redirect**&#x200B;值，以指向實際的內容頁面。
1. 在陰影頁的頁面屬性中設定「在導航中隱藏」選項。****
1. 將導航元件的&#x200B;**導航根**&#x200B;值設定為指向新陰影站點結構的根。

然後，「導覽元件」會根據陰影網站結構來轉換功能表。 元件轉譯的連結是實際內容頁面，陰影頁面會重新導向至實際內容頁面，而非陰影頁面本身。 此外，元件會顯示實際頁面的名稱，並正確反白顯示作用中頁面，即使導覽是以陰影頁面為基礎。 導覽元件可讓陰影頁面對訪客完全透明。

>[!NOTE]
>陰影頁面可讓您的導覽選項更有彈性，但請記住，此結構的維護是完全手動的。 如果您重新排列實際的網站內容或新增／移除內容，則需要視需要手動更新陰影結構。

>[!NOTE]
>在呈現陰影網站結構時，導覽邏輯只會遞回陰影網頁。 該邏輯不會重複重新導向目的地的結構。

## 版本和相容性{#version-and-compatibility}

目前的導覽元件版本為v1，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗導覽元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_navigation)。

## 技術詳細資訊{#technical-details}

有關導覽元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_navigation_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

>[!NOTE]
>
>自2.1.0版核心元件起，導覽元件支援[schema.org microdata](https://schema.org)。

## 編輯對話框{#edit-dialog}

在編輯對話方塊中，內容作者可以定義導覽的根頁面，以及導覽結構的深度。

### 屬性頁籤{#properties-tab}

![導航元件的編輯對話框屬性頁籤](/help/assets/navigation-edit-properties.png)

* **導覽根** -將用來產生導覽樹的根頁面。
* **排除根層級** -導覽中通常不應包含根層級。此選項可讓您指定要從根目錄上排除的層數。 例如：
   * 0 =顯示根級別
   * 1 =排除根層級
   * 2 =排除根目錄和1個以上層級
   * 等等。
* **收集所有子頁面** -收集所有屬於導覽根目錄子項的頁面。
* **導覽結構深度** -定義元件在導覽樹狀結構下應相對於導覽根顯示多少層次(僅當未選取「收集所有子頁面」時 **** 才可用)。
* **停用遮蔽** -如果階層中的頁面是重新導向，則會顯示重新導向頁面的名稱，而非目標頁面。如需詳細資訊，請參閱[陰影網站結構支援](#shadow-structure)。
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

### 輔助功能頁籤{#accessibility-tab}

![導覽元件的編輯對話框輔助功能標籤](/help/assets/navigation-edit-accessibility.png)

在&#x200B;**Accessibility**&#x200B;標籤上，可為元件的[ARIA accessibility](https://www.w3.org/WAI/standards-guidelines/aria/)標籤設定值。

* **Label**  —— 元件的ARIA label屬性的值

## 設計對話框{#design-dialog}

設計對話框允許模板作者設定顯示給內容作者的導航根頁面和導航深度的預設值。

### 屬性頁籤{#properties-tab-design}

![導覽元件的設計對話方塊](/help/assets/navigation-design.png)

* **導覽根** -導覽結構的根頁面的預設值，此值將用於產生導覽樹，並在內容作者將元件新增至頁面時預設。
* **排除根層級** -導覽中通常不應包含根層級。此選項可讓您指定您要排除之根目錄上限的預設值。 例如：
   * 0 =顯示根級別
   * 1 =排除根層級
   * 2 =排除根目錄和1個以上層級
   * 等等。
* **收集所有子頁面** -用於收集所有作為導航根目錄子體的頁面的選項的預設值。
* **導覽結構深度** -導覽結構深度的預設值。
* **停用遮蔽** -新增導覽元件時，是否應停用遮蔽的預設值

### 樣式標籤{#styles-tab}

導航元件支AEM持[樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層{#data-layer}

導航元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
