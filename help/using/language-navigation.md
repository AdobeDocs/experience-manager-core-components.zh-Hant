---
title: 語言導覽元件
seo-title: 語言導覽元件
description: 'null'
seo-description: 語言導覽元件提供網站的語言／國家導覽，讓訪客可以在不同地區設定中導覽至相同頁面。
uuid: ce736458-9cdf-4bc2-b90f-9c5a62fe1ca0
content-type: 引用
topic-tags: 編寫
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新功能
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
source-git-commit: c4e86960ec271464661193f6409cd93d1b9ec51b

---


# Language Navigation Component{#language-navigation-component}

「語言導覽元件」提供網站的語言／國家導覽，讓訪客可以在不同地區設定中導覽至相同頁面。

## 使用狀況 {#usage}

網站通常針對不同地區提供多種語言版本。 語言導覽元件可讓訪客檢視不同語言／地區的相同頁面。 因此，如果您是瑞士德文版網站的讀者，則可輕鬆切換至相同頁面的美國英文版。 「語言導覽」元件可處理對網站語言結構的瞭解，並自動尋找對應的頁面。

* 如需「語言導覽元件」的本地化功能如何運作的範例，請參 [閱下節](#example)。
* 如需其他核心元件的本地化功能如何搭配運作的範例，請參閱核心元 [件的本地化功能頁面](localization.md)。

編輯 [對話方塊](#edit-dialog) ，可讓您定義全域網站導覽根目錄，以及導覽應深入的結構。 使用設 [計對話框](#design-dialog)，模板作者可以設定相同選項的預設值。

## 版本與相容性 {#version-and-compatibility}

目前的語言導覽元件版本為v1，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗「語言導覽元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](http://opensource.adobe.com/aem-core-wcm-components/library/language-navigation/language-structure/us/en/language-navigation.html)。

## 技術詳細資訊 {#technical-details}

有關語言導覽元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## 設計對話框 {#design-dialog}

The edit dialog allows the definition of the global site navigation root as well as how deep into the structure the navigation should go.

通常，這些設定只需在頁面範本層執行。 不過，您可以透過編輯對話方塊，在頁面層級 [變更](#edit-dialog)。

### 屬性標籤 {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **導覽根目錄**
   * 這是網站的語言導覽應從這裡開始。
   * 網站的語言結構從此根目錄下的下一層開始。
* **語言結構深度**
   * 這是導覽根目錄下的內容樹狀結構 **中** ，有多少層級代表網站的語言結構。 範例：
      * `1` 通常表示您只有語言選擇。
      * `2` 通常是說，你有語言和國家的選擇。
      * `3` 通常表示您有語言、國家／地區的選擇。

#### 例如 {#example}

假設您的內容看起來像這樣：

```
/content
+-- we-retail
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

對於網站We.Retail，您可能會想將「語言導覽」元件置於頁面範本上，做為頁首的一部分。 範本一經包含，您就可將元件的 **Navigation Root** （導覽根）設 `/content/we-retail` 定為，因為該網站的本地化內容就是從這裡開始。 您也想將「語言結構深 **度」設為** , `2` 因為您的結構是兩個層級（國家／地區接著是語言）。

使用導 **覽根** (Navigation Root `/content/we-retail` )值，語言元件會知道，在導覽開始後，它就可以產生語言導覽選項，方法是將內容樹中的下兩個層級辨識為網站的語言導覽結構(由「語言結構深度( **Language Structure Depth** )」值定義)。

無論使用者檢視的是哪個頁面，「語言導覽」元件都能以其他語言找到對應的頁面，方法是知道目前頁面的位置並向後工作至根目錄，然後轉送至對應的頁面。

### 樣式標籤 {#styles-tab}

「語言導覽元件」支援AEM [Style系統](authoring.md#component-styling)。

## Edit Dialog {#edit-dialog}

通常，語言導覽元件只需要新增至網站的頁面範本並加以設定。 不過，如果「語言導覽」元件需要新增至個別內容頁面，編輯對話方塊可讓內容作者設定與設計對話方塊中所述相 [同的值](#design-dialog)。

![](assets/screen_shot_2018-01-12at133353.png)
