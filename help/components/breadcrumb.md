---
title: Breadcrumb元件
description: 核心元件Breadcrumb元件是一個導航元件，它根據頁面在內容層次結構中的位置建立連結的Breadcrumb。
role: Architect, Developer, Admin, User
exl-id: 19d65b9d-a407-4f50-9c55-8de0f12222ed
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 1%

---

# Breadcrumb元件{#breadcrumb-component}

核心元件Breadcrumb元件是一個導航元件，它根據頁面在內容層次結構中的位置建立連結的Breadcrumb。

## 使用狀況 {#usage}

Breadcrumb元件顯示當前頁面在站點層次結構中的位置，使頁面訪問者能夠從其當前位置導航頁面層次結構。 這通常整合到頁眉或頁腳中。

可用選項（如預設導航級別和顯示當前頁面或隱藏頁面的能力）可由模板作者在 [設計對話框](#design-dialog)。 然後，內容編輯器可以選擇是否顯示隱藏頁面以及元件的實際導航級別 [編輯對話框](#edit-dialog)。

## 版本和相容性 {#version-and-compatibility}

Breadcrumb元件的當前版本為v3，該版本於2022年2月隨核心元件2.18.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- | --- |--- |---|
| v3 | - | 相容 | 相容 |
| [v2](v2/breadcrumb.md) | 相容 | 相容 | 相容 |
| [v1](v1/breadcrumb-v1.md) | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗Breadcrumb元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_breadcrumb)。

>[!NOTE]
>
>從2.1.0版核心元件開始，Breadcrumb元件支援 [schema.org微資料](https://schema.org/BreadcrumbList)。

## 技術詳細資訊 {#technical-details}

有關Breadcrumb元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者隱藏麵包屑中的隱藏頁面和活動頁面，以及該頁面應顯示的層次結構中的深度。

## 屬性頁籤 {#properties-tab}

![Breadcrumb元件編輯對話框](/help/assets/breadcrumb-edit.png)

* **導航起始級別**  — 在層次結構中，breadcrumb元件應開始向下走到當前頁。 例如：

   * 0開始於 `/content`
   * 1開始 `/content/<yourSite>`
   * 2開始 `/content/<yourSite>/<country>`

* **顯示隱藏的導航項**  — 在breadcrumb中顯示標籤為隱藏的頁面（預設情況下，不會顯示這些頁面）
* **隱藏當前頁**  — 在breadcrumb中隱藏當前頁（預設情況下將顯示）
* **禁用跟蹤**  — 如果層次結構中的頁面是重定向，則將顯示重定向頁面的名稱，而不是目標頁面。 查看 [卷影站點結構支援](navigation.md#shadow-structure) 的子菜單。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

### 樣式頁籤 {#styles-tab-edit}

![Breadcrumb清單元件的編輯對話框的「樣式」頁籤](/help/assets/breadcrumb-edit-styles.png)

Breadcrumb元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便下拉菜單可用。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義用於隱藏麵包屑中隱藏的和活動的頁面的選項的預設值，以及該選項應顯示的層次中的深度。

### 主頁籤 {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **導航起始級別**  — 定義在將breadcrumb元件添加到頁面時，breadcrumb元件應開始向下走到當前頁面的層次中的預設值。
* **顯示隱藏的導航項**  — 定義 **顯示隱藏的導航項** 選項。

   * 它不會為作者啟用或禁用選項。 它只設定預設值。

* **隱藏當前頁** — 定義 **隱藏當前頁** 選項。

   * 它不會為作者啟用或禁用選項。 它只設定預設值。

* **禁用跟蹤**  — 定義 **禁用跟蹤** 選項。

### 樣式頁籤 {#styles-tab}

Breadcrumb元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

Breadcrumb元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
