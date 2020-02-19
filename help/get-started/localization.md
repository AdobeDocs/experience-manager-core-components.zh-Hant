---
title: 核心元件的本地化功能
description: 核心元件的本地化功能
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 核心元件的本地化功能 {#localization-features-of-the-core-components}

許多網站都要求以本地化格式在多種語言和地區提供內容。 選取的核心元件提供智慧型參考解析度，讓您輕鬆針對所有本地化內容建立統一範本，並根據本地化網站結構自動調整。

## 範例——包含導覽和頁尾的本地化頁面 {#example}

大部分網站都需要在所有頁面上顯示頁尾。 這些頁尾在頁面的所有內容上通常都保持一致。 但是，對於本地化內容頁面，必須顯示該頁首或頁尾的本地化版本。

同樣地，導覽元件通常必須顯示在所有頁面上。 不過，它也需要反映本地化頁面的內容。

使用Navigation Core Component和 [Experience Fragment Core Component的本地化功能](/help/components/navigation.md) ，以及AEM的 [](/help/components/experience-fragment.md)[](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)可編輯範本，這項工作變得簡單。 此範例可進一步擴充，以便使 [用語言導覽元件](/help/components/language-navigation.md) 。

## 內容結構 {#content-structure}

AEM及其核心元件的所有本地化功能都有賴於明確且符合邏輯的內容結構，讓您的本地化內容更符合邏輯。

假設您的網站只是被呼叫， `my-site` 位於以下位置：

```
/content/my-site
```

我們也假設您使用英文製作網站，並以法文提供網站。 因此，如果您有一個簡單的頁面， `my-page` 稱為它，則會在網站內容樹狀結構的兩個本地化分支中找到：

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

它位於這些本地化分支之下，您將在其中建立其他網站頁面。

頁尾通常使用「體驗片段」製作，因此您需要英文和法文版本，就像您的頁面一樣。 不過，「體驗片段」不是頁面，而是可跨頁面重複使用的頁面部分，因此不會直接存 `/content` 在於您其餘的頁面。 他們會生活在自己的資料夾下，但是由於他們也必須本土化，因此其結構必須與您網站的本地化結構相反。

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

通過鏡像的本地化結構，核心元件可以找到相應頁面所需的本地化內容。

## 頁尾——體驗片段 {#xf-footer}

體驗片段元件非常有彈性，非常適合用於頁首或頁尾。

由於我們假設的網站提供英文和法文版本，因此我們需要建立兩個體驗片段，這兩個片段都 `footer` 在我們 [先前描述的位置中呼叫。](#content-structure)

![](/help/assets/screen-shot-2019-09-09-11.08.28.png)

## 頁面範本 {#template}

由於頁尾會出現在每個頁面上，因此我們需要將「體驗片段」新增至標準頁面範本。

我們的範本只是叫做 `my-template` 範本，並與其他範本一起定位：

```
/conf/my-site/settings/wcm/templates/my-template
```

在此範本中，我們將新增我們希望頁面以其為基礎的基本元件。

* [導覽元件](/help/components/navigation.md)
   * 導覽元件會顯示在每個頁面的頂端。
   * 在導覽元件中，我們定義導覽根目錄，並告知元件網站的導覽結構從何處開始。
   * 根據導覽根，元件可以自動找到對應的本地化內容。
* [容器元件](/help/components/container.md)
   * 每個頁面都會包含可編輯的容器元件，讓作者可以在頁面上置入其他內容。
* [體驗片段](/help/components/experience-fragment.md)
   * 我們使用我們的編寫語言將體驗片段元件指向代表頁尾的片段路徑。
   * 根據該片段的路徑和反映本地化頁面結構的體驗片段的結構，元件可以自動找到相應的本地化內容。
   ![](/help/assets/screen-shot-2019-09-09-11.20.10.png)

## 頁面 {#pages}

在網站結構和範本的設定上，內容作者只需將必要的內容加入網頁即可。 由於元件的範本和本地化邏輯，導覽和頁尾會自動新增至頁面並本地化。

例如，作者只需將文字元件等內容新增至英文和法文頁面（以下藍色表示）。

導覽元件和體驗片段元件來自頁面範本，並知道會根據本地化結構和頁面本身的位置（以下白色表示）自動顯示正確的內容。

![](/help/assets/screen-shot-2019-09-09-11.22.14.png)

## 整合在一起 {#fitting-it-all-together}

以下是這些簡單但強大的元素如何搭配運作，為內容作者提供本地化頁面的完整說明。

![](/help/assets/screen-shot-2019-09-09-11.27.58.png)
