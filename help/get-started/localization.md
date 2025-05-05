---
title: 核心元件的本地化功能
description: 核心元件的本地化功能
role: Architect, Developer, Admin, User
exl-id: 9140b65a-6dd7-4ec9-9095-6e8243ec8424
source-git-commit: 888719359f9a1d1c9dccff97fb639b332f2be54c
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%

---

# 核心元件的本地化功能 {#localization-features-of-the-core-components}

許多網站都要求以本地化格式跨多種語言和地理區域提供內容。 選取的核心元件具有智慧型參考解析功能，可讓您輕鬆為所有本地化內容建立統一的範本，並依據您的本地化網站結構自動調整。

## 範例 — 含導覽與頁尾的本地化頁面 {#example}

大多數網站都要求跨所有頁面顯示頁尾。 這些頁尾通常在頁面的所有內容中保持一致。 不過，如果是當地語系化的內容頁面，則需要顯示該頁首或頁尾的當地語系化版本。

同樣地，導覽元件通常必須跨所有頁面顯示。 不過，它也必須反映當地語系化頁面的內容。

使用[導覽核心元件](/help/components/navigation.md)和[體驗片段核心元件](/help/components/experience-fragment.md)的本地化功能，以及AEM[&#128279;](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)的可編輯範本，這項工作就會變得簡單。 此範例可進一步延伸以使用[語言導覽元件](/help/components/language-navigation.md)。

## 內容結構 {#content-structure}

AEM及其核心元件的所有本地化功能，都仰賴本地化內容的清晰邏輯內容結構。

假設您的網站名稱為`my-site`，且位於此處：

```
/content/my-site
```

假設您以英文撰寫網站，並提供法文版本。 因此，如果您有一個名為`my-page`的簡單頁面，則會在您網站的內容樹狀結構中找到該頁面的兩個本地化分支：

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

您將在這些本地化分支下建立其他網站頁面。

頁尾通常使用體驗片段來建立，因此您將需要英文版和法文版，就像您的頁面一樣。 不過，體驗片段不是頁面，而是可跨頁面重複使用的頁面部分，因此不會直接在`/content`下存放，做為您的其餘頁面。 相反地，它們位在自己的資料夾下，但由於它們也必須本地化，因此其結構必須映象您網站的本地化結構。

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

核心元件可透過映象本地化結構找到對應頁面所需的本地化內容。

## 頁尾 — 體驗片段 {#xf-footer}

體驗片段元件非常靈活，非常適用於頁首或頁尾。

由於我們假定的網站有英文和法文兩種版本，因此我們必須在先前描述的位置建立兩個稱為`footer` [的體驗片段。](#content-structure)

![](/help/assets/screen-shot-2019-09-09-11.08.28.png)

## 頁面範本 {#template}

由於頁尾會出現在每個頁面上，因此我們需要將體驗片段新增至標準頁面範本。

我們的範本稱為`my-template`，與其他範本位於同一位置：

```
/conf/my-site/settings/wcm/templates/my-template
```

在此範本中，我們將新增頁面所依據的基本元件。

* [導覽元件](/help/components/navigation.md)
   * 導覽元件會出現在每個頁面的頂端。
   * 在導覽元件中，我們會定義導覽根目錄，告知元件網站的導覽結構從何處開始。
   * 元件可依據導覽根目錄，自動尋找對應的本地化內容。
* [容器元件](/help/components/container.md)
   * 每個頁面都會包含可編輯的容器元件，方便作者在頁面上放置其他內容。
* [體驗片段](/help/components/experience-fragment.md)
   * 我們將體驗片段元件指向代表頁尾之片段的製作語言中的片段路徑。
   * 元件會自動根據片段的路徑以及映象本地化頁面結構的體驗片段結構來尋找對應的本地化內容。

  ![](/help/assets/screen-shot-2019-09-09-11.20.10.png)

## 頁面 {#pages}

藉由設定網站結構和範本的辛勤工作，內容作者只需將必要內容新增到頁面即可。 有了範本和元件的本地化邏輯，導覽和頁尾會自動新增到頁面並進行本地化。

例如，作者只需將文字元件等內容新增至英文和法文頁面（以下用藍色表示）。

導覽元件和體驗片段元件來自頁面範本，並會根據本地化結構和頁面本身的位置（以下以白色表示）知道要自動顯示正確的內容。

![](/help/assets/screen-shot-2019-09-09-11.22.14.png)

## 將所有元件配合在一起 {#fitting-it-all-together}

以下為這些簡單但功能強大的元素如何搭配運作，為內容作者提供當地語系化頁面的完整圖片。

![](/help/assets/screen-shot-2019-09-09-11.27.58.png)
