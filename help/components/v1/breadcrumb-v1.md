---
title: Breadcrumb元件(v1)
description: 核心元件Breadcrumb元件是一個導航元件，它根據頁面在內容層次結構中的位置建立連結的Breadcrumb。
index: n
role: Architect, Developer, Admin, User
exl-id: 4845e649-033a-43a8-b5ee-892a3f2a8b98
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---

# Breadcrumb元件(v1) {#breadcrumb-component-v}

核心元件Breadcrumb元件是一個導航元件，它根據頁面在內容層次結構中的位置建立連結的Breadcrumb。

## 使用狀況 {#usage}

Breadcrumb元件顯示當前頁面在站點層次結構中的位置，使頁面訪問者能夠從其當前位置導航頁面層次結構。 這通常整合到頁眉或頁腳中。

可用選項（如預設導航級別和顯示當前頁面或隱藏頁面的功能）可由模板作者在 [設計對話框](#design-dialog)。 然後，內容編輯器可以選擇是否顯示隱藏頁面以及元件的實際導航級別 [編輯對話框](#edit-dialog)。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹Breadcrumb元件的v1，最初是隨帶有6.3的核心元件1.0.0版一起推出AEM的。

下表列出了Breadcrumb元件v1的相容性。

| 版AEM本 | Breadcrumb元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔介紹Breadcrumb元件的v1。
>有關Breadcrumb元件當前版本的詳細資訊，請參見 [Breadcrumb元件](/help/components/breadcrumb.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件導出JSON需要1.1.0版核心元件。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 的子菜單。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者隱藏麵包屑中的隱藏頁面和活動頁面，以及該頁面應顯示的層次結構中的深度。

![](/help/assets/chlimage_1-34.png)

* **要啟動的導航級別**  — 在層次結構中，breadcrumb元件應開始向下走到當前頁。 例如，在We.Retail中：

   * 1開始 `/content/we-retail`
   * 2開始 `/content/we-retail/<country>`

* **顯示隱藏**  — 在breadcrumb中顯示標籤為隱藏的頁面（預設情況下，不會顯示這些頁面）
* **隱藏當前** — 在breadcrumb中隱藏當前頁（預設情況下將顯示）

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義用於隱藏麵包屑中隱藏的和活動的頁面的選項的預設值，以及該選項應顯示的層次中的深度。

![](/help/assets/chlimage_1-35.png)

* **要啟動的導航級別**  — 定義在將breadcrumb元件添加到頁面時，breadcrumb元件應開始向下走到當前頁面的層次中的預設值。
* **顯示隱藏**  — 定義 **顯示隱藏** 選項。

   * 它不會為作者啟用或禁用選項。 它只設定預設值。

* **隱藏當前**  — 定義 **隱藏當前** 選項。

   * 它不會為作者啟用或禁用選項。 它只設定預設值。

## 技術詳細資訊 {#technical-details}

有關Breadcrumb元件的最新技術文檔 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb)。

整個核心元件項目可從GitHub下載。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。
