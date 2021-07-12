---
title: 階層連結元件(v1)
description: 核心元件階層連結元件是導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。
index: n
role: Architect, Developer, Admin, User
exl-id: 4845e649-033a-43a8-b5ee-892a3f2a8b98
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---

# 階層連結元件(v1) {#breadcrumb-component-v}

核心元件階層連結元件是導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。

## 使用狀況 {#usage}

階層連結元件會顯示網站階層中目前頁面的位置，讓頁面訪客可從其目前位置導覽頁面階層。 這通常會整合至頁首或頁尾。

範本作者可在[設計對話方塊](#design-dialog)中定義的可用選項，例如預設導覽層級和顯示目前頁面或隱藏頁面的功能。 然後，內容編輯器可以在[edit對話框](#edit-dialog)中選擇是否顯示隱藏頁面以及元件的實際導航級別。

## 版本與相容性 {#version-and-compatibility}

本檔案說明階層連結元件v1，此元件最初於AEM 6.3的核心元件1.0.0版中推出。

下表列出階層連結元件v1的相容性。

| AEM版本 | 階層連結元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明階層連結元件的v1。
>如需階層連結元件目前版本的詳細資訊，請參閱[階層連結元件](/help/components/breadcrumb.md)檔案。

## 範例元件輸出 {#sample-component-output}

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
>從核心元件匯出JSON需使用1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者隱藏階層連結中的隱藏和作用中頁面，以及階層中應顯示的深度。

![](/help/assets/chlimage_1-34.png)

* **要開始的導覽層級**  — 階層中，階層連結元件應該開始向下移至目前頁面的位置。例如，在We.Retail中：

   * 1開始於`/content/we-retail`
   * 2從`/content/we-retail/<country>`開始

* **顯示隱藏**  — 顯示在階層連結中標示為隱藏的頁面（依預設不會顯示）
* **隱藏目前** — 在階層連結中隱藏目前的頁面（依預設會顯示）

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義預設值，供選項在階層連結中隱藏隱藏和作用中的頁面，以及應顯示的階層深度。

![](/help/assets/chlimage_1-35.png)

* **要開始的導覽層級**  — 定義階層中，當階層連結元件新增至頁面時，階層連結元件應該從哪個位置開始向下游到目前頁面的預設值。
* **顯示隱藏**  — 定義將階層連結元 **件新** 增至頁面時的顯示隱藏選項的預設值。

   * 它不會啟用或停用作者的選項。 它只設定預設值。

* **隱藏目前**  — 定義將階層連結元 **件新** 增至頁面時，隱藏目前選項的預設值。

   * 它不會啟用或停用作者的選項。 它只設定預設值。

## 技術詳細資訊 {#technical-details}

如需有關階層連結元件[的最新技術檔案，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
