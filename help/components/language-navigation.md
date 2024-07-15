---
title: 語言導覽元件
description: 語言導覽元件提供網站的語言/國家導覽，讓訪客可以導覽至不同地區設定的相同頁面。
role: Architect, Developer, Admin, User
exl-id: 10b218b4-c439-4a0f-a46f-0b15d78b0360
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 1%

---

# 語言導覽元件{#language-navigation-component}

語言導覽元件提供網站的語言/國家導覽，讓訪客可以導覽至不同地區設定的相同頁面。

## 使用情況 {#usage}

網站通常以多種語言提供給不同地區。 語言導覽元件可讓訪客檢視不同語言/地區設定的相同頁面。 因此，若您是網站瑞士德文版的讀者，可以輕鬆切換至相同頁面的美式英文版。 語言導覽元件可讓您瞭解網站語言結構，並自動找到對應的頁面。

* 如需語言導覽元件本地化功能的運作方式範例，請參閱[下節](#example)。
* 如需其他核心元件的本地化功能如何搭配運作的範例，請參閱核心元件頁面的[本地化功能](/help/get-started/localization.md)。

[編輯對話方塊](#edit-dialog)可定義全域網站導覽根目錄，以及導覽應該深入結構的程度。 範本作者可以使用[設計對話方塊](#design-dialog)設定相同選項的預設值。

## 版本和相容性 {#version-and-compatibility}

語言導覽元件的目前版本是v2，此版本隨2022年2月的核心元件發行版本2.18.0的發佈引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | - | 相容 | 相容 |
| [v1](v1/language-navigation.md) | 相容 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗語言導覽元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_langnav)。

## 技術細節 {#technical-details}

在GitHub](https://adobe.com/go/aem_cmp_tech_langnav_v2)上可找到有關語言導覽元件[的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓您定義全域網站導覽根目錄，以及導覽在結構中應該深入到什麼程度。

這些設定通常只需在頁面範本層級完成。 不過，可透過[編輯對話方塊](#edit-dialog)在頁面層級上變更它們。

### 屬性標籤 {#properties-tab}

![語言導覽元件的設計對話方塊](/help/assets/language-navigation-design.png)

* **導覽根目錄**
   * 這是網站語言導覽的開始位置。
   * 網站的語言結構會從此根目錄下的下一個層級開始。
* **語言結構深度**
   * **導覽根目錄**&#x200B;下的內容樹狀結構層級數目代表網站的語言結構。 範例：
      * `1`通常表示您只能選擇語言。
      * `2`通常表示您可以選擇語言和國家/地區。
      * `3`通常表示您可以選擇語言、國家/地區和地區。

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

對於網站WKND，您可能想要將語言導覽元件放在頁面範本上作為標頭的一部分。 一旦成為範本的一部分，您可以將元件的&#x200B;**導覽根目錄**&#x200B;設定為`/content/wknd`，因為這是您網站本地化內容的開始位置。 您也會想要將&#x200B;**語言結構深度**&#x200B;設為`2`，因為您的結構有兩個層級（國家/地區然後語言）。

透過&#x200B;**導覽根**&#x200B;值，語言元件知道在`/content/wknd`之後，導覽開始，而且它可以將內容樹狀結構中的下兩個層級辨識為網站的語言導覽結構（如&#x200B;**語言結構深度**&#x200B;值所定義），以產生語言導覽選項。

無論使用者正在檢視哪個頁面，語言導覽元件都可透過知道目前頁面的位置，並回溯至根目錄，然後前進至對應頁面，找到採用另一種語言的對應頁面。

### 樣式索引標籤 {#styles-tab}

語言導覽元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## 編輯對話方塊 {#edit-dialog}

### 屬性標籤 {#properties-tab-edit}

通常，只需在網站的頁面範本中新增及設定語言導覽元件。 不過，如果需要將語言導覽元件新增至個別內容頁面，內容作者可以利用「編輯」對話方塊來設定與[設計對話方塊](#design-dialog)中說明相同的值

此外，您可以設定&#x200B;**ID**。 此選項允許控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。

* 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
* 若指定ID，作者應負責確認該ID為唯一ID。
* 變更ID會對CSS、JS和資料層追蹤造成影響。

![語言導覽元件的編輯對話方塊](/help/assets/language-navigation-edit.png)

### 協助工具標籤 {#accessibility-tab}

* **標籤** — 如果頁面上有多個語言導覽來設定元件的aria標籤屬性，則應定義此選項。

![語言導覽協助工具標籤](/help/assets/language-navigation-edit-accessibility.png)

### 樣式索引標籤 {#styles-tab-edit}

語言導覽元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的選取具有相同的效果。

必須在[設計對話方塊](#design-dialog)中為此元件設定樣式，以便下拉式功能表可用。

語言導覽元件之[編輯]對話方塊的![樣式索引標籤](/help/assets/language-navigation-edit-styles.png)

## Adobe使用者端資料層 {#data-layer}

語言導覽元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
