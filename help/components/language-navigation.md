---
title: 語言導航元件
description: 語言導航元件為站點提供語言/國家/地區導航，以便訪問者可以在不同的區域環境中導航到同一頁面。
role: Architect, Developer, Admin, User
exl-id: 10b218b4-c439-4a0f-a46f-0b15d78b0360
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 1%

---

# 語言導航元件{#language-navigation-component}

語言導航元件為站點提供語言/國家/地區導航，以便訪問者可以在不同區域設定中導航到同一頁。

## 使用狀況 {#usage}

網站通常以多種語言提供，適用於不同的區域。 語言導航元件允許訪問者以不同的語言/語言環境查看同一頁面。 因此，如果你是瑞士德語版網站的讀者，你可以輕鬆地切換到美國英語版的同一頁。 「語言導航」元件可處理對站點語言結構的理解並自動查找相應頁面。

* 有關語言導航元件的本地化功能如何工作的示例，請參見 [下面一節](#example)。
* 有關其他核心元件的本地化功能如何協同工作的示例，請參見 [「核心元件」頁的本地化功能](/help/get-started/localization.md)。

的 [編輯對話框](#edit-dialog) 允許定義全局站點導航根，以及導航應深入到的結構。 使用 [設計對話框](#design-dialog)，模板作者可以設定相同選項的預設值。

## 版本和相容性 {#version-and-compatibility}

語言導航元件的當前版本是v2，該版本於2022年2月隨核心元件2.18.0版一起推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | - | 相容 | 相容 |
| [v1](v1/language-navigation.md) | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗語言導航元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_langnav)。

## 技術詳細資訊 {#technical-details}

有關語言導航元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_langnav_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 設計對話框 {#design-dialog}

設計對話框允許定義全局站點導航根以及導航應深入到結構中的程度。

通常，這些配置只需在頁面模板級別完成。 但是，可以通過 [編輯對話框](#edit-dialog)。

### 屬性頁籤 {#properties-tab}

![語言導航元件的設計對話框](/help/assets/language-navigation-design.png)

* **導覽根目錄**
   * 這是站點的語言導航的開始位置。
   * 站點的語言結構從此根下面的下一級開始。
* **語言結構深度**
   * 這是以下內容樹的多少級 **導航根** 表示站點的語言結構。 範例：
      * `1` 通常意味著你只有語言的選擇。
      * `2` 通常意味著你有語言和國家的選擇。
      * `3` 通常意味著您有語言、國家和地區的選擇。

#### 範例 {#example}

假設您的內容類似以下內容：

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

對於站點WKND，您可能希望將「語言導航」元件作為頁眉的一部分置於頁面模板上。 一旦成為模板的一部分，您就可以 **導航根** 到 `/content/wknd` 因為這是您針對該站點的本地化內容的開始。 您還要設定 **語言結構深度** 要 `2` 因為你的結構是兩級（國家/地區）。

使用 **導航根** 值，語言元件知道 `/content/wknd` 通過將內容樹中的後兩個級別識別為站點的語言導航結構(由 **語言結構深度** 值)。

無論用戶正在查看什麼頁面，語言導航元件都可以通過知道當前頁面的位置並向後向根頁面查找相應頁面，然後轉發到相應頁面，從而用另一種語言找到相應頁面。

### 樣式頁籤 {#styles-tab}

語言導航元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## 編輯對話框 {#edit-dialog}

### 屬性頁籤 {#properties-tab-edit}

通常，只需在站點的頁面模板中添加和配置語言導航元件。 但是，如果需要將語言導航元件添加到單個內容頁面，則編輯對話框允許內容作者配置與中所述相同的值 [設計對話框](#design-dialog)

另外，您可以 **ID**。 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。

* 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
* 如果指定了ID，則作者有責任確保其唯一。
* 更改ID可能會影響CSS、JS和資料層跟蹤。

![語言導航元件的編輯對話框](/help/assets/language-navigation-edit.png)

### 輔助功能頁籤 {#accessibility-tab}

* **標籤**  — 如果頁面上有多種語言導航，以設定元件的詠嘆調標籤屬性，則應定義此選項。

![「語言導航輔助功能」頁籤](/help/assets/language-navigation-edit-accessibility.png)

### 樣式頁籤 {#styles-tab-edit}

語言導航元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便下拉菜單可用。

![語言導航元件的「編輯」對話框的「樣式」頁籤](/help/assets/language-navigation-edit-styles.png)

## Adobe客戶端資料層 {#data-layer}

語言導航元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
