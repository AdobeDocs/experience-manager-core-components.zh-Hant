---
title: 表單文字元件
description: 核心元件表單文字元件可讓您輸入表單文字以供提交。
role: Architect, Developer, Admin, User
exl-id: e8fa3881-51fb-4726-9654-8f93acfb7464
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: ht
source-wordcount: '578'
ht-degree: 100%

---

# 表單文字元件{#form-text-component}

核心元件表單文字元件可讓您輸入表單文字以供提交。

## 用途 {#usage}

表單文字元件允許提交不同類型的文字，其設計用於與[表單容器元件](form-container.md)搭配使用。文字驗證類型、標籤和說明訊息可由內容編輯者在[設定對話框](#configure-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

表單文字元件的目前版本為 v2，此版本於 2018 年 1 月隨著核心元件 2.0.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v2 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-text-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「表單文字元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_form_text_tw)」。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_form_text_v2_tw)有關表單文字元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義要輸入的文字類型，以及預設值和標籤。

### 屬性索引標籤 {#properties-tab}

![屬性索引標籤](/help/assets/form-text-edit-properties.png)

* **限制** - 要輸入的文字類型，並據此進行驗證
   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數字**
   * **密碼**
* **文字行** - 要在文字區域中顯示的行數 (僅當&#x200B;**限制**&#x200B;設定為&#x200B;**文字區域**&#x200B;時才會顯示)
* **標籤** - 欄位上所顯示的標籤
* **隱藏標籤以避免顯示** - 標籤僅必須在協助工具用途時才需使用，不會提供欄位任何額外的可見資訊
* **元素名稱** - 與表單資料共同提交的欄位名稱
* **值** - 已預先填入欄位中的預設值
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

### 關於索引標籤 {#about-tab}

![關於索引標籤](/help/assets/form-text-edit-about.png)

* **說明訊息** - 向使用者提示可輸入於欄位的內容
* **將說明訊息顯示為預留位置** - 當表單輸入為空白且焦點不在其上時，在表單輸入中顯示說明訊息

### 限制索引標籤 {#constraints-tab}

![限制索引標籤](/help/assets/form-text-edit-constraints.png)

* **限制訊息**
   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 未針對&#x200B;**文字**&#x200B;和&#x200B;**文字區域**&#x200B;限制類型顯示
* **必要** - 如果選取，使用者必須在提交表單前填入值
   * **必要訊息** - 如果欄位留空，訊息會顯示為工具提示
* **設為唯讀** - 如果選取，使用者無法修改欄位的值

## 設計對話框 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

表單文字元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
