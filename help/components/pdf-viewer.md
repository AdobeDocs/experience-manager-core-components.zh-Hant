---
title: PDF檢視器元件
description: PDF檢視器元件可讓您顯示PDF檔案。
role: Architect, Developer, Admin, User
exl-id: deb635f5-2b73-4e7a-9838-3a941e39e898
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 3%

---


# PDF檢視器元件 {#pdf-viewer-component}

核心元件PDF Viewer元件允許在頁面上包含PDF檔案。

{{traditional-aem}}

## 使用情況 {#usage}

核心元件PDF Viewer元件內嵌檢視器，以在頁面上顯示儲存為資產的PDF檔案。

## 版本和相容性 {#version-and-compatibility}

PDF Viewer元件的目前版本是v1，此版本隨2020年6月的核心元件2.10.0版的發佈引入，說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v1 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗PDF Viewer元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_pdfviewer)。

## 技術細節 {#technical-details}

如需PDF Viewer元件[的最新技術檔案，請前往GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1)。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

>[!NOTE]
>
>PDF Viewer元件運用[Adobe的Document Services API](https://www.adobe.io/apis/documentcloud/dcsdk.html)，並要求您的管理員設定[內容感知設定](/help/developing/context-aware-configs.md)，才能使用這些服務。 如需此組態的[詳細資訊，請檢視元件的技術檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義檢視器，以及對於頁面的訪客它會如何表現和顯示。

### 組態標籤 {#configuration-tab}

設定索引標籤可讓作者定義應該顯示哪個PDF。 路徑可定義為AEM中的資產或其他資源的絕對路徑。

PDF Viewer元件](/help/assets/pdf-viewer-edit-configuration.png)之編輯對話方塊的![設定標籤

### 自訂標籤 {#customize-tab}

自訂標籤可讓作者定義檢視器中向讀者顯示的選項，以及應如何顯示檢視器。

![PDF Viewer元件之[編輯]對話方塊的[自訂]索引標籤](/help/assets/pdf-viewer-edit-customize.png)

可用選項的數目視選取的&#x200B;**型別**&#x200B;而定。

* [完整視窗](#full-window) — 檢視區域會在完整瀏覽器中呈現。 最適合儲存與生產力應用程式。
* [已調整大小的容器](#sized-container) — 檢視區域會在完整瀏覽器中呈現。 最適合儲存與生產力應用程式。
* [In-Line](#in-line) — 所有PDF頁面都會在網頁中內嵌呈現。 最適合讀取應用程式。

#### 完整視窗 {#full-window}

檢視區域會在完整瀏覽器中呈現。 最適合儲存與生產力應用程式。

![自訂PDF Viewer元件之編輯對話方塊的索引標籤完整視窗選項](/help/assets/pdf-viewer-edit-customize-full.png)

* **預設檢視模式** — 檢視器如何適應顯示它的頁面
   * 符合頁面
   * 符合寬度
* **全熒幕** — 啟用時，檢視器會佔據檢視區的完整高度/寬度。
* **註釋工具** — 啟用時，可以使用註釋工具。
* **左側面板** — 啟用時，會顯示左側面板。
* **下載PDF** — 啟用時，會顯示下載按鈕。
* **列印PDF** — 啟用時，會顯示列印按鈕。
* **頁面控制項** — 切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 已調整大小的容器 {#sized-container}

檢視區域會在完整瀏覽器中呈現。 最適合儲存與生產力應用程式。

![自訂PDF檢視器元件之編輯對話方塊的標籤大小容器選項](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **全熒幕** — 啟用時，檢視器會佔據檢視區的完整高度/寬度。
* **下載PDF** — 啟用時，會顯示下載按鈕。
* **列印PDF** — 啟用時，會顯示列印按鈕。
* **頁面控制項** — 切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 內嵌 {#in-line}

所有PDF頁面都會在網頁中內嵌呈現。 最適合讀取應用程式。

![自訂PDF檢視器元件之編輯對話方塊的標籤大小容器選項](/help/assets/pdf-viewer-edit-customize-inline.png)

* **下載PDF** — 啟用時，會顯示下載按鈕。
* **列印PDF** — 啟用時，會顯示列印按鈕。

## 設計對話方塊 {#design-dialog}

PDF Viewer元件沒有「設計」對話方塊。
