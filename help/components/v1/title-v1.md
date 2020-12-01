---
title: 標題元件(v1)
description: 核心元件標題元件是具有就地編輯功能的區段標題元件。
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 1%

---


# 標題元件(v1){#title-component-v}

核心元件標題元件是具有就地編輯功能的區段標題元件。

## 使用狀況 {#usage}

「標題元件」可用作內容區段的標題或標題。

可用標題層級可由範本作者在[設計對話方塊](#design-dialog)中定義。 內容編輯器可從[edit dialog](#edit-dialog)中的可用標題級別進行選擇。 為方便起見，您也可以在原地編輯標題文字。

## 版本和相容性{#version-and-compatibility}

本檔案說明第1版標題元件，最初是隨AEM 6.3版核心元件1.0.0一起推出。

下表列出了Title Component的v1相容性。

| AEM版本 | 標題元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明第1版標題元件。
>
>有關當前版本的標題元件的詳細資訊，請參閱[標題元件](/help/components/title.md)文檔。

## 元件輸出示例{#sample-component-output}

以下範例取自[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件匯出JSON需要1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者定義標題文字，並選取標題層級。

>[!NOTE]
>
>標題的空白值會導致顯示頁面標題。

![](/help/assets/chlimage_1-91.png)

就地編輯器也可用於編輯標題元件的文本。

![](/help/assets/chlimage_1-37.png)

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義標題元件在內容作者建立時所具有的預設標題層級。

![](/help/assets/chlimage_1-92.png)

## 技術詳細資訊{#technical-details}

有關Title Component [的最新技術文檔可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title)上找到。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
