---
title: 按鈕元件 (v1)
description: 核心元件按鈕元件允許建立和顯示按鈕。
role: Architect, Developer, Admin, User
exl-id: 63af16e4-dd4d-426d-88ef-769ecd1b3175
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '397'
ht-degree: 100%

---


# 按鈕元件 (v1) {#button-component}

核心元件按鈕元件允許在頁面上設定和顯示按鈕項目。

## 用途 {#usage}

利用核心元件按鈕元件，可在頁面上包含按鈕。

* 可以在[設定對話框](#configure-dialog)中選取按鈕的屬性。
* 按鈕元件的樣式可在[設計對話框](#design-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

本文件詳細說明「按鈕元件」的 v1 版本，此元件最初隨 2019 年 6 月的「核心元件」2.5.0 版發行導入。

>[!CAUTION]
>
>本文件說明按鈕元件 v1。
>
>如需按鈕元件目前版本的詳細資訊，請參閱[按鈕元件](/help/components/button.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「按鈕元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_button)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_button_v1_tw)有關按鈕元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義按鈕，以及其對頁面訪客的行為與顯示方式。

### 屬性索引標籤 {#properties-tab}

![按鈕元件編輯對話框的屬性索引標籤](/help/assets/button-edit-properties.png)

* **文字** - 按鈕上顯示的文字
* **連結** - 連結至 AEM 中的內容頁面、外部資源或錨點
   * 使用&#x200B;**選取對話框** 在 AEM 中選擇路徑。
* **圖示** - 在按鈕中顯示圖示的識別碼
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

### 協助工具索引標籤 {#accessibility-tab}

![按鈕元件編輯對話框的協助工具索引標籤](/help/assets/button-edit-accessibility.png)

在&#x200B;**協助工具**&#x200B;索引標籤上，可以設定元件的 [ARIA 協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤值。

* **標籤** - 元件的 ARIA 標籤屬性值

## 設計對話框 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

按鈕元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「按鈕元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
