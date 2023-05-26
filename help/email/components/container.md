---
title: 電子郵件容器元件
description: 電子郵件容器元件可讓您為電子郵件內容中的多個其他元件建立容器。
role: Architect, Developer, Admin, User
exl-id: 3b271e95-0093-4cb1-bb83-8446ba12a821
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---


# 電子郵件容器元件 {#email-container-component}

電子郵件容器元件可讓您為電子郵件內容中的多個其他元件建立容器。

## 使用狀況 {#usage}

電子郵件容器元件可讓您為電子郵件內容中的多個其他元件建立容器，並可用於分組其他元件及套用通用樣式或版面。

* 容器的屬性可在以下位置選取： [設定對話方塊。](#configure-dialog)
* 將電子郵件容器元件新增至頁面時的預設值，可以在 [設計對話方塊。](#design-dialog)

將電子郵件容器元件新增至頁面後，內容作者就可以將其他元件拖放至其中。

## 版本和相容性 {#version-and-compatibility}

電子郵件容器元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

如需電子郵件核心元件版本的詳細資訊，請參閱本檔案 [電子郵件核心元件版本。](/help/email/versions.md)

## 技術細節 {#technical-details}

有關容器元件的最新技術檔案 [在GitHub上可找到。](https://adobe.com/go/aem_cmp_tech_email_container_v1)

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案。](/help/developing/overview.md)

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義容器專案，以及它在您的內容中的行為和顯示方式。

![電子郵件容器元件的「編輯」對話方塊](/help/email/assets/email-container-configure.png)

* **版面**  — 此選項會定義電子郵件容器元件的行為或佈局行為。
   * **全寬**
   * **一半|一半**
   * **三分之一|三分之一**
   * **三分之二|三分之一**
   * **三分之一|三分之一|三分之一**
* **背景顏色**  — 定義為自由格式的RGB值，或使用檢色器、 [視設定而定](#container-settings-tab)
* **背景影像**  — 定義容器的背景影像， [視設定而定](#container-settings-tab)
* **ID**  — 此選項可讓您控制HTML中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果內容找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS造成影響。

### 樣式索引標籤 {#styles-tab-edit}

電子郵件容器元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的效果相同。

必須在以下位置為此元件設定樣式： [設計對話方塊](#design-dialog) 讓索引標籤可用。

## 設計對話方塊 {#design-dialog}

使用「設計」對話方塊時，範本作者可以定義哪些選項可供使用電子郵件容器元件的內容作者使用。

### 允許的元件索引標籤 {#allowed-components-tab}

此 **允許的元件** tab可用來定義哪些元件可由內容作者新增為電子郵件容器元件的專案。

此 **允許的元件** tab的功能與相同名稱的標籤相同，當 [在範本編輯器中定義配置容器的原則和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 預設元件標籤 {#default-components-tab}

此 **預設元件** tab可用來定義在特定資產型別拖放至容器時，要新增至元件的元件，類似於 [如何在頁面範本上定義預設元件。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 容器設定標籤 {#container-settings-tab}

此 **容器設定** tab會定義作者是否可以定義背景影像或顏色。

![電子郵件容器元件之「設計」對話方塊的「容器設定」標籤](/help/email/assets/email-container-design-container-settings.png)

* **背景影像**
   * **啟用背景影像**  — 選取此選項可讓內容作者定義容器的背景影像。
* **背景色彩**
   * **啟用背景顏色**  — 選取此選項可讓內容作者定義容器的背景顏色。
   * **僅限色票**  — 選取此選項，僅允許內容作者從預先定義的色票中選取容器背景顏色。
      * 僅適用於 **啟用背景顏色** 已選取
* **允許的色票**  — 定義內容作者可從中選擇容器背景顏色的預定義顏色
   * 使用 **新增** 按鈕以新增預先定義的色票。 新增後，一個專案會新增到清單中，包含以下欄：
   * **值**  — 透過RGB值手動定義顏色
      * 點選或按一下檢色器，即可調整個別RGB值或定義十六進位值，更輕鬆地選取顏色。
   * **刪除**  — 點選或按一下以刪除色票。
   * **重新排列**  — 點選或按一下並拖曳以重新排序色票。

### 樣式索引標籤 {#styles-tab}

電子郵件容器元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)
