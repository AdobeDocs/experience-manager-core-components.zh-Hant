---
title: 階層連結元件(v1)
seo-title: 階層連結元件(v1)
description: 核心元件階層連結元件是一個導覽元件，可根據頁面的內容階層中的位置建立連結的導覽路徑標示。
seo-description: AEM核心元件階層連結元件是一個導覽元件，可根據頁面的內容階層中的位置建立連結的導覽路徑標示。
uuid: c1f20a82-b6 ff-4a3 c-920a-6710084a69 f2
content-type: 引用
topic-tags: 核心元件
discoiquuid: 0b3a7d8f-d110-424f-b531-ff88 c9 a09128
disttype: dist5
gnavtheme: 淺色
groupsectionnavitems: 否
hidemerchandisingbar: 繼承
hidepromocomponent: 繼承
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# 階層連結元件(v1){#breadcrumb-component-v}

核心元件階層連結元件是一個導覽元件，可根據頁面的內容階層中的位置建立連結的導覽路徑標示。

## 使用狀況 {#usage}

階層連結元件會顯示網站階層內目前頁面的位置，讓頁面訪客可從其目前位置導覽頁面階層。這通常會與頁首或頁尾整合。

預設導覽層級，以及顯示目前頁面或隱藏頁面的能力，可由 [設計對話方塊中的範本作者定義](breadcrumb-v1.md#main-pars_title_1995166862)。然後內容編輯器可選擇是否應顯示隱藏頁面，並在 [編輯對話方塊中顯示元件的實際導覽層級](breadcrumb-v1.md#main-pars_title)。

## 版本與相容性 {#version-and-compatibility}

本文件說明The breadcrumb Component的v1，原始版本為AEM6.3的1.0.0版。

下表列出階層連結mbox元件的相容性。

| AEM版本 | 階層連結元件v1 |
|--- |--- |
| 6.3 | 相容相容性 |
| 6.4 | 相容相容性 |

>[!CAUTION]
>
>本文件說明階層連結元件的v1。
>如需目前版本「階層連結元件」的詳細資訊，請參閱 [「階層連結元件](breadcrumb.md) 」文件。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/chlimage_1-33.png)

### HTML {#html}

```
<div class="cmp cmp-breadcrumb aem-GridColumn aem-GridColumn--default--12">

<ol class="breadcrumb">
    <li class="breadcrumb-item ">
        <a href="/content/we-retail/us.html">
            United States
        </a>
    </li>

    <li class="breadcrumb-item ">
        <a href="/content/we-retail/us/en.html">
            English
        </a>
    </li>

    <li class="breadcrumb-item active">
        
            Experience
        
    </li>
</ol>
 
</div>
```

### JSON {#json}

```
"breadcrumb": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/breadcrumb"
            }
```

>[!NOTE]
>
>從核心元件匯出JSON需要1.1.0版核心元件。如需詳細資訊，請參閱核心元件v [](versions.md#main-pars_title_236368006) 的相容性資訊。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者抑制網站導覽路徑標示中隱藏和作用中頁面，以及應顯示階層中的深度。

![](assets/chlimage_1-34.png)

* **導覽層級要開始** -階層中的階層連結元件應該開始向下移至目前頁面。例如在我們的零售業：

   * 1開始於 `/content/we-retail`
   * 開始於 `/content/we-retail/<country>`

* **顯示隱藏** -顯示標示為隱藏在導覽路徑標示中的頁面(依預設不會顯示)
* **隱藏目前**-在階層連結中隱藏目前頁面(依預設會顯示)

## 設計對話方塊 {#design-dialog}

The design dialog allows the template author to define what the default value are for the options tocre抑制hideo and active page in the breadcrumbs and should should should shown.

![](assets/chlimage_1-35.png)

* **導覽層級以開始** -定義階層中階層連結元件在新增至頁面時應該開始至目前頁面的預設值。
* **顯示隱藏** -在頁面中新增階層連結元件時，定義 **「顯示隱藏** 」選項的預設值。

   * 它不會啓用或停用作者的選項。它只會設定預設值。

* **隱藏目前** -定義當階層連結元件新增至頁面時 **，「隱藏目前** 」選項的預設值。

   * 它不會啓用或停用作者的選項。它只會設定預設值。

## 技術細節 {#technical-details}

有關階層連結元件的 [最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb)。

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。
