---
title: 進度欄元件
description: 進度列元件以視覺化方式呈現目標的進度
role: Architect, Developer, Admin, User
exl-id: 47afc5a6-ac57-4b6c-92c4-015ca956a20b
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 2%

---

# 進度欄元件 {#progress-bar-component}

核心元件進度列元件以視覺化方式呈現目標的進度。

## 使用狀況 {#usage}

進度欄元件可讓內容作者借由定義完成百分比，輕鬆建立進度欄，以直觀的方式顯示邁向目標的進度。

## 版本與相容性 {#version-and-compatibility}

進度列元件的目前版本為v1，此版本於2020年5月隨核心元件2.9.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容 | 相容 | 相容 |

## 範例元件輸出 {#sample-component-output}

若要體驗進度列元件以及查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_progressbar)。

### 技術詳細資訊 {#technical-details}

如需進度列元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_progress_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

![進度欄元件的編輯對話框](/help/assets/progress-bar-edit.png)

* **完成**  — 進度以百分比表示
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

## 設計對話方塊 {#design-dialog}

設計對話框允許模板作者定義應用於進度欄元件的樣式。

### 樣式標籤 {#styles-tab}

進度欄元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層 {#data-layer}

進度欄元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
