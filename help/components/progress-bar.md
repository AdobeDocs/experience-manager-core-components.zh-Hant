---
title: 進度列元件
description: 進度條元件以視覺化方式表示實現目標的進展
role: 架構師、開發人員、管理員、商業從業人員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 2%

---


# 進度條元件{#progress-bar-component}

核心元件進度列元件以視覺化方式呈現目標的進度。

## 使用狀況 {#usage}

進度列元件可讓內容作者透過定義完成百分比，輕鬆建立進度列，讓您以直覺式視覺化方式顯示目標進度。

## 版本和相容性{#version-and-compatibility}

目前的進度列元件版本為v1，此版本於2020年5月隨核心元件2.9.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容 | 相容 | 相容 |

## 元件輸出示例{#sample-component-output}

若要體驗進度列元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_progressbar)。

### 技術詳細資訊{#technical-details}

有關進度列元件[的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_progress_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

![進度欄元件的編輯對話方塊](/help/assets/progress-bar-edit.png)

* **完成** -進度按百分比計算
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

## 設計對話框{#design-dialog}

設計對話框允許模板作者定義應用於進度欄元件的樣式。

### 樣式標籤{#styles-tab}

進度條元件支AEM持[樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層{#data-layer}

進度條元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
