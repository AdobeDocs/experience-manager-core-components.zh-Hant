---
title: 進度條元件
description: 進度條元件直觀地表示向目標的進度
role: Architect, Developer, Admin, User
exl-id: 47afc5a6-ac57-4b6c-92c4-015ca956a20b
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 2%

---

# 進度條元件 {#progress-bar-component}

核心元件進度條元件直觀地表示目標的進度。

## 使用狀況 {#usage}

進度條元件允許內容作者通過定義完成百分比來輕鬆建立進度條，從而允許直觀地顯示向目標前進的進度。

## 版本和相容性 {#version-and-compatibility}

進度條元件的當前版本為v1，該版本於2020年5月隨核心元件2.9.0版一起推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |

## 元件輸出示例 {#sample-component-output}

要體驗進度條元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_progressbar)。

### 技術詳細資訊 {#technical-details}

有關進度條元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_progress_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

![進度條元件的編輯對話框](/help/assets/progress-bar-edit.png)

* **完成**  — 進度（以百分比表示）
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義應用於進度條元件的樣式。

### 樣式頁籤 {#styles-tab}

進度欄元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

進度條元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
