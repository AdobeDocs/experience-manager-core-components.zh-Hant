---
title: 電子郵件頁面元件
description: 「電子郵件頁」元件
role: Architect, Developer, Admin, User
exl-id: 17fd0f5e-2b85-41a1-abaf-8ad190a5341a
source-git-commit: c16dd8696e89f89c7b178ece11f57a565d73588b
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 1%

---


# 電子郵件頁面元件 {#email-page-component}

「電子郵件頁面」元件是可擴展的頁面元件，旨在與 [模板編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 並允許將頁眉/頁腳和結構元件與模板編輯器一起裝配，以便為建立Adobe Campaign內容而定制。

## 使用狀況 {#usage}

「電子郵件頁面元件」構成了使用「電子郵件核心元件」和可編輯模板設計的所有頁面的基礎。 通過使用電子郵件頁面元件，頁眉、頁腳和頁面結構可以使用其他電子郵件核心元件定義為模板。

* 使用 [設計對話框，](#design-dialog) 可以為頁面定義自定義客戶端庫。
* 與具有可直接從元件訪問的編輯對話框的其他元件不同，因為「電子郵件頁面元件」是頁面本身， [編輯對話框](#edit-dialog) 「電子郵件頁面元件」的頁面屬性窗口。

## 版本和相容性 {#version-and-compatibility}

電子郵件頁面元件的當前版本為v1，此版本於2022年10月隨電子郵件核心元件的X版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

有關電子郵件核心元件版本和版本的詳細資訊，請參閱文檔 [電子郵件核心元件版本](/help/email/versions.md)

### 技術詳細資訊 {#technical-details}

有關頁面元件的最新技術文檔 [中。](https://adobe.com/go/aem_cmp_tech_email_page_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

因為元件代表整個頁面，所以通常在編輯對話框中的設定在 [頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) 的子菜單。

### Cloud Services頁籤 {#cloud-services}

為了使電子郵件核心元件能夠檢索市場活動變數和資料，必須將頁面連結到Adobe Campaign配置。

![電子郵件頁面屬性](/help/email/assets/email-page-properties.png)

下 **Cloud Service配置** 標題，在下拉式選擇中 **添加配置**。

下 **Adobe Campaign** 標題中，選擇與Adobe Campaign整合的配置。

查看文檔 [使用電子郵件核心元件](/help/email/using.md) 的子菜單。

### 電子郵件頁籤 {#email-tab}

「電子郵件」頁籤根據此頁的內容（如電子郵件主題和純文字檔案內容）定義通過Adobe Campaign發送的電子郵件的屬性。

![電子郵件頁面屬性](/help/email/assets/email-page-properties-email.png)

* **主題** -Adobe Campaign根據本頁發送的電子郵件的主題
   * 按一下 **選擇Adobe Campaign變數** 表徵圖以開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。
* **預報頭**
   * 按一下 **選擇Adobe Campaign變數** 表徵圖以開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。
* **純文字檔案** -Adobe Campaign發送的電子郵件的純文字檔案版本
   * 按一下 **選擇Adobe Campaign變數** 表徵圖以開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。
* **引用URL**

## 設計對話框 {#design-dialog}

由於元件代表整個頁面，因此可通過 **頁面資訊 — >頁面策略** 編輯頁面模板時。

![頁面原則](/help/assets/page-policy.png)

### 屬性頁籤 {#properties-tab}

使用「頁面設計」窗口，可以定義要載入的客戶端庫以及頁面的Web資源庫。

![「電子郵件頁面元件設計」對話框](/help/email/assets/email-page-design.png)

* **客戶端庫**  — 這定義要載入的客戶端庫類別。 JavaScript將添加在正文端，CSS將添加到頁面頭。
* **客戶端庫JavaScript頁面頭**  — 這定義了要載入到頁頭中的JavaScript客戶端庫類別。
   * 此處定義的類別， **客戶端庫** 欄位將在頁面頭中載入JavaScript，而不是在body結尾。
   * 除非類別也位於 **客戶端庫** 的子菜單。
* **非同步載入JavaScript庫**  — 如果啟用，將非同步載入自定義JavaScript庫。
* **Web資源客戶端庫**  — 用於為Web資源（如favicon）提供服務的客戶端庫類別。
* **跳至主內容元素選擇器**  — 用作輔助功能，可直接跳至頁面的主要內容

可以為 **客戶端庫** 和 **客戶端庫JavaScript頁面頭** 欄位：

* 要添加新欄位，請按一下或點擊 **添加** 按鈕。
* 要刪除欄位，請按一下或點擊要刪除的欄位旁邊的垃圾桶表徵圖。
* 要重新排列載入順序，請按一下或點擊並拖動要移動的欄位旁邊的控制滑塊。

有關使用客戶端庫的詳細資訊，請參見 [使用客戶端庫。](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)

### 樣式頁籤 {#styles-tab}

頁面元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
