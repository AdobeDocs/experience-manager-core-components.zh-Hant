---
title: 按鈕元件(v1)
description: 核心元件按鈕元件可讓您建立及顯示按鈕。
role: Architect, Developer, Admin, User
exl-id: 63af16e4-dd4d-426d-88ef-769ecd1b3175
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---

# 按鈕元件(v1) {#button-component}

利用核心元件按鈕元件，可在頁面上設定和顯示按鈕專案。

## 使用狀況 {#usage}

利用核心元件按鈕元件，可在頁面上包含按鈕。

* 按鈕的屬性可在 [設定對話方塊](#configure-dialog).
* 按鈕元件的樣式可在 [設計對話方塊](#design-dialog).

## 版本和相容性 {#version-and-compatibility}

本檔案說明按鈕元件v1，此版本隨2019年6月的核心元件發行版本2.5.0的發佈引入。

>[!CAUTION]
>
>本檔案說明按鈕元件v1。
>
>如需目前版本的Button元件的詳細資訊，請參閱 [按鈕元件](/help/components/button.md) 檔案。

## 範例元件輸出 {#sample-component-output}

若要體驗按鈕元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_button).

## 技術細節 {#technical-details}

有關按鈕元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_button_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義按鈕，以及對於頁面的訪客它會如何表現和顯示。

### 屬性標籤 {#properties-tab}

![按鈕元件「編輯」對話方塊的「屬性」標籤](/help/assets/button-edit-properties.png)

* **文字**  — 按鈕上顯示的文字
* **連結**  — 連結至AEM中的內容頁面、外部資源或錨點
   * 使用 **選擇對話方塊** 以在AEM中選擇路徑。
* **圖示**  — 在按鈕中顯示圖示的識別碼
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 協助工具標籤 {#accessibility-tab}

![按鈕元件「編輯」對話方塊的「協助工具」標籤](/help/assets/button-edit-accessibility.png)

於 **協助工具** 標籤，可設定的值 [ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性值

## 設計對話方塊 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

按鈕元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe使用者端資料層 {#data-layer}

按鈕元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
