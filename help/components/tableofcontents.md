---
title: 目錄元件
description: 目錄元件根據頁面內容中的標題建立一個ToC，使讀者能夠快速瀏覽頁面。
role: Architect, Developer, Admin, User
source-git-commit: 52c63ecb014e5d4fda4d166d92e8efb3163633ba
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 1%

---

# 目錄元件 {#table-of-contents-component}

目錄元件根據頁面內容中的標題建立一個ToC，使讀者能夠快速瀏覽頁面。

## 使用狀況 {#usage}

「目錄」元件使站點訪問者能夠通過基於頁面內容標題生成的ToC快速瀏覽頁面內容。

的 [編輯對話框](#edit-dialog) 允許內容作者定義要在ToC中使用的標題範圍。 使用 [設計對話框](#design-dialog)，當內容作者將目錄元件添加到頁面時，模板作者可以設定標題的預設值，並基於類名限制包含在ToC中的標題。

## 版本和相容性 {#version-and-compatibility}

目錄元件的當前版本為v1，該版本於2022年5月隨核心元件2.20.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗「目錄」元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_tableofcontents)。

### 技術詳細資訊 {#technical-details}

有關目錄元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者定義目錄元件應作為ToC呈現的標題級別範圍。

![目錄元件的編輯對話框](/help/assets/tableofcontents-edit.png)

**清單類型**  — 此選項定義清單應是項目符號清單還是編號清單。
* **標題起始級別**  — 此選項定義目錄元件應呈現的最高級別標題。
* **標題停止級別**  — 此選項定義目錄元件應呈現的最低級別標題。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

## 設計對話框 {#design-dialog}

使用「設計」對話框，模板作者可以設定「目錄元件」的標題範圍的預設值，並基於類名限制包含在ToC中的標題。

### 屬性頁籤 {#properties-tab}

![「快速搜索元件的設計」對話框](/help/assets/tableofcontents-design.png)

* **限制清單類型**  — 此選項定義元件將生成的清單類型。 選擇此選項將限制內容作者選擇其他清單類型的能力。
* **限制起始層**  — 此選項定義內容作者為定義ToC可選擇的最高標題級別。
* **限制停止級別**  — 此選項定義內容作者為定義ToC可選擇的最低標題級別。
* **包括類名**  — 如果設定此選項，則目錄元件將只考慮具有指定類名或包含在指定類名元素中的標題。
   * 點擊或按一下 **添加** 表徵圖，以添加一個或多個類名。
   * 點擊或按一下 **刪除** 表徵圖，可將其刪除。
* **忽略類名**  — 如果設定此選項，則目錄元件將忽略具有指定類名或包含在指定類名元素中的標題。
   * 點擊或按一下 **添加** 表徵圖，以添加一個或多個類名。
   * 點擊或按一下 **刪除** 表徵圖，可將其刪除。

### 樣式頁籤 {#styles-tab}

目錄元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

目錄元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
