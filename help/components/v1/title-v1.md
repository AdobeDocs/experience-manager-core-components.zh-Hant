---
title: 標題元件(v1)
description: 核心元件標題元件是章節標題元件，具備就地編輯的功能。
index: n
role: Architect, Developer, Admin, User
exl-id: 79549ac0-82f2-4ea0-9cce-d534d0b47b5c
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---


# 標題元件(v1) {#title-component-v}

核心元件標題元件是章節標題元件，具備就地編輯的功能。

## 使用情況 {#usage}

標題元件是用作內容區段的標題或標題。

可用的標題層級可由範本作者在[設計對話方塊](#design-dialog)中定義。 內容編輯者可在[編輯對話方塊](#edit-dialog)中選取可用的標題層級。 為了增加便利性，也可以簡單地就地編輯標題文字。

## 版本和相容性 {#version-and-compatibility}

本檔案說明Title元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出標題元件v1的相容性。

| AEM 版本 | 標題元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明第1版標題元件。
>
>如需目前版本的標題元件的詳細資訊，請參閱[標題元件](/help/components/title.md)檔案。

## 範例元件輸出 {#sample-component-output}

以下是從[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)中取得的範例。

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
>從核心元件匯出JSON需要版本1.1.0的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者定義標題文字並選取標題層級。

>[!NOTE]
>
>標題的空白值會顯示頁面標題。

![](/help/assets/chlimage_1-91.png)

就地編輯器也可用於編輯標題元件的文字。

![](/help/assets/chlimage_1-37.png)

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義內容作者建立標題元件時的預設標題層級。

![](/help/assets/chlimage_1-92.png)

## 技術細節 {#technical-details}

您可以在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title)上找到有關標題元件[的最新技術檔案。

您可以從GitHub下載整個核心元件專案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。
