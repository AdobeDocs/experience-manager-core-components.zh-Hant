---
title: 核心元件的本地化功能
seo-title: 核心元件的本地化功能
description: 核心元件的本地化功能
seo-description: 核心元件的本地化功能
content-type: 引用
topic-tags: 核心元件
index: y
internal: n
translation-type: tm+mt
source-git-commit: c4e86960ec271464661193f6409cd93d1b9ec51b

---


# 核心元件的本地化功能 {#localization-features-of-the-core-components}

許多網站都需要以本地化格式提供內容，以提供多種語言和地理位置。選取的核心元件功能智慧參考轉譯可讓您輕鬆建立所有本地化內容的統一範本，以便根據本地化的網站結構自動調整。

## 範例-含導覽和頁尾的本地化頁面 {#example}

大部分網站都需要頁尾存在於所有頁面上。這些頁尾通常會在頁面的所有內容上保持一致。但對於本地化內容頁面，則需要顯示本地化版本的頁首或頁尾。

同樣地，導覽元件通常必須顯示在所有頁面上。但是，它也需要反映本地化頁面的內容。

使用 [Navigation Core Component Component](navigation.md) and [Experience片段核心元件](experience-fragment.md) 的本地化功能以及AEM [](https://docs.adobe.com/content/help/en/experience-manager-64/authoring/siteandpage/templates.html)可編輯的範本，這項工作就會成為一項任務。

## 內容結構 {#content-structure}

AEM及其核心元件的所有本土化功能都依賴於您本地化內容的清楚邏輯內容結構。

假設您的網站只是被呼叫 `my-site` ，位於以下位置：

```
/content/my-site
```

也可以讓我們以英文製作您的網站，並以法文提供。因此，如果您有一個簡單的頁面，則 `my-page` 會在您網站內容樹狀目錄中的兩個本地化分支中找到這個頁面：

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

您可在這些本地化分支下建立其他網站頁面。

頁尾通常使用Experience片段製作，因此您需要的英文版和法文版就像頁面一樣。不過，「體驗片段」並非頁面，而是可跨頁面重復使用的頁面部分，因此它們不會直接位於 `/content` 您的其餘頁面下。它們是位於自己的資料夾下，但由於它們也必須本地化，因此其結構必須反映您網站的本地化結構。

```
/content
+-- experience-fragments
   +-- en
      \-- footer
   \-- fr
      \-- footer
\-- my-site
   +-- en
      \-- my-page
   \-- fr
      \-- my-page
```

核心元件可透過鏡像本地化結構，找出對應頁面的必要本地化內容。

## 頁尾-體驗片段 {#xf-footer}

Experience片段元件非常靈活，非常適合頁面頁首或頁尾。

由於我們的網站以英文和法文提供，所以我們需要建立兩個「體驗片段」，這兩個片段都在 `footer`[先前所述的位置中呼叫。](#content-structure)

![](assets/screen-shot-2019-09-09-11.08.28.png)

## 頁面範本 {#template}

由於頁尾會出現在每個頁面上，所以我們需要將「體驗片段」新增至標準頁面範本。

我們的範本只會被呼叫 `my-template` ，並與其他範本搭配使用：

```
/conf/my-site/settings/wcm/templates/my-template
```

在本範本中，我們將新增想要以頁面為基礎的基本元件。

* [導覽元件](navigation.md)
   * 導覽元件會出現在每個頁面的頂端。
   * 在導覽元件中，我們定義導覽根目錄，告知網站導覽結構開始的元件。
   * 元件可根據導覽根目錄自動尋找對應的本地化內容。
* [容器元件](container.md)
   * 每個頁面都包含可編輯的容器元件，讓作者可以在頁面上放置其他內容。
* [體驗片段](experience-fragment.md)
   * 我們將Expert片段元件指向片段的製作語言，以代表頁尾的片段語言。
   * 此元件可根據該片段的路徑和反映本地化頁面結構的體驗片段結構，自動尋找對應的本地化內容。
   ![](assets/screen-shot-2019-09-09-11.20.10.png)

## 頁面 {#pages}

在設定網站結構和範本時，內容作者只需要新增必要內容至頁面。由於元件的範本和本土化邏輯，導覽和頁尾將會自動新增至頁面和本土化。

例如，作者只需要將文字元件加入英文和法文頁面(以藍色表示)。

「Navigation Component」(導覽元件)和「Experience片段元件(Experience片段元件)」來自頁面範本，並知道根據本地化結構和頁面本身的位置(以下方的白色表示)自動顯示正確內容。

![](assets/screen-shot-2019-09-09-11.22.14.png)

## 將它全部整合在一起 {#fitting-it-all-together}

以下完整瞭解這些簡單但強大的元素如何搭配運作，為內容作者提供本土化頁面。

![](assets/screen-shot-2019-09-09-11.27.58.png)
