---
title: 分隔符號元件
description: 分隔符號元件會在頁面上的元件之間建立分隔符號
role: Architect, Developer, Admin, User
exl-id: 79f19368-67fa-4864-93f7-2aa801d13fdb
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 4%

---

# 分隔符號元件 {#separator-component}

核心元件分隔符號元件會顯示用於分隔內容的水準規則。

## 使用狀況 {#usage}

分隔符號元件可讓內容作者輕鬆建立水準規則，作為內容之間的分隔，以便更妥善地組織頁面上的資訊。

## 版本與相容性 {#version-and-compatibility}

分隔符號元件的目前版本為v1，已於2019年2月隨核心元件2.3.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容 | 相容 | 相容 |

## 範例元件輸出 {#sample-component-output}

若要體驗分隔符號元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_separator)。

### 技術詳細資訊 {#technical-details}

如需分隔符號元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_separator_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

![分隔符元件的編輯對話框](/help/assets/separator-edit.png)

* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義套用至分隔符號元件的樣式。

### 樣式標籤 {#styles-tab}

分隔符元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
