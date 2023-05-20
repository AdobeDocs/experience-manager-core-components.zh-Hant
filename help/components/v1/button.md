---
title: 按鈕元件(v1)
description: 核心元件按鈕元件允許建立和顯示按鈕。
role: Architect, Developer, Admin, User
exl-id: 63af16e4-dd4d-426d-88ef-769ecd1b3175
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---

# 按鈕元件(v1) {#button-component}

核心元件按鈕元件允許在頁面上配置和顯示按鈕項。

## 使用狀況 {#usage}

核心元件按鈕元件允許在頁面中包含按鈕。

* 可以在 [配置對話框](#configure-dialog)。
* 可在 [設計對話框](#design-dialog)。

## 版本和相容性 {#version-and-compatibility}

該文檔描述了2019年6月隨核心元件2.5.0版推出的按鈕元件v1。

>[!CAUTION]
>
>本文檔介紹按鈕元件的v1。
>
>有關按鈕元件當前版本的詳細資訊，請參閱 [按鈕元件](/help/components/button.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

要體驗按鈕元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_button)。

## 技術詳細資訊 {#technical-details}

有關按鈕元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_button_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

「配置」對話框允許內容作者定義按鈕及其行為和對頁面訪問者的顯示方式。

### 屬性頁籤 {#properties-tab}

![按鈕元件編輯對話框的屬性頁籤](/help/assets/button-edit-properties.png)

* **文本**  — 按鈕上顯示的文本
* **連結**  — 連結到內部、外AEM部資源或錨點的內容頁
   * 使用 **選擇對話框** 的子例AEM行。
* **表徵圖**  — 用於在按鈕中顯示表徵圖的標識符
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

### 輔助功能頁籤 {#accessibility-tab}

![按鈕元件編輯對話框的輔助功能頁籤](/help/assets/button-edit-accessibility.png)

在 **輔助功能** 頁籤，可為 [ARIA輔助功能](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性的值

## 設計對話框 {#design-dialog}

### 樣式頁籤 {#styles-tab}

按鈕元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

按鈕元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
