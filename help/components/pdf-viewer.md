---
title: PDF檢視器元件
description: PDF檢視器元件可讓您顯示PDF檔案。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 3%

---


# PDF檢視器元件{#pdf-viewer-component}

核心元件PDF檢視器元件可讓PDF檔案包含在頁面上。

## 使用狀況 {#usage}

核心元件PDF檢視器元件內嵌檢視器，以顯示儲存為頁面上資產的PDF檔案。

## 版本和相容性{#version-and-compatibility}

目前的PDF檢視器元件版本為v1，此版本於2020年6月隨核心元件2.10.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗PDF檢視器元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_pdfviewer)。

## 技術詳細資訊{#technical-details}

有關PDF檢視器元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

>[!NOTE]
>
>PDF檢視器元件運用[Adobe的檔案服務API](https://www.adobe.io/apis/documentcloud/dcsdk.html)，並要求您的管理員設定[內容感知組態](/help/developing/context-aware-configs.md)，以使用這些服務。 有關此配置的[詳細資訊，請查看元件的技術文檔。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)

## 配置對話框{#configure-dialog}

設定對話方塊可讓內容作者定義檢視器，以及檢視器的行為和顯示方式，讓訪客瀏覽頁面。

### 配置頁籤{#configuration-tab}

「設定」標籤可讓作者定義應顯示的PDF。 路徑可以定義為中的資產或AEM到其他資源的絕對路徑。

![PDF檢視器元件編輯對話方塊的設定標籤](/help/assets/pdf-viewer-edit-configuration.png)

### 自定義頁籤{#customize-tab}

「自訂標籤」可讓作者定義檢視器中可供讀者使用的選項，以及檢視器的呈現方式。

![PDF檢視器元件編輯對話方塊的自訂標籤](/help/assets/pdf-viewer-edit-customize.png)

可用選項的數量取決於選擇的&#x200B;**類型**。

* [完整視窗](#full-window) -檢視區域會在完整瀏覽器中呈現。這最適合儲存和生產力應用程式。
* [大小容器](#sized-container) -檢視區域會在完整瀏覽器中呈現。這最適合儲存和生產力應用程式。
* [行內](#in-line) -在網頁內以行內呈現的所有PDF頁面。這最適合用來讀取應用程式。

#### 完整視窗 {#full-window}

檢視區域會在完整瀏覽器中呈現。 這最適合儲存和生產力應用程式。

![PDF檢視器元件編輯對話方塊的自訂標籤完整視窗選項](/help/assets/pdf-viewer-edit-customize-full.png)

* **預設檢視模式** -檢視器在顯示頁面時的大小
   * 符合頁面
   * 符合寬度
* **全螢幕** -啟用後，檢視器將佔用檢視區的全高／寬度。
* **注釋工具** -啟用後，注釋工具可用。
* **左側面板** -啟用後，會顯示左側面板。
* **下載PDF**  —— 啟用後，會顯示下載按鈕。
* **列印PDF**  —— 啟用時，會顯示列印按鈕。
* **頁面控制** -切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 已調整大小的容器 {#sized-container}

檢視區域會在完整瀏覽器中呈現。 這最適合儲存和生產力應用程式。

![自訂PDF檢視器元件編輯對話方塊的標籤大小容器選項](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **全螢幕** -啟用後，檢視器將佔用檢視區的全高／寬度。
* **下載PDF**  —— 啟用後，會顯示下載按鈕。
* **列印PDF**  —— 啟用時，會顯示列印按鈕。
* **頁面控制** -切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 內嵌 {#in-line}

在網頁中以行形呈現的所有PDF頁面。 這最適合用來讀取應用程式。

![自訂PDF檢視器元件編輯對話方塊的標籤大小容器選項](/help/assets/pdf-viewer-edit-customize-inline.png)

* **下載PDF**  —— 啟用後，會顯示下載按鈕。
* **列印PDF**  —— 啟用時，會顯示列印按鈕。

## 設計對話框{#design-dialog}

PDF檢視器元件沒有「設計對話方塊」。
