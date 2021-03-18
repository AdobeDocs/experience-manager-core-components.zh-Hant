---
title: 階層連結元件(v1)
description: 核心元件階層連結元件是導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。
index: n
role: 架構師、開發人員、管理員、商業從業人員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 1%

---


# 階層連結元件(v1){#breadcrumb-component-v}

核心元件階層連結元件是導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。

## 使用狀況 {#usage}

「階層連結元件」會顯示目前頁面在網站階層中的位置，讓頁面訪客從目前位置導覽頁面階層。 這通常整合在頁首或頁尾中。

可用選項，例如預設導覽層級，以及範本作者在[設計對話方塊](#design-dialog)中可定義的顯示目前頁面或隱藏頁面的能力。 然後，內容編輯器可以在[編輯對話框](#edit-dialog)中選擇是否顯示隱藏頁面以及元件的實際導航級別。

## 版本和相容性{#version-and-compatibility}

本檔案說明Breadcrumb元件的v1，此元件最初是隨6.3版核心元件的1.0.0版一起AEM推出。

下表列出Breadcrumb元件的v1相容性。

| 版AEM本 | 階層連結元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明Breadcrumb元件的v1。
>如需Breadcrumb元件目前版本的詳細資訊，請參閱[Breadcrumb元件](/help/components/breadcrumb.md)檔案。

## 元件輸出示例{#sample-component-output}

以下範例取自[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 螢幕擷圖 {#screenshot}

![](/help/assets/chlimage_1-33.png)

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
>從核心元件匯出JSON需要1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者隱藏階層路徑標示中隱藏和作用中的頁面，以及應顯示的階層深度。

![](/help/assets/chlimage_1-34.png)

* **Navigation-Level to start** -階層中，階層中的階層階層中，階層連結元件應開始向下移至目前頁面的位置。例如，在We.Retail中：

   * 1開頭為`/content/we-retail`
   * 2開頭為`/content/we-retail/<country>`

* **顯示隱藏** -顯示標示為隱藏在階層連結中的頁面（依預設不會顯示）
* **隱藏目前**-隱藏階層連結中的目前頁面（依預設會顯示）

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義選項的預設值，以隱藏階層路徑標示中隱藏和作用中的頁面，以及應顯示的階層深度。

![](/help/assets/chlimage_1-35.png)

* **Navigation-Level to start** -定義階層中階層中階層階層中階層導覽路徑標示元件新增至頁面時，該階層中該元件應開始向下移至目前頁面的預設值。
* **顯示隱藏** -定義將Breadcrumb元件新 **增** 至頁面時Show Hiddenoption的預設值。

   * 它不會為作者啟用或停用選項。 它只設定預設值。

* **Hide Current**  —— 定義將階層連結元件新 **增至** 頁面時，Hide Currentoption的預設值。

   * 它不會為作者啟用或停用選項。 它只設定預設值。

## 技術詳細資訊{#technical-details}

有關Breadcrumb Component [的最新技術文檔可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb)上找到。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
