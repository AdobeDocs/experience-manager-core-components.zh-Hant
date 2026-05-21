---
title: 分隔符號元件
description: 分隔符號元件會在頁面上的元件之間建立區隔
role: Developer, Admin, User
exl-id: 79f19368-67fa-4864-93f7-2aa801d13fdb
TQID: https://experienceleague.adobe.com/phmSUsqkY69wmGhAtWuj1qvFcjr84gPe2H90CsKVAAE
product_v2:
  - id: c45915cf-e157-4af7-a80d-97b905bcb3a5
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: e2c1b6d3-bb7e-4fe8-8c72-f7b403298e91
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 73aa5234ac63fa3be99feebce448bb6722513838
workflow-type: tm+mt
source-wordcount: 309
ht-degree: 100%

---

# 分隔符號元件 {#separator-component}

核心元件分隔符號元件會顯示分隔內容的水平線。

{{traditional-aem}}

## 用途 {#usage}

分隔符號元件可讓內容作者輕鬆建立水平線作為內容之間的區隔，以便更妥善地整理頁面上的資訊。

## 版本和相容性 {#version-and-compatibility}

分隔符號元件的目前版本為 v1，此版本於 2019 年 2 月隨著核心元件 2.3.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|---|
| v1 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |

## 範例元件輸出 {#sample-component-output}

若要體驗「分隔符號元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_separator_tw)」。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_separator_v1_tw)有關分隔符號元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

![分隔符號元件的編輯對話框](/help/assets/separator-edit.png)

* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義套用至分隔符號元件的樣式。

### 樣式索引標籤 {#styles-tab}

分隔符號元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
