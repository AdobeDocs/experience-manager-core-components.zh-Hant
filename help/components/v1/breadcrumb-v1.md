---
title: 階層連結元件(v1)
description: 核心元件階層連結元件是導覽元件，會根據頁面在內容階層中的位置建立連結的階層連結。
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 階層連結元件(v1) {#breadcrumb-component-v}

核心元件階層連結元件是導覽元件，會根據頁面在內容階層中的位置建立連結的階層連結。

## 使用狀況 {#usage}

「階層連結元件」會顯示目前頁面在網站階層中的位置，讓頁面訪客從目前位置導覽頁面階層。 這通常整合在頁首或頁尾中。

可用選項，例如預設導覽層級，以及顯示範本作者在設計對話方塊中所定義的目前頁面或隱藏頁 [面的能力](#design-dialog)。 然後內容編輯器可以選擇是否應顯示隱藏頁面，以及編輯對話方塊中元件的實際導 [覽層級](#edit-dialog)。

## 版本與相容性 {#version-and-compatibility}

本檔案說明Breadcrumb元件的v1，最初是隨AEM 6.3核心元件的1.0.0版一起推出。

下表列出Breadcrumb元件的v1相容性。

| AEM版本 | 階層連結元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明Breadcrumb元件的v1。
>如需Breadcrumb元件目前版本的詳細資訊，請參閱 [Breadcrumb元件檔案](/help/components/breadcrumb.md) 。

## 元件輸出示例 {#sample-component-output}

以下是 [We.Retail的範例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件匯出JSON需要1.1.0版的核心元件。 如需詳細 [資訊，請參閱核心元件v1的相容性資訊](/help/versions.md) 。

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者隱藏階層路徑標示中隱藏和作用中的頁面，以及應顯示的階層深度。

![](/help/assets/chlimage_1-34.png)

* **Navigation-Level to start** —— 階層中階層中，階層導覽路徑標示元件應開始向下移至目前頁面的位置。 例如，在We.Retail中：

   * 1開始於 `/content/we-retail`
   * 2開始於 `/content/we-retail/<country>`

* **顯示隱藏** -顯示標示為隱藏在階層連結中的頁面（依預設不會顯示）
* **隱藏目前**-隱藏階層連結中的目前頁面（依預設會顯示）

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者定義選項的預設值，以隱藏階層路徑標示中隱藏和作用中的頁面，以及應顯示的階層深度。

![](/help/assets/chlimage_1-35.png)

* **Navigation-Level to start** —— 定義階層中階層中階層階層中階層導覽路徑標示元件新增至頁面時，該階層應該開始向下移至目前頁面的預設值。
* **顯示隱藏** -定義將導覽路徑標示元件新增至頁面時， **** 顯示隱藏選項的預設值。

   * 它不會為作者啟用或停用選項。 它只設定預設值。

* **Hide Current** —— 定義將階層連結元件新增至頁面時，「 **Hide Current** 」（隱藏目前）選項的預設值。

   * 它不會為作者啟用或停用選項。 它只設定預設值。

## 技術詳細資訊 {#technical-details}

有關Breadcrumb元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。
