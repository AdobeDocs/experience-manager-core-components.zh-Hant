---
title: PDF檢視器元件
description: PDF檢視器元件可顯示PDF檔案。
role: Architect, Developer, Admin, User
exl-id: deb635f5-2b73-4e7a-9838-3a941e39e898
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 3%

---

# PDF檢視器元件 {#pdf-viewer-component}

利用核心元件PDF檢視器元件，可在頁面上包含PDF檔案。

## 使用狀況 {#usage}

核心元件PDF檢視器元件內嵌檢視器，以顯示儲存為頁面資產的PDF檔案。

## 版本和相容性 {#version-and-compatibility}

PDF Viewer元件的目前版本是v1，此版本隨2020年6月的核心元件2.10.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容於<br>[版本2.17.4](/help/versions.md) 和先前的 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗PDF檢視器元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_pdfviewer).

## 技術細節 {#technical-details}

有關PDF檢視器元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

>[!NOTE]
>
>PDF檢視器元件會利用 [Adobe的檔案服務API](https://www.adobe.io/apis/documentcloud/dcsdk.html) 並要求您的管理員設定 [內容感知設定](/help/developing/context-aware-configs.md) 才能使用這些服務。 請檢視元件的技術檔案，以瞭解 [此設定的詳細資料。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義檢視器，以及對於頁面的訪客它會如何表現和顯示。

### 設定標籤 {#configuration-tab}

Configuration索引標籤可讓作者定義應顯示的PDF。 路徑可定義為AEM中的資產或其他資源的絕對路徑。

![PDF檢視器元件之「編輯」對話方塊的「設定」索引標籤](/help/assets/pdf-viewer-edit-configuration.png)

### 自訂標籤 {#customize-tab}

自訂標籤可讓作者定義檢視器中可供讀者使用的選項，以及應如何顯示檢視器。

![PDF檢視器元件之「編輯」對話方塊的「自訂」標籤](/help/assets/pdf-viewer-edit-customize.png)

可用選項的數目取決於 **型別** 「 」已選取。

* [完整視窗](#full-window)  — 檢視區域會在完整瀏覽器中呈現。 最適合儲存與生產力應用程式。
* [已調整大小的容器](#sized-container)  — 檢視區域會在完整瀏覽器中呈現。 最適合儲存與生產力應用程式。
* [內嵌](#in-line)  — 所有PDF頁面都會在網頁內內成一行。 最適合閱讀應用程式。

#### 完整視窗 {#full-window}

檢視區域會在整個瀏覽器中呈現。 最適合儲存與生產力應用程式。

![PDF檢視器元件之「編輯」對話方塊的「自訂」標籤完整視窗選項](/help/assets/pdf-viewer-edit-customize-full.png)

* **預設檢視模式**  — 檢視器如何適應顯示它的頁面
   * 符合頁面
   * 符合寬度
* **全熒幕**  — 啟用時，檢視器會佔據檢視區的完整高度/寬度。
* **註解工具**  — 啟用時，註釋工具可供使用。
* **左側面板**  — 啟用時，會顯示左側面板。
* **下載PDF**  — 啟用時，會顯示下載按鈕。
* **列印PDF**  — 啟用時，會顯示列印按鈕。
* **頁面控制項**  — 切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 已調整大小的容器 {#sized-container}

檢視區域會在整個瀏覽器中呈現。 最適合儲存與生產力應用程式。

![PDF檢視器元件之「編輯」對話方塊的「自訂」標籤調整容器大小選項](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **全熒幕**  — 啟用時，檢視器會佔據檢視區的完整高度/寬度。
* **下載PDF**  — 啟用時，會顯示下載按鈕。
* **列印PDF**  — 啟用時，會顯示列印按鈕。
* **頁面控制項**  — 切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 內嵌 {#in-line}

所有PDF頁面都會在網頁中內聯呈現。 最適合閱讀應用程式。

![PDF檢視器元件之「編輯」對話方塊的「自訂」標籤調整容器大小選項](/help/assets/pdf-viewer-edit-customize-inline.png)

* **下載PDF**  — 啟用時，會顯示下載按鈕。
* **列印PDF**  — 啟用時，會顯示列印按鈕。

## 設計對話方塊 {#design-dialog}

PDF檢視器元件沒有「設計」對話方塊。
