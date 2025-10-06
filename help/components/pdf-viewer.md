---
title: PDF 檢視器元件
description: PDF 檢視器元件允許顯示 PDF 文件。
role: Architect, Developer, Admin, User
exl-id: deb635f5-2b73-4e7a-9838-3a941e39e898
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '685'
ht-degree: 100%

---


# PDF 檢視器元件 {#pdf-viewer-component}

核心元件 PDF 檢視器元件允許在頁面上包含 PDF 文件。

{{traditional-aem}}

## 用途 {#usage}

核心元件 PDF 檢視器元件內嵌檢視器，以在頁面上顯示儲存為資產的 PDF 檔案。

## 版本和相容性 {#version-and-compatibility}

PDF 檢視器元件的目前版本為 v1，此版本於 2020 年 6 月隨著核心元件 2.10.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v1 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「PDF 檢視器元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_pdfviewer)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1)有關 PDF 檢視器元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

>[!NOTE]
>
>PDF 檢視器元件運用 [Adobe 的 Document Services API](https://www.adobe.io/apis/documentcloud/dcsdk.html)，並要求您的管理員設定[內容感知設定](/help/developing/context-aware-configs.md) ，才能使用這些服務。如需[此設定的詳細資訊](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)，請檢視元件的技術文件。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義檢視器，以及其對頁面訪客的行為與顯示方式。

### 設定索引標籤 {#configuration-tab}

設定索引標籤可讓作者定義應該顯示哪個 PDF。路徑可定義為 AEM 中的資產或其他資源的絕對路徑。

![PDF 檢視器元件編輯對話框的設定索引標籤](/help/assets/pdf-viewer-edit-configuration.png)

### 自訂索引標籤 {#customize-tab}

自訂索引標籤可讓作者定義檢視器中向讀者顯示的選項，以及應如何顯示檢視器。

![PDF 檢視器元件編輯對話框的自訂索引標籤](/help/assets/pdf-viewer-edit-customize.png)

可用選項的數目視選取的&#x200B;**類型**&#x200B;而定。

* [完整視窗](#full-window) - 檢視區域會在完整瀏覽器中呈現。最適合用於儲存與生產力應用程式。
* [已調整大小的容器](#sized-container) - 檢視區域會在完整瀏覽器中呈現。最適合用於儲存與生產力應用程式。
* [內嵌](#in-line) - 所有 PDF 頁面都會在網頁中內嵌呈現。最適合用於閱讀應用程式。

#### 完整視窗 {#full-window}

檢視區域會在完整瀏覽器中呈現。最適合用於儲存與生產力應用程式。

![PDF 檢視器元件編輯對話框的自訂索引標籤完整視窗選項](/help/assets/pdf-viewer-edit-customize-full.png)

* **預設檢視模式** - 檢視器將如何符合其所顯示的頁面大小
   * 符合頁面
   * 符合寬度
* **全螢幕** - 啟用時，檢視器會佔據檢視區的完整高度/寬度。
* **註解工具** - 啟用時，可以使用註解工具。
* **左側面板** - 啟用時，會顯示左側面板。
* **下載 PDF** - 啟用時，會顯示下載按鈕。
* **列印 PDF** - 啟用時，會顯示列印按鈕。
* **頁面控制項** - 切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 已調整大小的容器 {#sized-container}

檢視區域會在完整瀏覽器中呈現。最適合用於儲存與生產力應用程式。

![PDF 檢視器元件編輯對話框的自訂索引標籤已調整大小容器選項](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **全螢幕** - 啟用時，檢視器會佔據檢視區的完整高度/寬度。
* **下載 PDF** - 啟用時，會顯示下載按鈕。
* **列印 PDF** - 啟用時，會顯示列印按鈕。
* **頁面控制項** - 切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 內嵌 {#in-line}

所有 PDF 頁面都會在網頁中內嵌呈現。最適合用於閱讀應用程式。

![PDF 檢視器元件編輯對話框的自訂索引標籤已調整大小容器選項](/help/assets/pdf-viewer-edit-customize-inline.png)

* **下載 PDF** - 啟用時，會顯示下載按鈕。
* **列印 PDF** - 啟用時，會顯示列印按鈕。

## 設計對話框 {#design-dialog}

PDF 檢視器元件沒有設計對話框。
