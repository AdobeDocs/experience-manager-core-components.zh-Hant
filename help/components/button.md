---
title: 按鈕元件
description: 核心元件按鈕元件可讓您建立和顯示按鈕。
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---


# 按鈕元件{#button-component}

核心元件按鈕元件可讓您在頁面上設定和顯示按鈕項目。

## 使用狀況 {#usage}

核心元件按鈕元件允許在頁面上包含按鈕。

* 可在[configure dialog](#configure-dialog)中選擇按鈕的屬性。
* 可在[設計對話框](#design-dialog)中定義「按鈕元件」的樣式。

## 版本和相容性{#version-and-compatibility}

Button Component的目前版本為v1，此版本於2019年6月隨核心元件2.5.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗「按鈕元件」，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_button)。

## 技術詳細資訊{#technical-details}

有關Button Component [的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_button_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

「設定」對話方塊可讓內容作者定義按鈕，以及按鈕的行為和顯示方式，讓頁面的訪客使用。

### 屬性頁籤{#properties-tab}

![按鈕元件編輯對話框的屬性頁籤](/help/assets/button-edit-properties.png)

* **文字** -要顯示在按鈕上的文字
* **連結** -連結至AEM內的內容頁面、外部資源或錨點
   * 使用&#x200B;**選擇對話方塊**&#x200B;來選擇AEM中的路徑。
* **Icon**  —— 用於在按鈕中顯示表徵圖的標識符
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

### 輔助功能頁籤{#accessibility-tab}

![「按鈕元件」編輯對話方塊的「協助工具」索引標籤](/help/assets/button-edit-accessibility.png)

在&#x200B;**Accessibility**&#x200B;標籤上，可為元件的[ARIA accessibility](https://www.w3.org/WAI/standards-guidelines/aria/)標籤設定值。

* **Label**  —— 元件的ARIA label屬性的值

## 設計對話框{#design-dialog}

### 樣式標籤{#styles-tab}

Button Component支援AEM [Style System](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層{#data-layer}

按鈕元件支援[Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
