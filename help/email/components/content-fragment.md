---
title: 電子郵件內容片段元件
description: 電子郵件內容片段元件允許在內容中顯示內容片段。
role: Architect, Developer, Admin, User
exl-id: 9bc6b730-0d2a-4e5b-891c-d2f67f600bcc
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---


# 電子郵件內容片段元件 {#email-content-fragment-component}

電子郵件內容片段元件允許顯示 [內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 內容。

## 使用狀況 {#usage}

電子郵件內容片段元件允許包含 [內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 郵件內容。 內容片段是多通道結構化內容，可集中創作且易於重用。

* 可在 [配置對話框。](#configure-dialog)
* 可以在中定義處理某些影像和網格的資源類型 [設計對話框。](#design-dialog)
* 編輯選項將在 [內容片段編輯器，](#edit-dialog) 自定義以與電子郵件核心元件一起使用。

## 版本和相容性 {#version-and-compatibility}

電子郵件內容片段元件的當前版本為v1，此版本於2022年10月隨電子郵件核心元件的X版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

有關電子郵件核心元件版本和版本的詳細資訊，請參閱文檔 [電子郵件核心元件版本。](/help/email/versions.md)

## 技術詳細資訊 {#technical-details}

有關電子郵件內容片段元件的最新技術文檔 [中。](https://adobe.com/go/aem_cmp_tech_email_cf_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義要包括哪些內容片段和該片段的元素。

### 屬性頁籤 {#properties-tab}

![電子郵件內容片段元件](/help/email/assets/email-content-fragment-edit-properties.png)

* **內容片段**

   * 所需內容片段的路徑
   * 的 **選擇對話框** 可以用來定位碎片

* **顯示模式**
   * **單文本元素**  — 啟用選擇一個多行文本元素並啟用段落控制選項
* **變異**  — 要使用的內容片段的哪個變體(預設為 **母版**)

* **ID**  — 此選項允許控制HTML中元件的唯一標識符。
   * 如果留空，則系統會為您自動生成唯一ID，並且可以通過檢查生成的內容來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS。

### 段落控制項頁籤 {#paragraph-control-tab}

![電子郵件內容片段元件](/help/assets/content-fragment-edit-paragraph.png)

* **段落**  — 允許選擇所有段落或範圍
   * **全部**  — 顯示所有段落
   * **範圍**
      * 指定應顯示的段落範圍，用分號分隔
      * 例如 `1;3-5;7;9-*` 包括第一、第三至第五、第七和第九至最後各段
* **將標題作為自己的段落處理**

## 編輯對話框 {#edit-dialog}

使用電子郵件內容片段元件配置內容片段後，在內容編輯器中選擇該元件時，它會顯示 **編輯** 的雙曲餘切值。

![電子郵件內容片段元件工具欄](/help/email/assets/email-content-fragment-edit-toolbar.png)

點擊或按一下 **編輯** 按鈕開啟內容片段編輯器。 內容片段編輯器已擴展為包含 **選擇Adobe Campaign變數** 將Adobe Campaign變數插入內容片段。

![電子郵件的內容片段編輯器](/help/email/assets/email-content-fragment-editor.png)

有關編輯和創作內容片段的詳細資訊，請參閱文檔 [創作片段內容。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html)

## 設計對話框 {#design-dialog}

當使用內容片段配置電子郵件內容片段元件時，當您在內容編輯器中選擇它時，工具欄將顯示一個按鈕以開啟內容片段編輯器。


### 主頁籤 {#main-tab}

![電子郵件內容片段元件的設計對話框](/help/email/assets/email-content-fragment-design.png)

* **內部回應式格線**

   * 用於內部響應網格的Sling資源類型

### 樣式頁籤 {#styles-tab}

電子郵件體驗片段元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)
