---
title: 標題元件(v1)
seo-title: 標題元件(v1)
description: 核心元件標題元件是一個區段標題元件，具備就地編輯功能。
seo-description: 核心元件標題元件是一個區段標題元件，具備就地編輯功能。
uuid: 5c4d276c-f0 be-4122-a15 e-3f7443 d8 b209
content-type: 引用
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: a028eBef-2957-410c-9bab-a7040 c350 f2 f
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# 標題元件(v1){#title-component-v}

核心元件標題元件是一個區段標題元件，具備就地編輯功能。

## 使用狀況 {#usage}

「標題元件」旨在做為內容區段的標題或標題。

可用的標題層級可由 [設計對話方塊中的範本作者定義](title-v1.md#main-pars_title_1995166862)。內容編輯器可從 [編輯對話方塊](title-v1.md#main-pars_title)中選擇可用標題層級。為方便您加入，也提供簡單的標題文字就地編輯功能。

## 版本與相容性 {#version-and-compatibility}

本文件說明Title Component v1of the Title Component with AEM6.3版的版本1.0.0。

下表列出「標題元件」v的相容性。

| AEM版本 | Title Component v1 |
|--- |--- |
| 6.3 | 相容相容性 |
| 6.4 | 相容相容性 |

>[!CAUTION]
>
>本文件說明標題元件的第版。
>
>如需目前版本元件的詳細資訊，請參閱 [「標題元件](title.md) 」文件。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/chlimage_1-36.png)

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
>從核心元件匯出JSON需要1.1.0版核心元件。如需詳細資訊，請參閱核心元件v [](versions.md#main-pars_title_236368006) 的相容性資訊。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者定義標題文字，並選取標題層級。

>[!NOTE]
>
>標題的空白值會導致顯示頁面標題。

![](assets/chlimage_1-91.png)

原地編輯器也可以用來編輯標題元件的文字。

![](assets/chlimage_1-37.png)

## 設計對話方塊 {#design-dialog}

此設計對話方塊可讓範本作者定義內容作者建立時，標題元件將擁有的預設標題層級。

![](assets/chlimage_1-92.png)

## 技術細節 {#technical-details}

有關Title Component [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title)。

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。
