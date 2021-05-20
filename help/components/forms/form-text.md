---
title: 表單文字元件
description: 核心元件表單文字元件可輸入表單文字以供提交。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: e8fa3881-51fb-4726-9654-8f93acfb7464
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 6%

---

# 表單文本元件{#form-text-component}

核心元件表單文字元件可輸入表單文字以供提交。

## 使用狀況 {#usage}

「表單文字」元件允許提交不同類型的文字，並打算與[表單容器元件](form-container.md)一起使用。 文本驗證、標籤和幫助消息的類型可由[配置對話框](#configure-dialog)中的內容編輯器定義。

## 版本和相容性{#version-and-compatibility}

目前的表單文字元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，本檔案已詳細說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-text-v1.md) | 相容 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗表單文字元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_form_text)。

### 技術詳細資訊{#technical-details}

如需表單文字元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_form_text_v2)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

設定對話方塊可讓內容作者定義要輸入的文字類型以及預設值和標籤。

### 屬性頁簽{#properties-tab}

![「屬性」頁簽](/help/assets/form-text-edit-properties.png)

* **限制**  — 要輸入並將根據驗證的文字類型
   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數量**
   * **密碼**
* **文本行**  — 要在文本區域中顯示的行數(僅當「約束」設 **** 定為「文本 **區域」**&#x200B;時顯示)
* **標籤**  — 將針對欄位顯示的標籤
* **隱藏標籤，使其不顯示**  — 如果標籤僅用於輔助功能目的，並且沒有傳遞任何有關該欄位的其他視覺資訊，則需要此標籤
* **元素名稱**  — 隨表單資料提交的欄位名稱
* **值**  — 在欄位中預先填入的預設值
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

### 關於標籤{#about-tab}

![關於標籤](/help/assets/form-text-edit-about.png)

* **說明訊息**  — 提示使用者可在欄位中輸入的內容
* **將說明訊息顯示為預留位置**  — 在表單輸入為空且未聚焦時，在其內顯示說明訊息

### 約束頁簽{#constraints-tab}

![限制索引標籤](/help/assets/form-text-edit-constraints.png)

* **限制訊息**
   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 未針對&#x200B;**Text**&#x200B;和&#x200B;**Text Area**&#x200B;約束類型顯示
* **必要**  — 如果選取此選項，則使用者必須先填入值，才能提交表單
   * **必填訊息**  — 如果欄位留空，則訊息會顯示為工具提示
* **設為唯讀**  — 如果選取，使用者無法修改欄位的值

## 設計對話框{#design-dialog}

### 樣式標籤{#styles-tab}

表單文本元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
