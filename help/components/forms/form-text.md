---
title: 表單文字元件
description: 核心元件表單文字元件允許輸入表單文字以供提交。
role: 架構師、開發人員、管理員、商業從業人員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 6%

---


# 表單文字元件{#form-text-component}

核心元件表單文字元件允許輸入表單文字以供提交。

## 使用狀況 {#usage}

表單文本元件允許提交不同類型的文本，並準備與[表單容器元件](form-container.md)一起使用。 文本驗證、標籤和幫助消息的類型可由[configure dialog](#configure-dialog)中的內容編輯器定義。

## 版本和相容性{#version-and-compatibility}

目前的表單文字元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-text-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗「表單文字元件」，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_form_text)。

### 技術詳細資訊{#technical-details}

有關表單文字元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_form_text_v2)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

配置對話框允許內容作者定義要輸入的文本類型以及預設值和標籤。

### 屬性頁籤{#properties-tab}

![「屬性」頁籤](/help/assets/form-text-edit-properties.png)

* **約束** -要輸入和將驗證的文本類型
   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數量**
   * **密碼**
* **文本行** -要在文本區域中顯示的行數(僅在「約束」( **** Constraintis)設定為「文本區域」( **Text Area**)時顯示)
* **Label**  —— 將為欄位顯示的標籤
* **隱藏標籤不顯示** -如果標籤僅用於輔助功能用途，且不提供任何有關該欄位的其他視覺資訊，則需要此標籤
* **元素名稱** -隨表單資料提交的欄位名稱
* **值** -在欄位中預先填入的預設值
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

### 關於頁籤{#about-tab}

![關於頁籤](/help/assets/form-text-edit-about.png)

* **幫助消息** -提示用戶可在欄位中輸入的內容
* **將幫助消息顯示為預留位置** -在表單輸入內顯示幫助消息，當其為空且未聚焦

### 約束頁籤{#constraints-tab}

![「約束」頁籤](/help/assets/form-text-edit-constraints.png)

* **限制訊息**
   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * **Text**&#x200B;和&#x200B;**Text Area**&#x200B;約束類型未顯示
* **必要** -如果選取此選項，使用者必須先填入值，才能提交表格
   * **必要訊息** -如果欄位留空，則訊息會顯示為工具提示
* **只讀** -如果選中此選項，則用戶無法修改欄位的值

## 設計對話框{#design-dialog}

### 樣式標籤{#styles-tab}

表單文本元件支AEM持[樣式系統](/help/get-started/authoring.md#component-styling)。
