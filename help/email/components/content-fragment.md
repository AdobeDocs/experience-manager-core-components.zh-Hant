---
title: 電子郵件內容片段元件
description: 電子郵件內容片段元件可讓您在內容中顯示內容片段。
role: Architect, Developer, Admin, User
exl-id: 9bc6b730-0d2a-4e5b-891c-d2f67f600bcc
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---


# 電子郵件內容片段元件 {#email-content-fragment-component}

電子郵件內容片段元件可顯示 [內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 在內容中。

## 使用狀況 {#usage}

電子郵件內容片段元件可包含 [內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 在您的電子郵件內容中。 內容片段是多頻道結構化內容，可集中製作並輕鬆重複使用。

* 片段及其屬性可在 [配置對話框。](#configure-dialog)
* 可在 [設計對話方塊。](#design-dialog)
* 編輯選項會在 [內容片段編輯器，](#edit-dialog) 已自訂，以搭配電子郵件核心元件使用。

## 版本與相容性 {#version-and-compatibility}

電子郵件內容片段元件的目前版本為v1，已於2022年10月隨電子郵件核心元件X版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

如需電子郵件核心元件版本和版本的詳細資訊，請參閱本檔案 [電子郵件核心元件版本。](/help/email/versions.md)

## 技術詳細資訊 {#technical-details}

有關電子郵件內容片段元件的最新技術檔案 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_cf_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

設定對話方塊可讓內容作者定義要包含的內容片段及該片段的元素。

### 屬性標籤 {#properties-tab}

![電子郵件內容片段元件](/help/email/assets/email-content-fragment-edit-properties.png)

* **內容片段**

   * 所需內容片段的路徑
   * 此 **選擇對話框** 可用來尋找片段

* **顯示模式**
   * **單一文字元素**  — 啟用選擇一個多行文本元素並啟用段落控制選項
* **變異**  — 要使用的內容片段變化(預設為 **主版**)

* **ID**  — 此選項可控制HTML中元件的唯一標識符。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查產生的內容來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會對CSS造成影響。

### 段落控制標籤 {#paragraph-control-tab}

![電子郵件內容片段元件](/help/assets/content-fragment-edit-paragraph.png)

* **段落**  — 允許選擇所有段落或範圍
   * **全部**  — 顯示所有段落
   * **範圍**
      * 指定應顯示的段落範圍，以分號分隔
      * 例如 `1;3-5;7;9-*` 包括第一、第三至第五、第七和第九至最後各段
* **將標題當作自己的段落處理**

## 編輯對話方塊 {#edit-dialog}

使用電子郵件內容片段元件來設定內容片段後，在內容編輯器中選取元件時，此元件會顯示 **編輯** 選項。

![電子郵件內容片段元件工具列](/help/email/assets/email-content-fragment-edit-toolbar.png)

點選或按一下 **編輯** 按鈕會開啟內容片段編輯器。 內容片段編輯器已擴充為包含 **選取Adobe Campaign變數** 將Adobe Campaign變數插入內容片段中。

![電子郵件的內容片段編輯器](/help/email/assets/email-content-fragment-editor.png)

如需編輯和編寫內容片段的詳細資訊，請參閱本檔案 [製作片段內容。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html)

## 設計對話方塊 {#design-dialog}

使用內容片段設定電子郵件內容片段元件時，當您在內容編輯器中選取該元件時，工具列會顯示一個按鈕以開啟內容片段編輯器。


### 主要標籤 {#main-tab}

![電子郵件內容片段元件的設計對話方塊](/help/email/assets/email-content-fragment-design.png)

* **內部回應式格線**

   * 用於內部回應式格線的Sling資源類型

### 樣式標籤 {#styles-tab}

電子郵件體驗片段元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)
