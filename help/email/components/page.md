---
title: 電子郵件頁面元件
description: 電子郵件頁面元件
role: Architect, Developer, Admin, User
exl-id: 17fd0f5e-2b85-41a1-abaf-8ad190a5341a
source-git-commit: c16dd8696e89f89c7b178ece11f57a565d73588b
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 1%

---


# 電子郵件頁面元件 {#email-page-component}

電子郵件頁面元件是可擴充的頁面元件，設計用於 [範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 並允許使用範本編輯器來組裝頁首/頁尾和結構元件，為建立Adobe Campaign內容量身打造。

## 使用狀況 {#usage}

電子郵件頁面元件構成了使用電子郵件核心元件和可編輯範本設計的所有頁面的基礎。 透過使用電子郵件頁面元件，可以使用其他電子郵件核心元件將頁首、頁尾和頁面結構定義為範本。

* 使用 [設計對話方塊，](#design-dialog) 可以為頁面定義自訂使用者端程式庫。
* 有別於可從元件直接存取編輯對話方塊的其他元件，由於電子郵件頁面元件是頁面本身， [編輯對話方塊](#edit-dialog) 「電子郵件頁面元件」的「頁面屬性」視窗。

## 版本和相容性 {#version-and-compatibility}

電子郵件頁面元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

如需電子郵件核心元件版本的詳細資訊，請參閱本檔案 [電子郵件核心元件版本](/help/email/versions.md)

### 技術細節 {#technical-details}

有關頁面元件的最新技術檔案 [在GitHub上可找到。](https://adobe.com/go/aem_cmp_tech_email_page_v1)

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 編輯對話方塊 {#edit-dialog}

由於元件呈現整個頁面，通常位於編輯對話方塊的設定可在 [頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) 視窗。

### Cloud Services標籤 {#cloud-services}

為了讓電子郵件核心元件能夠擷取促銷活動變數和資料，頁面必須連結至Adobe Campaign設定。

![電子郵件頁面屬性](/help/email/assets/email-page-properties.png)

下 **Cloud Service設定** 標題，在下拉式清單中選取 **新增設定**.

下 **Adobe Campaign** 標題中，選取與Adobe Campaign整合的設定。

檢視檔案 [使用電子郵件核心元件](/help/email/using.md) 以取得關於設定電子郵件核心元件的詳細資訊。

### 電子郵件標籤 {#email-tab}

電子郵件索引標籤會根據此頁面的內容（例如電子郵件主旨和純文字內容），定義透過Adobe Campaign傳送的電子郵件屬性。

![電子郵件頁面屬性](/help/email/assets/email-page-properties-email.png)

* **主旨** - Adobe Campaign根據此頁面傳送的電子郵件主題
   * 按一下 **選取Adobe Campaign變數** 圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，插入來自Adobe Campaign的動態內容。
* **前置標題**
   * 按一下 **選取Adobe Campaign變數** 圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，插入來自Adobe Campaign的動態內容。
* **純文字** - Adobe Campaign所傳送電子郵件的純文字版本
   * 按一下 **選取Adobe Campaign變數** 圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，插入來自Adobe Campaign的動態內容。
* **參考Url**

## 設計對話方塊 {#design-dialog}

由於元件呈現整個頁面，因此設計對話方塊可透過以下方式存取： **頁面資訊 — >頁面原則** 編輯頁面範本時。

![頁面原則](/help/assets/page-policy.png)

### 屬性標籤 {#properties-tab}

使用「頁面設計」視窗，您可以定義要載入的使用者端程式庫，以及頁面的網頁資源程式庫。

![電子郵件頁面元件設計對話方塊](/help/email/assets/email-page-design.png)

* **使用者端資料庫**  — 這會定義要載入的使用者端程式庫類別。 JavaScript會新增至內文結尾，而CSS會新增至頁首。
* **使用者端資料庫JavaScript頁首**  — 這會定義要在頁面標頭中載入的JavaScript使用者端程式庫類別。
   * 此處定義的類別，也存在於中 **使用者端資料庫** 欄位會將JavaScript載入頁面標頭中，而非本文結尾處。
   * 除非類別也出現在中，否則不會載入CSS **使用者端資料庫** 欄位。
* **非同步載入JavaScript程式庫**  — 如果啟用，將會非同步載入自訂JavaScript程式庫。
* **Web資源使用者端資源庫**  — 用來提供Favicon等Web資源的使用者端資料庫類別。
* **跳至主要內容元素選擇器**  — 當作協助工具功能，可直接跳至頁面的主要內容

程式庫可同時針對以下兩項進行設定： **使用者端資料庫** 和 **使用者端資料庫JavaScript頁首** 欄位如下所示：

* 若要新增欄位，請按一下或點選 **新增** 按鈕來設定欄位。
* 若要移除欄位，請按一下或點選要移除欄位旁的垃圾桶圖示。
* 若要重新排列載入順序，請按一下或點選並拖曳要移動欄位旁的控制點。

如需有關使用使用者端資料庫的詳細資訊，請參閱 [使用使用者端資料庫。](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)

### 樣式索引標籤 {#styles-tab}

頁面元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
