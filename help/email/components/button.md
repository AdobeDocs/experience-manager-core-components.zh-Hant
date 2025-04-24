---
title: 電子郵件按鈕元件
description: 電子郵件按鈕元件允許您在內容中設定和顯示按鈕專案。
role: Architect, Developer, Admin, User
exl-id: b144e8d1-1097-475d-b2eb-3353c176afb9
source-git-commit: 91969e4956bef1a511b8d588d5290a7999bf86ec
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 1%

---


# 電子郵件按鈕元件 {#email-button-component}

電子郵件按鈕元件允許您在內容中設定和顯示按鈕專案。

## 使用情況 {#usage}

電子郵件按鈕元件允許在您的內容中加入按鈕，內容閱讀器可點按，連結到其他資源。

* 可在[設定對話方塊中選取按鈕的屬性。](#configure-dialog)
* 電子郵件按鈕元件的樣式可在[設計對話方塊中定義。](#design-dialog)

## 版本和相容性 {#version-and-compatibility}

電子郵件按鈕元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容 | - | - |

如需核心元件版本的詳細資訊，請參閱檔案[電子郵件核心元件版本。](/help/email/versions.md)

## 技術細節 {#technical-details}

您可以在GitHub上找到有關電子郵件按鈕元件[的最新技術檔案。](https://adobe.com/go/aem_cmp_tech_email_button_v1)

在[核心元件開發人員檔案中可找到有關開發核心元件的進一步詳細資料。](/help/developing/overview.md)

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義按鈕，以及按鈕對內容讀者的行為和顯示方式。

### 屬性標籤 {#properties-tab}

按鈕元件](/help/email/assets/email-button-edit-properties.png)之編輯對話方塊的![屬性標籤

* **文字** — 按鈕上顯示的文字
   * 按一下Campaign圖示以開啟[選取Adobe Campaign變數](/help/email/campaign-variables.md)對話方塊，插入來自Adobe Campaign的動態內容。
* **連結** — 連結至AEM中的內容頁面、外部資源或錨點
   * 使用&#x200B;**選取範圍對話方塊**&#x200B;在AEM中選擇路徑。
   * 按一下Campaign圖示以開啟[選取Adobe Campaign變數](/help/email/campaign-variables.md)對話方塊，插入來自Adobe Campaign的動態內容。
* **圖示** — 在按鈕中顯示圖示的識別碼
* **ID** — 此選項允許控制HTML中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，但您可在檢查結果內容時找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS造成影響。
* **在新標籤中開啟連結** — 如果勾選，將在新的瀏覽器標籤中開啟連結。

### 協助工具標籤 {#accessibility-tab}

![按鈕元件](/help/email/assets/email-button-edit-accessibility.png)之編輯對話方塊的協助工具標籤

在&#x200B;**協助工具**&#x200B;標籤上，可以為元件設定[ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤的值。

* **標籤** — 元件的ARIA標籤屬性值

### 樣式索引標籤 {#styles-tab-edit}

電子郵件按鈕元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的選取具有相同的效果。

必須在[設計對話方塊](#design-dialog)中為此元件設定樣式，才能使用索引標籤。

## 設計對話方塊 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

電子郵件按鈕元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
