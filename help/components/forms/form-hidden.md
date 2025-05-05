---
title: 表單隱藏元件
description: 核心元件表單隱藏元件可顯示隱藏欄位。
role: Architect, Developer, Admin, User
exl-id: 0364cd3b-3c09-46db-9392-a67e3f9ea7a5
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 2%

---

# 表單隱藏元件{#form-hidden-component}

核心元件表單隱藏元件可顯示隱藏欄位。

## 使用情況 {#usage}

核心元件表單隱藏元件可建立隱藏欄位，以將目前頁面的相關資訊傳回AEM，並且此元件旨在與[表單容器元件](form-container.md)搭配使用。

欄位屬性可由內容編輯者在[設定對話方塊](form-hidden.md)中定義。

## 版本和相容性 {#version-and-compatibility}

表單隱藏元件的目前版本是v2，此版本隨2018年1月的核心元件2.0.0版的發佈引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|--- |--- |--- |---|---|
| v2 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-hidden-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗表單隱藏元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_form_hidden)。

### 技術細節 {#technical-details}

您可以在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_form_hidden_v2)上找到有關表單隱藏元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義隱藏欄位的引數。

![表單隱藏編輯對話方塊](/help/assets/form-hidden-edit.png)

* **名稱** — 與表單資料共同提交的欄位名稱
* **值** — 與表單資料共同提交的欄位值
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

由於表單隱藏元件通常沒有可見屬性，編輯器中元件的預留位置會顯示&#x200B;**Name**&#x200B;和&#x200B;**Value**&#x200B;欄位值（如果已指派），以協助作者識別適當的表單隱藏元件。

![表單隱藏元件範例](/help/assets/form-hidden-example.png)

## 設計對話方塊 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

表單隱藏元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
