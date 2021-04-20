---
title: 表單按鈕元件
description: 核心元件表單隱藏元件允許在表單中包含隱藏欄位。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 3%

---


# 表單按鈕元件{#form-button-component}

核心元件表單按鈕元件允許包含按鈕以觸發頁面上的動作。

## 使用狀況 {#usage}

核心元件表單按鈕元件允許建立按鈕欄位，通常用於觸發表單提交，並與[表單容器元件](form-container.md)一起使用。

按鈕屬性可由[configure dialog](#configure-dialog)中的內容編輯器定義。

## 版本和相容性{#version-and-compatibility}

目前的表單按鈕元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-button-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗「表單按鈕元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_form_button)。

### 技術詳細資訊{#technical-details}

有關表單按鈕元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_form_button_v2)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

配置對話框允許內容作者定義按鈕的參數。

### 屬性頁籤{#properties-tab}

![表單按鈕元件的編輯對話方塊](/help/assets/form-button-edit.png)

* **類型**

   * **按鈕**
   * **提交**

* **Title**  —— 按鈕上顯示的文字

   * 如果沒有提供，則預設為按鈕類型

* **名稱** -按鈕的名稱，隨表單資料提交
* **Value**  —— 隨表單資料提交的按鈕值

* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

## 設計對話框{#design-dialog}

### 樣式標籤{#styles-tab}

表單按鈕元件AEM支援[樣式系統](/help/get-started/authoring.md#component-styling)。
