---
title: 階層連結元件
description: 核心元件階層連結元件是一種導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。
role: Architect, Developer, Admin, User
exl-id: 19d65b9d-a407-4f50-9c55-8de0f12222ed
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 1%

---

# 階層連結元件{#breadcrumb-component}

核心元件階層連結元件是一種導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。

## 使用狀況 {#usage}

階層連結元件會顯示目前頁面在網站階層中的位置，讓頁面訪客可以從其目前位置導覽頁面階層。 這通常會整合到頁首或頁尾中。

可用選項（例如預設導覽層級和顯示目前頁面或隱藏頁面的能力）可由範本作者在 [設計對話方塊](#design-dialog). 然後，內容編輯器可以選擇是否顯示隱藏的頁面，以及在中元件的實際導覽層級 [編輯對話方塊](#edit-dialog).

## 版本和相容性 {#version-and-compatibility}

階層連結元件的目前版本是v3，此版本隨2022年2月的核心元件2.18.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- | --- |--- |---|
| v3 | - | 相容 | 相容 |
| [v2](v2/breadcrumb.md) | 相容 | 相容 | 相容 |
| [v1](v1/breadcrumb-v1.md) | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗階層連結元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_breadcrumb).

>[!NOTE]
>
>截至核心元件2.1.0版，階層連結元件支援 [schema.org microdata](https://schema.org/BreadcrumbList).

## 技術細節 {#technical-details}

有關階層連結元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_breadcrumb_v3).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 編輯對話方塊 {#edit-dialog}

「編輯」對話方塊可讓內容作者在階層連結中隱藏隱藏和作用中的頁面，以及它應顯示的階層中的深度。

## 屬性標籤 {#properties-tab}

![階層連結元件編輯對話方塊](/help/assets/breadcrumb-edit.png)

* **導覽開始層級**  — 階層中階層連結元件的位置，應從這裡開始，逐步前往目前頁面。 例如：

   * 0開始於 `/content`
   * 1開始於 `/content/<yourSite>`
   * 2開始於 `/content/<yourSite>/<country>`

* **顯示隱藏的導覽專案**  — 在階層連結中顯示標籤為隱藏的頁面（預設不會顯示）
* **隱藏目前頁面**  — 在階層連結中隱藏目前頁面（預設會顯示）
* **停用陰影**  — 如果階層中的頁面是重新導向，將顯示重新導向頁面的名稱而非目標。 請參閱 [陰影網站結構支援](navigation.md#shadow-structure) 以取得詳細資訊。
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 樣式索引標籤 {#styles-tab-edit}

![階層連結清單元件之「編輯」對話方塊的「樣式」索引標籤](/help/assets/breadcrumb-edit-styles.png)

階層連結元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling).

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的效果相同。

必須在以下位置為此元件設定樣式： [設計對話方塊](#design-dialog) 讓下拉式功能表可供使用。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義選項的預設值，以隱藏階層連結中的隱藏頁面和使用中頁面，以及應顯示的階層中的深度。

### 主要標籤 {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **導覽開始層級**  — 定義階層中位置的預設值，在將階層連結元件新增至頁面時，它會從該位置開始向下瀏覽至目前頁面。
* **顯示隱藏的導覽專案**  — 定義 **顯示隱藏的導覽專案** 將階層連結元件新增至頁面時的選項。

   * 它不會為作者啟用或停用選項。 它只會設定預設值。

* **隱藏目前頁面** — 定義 **隱藏目前頁面** 將階層連結元件新增至頁面時的選項。

   * 它不會為作者啟用或停用選項。 它只會設定預設值。

* **停用陰影**  — 定義 **停用陰影** 將階層連結元件新增至頁面時的選項。

### 樣式索引標籤 {#styles-tab}

階層連結元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe使用者端資料層 {#data-layer}

階層連結元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
