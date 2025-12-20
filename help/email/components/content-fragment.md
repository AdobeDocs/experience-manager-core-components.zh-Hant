---
title: 電子郵件內容片段元件
description: 透過「電子郵件內容片段」元件，您可在內容中顯示內容片段。
role: Architect, Developer, Admin, User
exl-id: 9bc6b730-0d2a-4e5b-891c-d2f67f600bcc
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '607'
ht-degree: 100%

---


# 電子郵件內容片段元件 {#email-content-fragment-component}

「電子郵件內容片段」元件允許在您的內容中顯示[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=zh-Hant)。

## 用途 {#usage}

「電子郵件內容片段元件」允許在您的電子郵件內容中包含[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=zh-Hant)。內容片段為多管道結構化內容，可以集中編寫並輕鬆重複使用。

* 可在[設定對話框](#configure-dialog)中選取片段及其屬性。
* 可在[設計對話框](#design-dialog)中定義處理特定影像和格線的資源類型。
* 編輯選項會在自訂用於搭配「電子郵件核心元件」使用的[內容片段編輯器](#edit-dialog)中開啟已選取的片段。

## 版本和相容性 {#version-and-compatibility}

「電子郵件內容片段元件」的目前版本為 v1，此版本於 2022 年 10 月隨著「電子郵件核心元件」X 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

如需「電子郵件核心元件」版本和發行版本的進一步詳細資訊，請參閱[電子郵件核心元件版本](/help/email/versions.md)文件。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_cf_v1_tw)有關「電子郵件內容片段元件」的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件。](/help/developing/overview.md)

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義要包含的內容片段和片段元素。

### 屬性索引標籤 {#properties-tab}

![電子郵件內容片段元件](/help/email/assets/email-content-fragment-edit-properties.png)

* **內容片段**

   * 所需內容片段的路徑
   * **選取對話框**&#x200B;可用來尋找片段

* **顯示模式**
   * **單一文字元素** - 啟用選取一個多行文字元素，並啟用段落控制選項
* **變化版本** - 要使用的內容片段變化版本 (預設為&#x200B;**主版**)

* **ID** - 此選項允許控制 HTML 中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的內容找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS 產生影響。

### 段落控制索引標籤 {#paragraph-control-tab}

![電子郵件內容片段元件](/help/assets/content-fragment-edit-paragraph.png)

* **段落** - 允許選取所有段落或一個範圍
   * **全部** - 顯示所有段落
   * **範圍**
      * 指定應顯示的段落範圍，並以分號分隔
      * 例如 `1;3-5;7;9-*`，以包含第一段、第三至第五段、第七段，以及第九至最後一段
* **將標題視為單獨段落處理**

## 編輯對話框 {#edit-dialog}

使用「電子郵件內容片段元件」設定內容片段後，當您在內容編輯器中選取該元件時，會顯示&#x200B;**編輯**&#x200B;選項。

![電子郵件內容片段元件的工具列](/help/email/assets/email-content-fragment-edit-toolbar.png)

點選或按一下&#x200B;**編輯**&#x200B;按鈕，會開啟內容片段編輯器。內容片段編輯器已擴充為包含&#x200B;**選取 Adobe Campaign 變數**&#x200B;的按鈕，用於將 Adobe Campaign 變數插入至內容片段。

![電子郵件的內容片段編輯器](/help/email/assets/email-content-fragment-editor.png)

如需編輯和製作內容片段的進一步詳細資訊，請參閱[製作片段內容](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html?lang=zh-Hant)文件。

## 設計對話框 {#design-dialog}

當「電子郵件內容片段元件」設定具備內容片段後，在內容編輯器中選取該元件時，工具列會顯示用於開啟內容片段編輯器的按鈕。


### 主要索引標籤 {#main-tab}

![電子郵件內容片段元件的設計對話框](/help/email/assets/email-content-fragment-design.png)

* **內部回應式格線**

   * 用於內部回應式格線的 Sling 資源類型

### 樣式索引標籤 {#styles-tab}

「電子郵件體驗片段元件」支援 AEM [樣式系統。](/help/get-started/authoring.md#component-styling)
