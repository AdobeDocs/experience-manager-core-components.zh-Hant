---
title: 分隔符號元件
description: 分隔符號元件會在頁面上的元件之間建立分隔符號
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 3%

---


# 分隔符號元件 {#separator-component}

核心元件分隔符號元件會顯示用於分隔內容的水準規則。

## 使用狀況 {#usage}

「分隔元件」可讓內容作者輕鬆建立水準規則，作為內容之間的分隔，以便更好地組織頁面上的資訊。

## 版本與相容性 {#version-and-compatibility}

目前的Separator元件版本為v1，此版本於2019年2月隨核心元件2.3.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 雲端服務 |
|---|---|---|---|
| v1 | 相容 | 相容 | 相容 |

## 元件輸出示例 {#sample-component-output}

若要體驗「分隔符號元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪「元件 [庫」](https://adobe.com/go/aem_cmp_library_separator)。

### 技術詳細資訊 {#technical-details}

有關Separator Component的最新技術文 [件可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_separator_v1)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

![分隔符元件的編輯對話框](/help/assets/separator-edit.png)

* **ID** —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義應用於分隔符元件的樣式。

### 樣式標籤 {#styles-tab}

Separator Component支援AEM [Style System](/help/get-started/authoring.md#component-styling)。
