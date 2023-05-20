---
title: 標題元件(v1)
description: 核心元件標題元件是具有就地編輯功能的節標題元件。
index: n
role: Architect, Developer, Admin, User
exl-id: 79549ac0-82f2-4ea0-9cce-d534d0b47b5c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 1%

---

# 標題元件(v1) {#title-component-v}

核心元件標題元件是具有就地編輯功能的節標題元件。

## 使用狀況 {#usage}

標題元件將用作內容部分的標題或標題。

可用標題級別可由模板作者在 [設計對話框](#design-dialog)。 內容編輯器可從 [編輯對話框](#edit-dialog)。 為了方便起見，酒店還提供標題文本的簡單就地編輯。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了標題元件的v1，最初是隨帶有6.3的核心元件1.0.0版而引AEM入的。

下表列出了標題元件v1的相容性。

| 版AEM本 | 標題元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔介紹標題元件的版本1。
>
>有關「標題元件」的當前版本的詳細資訊，請參閱 [標題元件](/help/components/title.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件導出JSON需要1.1.0版核心元件。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 的子菜單。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者定義標題文本並選擇標題級別。

>[!NOTE]
>
>標題的空值將導致顯示頁面標題。

![](/help/assets/chlimage_1-91.png)

就地編輯器還可用於編輯標題元件的文本。

![](/help/assets/chlimage_1-37.png)

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義由內容作者建立時標題元件將具有的預設標題級別。

![](/help/assets/chlimage_1-92.png)

## 技術詳細資訊 {#technical-details}

有關標題元件的最新技術文檔 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title)。

整個核心元件項目可從GitHub下載。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。
