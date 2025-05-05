---
title: 電子郵件頁面元件
description: 電子郵件頁面元件
role: Architect, Developer, Admin, User
exl-id: 17fd0f5e-2b85-41a1-abaf-8ad190a5341a
source-git-commit: 91969e4956bef1a511b8d588d5290a7999bf86ec
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 1%

---


# 電子郵件頁面元件 {#email-page-component}

電子郵件頁面元件是可擴充的頁面元件，設計用於[範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)，並允許使用範本編輯器來組裝頁首/頁尾和結構元件，為建立Adobe Campaign內容量身打造。

## 使用情況 {#usage}

電子郵件頁面元件構成了使用電子郵件核心元件及可編輯範本設計的所有頁面的基礎。 使用電子郵件頁面元件時，可以使用其他電子郵件核心元件將頁首、頁尾和頁面結構定義為範本。

* 使用[設計對話方塊，可以為頁面定義](#design-dialog)自訂使用者端資料庫。
* 與可從元件直接存取編輯對話方塊的其他元件不同，由於電子郵件頁面元件是頁面本身，電子郵件頁面元件的[編輯對話方塊](#edit-dialog)是頁面屬性視窗。

## 版本和相容性 {#version-and-compatibility}

電子郵件頁面元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容 | - | - |

如需電子郵件核心元件版本的詳細資訊，請參閱檔案[電子郵件核心元件版本](/help/email/versions.md)

### 技術細節 {#technical-details}

在GitHub上可找到有關頁面元件[的最新技術檔案。](https://adobe.com/go/aem_cmp_tech_email_page_v1)

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 編輯對話方塊 {#edit-dialog}

由於元件代表整個頁面，通常在編輯對話方塊中的設定可在[頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=zh-Hant)視窗中找到。

### 雲端服務標籤 {#cloud-services}

為了讓電子郵件核心元件能夠擷取促銷活動變數和資料，頁面必須連結至Adobe Campaign設定。

![電子郵件頁面屬性](/help/email/assets/email-page-properties.png)

在「**Cloud Service設定**」標題下，在下拉式清單中選取「**新增設定**」。

在&#x200B;**Adobe Campaign**&#x200B;標題下，選取您與Adobe Campaign整合的設定。

如需設定電子郵件核心元件的詳細資訊，請參閱檔案[使用電子郵件核心元件](/help/email/using.md)。

### 電子郵件索引標籤 {#email-tab}

電子郵件索引標籤會根據此頁面的內容（例如電子郵件主旨和純文字內容），定義透過Adobe Campaign傳送的電子郵件屬性。

![電子郵件頁面屬性](/help/email/assets/email-page-properties-email.png)

* **主旨** - Adobe Campaign根據此頁面所傳送之電子郵件的主旨
   * 按一下&#x200B;**選取Adobe Campaign變數**&#x200B;圖示以開啟[選取Adobe Campaign變數](/help/email/campaign-variables.md)對話方塊，插入來自Adobe Campaign的動態內容。
* **前置標題**
   * 按一下&#x200B;**選取Adobe Campaign變數**&#x200B;圖示以開啟[選取Adobe Campaign變數](/help/email/campaign-variables.md)對話方塊，插入來自Adobe Campaign的動態內容。
* **純文字** - Adobe Campaign所傳送之電子郵件的純文字版本
   * 按一下&#x200B;**選取Adobe Campaign變數**&#x200B;圖示以開啟[選取Adobe Campaign變數](/help/email/campaign-variables.md)對話方塊，插入來自Adobe Campaign的動態內容。
* **參考Url**

## 設計對話方塊 {#design-dialog}

因為元件代表整個頁面，所以在編輯頁面範本時，設計對話方塊是透過&#x200B;**頁面資訊 — >頁面原則**&#x200B;來存取。

![頁面原則](/help/assets/page-policy.png)

### 屬性標籤 {#properties-tab}

使用「頁面設計」視窗，您可以定義要載入的使用者端程式庫，以及頁面的網頁資源程式庫。

![電子郵件頁面元件設計對話方塊](/help/email/assets/email-page-design.png)

* **使用者端資料庫** — 這會定義要載入的使用者端資料庫類別。 JavaScript會新增至內文結尾，而CSS會新增至頁面標題。
* **使用者端資料庫JavaScript頁面標題** — 這會定義要在頁面標題中載入的JavaScript使用者端資料庫類別。
   * 在此處定義且出現在&#x200B;**使用者端資料庫**&#x200B;欄位中的類別，將在頁面標題而非本文結尾載入JavaScript。
   * 除非類別也出現在&#x200B;**使用者端資料庫**&#x200B;欄位中，否則不會載入CSS。
* **非同步載入JavaScript資料庫** — 如果啟用，將會非同步載入自訂JavaScript資料庫。
* **Web資源使用者端資源庫** — 用於提供favicon等網站資源的使用者端資源庫類別。
* **跳至主要內容元素選擇器** — 當作協助工具功能，可直接跳至頁面的主要內容

可以為&#x200B;**使用者端資料庫**&#x200B;和&#x200B;**使用者端資料庫JavaScript頁面標題**&#x200B;欄位設定資料庫，如下所示：

* 若要新增欄位，請按一下或點選欄位下方的&#x200B;**新增**&#x200B;按鈕。
* 若要移除欄位，請按一下或點選要移除欄位旁的垃圾桶圖示。
* 若要重新排列載入順序，請按一下或點選並拖曳要移動欄位旁的控點。

如需有關使用使用者端資料庫的詳細資訊，請參閱[使用使用者端資料庫。](https://helpx.adobe.com/tw/experience-manager/6-5/sites/developing/using/clientlibs.html)

### 樣式索引標籤 {#styles-tab}

頁面元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
