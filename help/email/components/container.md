---
title: 電子郵件容器元件
description: 電子郵件容器元件可讓您為電子郵件內容中的多個其他元件建立容器。
role: Architect, Developer, Admin, User
exl-id: 3b271e95-0093-4cb1-bb83-8446ba12a821
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '780'
ht-degree: 100%

---


# 電子郵件容器元件 {#email-container-component}

電子郵件容器元件可讓您為電子郵件內容中的多個其他元件建立容器。

## 用途 {#usage}

電子郵件核心元件容器元件可在您的電子郵件內容中為多個其他元件建立容器，並可用於分組其他元件及套用通用樣式或版面。

* 可以在[設定對話框](#configure-dialog)中選取容器的屬性。
* 將電子郵件容器元件新增至頁面時，可在[設計對話框](#design-dialog)中定義預設值。

將電子郵件容器元件新增到頁面後，內容作者就可以將其他元件拖放到該頁面中。

## 版本和相容性 {#version-and-compatibility}

電子郵件容器元件的目前版本為 v1，此版本於 2022 年 10 月隨著電子郵件核心元件 X 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

如需「電子郵件核心元件」版本和發行版本的進一步詳細資訊，請參閱[電子郵件核心元件版本](/help/email/versions.md)文件。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_container_v1)有關容器元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件。](/help/developing/overview.md)

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義容器項目，以及其在內容內的行為與顯示方式。

![電子郵件容器元件的編輯對話框](/help/email/assets/email-container-configure.png)

* **版面** - 此選項定義電子郵件容器元件的行為或版面行為。
   * **全寬**
   * **1/2|1/2**
   * **1/3|2/3**
   * **2/3|1/3**
   * **1/3|1/3|1/3**
* **背景顏色** - 透過自由格式的 RGB 值或使用檢色器定義，[視設定而定](#container-settings-tab)
* **背景影像** - 定義容器的背景影像，[視設定而定](#container-settings-tab)
* **ID** - 此選項允許控制 HTML 中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的內容找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS 產生影響。

### 樣式索引標籤 {#styles-tab-edit}

電子郵件容器元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取想要套用至元件的樣式。在編輯對話框中所做的選取，與從元件工具列中選擇具有相同效果。

元件樣式必須在[設計對話框](#design-dialog)中設定，才能使用該索引標籤。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可為使用電子郵件容器元件的內容作者定義可用選項。

### 允許的元件索引標籤 {#allowed-components-tab}

**允許的元件**&#x200B;索引標籤用於定義哪些元件可供內容作者作為項目新增至電子郵件容器元件。

[在範本編輯器中定義版面容器的原則與屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)時，**允許的元件**&#x200B;索引標籤與同名索引標籤的功能相同。

### 預設元件索引標籤 {#default-components-tab}

**預設元件**&#x200B;索引標籤用於定義當特定資產類型放置於容器上時，哪些元件要新增到元件中，類似於[如何在頁面範本上定義預設元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)。

### 容器設定索引標籤 {#container-settings-tab}

**容器設定**&#x200B;索引標籤定義作者是否可以定義背景影像或顏色。

![電子郵件容器元件設計對話框的容器設定索引標籤](/help/email/assets/email-container-design-container-settings.png)

* **背景影像**
   * **啟用背景影像** - 選取此選項可讓內容作者定義容器的背景影像。
* **背景顏色**
   * **啟用背景顏色** - 選取此選項可讓內容作者定義容器的背景顏色。
   * **僅色票** - 選取此選項，僅允許內容作者從預先定義的色票中選取容器背景顏色。
      * 只有在選取&#x200B;**啟用背景顏色**&#x200B;時可用
* **允許的色票** - 定義內容作者可從中選擇容器背景顏色的預先定義顏色
   * 使用&#x200B;**新增**&#x200B;按鈕新增預先定義的色票。新增後，就會在清單中新增一個項目，其中包含以下各欄：
   * **值** - 透過 RGB 值手動定義顏色
      * 點選或按一下檢色器，即可調整個別 RGB 值或定義十六進位值，更輕鬆地選取顏色。
   * **刪除** - 點選或按一下，以刪除色票。
   * **重新排列** - 點選或按一下並拖曳以重新排列色票。

### 樣式索引標籤 {#styles-tab}

電子郵件容器元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
