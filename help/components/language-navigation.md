---
title: 語言導覽元件
description: 語言導覽元件提供網站的語言/國家導覽，讓訪客可以在不同地區中導覽至相同頁面。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 10b218b4-c439-4a0f-a46f-0b15d78b0360
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 1%

---

# 語言導航元件{#language-navigation-component}

「語言導覽元件」提供網站的語言/國家導覽，讓訪客可以在不同地區中導覽至相同頁面。

## 使用狀況 {#usage}

網站通常針對不同地區提供多種語言版本。 語言導覽元件可讓訪客以不同語言/地區設定檢視相同的頁面。 因此，如果你是瑞士德語版網站的讀者，你可以輕鬆地切換到美國英語版的同一頁。 語言導航元件可處理理解站點語言結構並自動查找相應的頁面。

* 如需語言導覽元件本地化功能如何運作的範例，請參閱[下方的](#example)一節。
* 如需其他核心元件的本地化功能如何搭配運作的範例，請參閱核心元件頁面[本地化功能頁面](/help/get-started/localization.md)。

[edit對話框](#edit-dialog)允許定義全局站點導航根目錄以及導航應深入到結構中的深度。 範本作者可使用[設計對話方塊](#design-dialog)設定相同選項的預設值。

## 版本和相容性{#version-and-compatibility}

語言導覽元件的目前版本為v1，此版本於2018年1月隨核心元件2.0.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗語言導覽元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_langnav)。

## 技術詳細資訊{#technical-details}

有關語言導覽元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_langnav_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 設計對話框{#design-dialog}

編輯對話方塊可讓您定義全域網站導覽根目錄，以及導覽應深入到結構中的程度。

這些設定通常只需在頁面範本層級完成。 不過，您可透過[edit dialog](#edit-dialog)在頁面層級變更這些量度。

### 屬性頁簽{#properties-tab}

![語言導航元件的設計對話框](/help/assets/language-navigation-design.png)

* **導覽根目錄**
   * 這是網站語言導覽的開始位置。
   * 網站的語言結構從此根目錄下的下一層開始。
* **語言結構深度**
   * 這是&#x200B;**導覽根**&#x200B;下方的內容樹狀結構代表網站語言結構的數量。 範例：
      * `1` 通常表示您只能選擇語言。
      * `2` 通常意味著你可以選擇語言和國家。
      * `3` 通常表示您可以選擇語言、國家/地區。

#### 範例 {#example}

假設您的內容如下所示：

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

對於網站WKND，您可能會想要將語言導覽元件放置在頁面範本上，作為標題的一部分。 一旦加入範本，您就可以將元件的&#x200B;**導覽根**&#x200B;設為`/content/wknd`，因為這是您針對該網站的本地化內容開始的位置。 您也想將&#x200B;**語言結構深度**&#x200B;設為`2`，因為您的結構為兩個層級（國家/地區然後是語言）。

使用&#x200B;**導航根**&#x200B;值時，語言元件知道在`/content/wknd`之後，導航開始，它可以通過識別內容樹中的後兩個級別作為站點的語言導航結構（由&#x200B;**語言結構深度**&#x200B;值定義）來生成語言導航選項。

無論使用者正在檢視哪個頁面，語言導覽元件都能透過知道目前頁面的位置，並回溯至根目錄，然後轉送至對應的頁面，以其他語言找到對應的頁面。

### 樣式標籤{#styles-tab}

語言導航元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## 編輯對話框{#edit-dialog}

通常，語言導覽元件只需在網站的頁面範本中新增及設定。 不過，如果「語言導覽」元件需要新增至個別內容頁面，編輯對話方塊可讓內容作者設定與[設計對話方塊](#design-dialog)中所述相同的值。

此外，還可以設定&#x200B;**ID**。 此選項可控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一標識符。

* 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
* 若已指定ID，則作者應負責確認其唯一。
* 變更ID可能會影響CSS、JS和資料層追蹤。

![語言導航元件的編輯對話框](/help/assets/language-navigation-edit.png)

## Adobe客戶端資料層{#data-layer}

語言導航元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
