---
title: 窗體按鈕元件
description: 核心元件表單隱藏元件允許在表單中包含隱藏欄位。
role: Architect, Developer, Admin, User
exl-id: 1e5cff43-57db-4bfc-b2d2-23307eaf5eb3
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 3%

---

# 窗體按鈕元件 {#form-button-component}

核心元件表單按鈕元件允許包含按鈕以觸發頁面上的操作。

## 使用狀況 {#usage}

核心元件表單按鈕元件允許建立按鈕欄位，通常用於觸發表單的提交，並與 [窗體容器元件](form-container.md)。

按鈕屬性可由中的內容編輯器定義 [配置對話框](#configure-dialog)。

## 版本和相容性 {#version-and-compatibility}

表單按鈕元件的當前版本為v2，該版本於2018年1月隨核心元件2.0.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |
| [v1](/help/components/v1/form-button-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗「表單按鈕」元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_form_button)。

### 技術詳細資訊 {#technical-details}

有關表單按鈕元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_button_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義按鈕的參數。

### 屬性頁籤 {#properties-tab}

![表單按鈕元件的編輯對話框](/help/assets/form-button-edit.png)

* **類型**

   * **按鈕**
   * **提交**

* **標題**  — 按鈕上顯示的文本

   * 如果未提供，則預設為按鈕類型

* **名稱**  — 按鈕的名稱，該按鈕與表單資料一起提交
* **值**  — 按鈕的值，該按鈕與表單資料一起提交

* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

## 設計對話框 {#design-dialog}

### 樣式頁籤 {#styles-tab}

表單按鈕元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
