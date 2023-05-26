---
title: 表單隱藏元件
description: 核心元件表單隱藏元件可顯示隱藏欄位。
role: Architect, Developer, Admin, User
exl-id: 0364cd3b-3c09-46db-9392-a67e3f9ea7a5
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 2%

---

# 表單隱藏元件{#form-hidden-component}

核心元件表單隱藏元件可顯示隱藏欄位。

## 使用狀況 {#usage}

核心元件表單隱藏元件可讓您建立隱藏欄位，以將有關目前頁面的資訊傳回AEM，並且此元件旨在與 [表單容器元件](form-container.md).

欄位屬性可由內容編輯器在 [設定對話方塊](form-hidden.md).

## 版本和相容性 {#version-and-compatibility}

表單隱藏元件的目前版本是v2，此版本隨2018年1月的核心元件2.0.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容於<br>[版本2.17.4](/help/versions.md) 和先前的 | 相容 | 相容 |
| [v1](/help/components/v1/form-hidden-v1.md) | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗表單隱藏元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_form_hidden).

### 技術細節 {#technical-details}

有關表單隱藏元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_hidden_v2).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義隱藏欄位的引數。

![表單隱藏編輯對話方塊](/help/assets/form-hidden-edit.png)

* **名稱**  — 與表單資料共同提交的欄位名稱
* **值**  — 與表單資料共同提交的欄位值
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

由於「表單隱藏」元件通常沒有可見屬性，因此編輯器中的元件預留位置會顯示 **名稱** 和 **值** 欄位值（如果已指派）是為了協助作者識別適當的「表單隱藏」元件。

![表單隱藏元件範例](/help/assets/form-hidden-example.png)

## 設計對話方塊 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

表單隱藏元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
