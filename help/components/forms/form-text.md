---
title: 表單文字元件
description: 核心元件表單文字元件可讓您輸入表單文字以供提交。
role: Architect, Developer, Admin, User
exl-id: e8fa3881-51fb-4726-9654-8f93acfb7464
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 6%

---

# 表單文字元件{#form-text-component}

核心元件表單文字元件可讓您輸入表單文字以供提交。

## 使用狀況 {#usage}

「表單文字」元件可用於提交不同型別的文字，並且旨在與 [表單容器元件](form-container.md). 文字驗證的型別、標籤和說明訊息可由內容編輯者在 [設定對話方塊](#configure-dialog).

## 版本和相容性 {#version-and-compatibility}

表單文字元件的目前版本是v2，此版本隨2018年1月的核心元件2.0.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容於<br>[版本2.17.4](/help/versions.md) 和先前的 | 相容 | 相容 |
| [v1](/help/components/v1/form-text-v1.md) | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗表單文字元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_form_text).

### 技術細節 {#technical-details}

有關表單文字元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_text_v2).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

「設定」對話方塊可讓內容作者定義要輸入的文字型別，以及預設值和標籤。

### 屬性標籤 {#properties-tab}

![屬性標籤](/help/assets/form-text-edit-properties.png)

* **限制**  — 要輸入並進行驗證的文字型別
   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數字**
   * **密碼**
* **文字行**  — 文字區域中要顯示的行數(僅在 **限制** 設為 **文字區域**)
* **標籤**  — 針對欄位顯示的標籤
* **隱藏標籤以避免顯示**  — 標籤僅用於協助工具目的，且不會提供欄位的任何其他視覺資訊時需要
* **元素名稱**  — 與表單資料共同提交的欄位名稱
* **值**  — 在欄位中預先填入的預設值
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 關於索引標籤 {#about-tab}

![「關於」索引標籤](/help/assets/form-text-edit-about.png)

* **說明訊息**  — 向使用者提示可在欄位中輸入的內容
* **將說明訊息顯示為預留位置**  — 當表單輸入為空白且焦點不在其上時，在表單輸入中顯示說明訊息

### 限制標籤 {#constraints-tab}

![限制標籤](/help/assets/form-text-edit-constraints.png)

* **限制訊息**
   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 未顯示於 **文字** 和 **文字區域** 限制型別
* **必填**  — 如果選取，使用者必須在提交表單之前填寫值
   * **必要訊息**  — 如果欄位留空，訊息會顯示為工具提示
* **設為唯讀**  — 如果選取，使用者無法修改欄位的值

## 設計對話方塊 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

表單文字元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
