---
title: 頁面元件
description: 「頁面元件」是可擴充的頁面元件，專門用於與範本編輯器搭配使用，並可讓頁首/頁尾和結構元件與範本編輯器組合。
role: Architect, Developer, Admin, User
exl-id: 2503e067-abed-427d-8a54-8b79e3451487
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 3%

---

# 頁面元件{#page-component}

頁面元件是可擴充的頁面元件，設計用於與[範本編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)搭配使用，並可讓頁首/頁尾和結構元件與範本編輯器組裝。

## 使用狀況 {#usage}

頁面元件是所有以核心元件設計的頁面之基礎，也是可編輯的範本。 使用頁面元件、頁首、頁尾和頁面結構，即可使用其他核心元件定義為範本。

使用[設計對話方塊](#design-dialog)，可為頁面定義自訂用戶端程式庫。 與具有可直接從元件訪問的編輯對話框的其他元件不同，由於頁面元件是頁面本身，因此頁面元件的[edit dialog](#edit-dialog)是頁面屬性窗口。

## 漸進式網頁應用程式支援 {#pwa-support}

核心元件2.15.0版推出支援AEM as aCloud Service的內建[漸進式網頁應用程式(PWA)功能。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/enable-pwa.html) 只要在網站層級進行簡單的設定，就能將AEM體驗轉換為PWA!

## 版本與相容性 {#version-and-compatibility}

目前的頁面元件版本為v2，已於2018年1月隨核心元件2.0.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v2 | 相容 | 相容 | 相容 |
| [v1](v1/page-v1.md) | 相容 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

### 技術詳細資訊 {#technical-details}

如需頁面元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_page_v2)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話方塊 {#edit-dialog}

由於元件代表整個頁面，因此通常會在編輯對話方塊中的設定，會顯示在[頁面屬性](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)視窗中。

## 設計對話方塊 {#design-dialog}

由於元件代表整個頁面，因此在編輯頁面範本時，可透過&#x200B;**頁面資訊 — >頁面原則**&#x200B;存取設計對話方塊。

![頁面原則](/help/assets/page-policy.png)

>[!NOTE]
>
>在舊版AEM中，**頁面原則**&#x200B;稱為&#x200B;**頁面設計**。

### 屬性標籤 {#properties-tab}

使用「頁面設計」窗口，您可以定義要載入的客戶端庫以及該頁的Web資源庫。

* **用戶端程式庫**  — 這會定義要載入的用戶端程式庫類別。JavaScript會新增至內文結尾，而CSS會新增至頁面標題。
* **用戶端程式庫JavaScript頁面標題**  — 這會定義要在頁面標題中載入的JavaScript用戶端程式庫類別。
   * 此處定義且也存在於&#x200B;**用戶端程式庫**&#x200B;欄位中的類別，會在頁面標題中載入JavaScript，而非在內文結尾。
   * 除非類別也存在於&#x200B;**用戶端程式庫**&#x200B;欄位中，否則不會載入CSS。

* **Web資源客戶端庫**  — 用於提供Web資源（如Favicon）的客戶端庫類別。

* **略過至主要內容元素選取器**  — 作為協助工具功能，可直接略過至頁面的主要內容

![頁面元件設計對話方塊](/help/assets/page-design.png)

可以為&#x200B;**Client Libraries**&#x200B;和&#x200B;**Client Libraries JavaScript頁面標題**&#x200B;欄位配置庫，如下所示：

* 若要新增欄位，請按一下或點選欄位下方的&#x200B;**新增**&#x200B;按鈕。
* 若要移除欄位，請按一下或點選要移除之欄位旁的垃圾桶圖示。
* 要重新排列載入順序，請按一下或點選並拖動要移動的欄位旁邊的手柄。

如需使用用戶端程式庫的詳細資訊，請參閱[使用用戶端程式庫](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)。

>[!CAUTION]
>
>核心元件2.2.0版已導入為頁面標題分別定義用戶端程式庫的功能。

### 樣式標籤 {#styles-tab}

頁面元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層 {#data-layer}

頁面元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
