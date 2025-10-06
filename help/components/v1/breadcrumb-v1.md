---
title: 階層連結元件 (v1)
description: 核心元件階層連結元件是一種導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。
index: n
role: Architect, Developer, Admin, User
exl-id: 4845e649-033a-43a8-b5ee-892a3f2a8b98
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '530'
ht-degree: 100%

---


# 階層連結元件 (v1) {#breadcrumb-component-v}

核心元件階層連結元件是一種導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。

## 用途 {#usage}

階層連結元件會顯示目前頁面在網站階層中的位置，讓頁面訪客可以從其目前位置導覽頁面階層。這通常會整合到頁首或頁尾中。

可用選項 (例如：預設導覽層級、以及顯示目前頁面或隱藏頁面的功能) 可由範本作者在[設計對話框](#design-dialog)中定義。內容編輯者就可以在[編輯對話框](#edit-dialog)中選擇是否應該顯示隱藏的頁面，以及元件的實際導覽層級。

## 版本和相容性 {#version-and-compatibility}

本文件說明階層連結元件 v1，最初由 AEM 6.3 搭配的核心元件 1.0.0 版導入。

下表列出階層連結元件 v1 的相容性。

| AEM 版本 | 階層連結元件 v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文件說明階層連結元件 v1。
>>如需階層連結元件目前版本的詳細資訊，請參閱[階層連結元件](/help/components/breadcrumb.md)文件。

## 範例元件輸出 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html) 中取得的範例。

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
>從核心元件匯出 JSON 需要核心元件 1.1.0 版。如需詳細資訊，請參閱[核心元件 v1 的相容性資訊](/help/versions.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框可讓內容作者在階層連結中隱藏已隱藏和作用中的頁面，以及應顯示的階層深度。

![](/help/assets/chlimage_1-34.png)

* **開始導覽層級** - 階層連結元件在階層中開始向下導覽至目前頁面的起始位置。例如，在 We.Retail 中：

   * 1 從 `/content/we-retail` 開始
   * 2 從 `/content/we-retail/<country>` 開始

* **顯示隱藏** - 在階層連結中顯示標記為隱藏的頁面 (預設不會顯示這些頁面)
* **隱藏目前** - 在階層連結中隱藏目前頁面 (預設會顯示)

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義是否要隱藏階層連結中已隱藏和作用中頁面的選項預設值，以及應顯示的階層深度。

![](/help/assets/chlimage_1-35.png)

* **開始導覽層級** - 將階層連結元件新增至頁面時，此項目用於定義階層連結元件在階層中開始向下導覽至目前頁面的起始位置預設值。
* **顯示隱藏** - 將階層連結元件新增至頁面時，定義&#x200B;**顯示隱藏**&#x200B;選項的預設值。

   * 它不會為作者啟用或停用選項。它只會設定預設值。

* **隱藏目前** - 將階層連結元件新增至頁面時，定義&#x200B;**隱藏目前**&#x200B;選項的預設值。

   * 它不會為作者啟用或停用選項。它只會設定預設值。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb)有關階層連結元件的最新技術文件。

您可以從 GitHub 下載完整的核心元件專案。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。
