---
title: 階層連結元件 (v2)
description: 核心元件階層連結元件是一種導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。
role: Architect, Developer, Admin, User
exl-id: 5f2e6fef-e2f6-48e2-8dac-008db3131044
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '673'
ht-degree: 100%

---


# 階層連結元件 (v2) {#breadcrumb-component}

核心元件階層連結元件是一種導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。

## 用途 {#usage}

階層連結元件會顯示目前頁面在網站階層中的位置，讓頁面訪客可以從其目前位置導覽頁面階層。這通常會整合到頁首或頁尾中。

可用選項 (例如：預設導覽層級、以及顯示目前頁面或隱藏頁面的功能) 可由範本作者在[設計對話框](#design-dialog)中定義。內容編輯者就可以在[編輯對話框](#edit-dialog)中選擇是否應該顯示隱藏的頁面，以及元件的實際導覽層級。

## 版本和相容性 {#version-and-compatibility}

本文件說明階層連結元件 v2，最初於 2018 年 1 月隨著核心元件 2.0.0 版發行導入。

>[!CAUTION]
>
>本文件說明階層連結元件 v2。
>
>如需階層連結元件目前版本的詳細資訊，請參閱[階層連結元件](/help/components/breadcrumb.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「階層連結元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_breadcrumb)」。

>[!NOTE]
>
>截至「核心元件」2.1.0 版，「階層連結元件」支援[schema.org 結構化資料](https://schema.org/BreadcrumbList)。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2)有關階層連結元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框可讓內容作者在階層連結中隱藏已隱藏和作用中的頁面，以及應顯示的階層深度。

![階層連結元件編輯對話框](/help/assets/breadcrumb-edit.png)

* **導覽開始層級** - 階層連結元件在階層中開始向下導覽至目前頁面的起始位置。例如：

   * 0 從 `/content` 開始
   * 1 從 `/content/<yourSite>` 開始
   * 2 從 `/content/<yourSite>/<country>` 開始

* **顯示隱藏的導覽項目** - 在階層連結中顯示標記為隱藏的頁面 (預設不會顯示這些頁面)
* **隱藏目前頁面** - 在階層連結中隱藏目前頁面 (預設會顯示)
* **停用影子** - 如果階層中的頁面是重新導向，將顯示重新導向頁面的名稱而非目標。如需詳細資訊，請參閱導覽元件的[影子網站結構支援](../v1/navigation.md#shadow-structure)。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義是否要隱藏階層連結中已隱藏和作用中頁面的選項預設值，以及應顯示的階層深度。

### 主要索引標籤 {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **導覽開始層級** - 當階層連結元件新增至頁面時，此項目用於定義階層連結元件在階層中開始向下導覽至目前頁面的起始位置預設值。
* **顯示已隱藏的導覽項目** - 當階層連結元件新增至頁面時，定義&#x200B;**顯示已隱藏的導覽項目**&#x200B;選項的預設值。

   * 它不會為作者啟用或停用選項。它只會設定預設值。

* **隱藏目前頁面** - 當階層連結元件新增至頁面時，定義&#x200B;**隱藏目前頁面**&#x200B;選項的預設值。

   * 它不會為作者啟用或停用選項。它只會設定預設值。

* **停用影子** - 當階層連結元件新增至頁面時，定義&#x200B;**停用影子**&#x200B;選項的預設值。

### 樣式索引標籤 {#styles-tab}

階層連結元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「階層連結元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
