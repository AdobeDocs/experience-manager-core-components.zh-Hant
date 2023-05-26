---
title: 按鈕元件
description: 核心元件按鈕元件可讓您建立及顯示按鈕。
role: Architect, Developer, Admin, User
exl-id: e17efd1d-90d4-497a-9e7d-45934d81bc28
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---

# 按鈕元件{#button-component}

利用核心元件按鈕元件，可在頁面上設定和顯示按鈕專案。

## 使用狀況 {#usage}

利用核心元件按鈕元件，可在頁面上包含按鈕。

* 按鈕的屬性可在 [設定對話方塊](#configure-dialog).
* 按鈕元件的樣式可在 [設計對話方塊](#design-dialog).

## 版本和相容性 {#version-and-compatibility}

Button元件的目前版本是v2，此版本隨2022年2月的核心元件2.18.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v2 | - | 相容 | 相容 |
| [v1](v1/button.md) | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗按鈕元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_button).

## 技術細節 {#technical-details}

有關按鈕元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_button_v2).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義按鈕，以及對於頁面的訪客它會如何表現和顯示。

### 屬性標籤 {#properties-tab}

![按鈕元件「編輯」對話方塊的「屬性」標籤](/help/assets/button-edit-properties.png)

* **文字**  — 按鈕上顯示的文字
* **連結**  — 連結至AEM中的內容頁面、外部資源或錨點
   * 使用 **選擇對話方塊** 以在AEM中選擇路徑。
* **在新標籤中開啟連結**  — 如果勾選，連結將在新的瀏覽器分頁中開啟。
* **圖示**  — 在按鈕中顯示圖示的識別碼
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 協助工具標籤 {#accessibility-tab}

![按鈕元件「編輯」對話方塊的「協助工具」標籤](/help/assets/button-edit-accessibility.png)

於 **協助工具** 標籤，可設定的值 [ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性值

### 樣式索引標籤 {#styles-tab-edit}

![按鈕元件「編輯」對話方塊的「樣式」索引標籤](/help/assets/button-edit-styles.png)

按鈕元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling).

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的效果相同。

必須在以下位置為此元件設定樣式： [設計對話方塊](#design-dialog) 讓下拉式功能表可供使用。

## 設計對話方塊 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

按鈕元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe使用者端資料層 {#data-layer}

按鈕元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
