---
title: 頁面元件
description: 「頁面元件」是可延伸的頁面元件，設計用於範本編輯器，並允許使用範本編輯器來組裝頁首/頁尾和結構元件。
role: Architect, Developer, Admin, User
exl-id: 2503e067-abed-427d-8a54-8b79e3451487
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 1%

---

# 頁面元件{#page-component}

頁面元件是可擴充的頁面元件，設計用於 [範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 並允許使用範本編輯器來組裝頁首/頁尾和結構元件。

## 使用狀況 {#usage}

頁面元件構成了使用核心元件以及可編輯範本設計的所有頁面的基礎。 使用頁面元件時，可以使用其他核心元件將頁首、頁尾和頁面結構定義為範本。

使用 [設計對話方塊](#design-dialog)，您可以為頁面定義自訂使用者端程式庫。 有別於可從元件直接存取編輯對話方塊的其他元件，頁面元件是頁面本身， [編輯對話方塊](#edit-dialog) 頁面元件的「頁面屬性」視窗。

## 版本和相容性 {#version-and-compatibility}

頁面元件的目前版本是v3，此版本隨2022年2月的核心元件2.18.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v3 | - | 相容 | 相容 |
| [v2](v2/page.md) | 相容 | 相容 | 相容 |
| [v1](v1/page-v1.md) | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 漸進式網頁應用程式支援 {#pwa-support}

核心元件2.15.0版推出對AEMas a Cloud Service內建元件的支援 [漸進式網頁應用程式(PWA)功能。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/enable-pwa.html) 只要在網站層級進行簡單的設定，就能將您的AEM體驗轉換為PWA！

### 技術細節 {#technical-details}

有關頁面元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_page_v3).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 編輯對話方塊 {#edit-dialog}

由於元件呈現整個頁面，通常位於編輯對話方塊的設定可在 [頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) 視窗。

## 設計對話方塊 {#design-dialog}

由於元件呈現整個頁面，因此設計對話方塊可透過以下方式存取： **頁面資訊 — >頁面原則** 編輯頁面範本時。

![頁面原則](/help/assets/page-policy.png)

>[!NOTE]
>
>在舊版AEM中， **頁面原則** 已呼叫 **頁面設計**.

### 屬性標籤 {#properties-tab}

使用「頁面設計」視窗，您可以定義要載入的使用者端程式庫，以及頁面的網頁資源程式庫。

* **使用者端資料庫**  — 這會定義要載入的使用者端程式庫類別。 JavaScript會新增至內文結尾，而CSS會新增至頁首。
* **使用者端資料庫JavaScript頁首**  — 這會定義要在頁面標頭中載入的JavaScript使用者端程式庫類別。
   * 此處定義的類別，也存在於中 **使用者端資料庫** 欄位會將JavaScript載入頁面標頭中，而非本文結尾處。
   * 除非類別也出現在中，否則不會載入CSS **使用者端資料庫** 欄位。

* **Web資源使用者端資源庫**  — 用來提供Favicon等Web資源的使用者端資料庫類別。

* **跳至主要內容元素選擇器**  — 當作協助工具功能，可直接跳至頁面的主要內容

* **轉譯替代語言連結**  — 如果已啟用，在相同網站中頁面替代語言版本的連結將會新增到頁面的頁首。

![頁面元件設計對話方塊](/help/assets/page-design.png)

程式庫可同時針對以下兩項進行設定： **使用者端資料庫** 和 **使用者端資料庫JavaScript頁首** 欄位如下所示：

* 若要新增欄位，請按一下或點選 **新增** 按鈕來設定欄位。
* 若要移除欄位，請按一下或點選要移除欄位旁的垃圾桶圖示。
* 若要重新排列載入順序，請按一下或點選並拖曳要移動欄位旁的控制點。

如需有關使用使用者端資料庫的詳細資訊，請參閱 [使用使用者端資料庫](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html).

>[!CAUTION]
>
>核心元件2.2.0版匯入了個別定義頁面標題使用者端程式庫的功能。

### 樣式索引標籤 {#styles-tab}

頁面元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe使用者端資料層 {#data-layer}

頁面元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
