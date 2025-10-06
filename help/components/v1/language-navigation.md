---
title: 語言導覽元件 (v1)
description: 語言導覽元件提供網站的語言和國家/地區導覽，讓訪客可在不同地區設定下導覽至相同頁面。
role: Architect, Developer, Admin, User
exl-id: 41194ba0-6833-40e5-88d9-036e9c231edd
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '800'
ht-degree: 100%

---


# 語言導覽元件 (v1) {#language-navigation-component}

語言導覽元件提供網站的語言和國家/地區導覽，讓訪客可在不同地區設定下導覽至相同頁面。

## 用途 {#usage}

網站通常以多種語言提供給不同地區。語言導覽元件可讓訪客以不同語言/地區設定檢視相同頁面。因此，若您是網站瑞士德文版的讀者，可以輕鬆切換至相同頁面的美式英文版。語言導覽元件負責解析網站語言結構，並自動找到對應的頁面。

* 如需語言導覽元件本地化功能的運作方式範例，請參閱[下方章節](#example)。
* 如需其他核心元件的本地化功能如何搭配運作的範例，請參閱[核心元件頁面的本地化功能](/help/get-started/localization.md)。

[編輯對話框](#edit-dialog)可定義全域網站導覽根目錄，以及導覽應該深入結構的程度。範本作者可以使用[設計對話框](#design-dialog)設定相同選項的預設值。

## 版本和相容性 {#version-and-compatibility}

本文件說明語言導覽元件 v1，最初於 2018 年 1 月隨著核心元件 2.0.0 版發行導入。

>[!CAUTION]
>
>本文件說明語言導覽元件 v1。
>
>如需語言導覽元件目前版本的詳細資訊，請參閱[語言導覽元件](/help/components/language-navigation.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「語言導覽元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_langnav)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_langnav_v1)有關語言導覽元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設計對話框 {#design-dialog}

編輯對話框可定義全域網站導覽根目錄，以及導覽應該深入結構的程度。

這些設定通常只需在頁面範本層級完成。不過，可透過[編輯對話框](#edit-dialog)在頁面層級上進行變更。

### 屬性索引標籤 {#properties-tab}

![語言導覽元件的設計對話框](/help/assets/language-navigation-design.png)

* **導覽根目錄**
   * 這是網站語言導覽的開始位置。
   * 網站的語言結構會從此根目錄下的下一個層級開始。
* **語言結構深度**
   * **導覽根目錄**&#x200B;下的內容樹狀結構層級數目代表網站的語言結構。範例：
      * `1` 通常表示您只能選擇語言。
      * `2` 通常表示您可以選擇語言和國家/地區。
      * `3` 通常表示您可以選擇語言、國家/地區和區域。

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

對於網站 WKND，您可能想要將語言導覽元件放置在頁面範本上作為頁首的一部分。一旦成為範本的一部分，您可以將元件的&#x200B;**導覽根目錄**&#x200B;設定為 `/content/wknd`，因為這是您網站的本地化內容開始的位置。您也需要將&#x200B;**語言結構深度**&#x200B;設定為 `2` ，因為您的結構有兩個層級 (國家/地區然後語言)。

透過&#x200B;**導覽根目錄**&#x200B;值，語言元件會知道在 `/content/wknd` 之後為導覽開始位置，而且它可以將內容樹狀結構中的下兩個層級辨識為網站的語言導覽結構 (如&#x200B;**語言結構深度**&#x200B;值所定義)，以產生語言導覽選項。

無論使用者正在檢視哪個頁面，語言導覽元件都可藉由掌握目前頁面的位置，先回溯至根目錄，然後前進至對應頁面，以找出該對應頁面的其他語言版本。

### 樣式索引標籤 {#styles-tab}

語言導覽元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## 編輯對話框 {#edit-dialog}

通常，只需在網站的頁面範本中新增及設定語言導覽元件。不過，如果需要將語言導覽元件新增至個別內容頁面，內容作者可以利用編輯對話框來設定與[設計對話框](#design-dialog)中說明相同的值。

此外，您可以設定 **ID**。此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。

* 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
* 若已指定 ID，則作者應確保其為唯一識別碼。
* 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

![語言導覽元件的編輯對話框](/help/assets/language-navigation-edit.png)

## Adobe Client Data Layer {#data-layer}

「語言導覽元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
