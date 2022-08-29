---
title: 按鈕元件
description: 核心元件按鈕元件允許建立和顯示按鈕。
role: Architect, Developer, Admin, User
exl-id: e17efd1d-90d4-497a-9e7d-45934d81bc28
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---

# 按鈕元件{#button-component}

核心元件按鈕元件允許在頁面上配置和顯示按鈕項。

## 使用狀況 {#usage}

核心元件按鈕元件允許在頁面中包含按鈕。

* 可以在 [配置對話框](#configure-dialog)。
* 可在 [設計對話框](#design-dialog)。

## 版本和相容性 {#version-and-compatibility}

按鈕元件的當前版本是v2，該版本於2022年2月隨核心元件2.18.0版一起推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v2 | - | 相容 | 相容 |
| [v1](v1/button.md) | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗按鈕元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_button)。

## 技術詳細資訊 {#technical-details}

有關按鈕元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_button_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

「配置」對話框允許內容作者定義按鈕及其行為和對頁面訪問者的顯示方式。

### 屬性頁籤 {#properties-tab}

![按鈕元件編輯對話框的屬性頁籤](/help/assets/button-edit-properties.png)

* **文本**  — 按鈕上顯示的文本
* **連結**  — 連結到內部、外AEM部資源或錨點的內容頁
   * 使用 **選擇對話框** 的子例AEM行。
* **在新頁籤中開啟連結**  — 如果選中，連結將在新瀏覽器頁籤中開啟。
* **表徵圖**  — 用於在按鈕中顯示表徵圖的標識符
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

### 輔助功能頁籤 {#accessibility-tab}

![按鈕元件編輯對話框的輔助功能頁籤](/help/assets/button-edit-accessibility.png)

在 **輔助功能** 頁籤，可為 [ARIA輔助功能](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性的值

### 樣式頁籤 {#styles-tab-edit}

![按鈕元件編輯對話框的「樣式」頁籤](/help/assets/button-edit-styles.png)

按鈕元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便下拉菜單可用。

## 設計對話框 {#design-dialog}

### 樣式頁籤 {#styles-tab}

按鈕元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

按鈕元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
