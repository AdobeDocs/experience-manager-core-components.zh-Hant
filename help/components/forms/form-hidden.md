---
title: 表單隱藏元件
description: 核心元件表單隱藏元件可顯示隱藏欄位。
role: Architect, Developer, Admin, User
exl-id: 0364cd3b-3c09-46db-9392-a67e3f9ea7a5
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: ht
source-wordcount: '429'
ht-degree: 100%

---

# 表單隱藏元件{#form-hidden-component}

核心元件表單隱藏元件可顯示隱藏欄位。

## 用途 {#usage}

核心元件表單隱藏元件可建立隱藏欄位，以將目前頁面的相關資訊傳回 AEM，其設計用於與[表單容器元件](form-container.md)搭配使用。

欄位屬性可由內容編輯者在[設定對話框](form-hidden.md)中定義。

## 版本和相容性 {#version-and-compatibility}

表單隱藏元件的目前版本為 v2，此版本於 2018 年 1 月隨著核心元件 2.0.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v2 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-hidden-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「表單隱藏元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_form_hidden)」。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_form_hidden_v2)有關表單隱藏元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義隱藏欄位的參數。

![表單隱藏編輯對話框](/help/assets/form-hidden-edit.png)

* **名稱** - 與表單資料共同提交的欄位名稱
* **值** - 與表單資料共同提交的欄位值
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

由於表單隱藏元件通常沒有可見屬性，編輯器中元件的預留位置會顯示&#x200B;**名稱**&#x200B;和&#x200B;**值**&#x200B;欄位值 (如果已指派)，以協助作者識別適當的表單隱藏元件。

![表單隱藏元件範例](/help/assets/form-hidden-example.png)

## 設計對話框 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

表單隱藏元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
