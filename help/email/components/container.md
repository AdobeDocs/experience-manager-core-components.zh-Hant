---
title: 電子郵件容器元件
description: 電子郵件容器元件可讓您為電子郵件內容中的多個其他元件建立容器。
role: Architect, Developer, Admin, User
exl-id: 3b271e95-0093-4cb1-bb83-8446ba12a821
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 1%

---


# 電子郵件容器元件 {#email-container-component}

電子郵件容器元件可讓您為電子郵件內容中的多個其他元件建立容器。

## 使用情況 {#usage}

電子郵件容器元件可讓您為電子郵件內容中的多個其他元件建立容器，並可用於分組其他元件以及套用通用樣式或版面。

* 可在[設定對話方塊中選取容器的屬性。](#configure-dialog)
* 將電子郵件容器元件新增至頁面時的預設值可以在[設計對話方塊中定義。](#design-dialog)

將電子郵件容器元件新增到頁面後，內容作者就可以將其他元件拖放到該頁面中。

## 版本和相容性 {#version-and-compatibility}

電子郵件容器元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

如需電子郵件核心元件版本的詳細資訊，請參閱檔案[電子郵件核心元件版本。](/help/email/versions.md)

## 技術細節 {#technical-details}

在GitHub上可找到容器元件[的最新技術檔案。](https://adobe.com/go/aem_cmp_tech_email_container_v1)

在[核心元件開發人員檔案中可找到有關開發核心元件的進一步詳細資料。](/help/developing/overview.md)

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義容器專案，以及它在您的內容中的行為和顯示方式。

![電子郵件容器元件的[編輯]對話方塊](/help/email/assets/email-container-configure.png)

* **配置** — 此選項定義電子郵件容器元件的行為或配置行為。
   * **全寬**
   * **一半|一半**
   * **三分之一|三分之二**
   * **三分之二|三分之一**
   * **三分之一|三分之一|三分之一**
* **背景色彩** — 定義為自由格式的RGB值，或使用檢色器，[視組態而定](#container-settings-tab)
* **背景影像** — 定義容器的背景影像，[視組態而定](#container-settings-tab)
* **ID** — 此選項允許控制HTML中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，但您可在檢查結果內容時找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS造成影響。

### 樣式索引標籤 {#styles-tab-edit}

電子郵件容器元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的選取具有相同的效果。

必須在[設計對話方塊](#design-dialog)中為此元件設定樣式，才能使用索引標籤。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些選項可供使用電子郵件容器元件的內容作者使用。

### 允許的元件標籤 {#allowed-components-tab}

**允許的元件**&#x200B;索引標籤是用來定義哪些元件可由內容作者新增為電子郵件容器元件的專案。

**允許的元件**&#x200B;索引標籤的功能與[在範本編輯器中定義配置容器的原則與屬性時的相同名稱索引標籤的功能相同。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 預設元件標籤 {#default-components-tab}

**預設元件**&#x200B;索引標籤用於定義在特定資產型別放到容器上時，要新增到元件的元件，類似於[如何在頁面範本上定義預設元件。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 容器設定標籤 {#container-settings-tab}

**容器設定**&#x200B;索引標籤定義作者是否可以定義背景影像或顏色。

電子郵件容器元件之設計對話方塊的![容器設定標籤](/help/email/assets/email-container-design-container-settings.png)

* **背景影像**
   * **啟用背景影像** — 選取此選項可讓內容作者定義容器的背景影像。
* **背景色彩**
   * **啟用背景顏色** — 選取此選項可讓內容作者定義容器的背景顏色。
   * **僅色票** — 選取此選項，僅允許內容作者從預先定義的色票中選取容器背景顏色。
      * 只有在選取&#x200B;**啟用背景顏色**&#x200B;時可用
* **允許的色票** — 定義內容作者可從中選擇容器背景顏色的預定義顏色
   * 使用&#x200B;**新增**&#x200B;按鈕新增預先定義的色票。 新增專案後，專案會新增到清單中，包含以下欄：
   * **值** — 透過RGB值手動定義顏色
      * 點選或按一下檢色器，即可調整個別RGB值或定義十六進位值，更輕鬆地選取顏色。
   * **刪除** — 點選或按一下以刪除色票。
   * **重新排列** — 點選或按一下並拖曳以重新排列色票。

### 樣式索引標籤 {#styles-tab}

電子郵件容器元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)
