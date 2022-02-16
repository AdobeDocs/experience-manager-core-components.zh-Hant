---
title: 窗體隱藏元件
description: 「核心元件表單隱藏」元件允許顯示隱藏欄位。
role: Architect, Developer, Admin, User
exl-id: 0364cd3b-3c09-46db-9392-a67e3f9ea7a5
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 2%

---

# 窗體隱藏元件{#form-hidden-component}

「核心元件表單隱藏」元件允許顯示隱藏欄位。

## 使用狀況 {#usage}

核心元件表單隱藏元件允許建立隱藏欄位，將有關當前頁面的資訊傳回AEM，並與 [形式容器元件](form-container.md)。

欄位屬性可由中的內容編輯器定義 [配置對話框](form-hidden.md)。

## 版本和相容性 {#version-and-compatibility}

窗體隱藏元件的當前版本為v2，該版本於2018年1月隨核心元件2.0.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |
| [v1](/help/components/v1/form-hidden-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗「表單隱藏元件」，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_form_hidden)。

### 技術詳細資訊 {#technical-details}

有關表單隱藏元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_hidden_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義隱藏欄位的參數。

![「表單隱藏編輯」對話框](/help/assets/form-hidden-edit.png)

* **名稱**  — 與表單資料一起提交的欄位名稱
* **值**  — 與表單資料一起提交的欄位值
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

由於「表單隱藏」元件通常沒有可見屬性，因此編輯器中元件的佔位符將顯示 **名稱** 和 **值** 欄位值，以幫助作者確定相應的「表單隱藏」元件。

![窗體隱藏元件示例](/help/assets/form-hidden-example.png)

## 設計對話框 {#design-dialog}

### 樣式頁籤 {#styles-tab}

窗體隱藏元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
