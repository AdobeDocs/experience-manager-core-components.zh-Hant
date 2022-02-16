---
title: 分隔符號元件
description: 分隔符元件在頁面上的元件之間建立一個分隔符
role: Architect, Developer, Admin, User
exl-id: 79f19368-67fa-4864-93f7-2aa801d13fdb
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 4%

---

# 分隔符號元件 {#separator-component}

核心元件分隔符元件顯示用於分隔內容的水準規則。

## 使用狀況 {#usage}

「分隔符」元件允許內容作者輕鬆地建立水準規則作為內容之間的分隔，以更好地組織頁面上的資訊。

## 版本和相容性 {#version-and-compatibility}

Separator Component的當前版本是v1，該版本於2019年2月隨核心元件2.3.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |

## 元件輸出示例 {#sample-component-output}

要體驗分隔符元件，並查看其配置選項示例以及HTML和JSON輸出，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_separator)。

### 技術詳細資訊 {#technical-details}

有關分隔符元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_separator_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

![分隔符元件的編輯對話框](/help/assets/separator-edit.png)

* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義應用於分隔符元件的樣式。

### 樣式頁籤 {#styles-tab}

分隔符元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
