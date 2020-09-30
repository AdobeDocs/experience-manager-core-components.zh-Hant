---
title: 階層連結元件
description: 核心元件階層連結元件是導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。
translation-type: tm+mt
source-git-commit: ff943aeca0333b13e2b9aaf11f316457f001d507
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 1%

---


# 階層連結元件{#breadcrumb-component}

核心元件階層連結元件是導覽元件，可根據頁面在內容階層中的位置建立連結的階層連結。

## 使用狀況 {#usage}

「階層連結元件」會顯示目前頁面在網站階層中的位置，讓頁面訪客從目前位置導覽頁面階層。 這通常整合在頁首或頁尾中。

可用選項（例如預設導覽層級和顯示目前頁面或隱藏頁面的功能）可由範本作者在設計對話方塊中 [定義](#design-dialog)。 然後內容編輯器可以選擇是否應顯示隱藏頁面，以及編輯對話方塊中元件的實際導 [覽層級](#edit-dialog)。

## 版本與相容性 {#version-and-compatibility}

Breadcrumb元件的目前版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 雲端服務 |
|--- | --- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](v1/breadcrumb-v1.md) | 相容 | 相容 | - |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗Breadcrumb元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](https://adobe.com/go/aem_cmp_library_breadcrumb)。

>[!NOTE]
>
>自核心元件2.1.0版起，Breadcrumb元件支援 [schema.org微資料](https://schema.org/BreadcrumbList)。

## 技術詳細資訊 {#technical-details}

有關Breadcrumb元件的最新技術文 [件可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者隱藏階層路徑標示中隱藏和作用中的頁面，以及應顯示的階層深度。

![階層連結元件編輯對話方塊](/help/assets/breadcrumb-edit.png)

* **導覽開始層級** -階層中階層中，階層導覽路徑標示元件應開始向下移至目前頁面的位置。 例如：

   * 0開始於 `/content`
   * 1開始於 `/content/<yourSite>`
   * 2開始於 `/content/<yourSite>/<country>`

* **顯示隱藏的導覽項目** -顯示標示為隱藏在階層連結中的頁面（依預設不會顯示）
* **隱藏目前頁面** -隱藏階層連結中的目前頁面（依預設會顯示）
* **停用遮蔽** -如果階層中的頁面是重新導向，則會顯示重新導向頁面的名稱，而非目標頁面。 如需詳細 [資訊，請參閱導覽元件的](navigation.md#shadow-structure) 「陰影網站結構支援」。
* **ID** —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者定義選項的預設值，以隱藏階層路徑標示中隱藏和作用中的頁面，以及應顯示的階層深度。

### 主頁籤 {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **導覽開始層級** -定義階層中階層中階層階層中階層導覽路徑標示元件新增至頁面時，該階層中該元件應開始向下移至目前頁面的預設值。
* **顯示隱藏的導覽項目** -定義將階層連結元件新增至頁面時，「 **顯示隱藏的導覽項目** 」選項的預設值。

   * 它不會為作者啟用或停用選項。 它只設定預設值。

* **Hide current page**—— 定義將階層連結元件新增至頁面時，「 **Hide current page** 」（隱藏目前頁面）選項的預設值。

   * 它不會為作者啟用或停用選項。 它只設定預設值。

* **停用遮蔽** -定義將導覽路徑標示元件新增至頁面時， **** 停用遮蔽選項的預設值。

### 樣式標籤 {#styles-tab}

Breadcrumb元件支援AEM [Style系統](/help/get-started/authoring.md#component-styling)。
