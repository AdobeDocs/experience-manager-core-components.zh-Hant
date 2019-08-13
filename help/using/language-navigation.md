---
title: 語言導覽元件
seo-title: 語言導覽元件
description: 'null'
seo-description: 語言導覽元件提供網站的語言/國家導覽，讓訪客能夠在不同地區中導覽至相同的頁面。
uuid: ce73458-1cdf-4bc2-b90 f-9c5 a62 fe1 ca0
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 8f232eb0-65d5-4075-8668-75f1366882c8
disttype: dist5
gnavtheme: 淺色
groupsectionnavitems: 否
hidemerchandisingbar: 繼承
hidepromocomponent: 繼承
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8a34ecc432e489b8dc025aeda29d8eba9c788861

---


# Language Navigation Component{#language-navigation-component}

語言導覽元件提供網站的語言/國家導覽，讓訪客能夠在不同地區中導覽至相同的頁面。

## 使用狀況 {#usage}

網站通常以多種語言提供給不同地區。語言導覽元件可讓訪客以不同語言/地區設定檢視相同頁面。所以，如果您是瑞士德文版的讀者，您可以輕鬆切換至相同頁面的英文版。語言導覽元件可處理網站語言結構，並以自動方式尋找對應的頁面。

[編輯對話方塊](#edit-dialog) 可讓您定義全域網站導覽根目錄，以及導覽應前往的結構深度。範本作者可以使用 [設計對話方塊](#design-dialog)，設定相同選項的預設值。

## 版本與相容性 {#version-and-compatibility}

目前版本的語言導覽元件是v1，它是在2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

若要體驗語言導覽元件，以及查看其組態選項以及HTML和JSON輸出的範例，請造訪 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library/language-navigation/language-structure/us/en/language-navigation.html)。

## 技術細節 {#technical-details}

有關語言導覽元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 設計對話方塊 {#design-dialog}

編輯對話方塊可讓您定義全域網站導覽根目錄，以及導覽應前往的結構深度。

通常這些組態只需要在頁面範本中完成。不過，您可以透過 [編輯對話方塊在頁面層級變更](#edit-dialog)它們。

### 屬性索引標籤 {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **導覽根目錄**
   * 這是網站的languge導覽應該開始的地方。
   * 網站的語言結構從根下方的下一個層級開始。
* **語言結構深度**
   * 這是 **導覽根目錄下方的內容樹狀結構層級** ，代表網站的語言結構。範例：
      * `1` 通常表示您只擁有語言的選擇。
      * `2` 這表示您可以選擇語言和國家。
      * `3` 通常表示您有選擇的緯度、國家和地區。

#### 例如 {#example}

假設您的內容看起來像這樣：

```
/content
+-- we-retail
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      +-- it
+-- wknd-events
\-- wknd-shop
```

對於我們的零售網站，您可能想要將語言導覽元件置於頁首，做為標題的一部分。之後，您可以將元件的 **導覽根目錄** 設定為元件的導覽根目錄， `/content/we-retail` 因為這就是該網站的本地化內容開始的地方。您也希望設定 **「語言結構深度」** ， `2` 因為您的結構有兩個層級(接著是國家)。

使用 **「導覽根目錄** 」值，語言元件會知道 `/content/we-retail` 導覽開始後，就可產生語言導覽選項，並將內容樹狀結構中的下個層級識別為網站的語言導覽結構(由 **「語言結構深度** 」值定義)。

不論使用者檢視哪個頁面，語言導覽元件都能以另一種語言找到對應頁面，方法是知道目前頁面的位置並回溯至根目錄，然後轉送至對應的頁面。

### 樣式標籤 {#styles-tab}

語言導覽元件支援AEM [樣式系統](authoring.md#component-styling)。

## Edit Dialog {#edit-dialog}

Languge導覽元件通常只需要新增至網站的頁面範本並設定。但是，如果需要將語言導覽元件新增至個別內容頁面，編輯對話方塊可讓內容作者設定相同值，如 [設計對話方塊](#design-dialog)所述。

![](assets/screen_shot_2018-01-12at133353.png)
