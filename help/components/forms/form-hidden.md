---
title: 表單隱藏元件
description: 核心元件表單隱藏元件允許顯示隱藏欄位。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 0364cd3b-3c09-46db-9392-a67e3f9ea7a5
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 2%

---

# 表單隱藏元件{#form-hidden-component}

核心元件表單隱藏元件允許顯示隱藏欄位。

## 使用狀況 {#usage}

核心元件表單隱藏元件允許建立隱藏欄位，將有關當前頁面的資訊傳回AEM，並且與[表單容器元件](form-container.md)一起使用。

欄位屬性可由[configure dialog](form-hidden.md)中的內容編輯器定義。

## 版本和相容性{#version-and-compatibility}

目前的表單隱藏元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，本檔案已詳述。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-hidden-v1.md) | 相容 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗表單隱藏元件以及查看其設定選項的範例以及HTML和JSON輸出，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_form_hidden)。

### 技術詳細資訊{#technical-details}

如需表單隱藏元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_form_hidden_v2)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

設定對話方塊可讓內容作者定義隱藏欄位的參數。

![表單隱藏編輯對話方塊](/help/assets/form-hidden-edit.png)

* **名稱**  — 隨表單資料提交的欄位名稱
* **值**  — 隨表單資料提交之欄位的值
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

由於「表單隱藏」元件通常沒有可見的屬性，因此如果為了幫助作者識別適當的「表單隱藏」元件而指派了&#x200B;**Name**&#x200B;和&#x200B;**Value**&#x200B;欄位值，編輯器中元件的預留位置會顯示這些值。

![表單隱藏元件範例](/help/assets/form-hidden-example.png)

## 設計對話框{#design-dialog}

### 樣式標籤{#styles-tab}

表單隱藏元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
