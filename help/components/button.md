---
title: 按鈕元件
description: 核心元件按鈕元件可建立及顯示按鈕。
role: Architect, Developer, Admin, User
exl-id: e17efd1d-90d4-497a-9e7d-45934d81bc28
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---

# 按鈕元件{#button-component}

核心元件按鈕元件可在頁面上設定及顯示按鈕項目。

## 使用狀況 {#usage}

核心元件按鈕元件可在頁面上包含按鈕。

* 可在[配置對話框](#configure-dialog)中選擇按鈕的屬性。
* 可在[design對話框](#design-dialog)中定義按鈕元件的樣式。

## 版本與相容性 {#version-and-compatibility}

目前的按鈕元件版本為v1，已於2019年6月隨核心元件2.5.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗按鈕元件以及查看其設定選項的範例以及HTML和JSON輸出，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_button)。

## 技術詳細資訊 {#technical-details}

有關按鈕元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_button_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者定義按鈕，以及按鈕的行為和顯示方式，供頁面的訪客使用。

### 屬性標籤 {#properties-tab}

![按鈕元件的編輯對話框的屬性頁簽](/help/assets/button-edit-properties.png)

* **文字**  — 要在按鈕上顯示的文字
* **連結**  — 連結至AEM、外部資源或錨點內的內容頁面
   * 使用&#x200B;**選擇對話框**&#x200B;選擇AEM內的路徑。
* **圖示**  — 在按鈕中顯示圖示的識別碼
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

### 協助工具標籤 {#accessibility-tab}

![按鈕元件的編輯對話方塊的協助工具索引標籤](/help/assets/button-edit-accessibility.png)

在&#x200B;**協助工具**&#x200B;標籤上，可以為元件的[ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤設定值。

* **標籤**  — 元件的ARIA標籤屬性值

## 設計對話方塊 {#design-dialog}

### 樣式標籤 {#styles-tab}

按鈕元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層 {#data-layer}

按鈕元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
