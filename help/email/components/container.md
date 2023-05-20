---
title: 電子郵件容器元件
description: 電子郵件容器元件允許為電子郵件內容中的多個附加元件建立容器。
role: Architect, Developer, Admin, User
exl-id: 3b271e95-0093-4cb1-bb83-8446ba12a821
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---


# 電子郵件容器元件 {#email-container-component}

電子郵件容器元件允許為電子郵件內容中的多個附加元件建立容器。

## 使用狀況 {#usage}

「電子郵件容器」元件允許為電子郵件內容中的多個附加元件建立容器，並可用於對其他元件進行分組並應用通用樣式或佈局。

* 可在 [配置對話框。](#configure-dialog)
* 將電子郵件容器元件添加到頁面時的預設值可以在 [設計對話框。](#design-dialog)

將電子郵件容器元件添加到頁面後，內容作者可以將其他元件拖放到頁面中。

## 版本和相容性 {#version-and-compatibility}

電子郵件容器元件的當前版本是v1，該版本於2022年10月隨電子郵件核心元件的X版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

有關電子郵件核心元件版本和版本的詳細資訊，請參閱文檔 [電子郵件核心元件版本。](/help/email/versions.md)

## 技術詳細資訊 {#technical-details}

有關容器元件的最新技術文檔 [中。](https://adobe.com/go/aem_cmp_tech_email_container_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

「配置」對話框允許內容作者定義容器項目及其在內容中的行為和顯示方式。

![電子郵件容器元件的編輯對話框](/help/email/assets/email-container-configure.png)

* **佈局**  — 此選項定義電子郵件容器元件的行為或佈局行為。
   * **全寬**
   * **半|半**
   * **三分之一|三分之二**
   * **三分之二|三分之一**
   * **第三|第三|第三|**
* **背景顏色**  — 可定義為自由格式RGB值或使用拾色器 [取決於配置](#container-settings-tab)
* **背景影像**  — 為容器定義背景影像， [取決於配置](#container-settings-tab)
* **ID**  — 此選項允許控制HTML中元件的唯一標識符。
   * 如果留空，則系統會為您自動生成唯一ID，並且可以通過檢查生成的內容來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS。

### 樣式頁籤 {#styles-tab-edit}

電子郵件容器元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便該頁籤可用。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義使用電子郵件容器元件的內容作者可用的選項。

### 允許的元件頁籤 {#allowed-components-tab}

的 **允許的元件** 頁籤用於定義哪些元件可以作為項目由內容作者添加到電子郵件容器元件。

的 **允許的元件** 頁籤函式，與同名的頁籤相同 [在模板編輯器中定義佈局容器的策略和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 預設元件頁籤 {#default-components-tab}

的 **預設元件** 頁籤用於定義在容器上放置特定資產類型時將哪個元件添加到元件中，類似於 [如何在頁面模板中定義預設元件。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 「容器設定」頁籤 {#container-settings-tab}

的 **容器設定** 頁籤定義作者是否可以定義背景影像或顏色。

![電子郵件容器元件設計對話框的容器設定頁籤](/help/email/assets/email-container-design-container-settings.png)

* **背景影像**
   * **啟用背景影像**  — 選擇此選項可使內容作者為容器定義背景影像。
* **背景色彩**
   * **啟用背景顏色**  — 選擇此選項可使內容作者為容器定義背景顏色。
   * **僅色板**  — 選擇此選項僅允許內容作者從容器背景顏色的預定義顏色色板中進行選擇。
      * 僅在 **啟用背景顏色** 已選中
* **允許的色板**  — 定義內容作者可以從中選擇容器背景顏色的預定義顏色
   * 使用 **添加** 按鈕。 添加後，將向清單中添加一個條目，該清單包含以下列：
   * **值**  — 通過RGB值手動定義顏色
      * 點擊或按一下顏色選取器，通過調整單個RGB值或定義十六進位值，更輕鬆地選擇顏色。
   * **刪除**  — 點擊或按一下以刪除色板。
   * **重新排列**  — 點擊或按一下並拖動以重新排序色板。

### 樣式頁籤 {#styles-tab}

電子郵件容器元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)
