---
title: 頁面元件 (v2)
description: 頁面元件是可擴充的頁面元件，旨在與範本編輯器搭配使用，並允許使用範本編輯器來組合頁首/頁尾和結構元件。
role: Architect, Developer, Admin, User
exl-id: e85fe4db-6de4-4a84-a54c-bd07a67efed3
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '618'
ht-degree: 100%

---


# 頁面元件 (v2) {#page-component}

頁面元件是可擴充的頁面元件，旨在與[範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)搭配使用，並允許使用範本編輯器來組合頁首/頁尾和結構元件。

## 用途 {#usage}

頁面元件構成了使用核心元件以及可編輯範本設計的所有頁面的基礎。使用頁面元件時，可以使用其他核心元件將頁首、頁尾和頁面結構定義為範本。

使用[設計對話框](#design-dialog)，可以為頁面定義自訂用戶端程式庫。不同於可從元件直接存取編輯對話框的其他元件，由於頁面元件是頁面本身，頁面元件的[編輯對話框](#edit-dialog)為頁面屬性視窗。

## 版本和相容性 {#version-and-compatibility}

本文件說明頁面元件 v2，最初於 2018 年 1 月隨著核心元件 2.0.0 版發行導入。

>[!CAUTION]
>
>本文件說明頁面元件 v2。
>
>如需頁面元件目前版本的詳細資訊，請參閱[頁面元件](/help/components/page.md)文件。

## 漸進式網頁應用程式支援 {#pwa-support}

核心元件 2.15.0 版導入支援 AEM as a Cloud Service 的內建[漸進式網頁應用程式 (PWA) 功能。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/enable-pwa.html?lang=zh-Hant)透過網站層級的簡單設定，將您的 AEM 體驗轉換為 PWA！

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_page_v2_tw)有關頁面元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

由於元件代表整個頁面，通常在編輯對話框中的設定可在[頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=zh-Hant)視窗中找到。

## 設計對話框 {#design-dialog}

因為元件代表整個頁面，所以在編輯頁面範本時，設計對話框是透過&#x200B;**頁面資訊 -> 頁面原則**&#x200B;來存取。

![頁面原則](/help/assets/page-policy.png)

>[!NOTE]
>
>在舊版 AEM 中，**頁面原則**&#x200B;原稱為&#x200B;**頁面設計**。

### 屬性索引標籤 {#properties-tab}

使用「頁面設計」視窗，您可以定義要載入的用戶端程式庫，以及頁面的網頁資源資料庫。

* **用戶端程式庫** - 這會定義要載入的用戶端程式庫類別。JavaScript 會新增至正文結尾，而 CSS 會新增至頁面標題。
* **用戶端程式庫 JavaScript 頁面標題** - 這會定義要在頁面標題中載入的 JavaScript 用戶端程式庫類別。
   * 在此處定義且出現在&#x200B;**用戶端程式庫**&#x200B;欄位中的類別，將在頁面標題而非正文結尾載入 JavaScript。
   * 除非類別也出現在&#x200B;**用戶端程式庫**&#x200B;欄位中，否則不會載入 CSS。

* **網頁資源用戶端程式庫** - 提供網站資源 (例如 Favicon) 的用戶端程式庫類別。

* **跳至主要內容元素選擇器** - 當作協助工具功能，可直接跳至頁面的主要內容

![頁面元件設計對話框](/help/assets/page-design.png)

可以為&#x200B;**用戶端程式庫**&#x200B;和&#x200B;**用戶端程式庫 JavaScript 頁面標題**&#x200B;欄位設定資料庫，如下所示：

* 若要新增欄位，請按一下或點選欄位下方的&#x200B;**新增**&#x200B;按鈕。
* 若要移除欄位，請按一下或點選要移除欄位旁的垃圾桶圖示。
* 若要重新排列載入順序，請按一下或點選並拖曳要移動欄位旁的控點。

如需有關使用用戶端程式庫的進一步詳細資訊，請參閱[使用用戶端程式庫](https://helpx.adobe.com/tw/experience-manager/6-5/sites/developing/using/clientlibs.html)。

>[!CAUTION]
>
>為頁面標題個別定義用戶端程式庫的功能已在核心元件發行版本 2.2.0 中導入。

### 樣式索引標籤 {#styles-tab}

頁面元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「頁面元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
