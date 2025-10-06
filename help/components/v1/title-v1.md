---
title: 標題元件 (v1)
description: 核心元件標題元件是區段標題元件，具備就地編輯的功能。
index: n
role: Architect, Developer, Admin, User
exl-id: 79549ac0-82f2-4ea0-9cce-d534d0b47b5c
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '320'
ht-degree: 100%

---


# 標題元件 (v1) {#title-component-v}

核心元件標題元件是區段標題元件，具備就地編輯的功能。

## 用途 {#usage}

標題元件用作內容的主標題或區段的標題。

可用的標題層級可由範本作者在[設計對話框](#design-dialog)中定義。內容編輯者可在[編輯對話框](#edit-dialog)中選取可用的標題層級。為了增加便利性，也可以簡單地就地編輯標題文字。

## 版本和相容性 {#version-and-compatibility}

本文件說明標題元件 v1，最初由 AEM 6.3 搭配的核心元件 1.0.0 版導入。

下表列出標題元件 v1 的相容性。

| AEM 版本 | 標題元件 v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文件說明標題元件 1。
>
>如需標題元件目前版本的詳細資訊，請參閱[標題元件](/help/components/title.md)文件。

## 範例元件輸出 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html) 中取得的範例。

### 螢幕擷圖 {#screenshot}

![](/help/assets/chlimage_1-36.png)

### HTML {#html}

```
<div class="cmp cmp-title aem-GridColumn aem-GridColumn--default--12">
     <h2>Welcome! This is our finest equipment!</h2>
</div>
```

### JSON {#json}

```
"title": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/title",
              "jcr:title": "Welcome! This is our finest equipment!",
              "type": "h2"
            }
```

>[!NOTE]
>
>從核心元件匯出 JSON 需要核心元件 1.1.0 版。如需詳細資訊，請參閱[核心元件 v1 的相容性資訊](/help/versions.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框可讓內容作者定義標題文字並選取標題層級。

>[!NOTE]
>
>標題如為空白值，會顯示頁面標題。

![](/help/assets/chlimage_1-91.png)

也可以使用就地編輯器來編輯標題元件的文字。

![](/help/assets/chlimage_1-37.png)

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義內容作者建立標題元件時應具備的預設標題層級。

![](/help/assets/chlimage_1-92.png)

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title)有關標題元件的最新技術文件。

您可以從 GitHub 下載完整的核心元件專案。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。
