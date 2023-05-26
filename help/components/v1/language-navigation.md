---
title: 語言導覽元件(v1)
description: 語言導覽元件提供網站的語言/國家導覽，讓訪客可以導覽至不同地區設定的相同頁面。
role: Architect, Developer, Admin, User
exl-id: 41194ba0-6833-40e5-88d9-036e9c231edd
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 0%

---

# 語言導覽元件(v1) {#language-navigation-component}

語言導覽元件提供網站的語言/國家導覽，讓訪客可以導覽至不同地區設定的相同頁面。

## 使用狀況 {#usage}

網站通常以多種語言提供給不同地區。 語言導覽元件可讓訪客以不同語言/地區設定檢視相同頁面。 因此，如果您是網站的瑞士德文版的讀者，可以輕鬆切換至相同頁面的美式英文版。 語言導覽元件可讓您瞭解網站語言結構，並自動找到對應的頁面。

* 如需語言導覽元件本地化功能運作方式的範例，請參閱 [下節](#example).
* 如需其他核心元件本地化功能如何搭配運作的範例，請參閱 [核心元件頁面的本地化功能](/help/get-started/localization.md).

此 [編輯對話方塊](#edit-dialog) 可定義全域網站導覽根目錄，以及導覽在結構中的深度。 使用 [設計對話方塊](#design-dialog)，範本作者可以設定相同選項的預設值。

## 版本和相容性 {#version-and-compatibility}

本檔案說明語言導覽元件v1，此元件隨2018年1月的核心元件發行版本2.0.0的發佈引入。

>[!CAUTION]
>
>本檔案說明語言導覽元件v1。
>
>如需目前版本的語言導覽元件詳細資訊，請參閱 [語言導覽元件](/help/components/language-navigation.md) 檔案。

## 範例元件輸出 {#sample-component-output}

若要體驗語言導覽元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_langnav).

## 技術細節 {#technical-details}

有關語言導覽元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_langnav_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設計對話方塊 {#design-dialog}

「編輯」對話方塊可讓您定義全域網站導覽根目錄，以及導覽在結構中應該深入到什麼程度。

這些設定通常只需在頁面範本層級完成。 不過，您可在頁面層級透過 [編輯對話方塊](#edit-dialog).

### 屬性標籤 {#properties-tab}

![語言導覽元件的設計對話方塊](/help/assets/language-navigation-design.png)

* **導覽根目錄**
   * 這是網站語言導覽的開始位置。
   * 網站的語言結構會從此根目錄下的下一個層級開始。
* **語言結構深度**
   * 這是目錄下的內容樹狀結構層級 **導覽根目錄** 代表網站的語言結構。 範例：
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

對於網站WKND，您可能想要將語言導覽元件放在頁面範本上作為標頭的一部分。 一旦成為範本的一部分，您就可以將 **導覽根目錄** 的元件至 `/content/wknd` 因為這是您網站本地化內容的開始位置。 您也會想要設定 **語言結構深度** 成為 `2` 因為您的結構有兩個層級（國家/地區然後語言）。

使用 **導覽根目錄** 值，則語言元件會在以下步驟後得知該 `/content/wknd` 會識別內容樹狀結構中的下兩個層級為網站的語言導覽結構(如 **語言結構深度** 值)。

無論使用者正在檢視哪個頁面，語言導覽元件都可藉由知道目前頁面的位置，並向後移至根目錄，然後向前移至對應頁面，找到其他語言的對應頁面。

### 樣式索引標籤 {#styles-tab}

語言導覽元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## 編輯對話方塊 {#edit-dialog}

通常，只需在網站的頁面範本中新增及設定語言導覽元件。 不過，如果需要將「語言導覽」元件新增至個別內容頁面，內容作者就可以利用「編輯」對話方塊來設定相同的值，如 [設計對話方塊](#design-dialog).

此外，您可以設定 **ID**. 此選項可讓您控制HTML和中的元件的唯一識別碼 [資料層](/help/developing/data-layer/overview.md).

* 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
* 若指定ID，作者應負責確認該ID是唯一的。
* 變更ID會對CSS、JS和資料層追蹤造成影響。

![語言導覽元件的編輯對話方塊](/help/assets/language-navigation-edit.png)

## Adobe使用者端資料層 {#data-layer}

語言導覽元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
