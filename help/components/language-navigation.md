---
title: 語言導覽元件
description: 語言導覽元件提供網站的語言／國家導覽，讓訪客可以在不同地區設定中導覽至相同頁面。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---


# 語言導覽元件{#language-navigation-component}

「語言導覽元件」提供網站的語言／國家導覽，讓訪客可以在不同地區設定中導覽至相同頁面。

## 使用狀況 {#usage}

網站通常針對不同地區提供多種語言版本。 語言導覽元件可讓訪客檢視不同語言／地區的相同頁面。 因此，如果您是瑞士德文版網站的讀者，則可輕鬆切換至相同頁面的美國英文版。 「語言導覽」元件可處理瞭解網站語言結構並自動尋找對應的頁面。

* 如需語言導覽元件本地化功能如何運作的範例，請參閱[下方的](#example)一節。
* 有關其他核心元件的本地化功能如何協同工作的示例，請參閱核心元件的[本地化功能頁](/help/get-started/localization.md)。

[edit對話框](#edit-dialog)允許定義全局站點導航根目錄以及導航應深入到何種結構中。 使用[design對話框](#design-dialog)，模板作者可以設定相同選項的預設值。

## 版本和相容性{#version-and-compatibility}

目前的語言導覽元件版本為v1，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗語言導覽元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_langnav)。

## 技術詳細資訊{#technical-details}

有關語言導航元件[的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_langnav_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 設計對話框{#design-dialog}

編輯對話框允許定義全局站點導航根目錄以及導航應深入到結構中的程度。

通常，這些設定只需在頁面範本層級進行。 不過，您可透過[edit dialog](#edit-dialog)在頁面層級變更這些變數。

### 屬性頁籤{#properties-tab}

![語言導覽元件的設計對話方塊](/help/assets/language-navigation-design.png)

* **導覽根目錄**
   * 這是網站的語言導覽應該開始的位置。
   * 網站的語言結構從此根目錄下的下一層開始。
* **語言結構深度**
   * 這是&#x200B;**導覽根**&#x200B;下方的內容樹狀結構代表網站語言結構的層數。 範例：
      * `1` 通常表示您只有語言選擇。
      * `2` 通常意味著您可以選擇語言和國家。
      * `3` 通常表示您有語言、國家和地區的選擇。

#### 範例 {#example}

假設您的內容看起來像這樣：

```
/content
+-- wknd
   +-- language-masters
   +-- us
      +-- en
      \-- es
   \-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

對於網站WKND，您可能想要將「語言導覽」元件置於頁面範本上，做為頁首的一部分。 範本一經包含，您就可將元件的&#x200B;**導覽根**&#x200B;設為`/content/wknd`，因為此處就是該網站的本地化內容開始處。 您也希望將&#x200B;**語言結構深度**&#x200B;設為`2`，因為您的結構是兩個層級（國家／地區接著語言）。

使用&#x200B;**導覽根**&#x200B;值，語言元件知道在`/content/wknd`導覽開始後，它可以將內容樹中的下兩個層級識別為網站的語言導覽結構（如&#x200B;**語言結構深度**&#x200B;值所定義），以產生語言導覽選項。

無論使用者檢視的是哪個頁面，「語言導覽」元件都能以其他語言找到對應的頁面，方法是知道目前頁面的位置並向後工作至根目錄，然後轉送至對應的頁面。

### 樣式標籤{#styles-tab}

語言導航元件支AEM持[樣式系統](/help/get-started/authoring.md#component-styling)。

## 編輯對話框{#edit-dialog}

通常，「語言導覽」元件只需新增至網站的頁面範本並加以設定。 不過，如果「語言導覽」元件需要新增至個別內容頁面，編輯對話方塊可讓內容作者設定與[設計對話方塊](#design-dialog)中所述的相同值。

此外，您還可以設定&#x200B;**ID**。 此選項可控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。

* 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
* 如果指定ID，則作者有責任確保其唯一性。
* 變更ID可能會影響CSS、JS和資料圖層追蹤。

![語言導覽元件的編輯對話方塊](/help/assets/language-navigation-edit.png)

## Adobe客戶端資料層{#data-layer}

語言導航元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
