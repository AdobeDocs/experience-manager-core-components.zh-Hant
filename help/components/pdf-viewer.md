---
title: PDF Viewer元件
description: PDF Viewer元件允許顯示PDF文檔。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: deb635f5-2b73-4e7a-9838-3a941e39e898
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 3%

---

# PDF Viewer元件{#pdf-viewer-component}

核心元件PDF Viewer元件允許在頁面上包含PDF檔案。

## 使用狀況 {#usage}

核心元件PDF檢視器元件內嵌檢視器，可顯示儲存為頁面上資產的PDF檔案。

## 版本和相容性{#version-and-compatibility}

目前的PDF檢視器元件版本為v1，此版本於2020年6月2.10.0版核心元件時推出，本檔案將詳細說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗PDF檢視器元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_pdfviewer)。

## 技術詳細資訊{#technical-details}

有關PDF檢視器元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

>[!NOTE]
>
>PDF Viewer元件利用[Adobe的Document Services API](https://www.adobe.io/apis/documentcloud/dcsdk.html)，並要求管理員配置[上下文感知配置](/help/developing/context-aware-configs.md)以便使用這些服務。 有關此配置的詳細資訊，請查看元件的技術文檔。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)[

## 配置對話框{#configure-dialog}

「設定」對話方塊可讓內容作者定義檢視器，以及檢視器的行為和顯示方式，供造訪頁面的訪客使用。

### 配置頁簽{#configuration-tab}

「設定」索引標籤可讓作者定義應顯示的PDF。 路徑可定義為AEM中的資產，或其他資源的絕對路徑。

![PDF查看器元件的編輯對話框的配置頁簽](/help/assets/pdf-viewer-edit-configuration.png)

### 自定義頁簽{#customize-tab}

「自訂」索引標籤可讓作者定義檢視器中可供讀者使用的選項，以及檢視器的呈現方式。

![自定義PDF查看器元件編輯對話框的頁簽](/help/assets/pdf-viewer-edit-customize.png)

可用的選項數取決於所選的&#x200B;**類型**。

* [完整視窗](#full-window)  — 檢視區域會在完整瀏覽器中呈現。這最適合儲存和生產應用程式。
* [大小容器](#sized-container)  — 檢視區域會在完整瀏覽器中呈現。這最適合儲存和生產應用程式。
* [串聯](#in-line)  — 在網頁中以串聯方式呈現的所有PDF頁面。這最適合讀取應用程式。

#### 完整視窗 {#full-window}

檢視區會在完整瀏覽器中轉譯。 這最適合儲存和生產應用程式。

![PDF查看器元件的編輯對話框的「自定義」頁簽全窗口選項](/help/assets/pdf-viewer-edit-customize-full.png)

* **預設檢視模式**  — 檢視器與其顯示頁面的配適方式
   * 符合頁面
   * 符合寬度
* **全螢幕**  — 啟用後，檢視器會取用檢視區的全高/寬度。
* **注釋工具**  — 啟用後，注釋工具可用。
* **左側面板**  — 啟用後，會顯示左側面板。
* **下載PDF**  — 啟用後，會顯示下載按鈕。
* **打印PDF**  — 啟用後，將顯示打印按鈕。
* **頁面控制項**  — 切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 已調整大小的容器 {#sized-container}

檢視區會在完整瀏覽器中轉譯。 這最適合儲存和生產應用程式。

![PDF查看器元件的編輯對話框的自定義頁簽大小容器選項](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **全螢幕**  — 啟用後，檢視器會取用檢視區的全高/寬度。
* **下載PDF**  — 啟用後，會顯示下載按鈕。
* **打印PDF**  — 啟用後，將顯示打印按鈕。
* **頁面控制項**  — 切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 內嵌 {#in-line}

在網頁中以行呈現的所有PDF頁面。 這最適合讀取應用程式。

![PDF查看器元件的編輯對話框的自定義頁簽大小容器選項](/help/assets/pdf-viewer-edit-customize-inline.png)

* **下載PDF**  — 啟用後，會顯示下載按鈕。
* **打印PDF**  — 啟用後，將顯示打印按鈕。

## 設計對話框{#design-dialog}

PDF Viewer元件沒有「設計」對話框。
