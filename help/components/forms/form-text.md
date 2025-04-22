---
title: 表單文字元件
description: 核心元件表單文字元件可讓您輸入表單文字以供提交。
role: Architect, Developer, Admin, User
exl-id: e8fa3881-51fb-4726-9654-8f93acfb7464
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 5%

---

# 表單文字元件{#form-text-component}

核心元件表單文字元件可讓您輸入表單文字以供提交。

## 使用情況 {#usage}

表單文字元件允許提交不同型別的文字，並打算與[表單容器元件](form-container.md)搭配使用。 文字驗證型別、標籤和說明訊息可由內容編輯者在[設定對話方塊](#configure-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

表單文字元件的目前版本是v2，此版本隨2018年1月的核心元件發行版本2.0.0的發佈引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|--- |--- |--- |---|---|
| v2 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-text-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗表單文字元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_form_text)。

### 技術細節 {#technical-details}

在GitHub](https://adobe.com/go/aem_cmp_tech_form_text_v2)上可找到有關表單文字元件[的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

「設定」對話方塊可讓內容作者定義要輸入的文字型別，以及預設值和標籤。

### 屬性標籤 {#properties-tab}

![屬性標籤](/help/assets/form-text-edit-properties.png)

* **限制** — 要輸入且將接受驗證的文字型別
   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數字**
   * **密碼**
* **文字行** — 要在文字區域中顯示的行數（僅當&#x200B;**條件約束**&#x200B;設定為&#x200B;**文字區域**&#x200B;時才會顯示）
* **標籤** — 將為欄位顯示的標籤
* **隱藏標籤以避免顯示** — 標籤僅需用於協助工具目的且不會提供欄位任何額外視覺資訊時需要
* **元素名稱** — 與表單資料共同提交的欄位名稱
* **值** — 預設值（已預先填入欄位中）
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 關於標籤 {#about-tab}

![關於索引標籤](/help/assets/form-text-edit-about.png)

* **說明訊息** — 使用者可在欄位中輸入的內容提示
* **將說明訊息顯示為預留位置** — 當表單輸入為空白且焦點不在其上時，在表單輸入中顯示說明訊息

### 限制標籤 {#constraints-tab}

![條件約束標籤](/help/assets/form-text-edit-constraints.png)

* **限制訊息**
   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 未針對&#x200B;**文字**&#x200B;和&#x200B;**文字區域**&#x200B;限制型別顯示
* **必要** — 如果選取，使用者必須在提交表單前填入值
   * **必要訊息** — 如果欄位留空，訊息會顯示為工具提示
* **設為唯讀** — 如果選取，使用者無法修改欄位的值

## 設計對話方塊 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

表單文字元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
