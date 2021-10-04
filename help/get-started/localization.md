---
title: 核心元件的本地化功能
description: 核心元件的本地化功能
role: Architect, Developer, Admin, User
exl-id: 9140b65a-6dd7-4ec9-9095-6e8243ec8424
source-git-commit: 888719359f9a1d1c9dccff97fb639b332f2be54c
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 0%

---

# 核心元件的本地化功能 {#localization-features-of-the-core-components}

許多網站都要求以跨多種語言和地理位置的本地化格式提供內容。 選取的核心元件提供智慧型參考解析度，可讓您輕鬆為所有本地化內容建立統一的範本，並根據您的本地化網站結構自動調整。

## 範例 — 包含導覽和頁尾的本地化頁面 {#example}

大部分網站都需要在所有頁面上顯示頁尾。 這些頁腳通常在頁面的所有內容中保持一致。 不過，若是本地化內容頁面，則必須顯示該頁首或頁尾的本地化版本。

同樣地，導覽元件通常必須顯示在所有頁面上。 不過，這也需要反映本地化頁面的內容。

使用[導覽核心元件](/help/components/navigation.md)和[體驗片段核心元件](/help/components/experience-fragment.md)的本地化功能，以及AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)的[可編輯範本，這將變成一項簡單的工作。 此示例可進一步擴展為使用[語言導航元件](/help/components/language-navigation.md)。

## 內容結構 {#content-structure}

AEM及其核心元件的所有本地化功能，都有賴於清晰且符合邏輯的內容結構。

假設您的網站僅稱為`my-site`，且位於此處：

```
/content/my-site
```

也可以說您使用英文撰寫網站，並以法文提供。 因此，如果您有一個名為`my-page`的簡單頁面，則會在網站內容樹狀結構的兩個本地化分支中找到：

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

它位於這些本地化分支下，您將在其中建立其他網站頁面。

頁尾通常使用體驗片段製作，因此您需要的英文和法文版本與頁面相同。 不過，體驗片段不是頁面，而是可在各頁面重複使用的頁面的一部分，因此不會直接在`/content`下方顯示，作為其餘的頁面。 而是存放於自己的資料夾下，但由於這些資料夾也必須經過本地化，因此其結構必須與網站的本地化結構相反。

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

## 頁尾 — 體驗片段 {#xf-footer}

體驗片段元件非常彈性，非常適合頁首或頁尾。

因為我們的假設網站提供英文和法文版，因此我們需要在先前描述的位置中建立兩個稱為`footer` [的體驗片段。](#content-structure)

![](/help/assets/screen-shot-2019-09-09-11.08.28.png)

## 頁面範本 {#template}

因為頁尾會顯示在每個頁面上，因此我們需要將體驗片段新增至標準頁面範本。

我們的範本簡稱為`my-template`，並與其他範本一起位置：

```
/conf/my-site/settings/wcm/templates/my-template
```

在此範本中，我們將新增您希望頁面所依據的基本元件。

* [導覽元件](/help/components/navigation.md)
   * 導覽元件會顯示在每個頁面的頂端。
   * 在導覽元件中，我們定義導覽根目錄，告訴元件網站的導覽結構從何開始。
   * 元件可以根據導覽根，自動尋找對應的本地化內容。
* [容器元件](/help/components/container.md)
   * 每個頁面都會包含可編輯的容器元件，供作者在頁面上放置其他內容。
* [體驗片段](/help/components/experience-fragment.md)
   * 我們會以代表頁尾的片段製作語言，將體驗片段元件指向片段路徑。
   * 根據該片段的路徑以及鏡射本地化頁面結構的體驗片段結構，元件可自動尋找對應的本地化內容。

   ![](/help/assets/screen-shot-2019-09-09-11.20.10.png)

## 頁面 {#pages}

內容作者在設定網站結構和範本時，不費吹灰之力，只需將必要的內容新增至頁面即可。 由於這些範本和元件的本地化邏輯，導覽和頁尾會自動新增至頁面並翻譯。

例如，作者只需將文字元件等內容新增至英文和法文頁面（以下藍色表示）。

導覽元件和體驗片段元件來自頁面範本，且知道會根據本地化結構和頁面本身的位置（以下白色表示）自動顯示正確的內容。

![](/help/assets/screen-shot-2019-09-09-11.22.14.png)

## 把它整合在一起 {#fitting-it-all-together}

以下是這些簡單但強大的元素如何搭配運作，為內容作者提供本地化頁面的完整說明。

![](/help/assets/screen-shot-2019-09-09-11.27.58.png)
