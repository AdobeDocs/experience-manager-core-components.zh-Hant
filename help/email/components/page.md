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

「電子郵件頁面元件」是可擴充的頁面元件，專門用於 [範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 並可讓頁首/頁尾和結構元件與範本編輯器組合，並針對建立Adobe Campaign內容量身打造。

## 使用狀況 {#usage}

電子郵件頁面元件是使用電子郵件核心元件和可編輯範本設計的所有頁面的基礎。 使用「電子郵件頁面元件」時，頁首、頁尾和頁面結構可以定義為範本，使用其他「電子郵件核心元件」。

* 使用 [設計對話方塊，](#design-dialog) 可為頁面定義自訂用戶端程式庫。
* 其他元件有可直接從元件存取的編輯對話方塊，不同於此元件，因為「電子郵件頁面元件」是頁面本身，因此 [編輯對話框](#edit-dialog) 「電子郵件頁面元件」的「頁面屬性」視窗。

## 版本與相容性 {#version-and-compatibility}

電子郵件頁面元件的目前版本為v1，已於2022年10月隨電子郵件核心元件X版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

如需電子郵件核心元件版本和版本的詳細資訊，請參閱本檔案 [電子郵件核心元件版本](/help/email/versions.md)

### 技術詳細資訊 {#technical-details}

頁面元件的最新技術檔案 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_page_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 編輯對話方塊 {#edit-dialog}

由於元件代表整個頁面，因此通常會在編輯對話方塊中的設定，會顯示在 [頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) 窗口。

### Cloud Services標籤 {#cloud-services}

為了讓電子郵件核心元件能夠擷取促銷活動變數和資料，頁面必須連結至Adobe Campaign設定。

![電子郵件頁面屬性](/help/email/assets/email-page-properties.png)

在 **Cloud Service配置** 標題，在下拉式清單中選取 **新增設定**.

在 **Adobe Campaign** 標題，選取您與Adobe Campaign整合的設定。

請參閱檔案 [使用電子郵件核心元件](/help/email/using.md) 以取得設定電子郵件核心元件的詳細資訊。

### 電子郵件標籤 {#email-tab}

「電子郵件」索引標籤會根據本頁面的內容（例如電子郵件主旨和純文字內容），定義透過Adobe Campaign傳送的電子郵件屬性。

![電子郵件頁面屬性](/help/email/assets/email-page-properties-email.png)

* **主旨** -Adobe Campaign根據本頁面所傳送電子郵件的主旨
   * 按一下 **選取Adobe Campaign變數** 圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。
* **前置標題**
   * 按一下 **選取Adobe Campaign變數** 圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。
* **純文字**  — 由Adobe Campaign傳送之電子郵件的純文字版本
   * 按一下 **選取Adobe Campaign變數** 圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。
* **參考Url**

## 設計對話方塊 {#design-dialog}

由於元件代表整個頁面，因此可透過 **頁資訊 — >頁策略** 編輯頁面範本時。

![頁面原則](/help/assets/page-policy.png)

### 屬性標籤 {#properties-tab}

使用「頁面設計」窗口，您可以定義要載入的客戶端庫以及該頁的Web資源庫。

![電子郵件頁面元件設計對話方塊](/help/email/assets/email-page-design.png)

* **用戶端程式庫**  — 這會定義要載入的用戶端程式庫類別。 JavaScript會新增至內文結尾，而CSS會新增至頁面標題。
* **用戶端程式庫JavaScript頁面標題**  — 這會定義要在頁面標題中載入的JavaScript用戶端程式庫類別。
   * 此處定義的類別也存在於 **用戶端程式庫** 欄位會在頁面標題中載入JavaScript，而非在內文結尾。
   * 除非類別也存在於 **用戶端程式庫** 欄位。
* **非同步載入JavaScript程式庫**  — 如果已啟用，則自訂JavaScript程式庫將以非同步方式載入。
* **Web資源客戶端庫**  — 用於提供Web資源（如Favicon）的用戶端程式庫類別。
* **跳至主要內容元素選取器**  — 作為協助工具功能，可直接略過至頁面的主要內容

程式庫可針對 **用戶端程式庫** 和 **用戶端程式庫JavaScript頁面標題** 欄位如下：

* 若要新增欄位，請按一下或點選 **新增** 按鈕。
* 若要移除欄位，請按一下或點選要移除之欄位旁的垃圾桶圖示。
* 要重新排列載入順序，請按一下或點選並拖動要移動的欄位旁邊的手柄。

如需使用用戶端程式庫的詳細資訊，請參閱 [使用用戶端程式庫。](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)

### 樣式標籤 {#styles-tab}

頁面元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
