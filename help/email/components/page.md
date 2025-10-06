---
title: 電子郵件頁面元件
description: 電子郵件頁面元件
role: Architect, Developer, Admin, User
exl-id: 17fd0f5e-2b85-41a1-abaf-8ad190a5341a
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '780'
ht-degree: 100%

---


# 電子郵件頁面元件 {#email-page-component}

電子郵件頁面元件是可擴充的頁面元件，旨在與[範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)搭配使用，並允許使用範本編輯器來組合頁首/頁尾和結構元件，專為建立 Adobe Campaign 內容打造。

## 用途 {#usage}

電子郵件頁面元件構成了使用電子郵件核心元件以及可編輯範本設計的所有頁面的基礎。運用電子郵件頁面元件時，可以使用其他電子郵件核心元件將頁首、頁尾和頁面結構定義為範本。

* 使用[設計對話框，](#design-dialog)可以為頁面定義自訂用戶端程式庫。
* 不同於可從元件直接存取編輯對話框的其他元件，由於電子郵件頁面元件是頁面本身，電子郵件頁面元件的[編輯對話框](#edit-dialog)為頁面屬性視窗。

## 版本和相容性 {#version-and-compatibility}

電子郵件頁面元件的目前版本為 v1，此版本於 2022 年 10 月隨著電子郵件核心元件 X 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

如需「電子郵件核心元件」版本和發行的進一步詳細資訊，請參閱[電子郵件核心元件版本](/help/email/versions.md)文件

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_page_v1)有關頁面元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

由於元件代表整個頁面，通常在編輯對話框中的設定可在[頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=zh-Hant)視窗中找到。

### Cloud Services 索引標籤 {#cloud-services}

為了讓電子郵件核心元件能夠擷取行銷活動變數和資料，該頁面必須連結至 Adobe Campaign 設定。

![電子郵件頁面屬性](/help/email/assets/email-page-properties.png)

在 **Cloud Service 設定**&#x200B;標題下，於下拉式清單中選取&#x200B;**新增設定**。

在 **Adobe Campaign** 標題下，選取與 Adobe Campaign 整合的設定。

如需設定電子郵件核心元件的進一步詳細資訊，請參閱[使用電子郵件核心元件](/help/email/using.md)文件。

### 電子郵件索引標籤 {#email-tab}

電子郵件索引標籤會根據此頁面的內容 (例如電子郵件主旨和純文字內容) 定義透過 Adobe Campaign 傳送的電子郵件屬性。

![電子郵件頁面屬性](/help/email/assets/email-page-properties-email.png)

* **主旨** - Adobe Campaign 根據此頁面傳送的電子郵件主旨
   * 按一下&#x200B;**選取 Adobe Campaign 變數**&#x200B;圖示，開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入 Adobe Campaign 的動態內容。
* **預覽文字**
   * 按一下&#x200B;**選取 Adobe Campaign 變數**&#x200B;圖示，開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入 Adobe Campaign 的動態內容。
* **純文字** - Adobe Campaign 傳送的電子郵件純文字版本
   * 按一下&#x200B;**選取 Adobe Campaign 變數**&#x200B;圖示，開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入 Adobe Campaign 的動態內容。
* **參照 URL**

## 設計對話框 {#design-dialog}

因為元件代表整個頁面，所以在編輯頁面範本時，設計對話框是透過&#x200B;**頁面資訊 -> 頁面原則** 來存取。

![頁面原則](/help/assets/page-policy.png)

### 屬性索引標籤 {#properties-tab}

使用「頁面設計」視窗，您可以定義要載入的用戶端程式庫，以及頁面的網頁資源資料庫。

![電子郵件頁面元件設計對話框](/help/email/assets/email-page-design.png)

* **用戶端程式庫** - 這會定義要載入的用戶端程式庫類別。JavaScript 會新增至正文結尾，而 CSS 會新增至頁面標題。
* **用戶端程式庫 JavaScript 頁面標題** - 這會定義要在頁面標題中載入的 JavaScript 用戶端程式庫類別。
   * 在此處定義且出現在&#x200B;**用戶端程式庫**&#x200B;欄位中的類別，將在頁面標題而非正文結尾載入 JavaScript。
   * 除非類別也出現在&#x200B;**用戶端程式庫**&#x200B;欄位中，否則不會載入 CSS。
* **以非同步方式載入 JavaScript 程式庫** - 若啟用，將會以非同步方式載入自訂 JavaScript 程式庫。
* **網頁資源用戶端程式庫** - 提供網站資源 (例如 Favicon) 的用戶端程式庫類別。
* **跳至主要內容元素選擇器** - 當作協助工具功能，可直接跳至頁面的主要內容

可以為&#x200B;**用戶端程式庫**&#x200B;和&#x200B;**用戶端程式庫 JavaScript 頁面標題**&#x200B;欄位設定程式庫，如下所示：

* 若要新增欄位，請按一下或點選欄位下方的&#x200B;**新增**&#x200B;按鈕。
* 若要移除欄位，請按一下或點選要移除欄位旁的垃圾桶圖示。
* 若要重新排列載入順序，請按一下或點選並拖曳要移動欄位旁的控點。

如需有關使用用戶端程式庫的詳細資訊，請參閱[使用用戶端程式庫](https://helpx.adobe.com/tw/experience-manager/6-5/sites/developing/using/clientlibs.html)。

### 樣式索引標籤 {#styles-tab}

頁面元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
