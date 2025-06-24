---
title: 進度列元件
description: 進度列元件會以視覺化方式呈現目標的進度
role: Architect, Developer, Admin, User
exl-id: 47afc5a6-ac57-4b6c-92c4-015ca956a20b
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 4%

---


# 進度列元件 {#progress-bar-component}

核心元件進度列元件會以視覺化方式呈現目標的進度。

{{traditional-aem}}

## 使用情況 {#usage}

進度列元件可讓內容作者透過定義完成百分比來輕鬆建立進度列，並以直覺式的視覺方式顯示向目標的進度。

## 版本和相容性 {#version-and-compatibility}

進度列元件的目前版本是v1，此版本隨2020年5月的核心元件2.9.0版的發行版本引入，說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|---|
| v1 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 | 相容 |

## 範例元件輸出 {#sample-component-output}

若要體驗進度列元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_progressbar)。

### 技術細節 {#technical-details}

在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_progress_v1)上可找到有關進度列元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

![進度列元件的編輯對話方塊](/help/assets/progress-bar-edit.png)

* **完成** — 以百分比表示的進度
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義套用至進度列元件的樣式。

### 樣式索引標籤 {#styles-tab}

進度列元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

進度列元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
