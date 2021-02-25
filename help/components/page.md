---
title: 頁面元件
description: 「頁面元件」是可擴充的頁面元件，可與範本編輯器搭配使用，並允許與範本編輯器組合頁首／頁尾和結構元件。
translation-type: tm+mt
source-git-commit: f4a45b2af87e5a5f0396b335c65856ce821455c9
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 3%

---


# 頁面元件{#page-component}

頁面元件是可擴充的頁面元件，其設計可與[範本編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)搭配使用，並可讓頁首／頁尾和結構元件與範本編輯器組合。

## 使用狀況 {#usage}

頁面元件是使用核心元件設計的所有頁面以及可編輯範本的基礎。 使用頁面元件，頁首、頁尾和頁面結構就可使用其他核心元件定義為範本。

使用[設計對話方塊](#design-dialog)，可為頁面定義自訂用戶端程式庫。 與具有可直接從元件訪問的編輯對話框的其他元件不同，因為頁面元件是頁面本身，所以頁面元件的[edit對話框](#edit-dialog)是頁面屬性窗口。

## 漸進式網頁應用程式支援{#pwa-support}

核心元件2.15.0版推出支援AEM做為雲端服務的內建漸進式網頁應用程式(PWA)功能。 透過網站層級的簡單設定，將您的AEM體驗轉變為PWA!

## 版本和相容性{#version-and-compatibility}

目前的頁面元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v2 | 相容 | 相容 | 相容 |
| [v1](v1/page-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

### 技術詳細資訊{#technical-details}

有關頁面元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_page_v2)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話框{#edit-dialog}

由於元件代表整個頁面，因此通常在編輯對話框中的設定會出現在[頁面屬性](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)窗口中。

## 設計對話框{#design-dialog}

由於元件代表整個頁面，因此在編輯頁面模板時可通過&#x200B;**頁面資訊->頁面策略**&#x200B;訪問設計對話框。

![頁面原則](/help/assets/page-policy.png)

>[!NOTE]
>
>在舊版AEM中，**Page Policy**&#x200B;稱為&#x200B;**Page Design**。

### 屬性頁籤{#properties-tab}

使用「頁面設計」視窗，您可以定義要載入的用戶端程式庫以及頁面的網頁資源程式庫。

* **Client Libraries**  —— 這定義要載入的用戶端程式庫類別。JavaScript會新增至內文結尾，而CSS則會新增至頁面標題。
* **用戶端程式庫JavaScript頁面標題** -這會定義要載入頁面標題中的JavaScript用戶端程式庫類別。
   * 此處定義的類別也會出現在&#x200B;**用戶端程式庫**&#x200B;欄位中，其JavaScript將載入頁面標題中，而非載入內文結尾。
   * 除非&#x200B;**用戶端程式庫**&#x200B;欄位中也包含類別，否則不會載入CSS。

* **Web資源客戶端庫** -用於提供Web資源（如Favicon）的客戶端庫類別。

* **跳至主要內容元素選擇器** -用作協助工具功能，可直接跳至頁面的主要內容

![頁面元件設計對話方塊](/help/assets/page-design.png)

可以為&#x200B;**客戶端庫**&#x200B;和&#x200B;**客戶端庫JavaScript頁面標題**&#x200B;欄位配置庫，如下所示：

* 若要新增欄位，請按一下或點選欄位下方的&#x200B;**新增**&#x200B;按鈕。
* 若要移除欄位點按或點選要移除欄位旁的垃圾桶圖示。
* 若要重新排列載入順序，請按一下或點選並拖曳要移動之欄位旁的控點。

有關使用客戶端庫的詳細資訊，請參閱[使用客戶端庫](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)。

>[!CAUTION]
>
>核心元件版本2.2.0中，已引入為頁首個別定義用戶端程式庫的功能。

### 樣式標籤{#styles-tab}

頁面元件支援AEM [Style System](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層{#data-layer}

頁面元件支援[Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
