---
title: 電子郵件按鈕元件
description: 電子郵件按鈕元件允許配置和顯示內容中的按鈕項。
role: Architect, Developer, Admin, User
exl-id: b144e8d1-1097-475d-b2eb-3353c176afb9
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---


# 電子郵件按鈕元件 {#email-button-component}

電子郵件按鈕元件允許配置和顯示內容中的按鈕項。

## 使用狀況 {#usage}

「電子郵件按鈕」元件允許在內容中包含按鈕，內容讀取器可按一下，並連結到其他資源。

* 可以在 [配置對話框。](#configure-dialog)
* 可在 [設計對話框。](#design-dialog)

## 版本和相容性 {#version-and-compatibility}

電子郵件按鈕元件的當前版本是v1，該版本於2022年10月隨電子郵件核心元件的第x版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [電子郵件核心元件版本。](/help/email/versions.md)

## 技術詳細資訊 {#technical-details}

有關電子郵件按鈕元件的最新技術文檔 [中。](https://adobe.com/go/aem_cmp_tech_email_button_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

「配置」對話框允許內容作者定義按鈕以及按鈕對內容閱讀器的行為和顯示方式。

### 屬性頁籤 {#properties-tab}

![按鈕元件編輯對話框的屬性頁籤](/help/email/assets/email-button-edit-properties.png)

* **文本**  — 按鈕上顯示的文本
   * 按一下「市場活動」表徵圖以開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。
* **連結**  — 連結到內部、外AEM部資源或錨點的內容頁
   * 使用 **選擇對話框** 的子例AEM行。
   * 按一下「市場活動」表徵圖以開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。
* **表徵圖**  — 用於在按鈕中顯示表徵圖的標識符
* **ID**  — 此選項允許控制HTML中元件的唯一標識符。
   * 如果留空，則系統會為您自動生成唯一ID，並且可以通過檢查生成的內容來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS。
* **在新頁籤中開啟連結**  — 如果選中，連結將在新瀏覽器頁籤中開啟。

### 輔助功能頁籤 {#accessibility-tab}

![按鈕元件編輯對話框的輔助功能頁籤](/help/email/assets/email-button-edit-accessibility.png)

在 **輔助功能** 頁籤，可為 [ARIA輔助功能](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性的值

### 樣式頁籤 {#styles-tab-edit}

電子郵件按鈕元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便該頁籤可用。

## 設計對話框 {#design-dialog}

### 樣式頁籤 {#styles-tab}

電子郵件按鈕元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
