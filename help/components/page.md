---
title: 頁面元件
description: 「頁面元件」是可延伸的頁面元件，設計用於範本編輯器，允許使用範本編輯器來組裝頁首/頁尾和結構元件。
role: Architect, Developer, Admin, User
exl-id: 2503e067-abed-427d-8a54-8b79e3451487
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 2%

---


# 頁面元件{#page-component}

頁面元件是可擴充的頁面元件，設計用於[範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)，並允許使用範本編輯器來組裝頁首/頁尾和結構元件。

{{traditional-aem}}

## 使用情況 {#usage}

頁面元件構成了使用核心元件以及可編輯範本設計的所有頁面的基礎。 使用頁面元件時，可以使用其他核心元件將頁首、頁尾和頁面結構定義為範本。

使用[設計對話方塊](#design-dialog)，可以為頁面定義自訂使用者端資料庫。 不同於可從元件直接存取編輯對話方塊的其他元件，由於頁面元件是頁面本身，頁面元件的[編輯對話方塊](#edit-dialog)是頁面屬性視窗。

## 版本和相容性 {#version-and-compatibility}

頁面元件的目前版本是v3，此版本隨2022年2月的核心元件發行版本2.18.0的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|---|
| v3 | - | 相容 | 相容 | 相容 |
| [v2](v2/page.md) | 相容 | 相容 | - | 相容 |
| [v1](v1/page-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 漸進式網頁應用程式支援 {#pwa-support}

核心元件2.15.0版推出支援AEM as a Cloud Service的內建[漸進式網頁應用程式(PWA)功能。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/enable-pwa.html?lang=zh-Hant)透過網站層級的簡單設定，將您的AEM體驗轉換為PWA！

### 技術細節 {#technical-details}

在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_page_v3_tw)上可找到有關頁面元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 編輯對話方塊 {#edit-dialog}

由於元件代表整個頁面，通常在編輯對話方塊中的設定可在[頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=zh-Hant)視窗中找到。

## 設計對話方塊 {#design-dialog}

因為元件代表整個頁面，所以在編輯頁面範本時，設計對話方塊是透過&#x200B;**頁面資訊 — >頁面原則**&#x200B;來存取。

![頁面原則](/help/assets/page-policy.png)

>[!NOTE]
>
>在舊版AEM中，**頁面原則**&#x200B;已呼叫&#x200B;**頁面設計**。

### 屬性標籤 {#properties-tab}

使用「頁面設計」視窗，您可以定義要載入的使用者端程式庫，以及頁面的網頁資源程式庫。

* **使用者端資料庫** — 這會定義要載入的使用者端資料庫類別。 JavaScript會新增至內文結尾，而CSS會新增至頁面標題。
* **使用者端資料庫JavaScript頁面標題** — 這會定義要在頁面標題中載入的JavaScript使用者端資料庫類別。
   * 在此處定義且出現在&#x200B;**使用者端資料庫**&#x200B;欄位中的類別，將在頁面標題而非本文結尾載入JavaScript。
   * 除非類別也出現在&#x200B;**使用者端資料庫**&#x200B;欄位中，否則不會載入CSS。

* **Web資源使用者端資源庫** — 用於提供favicon等網站資源的使用者端資源庫類別。

* **跳至主要內容元素選擇器** — 當作協助工具功能，可直接跳至頁面的主要內容

* **轉譯替代語言連結** — 如果啟用，相同網站中頁面替代語言版本的連結將會新增到頁面的頁首。

![頁面元件設計對話方塊](/help/assets/page-design.png)

可以為&#x200B;**使用者端資料庫**&#x200B;和&#x200B;**使用者端資料庫JavaScript頁面標題**&#x200B;欄位設定資料庫，如下所示：

* 若要新增欄位，請按一下或點選欄位下方的&#x200B;**新增**&#x200B;按鈕。
* 若要移除欄位，請按一下或點選要移除欄位旁的垃圾桶圖示。
* 若要重新排列載入順序，請按一下或點選並拖曳要移動欄位旁的控點。

如需有關使用使用者端資料庫的詳細資訊，請參閱[使用使用者端資料庫](https://helpx.adobe.com/tw/experience-manager/6-5/sites/developing/using/clientlibs.html)。

>[!CAUTION]
>
>為頁面標頭個別定義使用者端程式庫的功能已在核心元件發行版本2.2.0中引入。

### 樣式索引標籤 {#styles-tab}

頁面元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

頁面元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
