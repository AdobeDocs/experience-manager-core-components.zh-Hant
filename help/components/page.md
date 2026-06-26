---
title: 頁面元件
description: 頁面元件是可擴充的頁面元件，旨在與範本編輯器搭配使用，並允許使用範本編輯器來組合頁首/頁尾和結構元件。
role: Developer, Admin, User
exl-id: 2503e067-abed-427d-8a54-8b79e3451487
TQID: https://experienceleague.adobe.com/d70sxBsyVP2Qh-O3cOkZv6Wj-3ZiqpRYVnAYD6zNl3A
product_v2:
  - id: c45915cf-e157-4af7-a80d-97b905bcb3a5
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: e2c1b6d3-bb7e-4fe8-8c72-f7b403298e91
subfeature_v2:
  - id: f86a5563-8f73-4ec0-be7d-a1782604870a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
source-git-commit: 2a9a69dd7eeade8cdc2f681a354350c4370d5d1b
workflow-type: tm+mt
source-wordcount: 778
ht-degree: 90%

---

# 頁面元件{#page-component}

頁面元件是可擴充的頁面元件，旨在與[範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)搭配使用，並允許使用範本編輯器來組合頁首/頁尾和結構元件。

{{traditional-aem}}

## 用途 {#usage}

頁面元件構成了使用核心元件以及可編輯範本設計的所有頁面的基礎。 使用頁面元件時，可以使用其他核心元件將頁首、頁尾和頁面結構定義為範本。

使用[設計對話框](#design-dialog)，可以為頁面定義自訂用戶端程式庫。 不同於可從元件直接存取編輯對話框的其他元件，由於頁面元件是頁面本身，頁面元件的[編輯對話框](#edit-dialog)為頁面屬性視窗。

## 版本和相容性 {#version-and-compatibility}

頁面元件的目前版本為 v3，此版本於 2022 年 2 月隨著核心元件 2.18.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|---|
| v3 | - | 相容 | 相容 | 相容 |
| [v2](v2/page.md) | 相容 | 相容 | - | 相容 |
| [v1](v1/page-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_page_v3)有關頁面元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

由於元件代表整個頁面，通常在編輯對話框中的設定可在[頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)視窗中找到。

### 結構化資料支援 {#structured-data}

[核心元件2.31.0](/help/versions.md)版將[schema.org](https://schema.org)型別的頁面層級結構化資料(JSON-LD)支援引入所有版本的頁面元件。  AEM會在頁面標頭中轉譯這些區塊。

[AEM as a Cloud Service](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-release-information/aem-release-updates/update-releases-roadmap)的2026.6.0版新增了作者使用「頁面屬性」視窗將一或多個JSON-LD區塊新增到&#x200B;**進階**&#x200B;索引標籤的&#x200B;**SEO**&#x200B;區段中的頁面的功能。

## 設計對話框 {#design-dialog}

因為元件代表整個頁面，所以在編輯頁面範本時，設計對話框是透過&#x200B;**頁面資訊 -> 頁面原則**&#x200B;來存取。

![頁面原則](/help/assets/page-policy.png)

>[!NOTE]
>
>在舊版 AEM 中，**頁面原則**&#x200B;原稱為&#x200B;**頁面設計**。

### 屬性索引標籤 {#properties-tab}

使用「頁面設計」視窗，您可以定義要載入的用戶端程式庫，以及頁面的網頁資源資料庫。

* **用戶端程式庫** - 這會定義要載入的用戶端程式庫類別。 JavaScript 會新增至正文結尾，而 CSS 會新增至頁面標題。
* **用戶端程式庫 JavaScript 頁面標題** - 這會定義要在頁面標題中載入的 JavaScript 用戶端程式庫類別。
   * 在此處定義且出現在&#x200B;**用戶端程式庫**&#x200B;欄位中的類別，將在頁面標題而非正文結尾載入 JavaScript。
   * 除非類別也出現在&#x200B;**用戶端程式庫**&#x200B;欄位中，否則不會載入 CSS。

* **網頁資源用戶端程式庫** - 提供網站資源 (例如 Favicon) 的用戶端程式庫類別。

* **跳至主要內容元素選擇器** - 當作協助工具功能，可直接跳至頁面的主要內容

* **轉譯替代語言連結**&#x200B;如果啟用，便會將相同網站中頁面替代語言版本的連結新增至頁面的頁首。

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
