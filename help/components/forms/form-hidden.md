---
title: 表單隱藏元件
description: 「核心元件表單隱藏」元件可顯示隱藏欄位。
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 表單隱藏元件{#form-hidden-component}

「核心元件表單隱藏」元件可顯示隱藏欄位。

## 使用狀況 {#usage}

核心元件表單隱藏元件可讓您建立隱藏欄位，將目前頁面的相關資訊傳回AEM，並與表單容器元件一 [起使用](form-container.md)。

欄位屬性可由內容編輯器在「設定」對話方塊中 [定義](form-hidden.md)。

## 版本與相容性 {#version-and-compatibility}

目前的表單隱藏元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 雲端服務 |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-hidden-v1.md) | 相容 | 相容 | - |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗「表單隱藏元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元件 [庫](https://adobe.com/go/aem_cmp_library_form_hidden)。

### 技術詳細資訊 {#technical-details}

有關「表單隱藏元件」的最新技 [術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_form_hidden_v2)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義隱藏欄位的參數。

![表單隱藏編輯對話框](/help/assets/form-hidden-edit.png)

* **Name** —— 隨表單資料提交的欄位名稱
* **Value** —— 隨表單資料提交的欄位值
* **ID** —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

由於「表單隱藏」元件通常沒有可見屬性，因此如果為幫助作者識別適當的「表單隱藏」元件而分配了「名稱」和「值 ******** 」欄位值，則編輯器中的元件佔位符將顯示這些值。

![表單隱藏元件範例](/help/assets/form-hidden-example.png)

## 設計對話框 {#design-dialog}

### 樣式標籤 {#styles-tab}

「表單隱藏元件」支援AEM [Style系統](/help/get-started/authoring.md#component-styling)。
