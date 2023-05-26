---
title: 階層連結元件(v1)
description: 核心元件階層連結元件是一種導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。
index: n
role: Architect, Developer, Admin, User
exl-id: 4845e649-033a-43a8-b5ee-892a3f2a8b98
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---

# 階層連結元件(v1) {#breadcrumb-component-v}

核心元件階層連結元件是一種導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。

## 使用狀況 {#usage}

階層連結元件會顯示目前頁面在網站階層中的位置，讓頁面訪客可以從其目前位置導覽頁面階層。 這通常會整合到頁首或頁尾中。

可用選項（例如，預設導覽層級和顯示目前頁面或隱藏頁面的能力）可由範本作者在 [設計對話方塊](#design-dialog). 然後，內容編輯器可以選擇是否顯示隱藏的頁面，以及在中元件的實際導覽層級 [編輯對話方塊](#edit-dialog).

## 版本和相容性 {#version-and-compatibility}

本檔案說明階層連結元件v1，它最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出階層連結元件v1的相容性。

| AEM版本 | 階層連結元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明階層連結元件v1。
>如需目前版本的階層連結元件的詳細資訊，請參閱 [階層連結元件](/help/components/breadcrumb.md) 檔案。

## 範例元件輸出 {#sample-component-output}

以下是取自下列專案的範例： [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>從核心元件匯出JSON需要核心元件1.1.0版。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 以取得詳細資訊。

## 編輯對話方塊 {#edit-dialog}

「編輯」對話方塊可讓內容作者在階層連結中隱藏隱藏和作用中的頁面，以及它應顯示的階層中的深度。

![](/help/assets/chlimage_1-34.png)

* **要開始的導覽層級**  — 階層中階層連結元件的位置，應從這裡開始，逐步前往目前頁面。 例如，在We.Retail中：

   * 1開始於 `/content/we-retail`
   * 2開始於 `/content/we-retail/<country>`

* **顯示隱藏專案**  — 在階層連結中顯示標籤為隱藏的頁面（預設不會顯示）
* **隱藏目前專案** — 在階層連結中隱藏目前頁面（預設會顯示）

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義選項的預設值，以隱藏階層連結中的隱藏頁面和使用中頁面，以及應顯示的階層中的深度。

![](/help/assets/chlimage_1-35.png)

* **要開始的導覽層級**  — 定義階層中位置的預設值，在將階層連結元件新增至頁面時，它會從該位置開始向下瀏覽至目前頁面。
* **顯示隱藏專案**  — 定義 **顯示隱藏專案** 將階層連結元件新增至頁面時的選項。

   * 它不會為作者啟用或停用選項。 它只會設定預設值。

* **隱藏目前專案**  — 定義 **隱藏目前專案** 將階層連結元件新增至頁面時的選項。

   * 它不會為作者啟用或停用選項。 它只會設定預設值。

## 技術細節 {#technical-details}

有關階層連結元件的最新技術檔案 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb).

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).
