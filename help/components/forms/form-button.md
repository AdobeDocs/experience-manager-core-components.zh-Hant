---
title: 表單按鈕元件
description: 核心元件表單隱藏元件允許在表單中包含隱藏欄位。
role: Architect, Developer, Admin, User
exl-id: 1e5cff43-57db-4bfc-b2d2-23307eaf5eb3
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: ht
source-wordcount: '413'
ht-degree: 100%

---

# 表單按鈕元件 {#form-button-component}

利用核心元件表單按鈕元件，您可在頁面中包含按鈕欄位以觸發動作。

## 用途 {#usage}

核心元件表單按鈕元件允許建立按鈕欄位，通常會觸發提交表單，其設計用於與[表單容器元件](form-container.md)搭配使用。

按鈕屬性可由內容編輯者在[設定對話框](#configure-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

表單按鈕元件的目前版本為 v2，此版本於 2018 年 1 月隨著核心元件 2.0.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v2 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-button-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「表單按鈕元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_form_button_tw)」。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_form_button_v2_tw)有關表單按鈕元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義按鈕的參數。

### 屬性索引標籤 {#properties-tab}

![表單按鈕元件的編輯對話框](/help/assets/form-button-edit.png)

* **類型**

   * **按鈕**
   * **提交**

* **標題** - 按鈕上顯示的文字

   * 若未提供，則預設為按鈕類型

* **名稱** - 與表單資料共同提交的按鈕名稱
* **值** - 與表單資料共同提交的按鈕值

* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

## 設計對話框 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

表單按鈕元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
