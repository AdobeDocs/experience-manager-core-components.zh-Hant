---
title: 核心元件的本地化特性
description: 核心元件的本地化特性
role: Architect, Developer, Admin, User
exl-id: 9140b65a-6dd7-4ec9-9095-6e8243ec8424
source-git-commit: 888719359f9a1d1c9dccff97fb639b332f2be54c
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 0%

---

# 核心元件的本地化特性 {#localization-features-of-the-core-components}

許多網站要求以跨多種語言和地理區域的本地化格式提供內容。 所選核心元件具有智慧參考解析度，可簡化為所有本地化內容建立統一模板的過程，這些模板可根據您的本地化網站結構自動調整。

## 示例 — 帶導航和頁腳的本地化頁面 {#example}

大多數網站都要求在所有頁面上都顯示頁腳。 這些頁腳通常在頁面的所有內容中保持一致。 但是，對於本地化內容頁面，需要顯示該頁眉或頁腳的本地化版本。

同樣，導航元件通常必須在所有頁面中顯示。 但是，它也需要反映本地化頁面的內容。

使用 [導航核心元件](/help/components/navigation.md) 和 [體驗片段核心元件](/help/components/experience-fragment.md) 以及 [可編輯模AEM板](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)，這就變成一項簡單的任務。 本示例可進一步擴展以使用 [語言導航元件](/help/components/language-navigation.md) 也是。

## 內容結構 {#content-structure}

其核心元件的所AEM有本地化功能都依賴於清晰且符合邏輯的內容結構。

假設您的站點僅被稱為 `my-site` 並位於此處：

```
/content/my-site
```

還假設您用英語編寫站點並用法語提供。 所以如果你有一個簡單的頁面 `my-page` 它位於站點內容樹中的兩個本地化分支中：

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

它位於這些本地化分支下，您將在其中建立其他網站頁。

頁腳通常使用「體驗片段」建立，因此您需要英文和法文版本，就像您的頁面一樣。 但「體驗片段」不是頁面，而是可跨頁面重複使用的頁面的一部分，因此它們不直接位於 `/content` 你的其餘頁面。 相反，它們位於自己的資料夾下，但由於它們也必須進行本地化，因此其結構必須鏡像您站點的本地化結構。

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

## 頁腳 — 體驗片段 {#xf-footer}

體驗片段元件非常靈活，非常適合於頁眉或頁腳。

由於我們假設的網站是英文和法文的，因此我們需要建立兩個「體驗片段」，這兩個片段都稱為 `footer` [我們之前描述的地點。](#content-structure)

![](/help/assets/screen-shot-2019-09-09-11.08.28.png)

## 頁面範本 {#template}

由於頁腳將顯示在每頁上，因此我們需要將「體驗片段」添加到標準頁面模板中。

我們的模板簡稱為 `my-template` 與其他模板一起：

```
/conf/my-site/settings/wcm/templates/my-template
```

在此模板中，我們將添加我們希望頁面基於的基本元件。

* [導航元件](/help/components/navigation.md)
   * 導航元件將出現在每頁的頂部。
   * 在導航元件中，我們定義導航根，告知元件站點的導航結構的起始位置。
   * 基於導航根，元件可自動找到相應的本地化內容。
* [容器元件](/help/components/container.md)
   * 每個頁面都包含一個可編輯的容器元件，以便作者可以在頁面上放置其他內容。
* [體驗片段](/help/components/experience-fragment.md)
   * 我們將「體驗片段元件」(Experience Fragment Component)指向代表頁腳的片段的創作語言中的片段路徑。
   * 基於該片段的路徑和反映該局部化頁面結構的體驗片段的結構，該元件可以自動找到相應的局部化內容。

   ![](/help/assets/screen-shot-2019-09-09-11.20.10.png)

## 頁面 {#pages}

通過在網站結構和模板的設定上進行艱苦的工作，內容作者只需要在頁面中添加必要的內容。 由於這些模板和元件的本地化邏輯，導航和頁腳將自動添加到頁面並進行本地化。

例如，作者只需將文本元件等內容添加到英文和法文頁面（以下藍色表示）。

導航元件和體驗片段元件來自頁面模板，並知道根據本地化結構和頁面本身的位置（以下白色表示）自動顯示正確的內容。

![](/help/assets/screen-shot-2019-09-09-11.22.14.png)

## 將所有元件裝配在一起 {#fitting-it-all-together}

下面是這些簡單但功能強大的元素如何協作為內容作者提供本地化頁面的完整圖片。

![](/help/assets/screen-shot-2019-09-09-11.27.58.png)
