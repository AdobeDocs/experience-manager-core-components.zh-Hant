---
title: 語言導覽元件
description: 語言導覽元件提供網站的語言／國家導覽，讓訪客可以在不同地區設定中導覽至相同頁面。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 1%

---


# Language Navigation Component{#language-navigation-component}

「語言導覽元件」提供網站的語言／國家導覽，讓訪客可以在不同地區設定中導覽至相同頁面。

## 使用狀況 {#usage}

網站通常針對不同地區提供多種語言版本。 語言導覽元件可讓訪客檢視不同語言／地區的相同頁面。 因此，如果您是瑞士德文版網站的讀者，則可輕鬆切換至相同頁面的美國英文版。 「語言導覽」元件可處理瞭解網站語言結構並自動尋找對應的頁面。

* 如需「語言導覽元件」的本地化功能如何運作的範例，請參 [閱下節](#example)。
* 如需其他核心元件的本地化功能如何搭配運作的範例，請參閱核心元 [件的本地化功能頁面](/help/get-started/localization.md)。

編輯 [對話方塊](#edit-dialog) ，可讓您定義全域網站導覽根目錄，以及導覽應深入的結構。 使用設 [計對話框](#design-dialog)，模板作者可以設定相同選項的預設值。

## 版本與相容性 {#version-and-compatibility}

目前的語言導覽元件版本為v1，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 雲端服務 |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗「語言導覽元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](https://adobe.com/go/aem_cmp_library_langnav)。

## 技術詳細資訊 {#technical-details}

有關語言導覽元件的最新技術文 [件可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_langnav_v1)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。

## 設計對話框 {#design-dialog}

編輯對話框允許定義全局站點導航根目錄以及導航應深入到結構中的程度。

通常，這些設定只需在頁面範本層級進行。 不過，您可以透過編輯對話方塊，在頁面層級 [變更](#edit-dialog)。

### 屬性標籤 {#properties-tab}

![語言導覽元件的設計對話方塊](/help/assets/language-navigation-design.png)

* **導覽根目錄**
   * 這是網站的語言導覽應該開始的位置。
   * 網站的語言結構從此根目錄下的下一層開始。
* **語言結構深度**
   * 這是導覽根目錄下的內容樹狀結構 **中** ，有多少層級代表網站的語言結構。 範例：
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

對於網站WKND，您可能想要將「語言導覽」元件置於頁面範本上，做為頁首的一部分。 範本一經包含，您就可將元件的 **Navigation Root** （導覽根）設 `/content/wknd` 定為，因為該網站的本地化內容就是從這裡開始。 您也想將「語言結構深 **度」設為** , `2` 因為您的結構是兩個層級（國家／地區接著語言）。

使用導 **覽根** (Navigation Root `/content/wknd` )值，語言元件會知道，在導覽開始後，它就可以產生語言導覽選項，方法是將內容樹中的下兩個層級辨識為網站的語言導覽結構(由「語言結構深度( **Language Structure Depth** )」值定義)。

無論使用者檢視的是哪個頁面，「語言導覽」元件都能以其他語言找到對應的頁面，方法是知道目前頁面的位置並向後工作至根目錄，然後轉送至對應的頁面。

### 樣式標籤 {#styles-tab}

「語言導覽元件」支援AEM [Style系統](/help/get-started/authoring.md#component-styling)。

## Edit Dialog {#edit-dialog}

通常，「語言導覽」元件只需新增至網站的頁面範本並加以設定。 不過，如果「語言導覽」元件需要新增至個別內容頁面，編輯對話方塊可讓內容作者設定與設計對話方塊中所述相 [同的值](#design-dialog)。

此外，您還可以設 **定ID**。 此選項可讓您控制HTML和資料層中元件的唯一識 [別碼](/help/developing/data-layer/overview.md)。

* 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
* 如果指定ID，則作者有責任確保其唯一性。
* 變更ID可能會影響CSS、JS和資料圖層追蹤。

![語言導覽元件的編輯對話方塊](/help/assets/language-navigation-edit.png)
