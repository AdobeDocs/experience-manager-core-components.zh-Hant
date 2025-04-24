---
title: 電子郵件內容片段元件
description: 電子郵件內容片段元件可讓您在內容中顯示內容片段。
role: Architect, Developer, Admin, User
exl-id: 9bc6b730-0d2a-4e5b-891c-d2f67f600bcc
source-git-commit: 91969e4956bef1a511b8d588d5290a7999bf86ec
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 1%

---


# 電子郵件內容片段元件 {#email-content-fragment-component}

電子郵件內容片段元件可讓您在內容中顯示[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

## 使用情況 {#usage}

電子郵件內容片段元件允許在您的電子郵件內容中包含[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。 內容片段是多頻道結構化內容，可以集中編寫並輕鬆重複使用。

* 可在[設定對話方塊中選取片段及其屬性。](#configure-dialog)
* 可在[設計對話方塊中定義要處理特定影像和網格的資源型別。](#design-dialog)
* 編輯選項會在[內容片段編輯器，](#edit-dialog)中開啟選取的片段，此編輯器是專為搭配電子郵件核心元件使用而自訂。

## 版本和相容性 {#version-and-compatibility}

電子郵件內容片段元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容 | - | - |

如需電子郵件核心元件版本的詳細資訊，請參閱檔案[電子郵件核心元件版本。](/help/email/versions.md)

## 技術細節 {#technical-details}

在GitHub上可找到有關電子郵件內容片段元件[的最新技術檔案。](https://adobe.com/go/aem_cmp_tech_email_cf_v1)

在[核心元件開發人員檔案中可找到有關開發核心元件的進一步詳細資料。](/help/developing/overview.md)

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義要包含的內容片段及該片段的元素。

### 屬性標籤 {#properties-tab}

![電子郵件內容片段元件](/help/email/assets/email-content-fragment-edit-properties.png)

* **內容片段**

   * 所需內容片段的路徑
   * **選取範圍對話方塊**&#x200B;可用來尋找片段

* **顯示模式**
   * **單一文字元素** — 啟用選取一個多行文字元素並啟用段落控制選項
* **變數** — 要使用的內容片段變數（預設為&#x200B;**Master**）

* **ID** — 此選項允許控制HTML中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，但您可在檢查結果內容時找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS造成影響。

### 段落控制標籤 {#paragraph-control-tab}

![電子郵件內容片段元件](/help/assets/content-fragment-edit-paragraph.png)

* **段落** — 允許選取所有段落或一個範圍
   * **全部** — 顯示所有段落
   * **範圍**
      * 指定應顯示的段落範圍（以分號分隔）
      * 如果執行個體`1;3-5;7;9-*`包含第一段、第三段到第五段、第七段、第九段到最後一段
* **將標題處理為它們自己的段落**

## 編輯對話方塊 {#edit-dialog}

使用電子郵件內容片段元件設定內容片段後，當您在內容編輯器中選取元件時，會顯示&#x200B;**編輯**&#x200B;選項。

![電子郵件內容片段元件](/help/email/assets/email-content-fragment-edit-toolbar.png)的工具列

點選或按一下&#x200B;**編輯**&#x200B;按鈕會開啟內容片段編輯器。 內容片段編輯器已擴充為包含&#x200B;**選取Adobe Campaign變數**&#x200B;以將Adobe Campaign變數插入內容片段的按鈕。

電子郵件](/help/email/assets/email-content-fragment-editor.png)的![內容片段編輯器

如需有關編輯和編寫內容片段的詳細資訊，請參閱檔案[編寫片段內容。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html)

## 設計對話方塊 {#design-dialog}

當電子郵件內容片段元件設定有內容片段時，當您在內容編輯器中選取它時，工具列會顯示一個按鈕來開啟內容片段編輯器。


### 主要標籤 {#main-tab}

![電子郵件內容片段元件](/help/email/assets/email-content-fragment-design.png)的「設計」對話方塊

* **內部回應式格線**

   * 用於內部回應式格線的Sling資源型別

### 樣式索引標籤 {#styles-tab}

電子郵件體驗片段元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)
