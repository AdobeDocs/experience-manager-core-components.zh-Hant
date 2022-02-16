---
title: 窗體文本元件
description: 核心元件表單文本元件允許輸入表單文本以供提交。
role: Architect, Developer, Admin, User
exl-id: e8fa3881-51fb-4726-9654-8f93acfb7464
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 6%

---

# 窗體文本元件{#form-text-component}

核心元件表單文本元件允許輸入表單文本以供提交。

## 使用狀況 {#usage}

「表單文本」元件允許提交不同類型的文本，並將與 [形式容器元件](form-container.md)。 文本驗證、標籤和幫助消息的類型可由內容編輯器在 [配置對話框](#configure-dialog)。

## 版本和相容性 {#version-and-compatibility}

表單文本元件的當前版本為v2，該版本於2018年1月隨核心元件2.0.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |
| [v1](/help/components/v1/form-text-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗表單文本元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_form_text)。

### 技術詳細資訊 {#technical-details}

有關表單文本元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_text_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義要輸入的文本類型以及預設值和標籤。

### 屬性頁籤 {#properties-tab}

![「屬性」頁籤](/help/assets/form-text-edit-properties.png)

* **約束**  — 要輸入並將根據
   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數量**
   * **密碼**
* **文本行**  — 要在文本區域中顯示的行數(僅在 **約束** 設定為 **文本區域**)
* **標籤**  — 將為欄位顯示的標籤
* **隱藏標籤，使其不顯示**  — 如果僅出於輔助功能目的而需要標籤且不傳遞任何有關欄位的附加視覺資訊，則需要
* **元素名稱**  — 隨表單資料提交的欄位的名稱
* **值**  — 欄位中預填充的預設值
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

### 關於頁籤 {#about-tab}

![關於頁籤](/help/assets/form-text-edit-about.png)

* **幫助消息**  — 向用戶提示可在欄位中輸入的內容
* **將幫助消息顯示為佔位符**  — 當表單輸入為空且未聚焦時，在表單輸入內顯示幫助消息

### 「約束」頁籤 {#constraints-tab}

![「約束」頁籤](/help/assets/form-text-edit-constraints.png)

* **限制訊息**
   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 未顯示 **文本** 和 **文本區域** 約束類型
* **必需**  — 如果選中此選項，則用戶必須在提交表單之前填寫值
   * **所需消息**  — 如果欄位為空，則顯示為工具提示的消息
* **只讀**  — 如果選中，則用戶無法修改欄位的值

## 設計對話框 {#design-dialog}

### 樣式頁籤 {#styles-tab}

表單文本元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
