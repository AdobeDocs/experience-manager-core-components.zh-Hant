---
title: 電子郵件按鈕元件
description: 電子郵件按鈕元件允許設定並在您的內容中顯示按鈕專案。
role: Architect, Developer, Admin, User
exl-id: b144e8d1-1097-475d-b2eb-3353c176afb9
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---


# 電子郵件按鈕元件 {#email-button-component}

電子郵件按鈕元件允許設定並在您的內容中顯示按鈕專案。

## 使用狀況 {#usage}

電子郵件按鈕元件允許在您的內容中加入按鈕，內容閱讀器可點按，連結到其他資源。

* 按鈕的屬性可在 [設定對話方塊。](#configure-dialog)
* 電子郵件按鈕元件的樣式可在 [設計對話方塊。](#design-dialog)

## 版本和相容性 {#version-and-compatibility}

電子郵件按鈕元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [電子郵件核心元件版本。](/help/email/versions.md)

## 技術細節 {#technical-details}

有關電子郵件按鈕元件的最新技術檔案 [在GitHub上可找到。](https://adobe.com/go/aem_cmp_tech_email_button_v1)

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案。](/help/developing/overview.md)

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義按鈕，以及按鈕的行為和顯示方式，以供內容讀者閱讀。

### 屬性標籤 {#properties-tab}

![按鈕元件「編輯」對話方塊的「屬性」標籤](/help/email/assets/email-button-edit-properties.png)

* **文字**  — 按鈕上顯示的文字
   * 按一下Campaign圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，插入來自Adobe Campaign的動態內容。
* **連結**  — 連結至AEM中的內容頁面、外部資源或錨點
   * 使用 **選擇對話方塊** 以在AEM中選擇路徑。
   * 按一下Campaign圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，插入來自Adobe Campaign的動態內容。
* **圖示**  — 在按鈕中顯示圖示的識別碼
* **ID**  — 此選項可讓您控制HTML中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果內容找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS造成影響。
* **在新標籤中開啟連結**  — 如果勾選，連結將在新的瀏覽器分頁中開啟。

### 協助工具標籤 {#accessibility-tab}

![按鈕元件「編輯」對話方塊的「協助工具」標籤](/help/email/assets/email-button-edit-accessibility.png)

於 **協助工具** 標籤，可設定的值 [ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性值

### 樣式索引標籤 {#styles-tab-edit}

電子郵件按鈕元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling).

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的效果相同。

必須在以下位置為此元件設定樣式： [設計對話方塊](#design-dialog) 讓索引標籤可用。

## 設計對話方塊 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

電子郵件按鈕元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
