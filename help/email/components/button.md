---
title: 電子郵件按鈕元件
description: 電子郵件按鈕元件允許您在內容中設定和顯示按鈕項目。
role: Architect, Developer, Admin, User
exl-id: b144e8d1-1097-475d-b2eb-3353c176afb9
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '517'
ht-degree: 100%

---


# 電子郵件按鈕元件 {#email-button-component}

電子郵件按鈕元件允許您在內容中設定和顯示按鈕項目。

## 用途 {#usage}

電子郵件按鈕元件允許在您的內容中加入按鈕，內容讀者點按後可連結至其他資源。

* 可以在[設定對話框](#configure-dialog)中選取按鈕的屬性。
* 電子郵件按鈕元件的樣式可在[設計對話框](#design-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

電子郵件按鈕元件的目前版本為 v1，此版本於 2022 年 10 月隨著電子郵件核心元件 x 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[電子郵件核心元件版本](/help/email/versions.md)文件。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_button_v1_tw)有關電子郵件按鈕元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件。](/help/developing/overview.md)

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義按鈕，以及其向內容讀者的行為與顯示方式。

### 屬性索引標籤 {#properties-tab}

![按鈕元件編輯對話框的屬性索引標籤](/help/email/assets/email-button-edit-properties.png)

* **文字** - 按鈕上顯示的文字
   * 按一下行銷活動圖示以開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入來自 Adobe Campaign 的動態內容。
* **連結** - 連結至 AEM 中的內容頁面、外部資源或錨點
   * 使用&#x200B;**選取對話框** 在 AEM 中選擇路徑。
   * 按一下行銷活動圖示以開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入來自 Adobe Campaign 的動態內容。
* **圖示** - 在按鈕中顯示圖示的識別碼
* **ID** - 此選項允許控制 HTML 中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的內容找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS 產生影響。
* **在新索引標籤中開啟連結** - 若已勾選，該連結將在新的瀏覽器索引標籤中開啟。

### 協助工具索引標籤 {#accessibility-tab}

![按鈕元件編輯對話框的協助工具索引標籤](/help/email/assets/email-button-edit-accessibility.png)

在&#x200B;**協助工具**&#x200B;索引標籤上，可以設定元件的 [ARIA 協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤值。

* **標籤** - 元件的 ARIA 標籤屬性值

### 樣式索引標籤 {#styles-tab-edit}

電子郵件按鈕元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取想要套用至元件的樣式。在編輯對話框中所做的選取，與從元件工具列中選擇具有相同效果。

元件樣式必須在[設計對話框](#design-dialog)中設定，才能使用該索引標籤。

## 設計對話框 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

電子郵件按鈕元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
