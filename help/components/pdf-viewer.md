---
title: PDF查看器元件
description: PDF查看器元件允許顯示PDF文檔。
role: Architect, Developer, Admin, User
exl-id: deb635f5-2b73-4e7a-9838-3a941e39e898
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 3%

---

# PDF查看器元件 {#pdf-viewer-component}

核心元件PDF查看器元件允許將PDF文檔包含在頁面上。

## 使用狀況 {#usage}

核心元件PDF查看器元件嵌入查看器，以在頁面上顯示作為資產儲存的PDF檔案。

## 版本和相容性 {#version-and-compatibility}

PDF查看器元件的當前版本為v1，該版本於2020年6月隨核心元件2.10.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗PDF查看器元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_pdfviewer)。

## 技術詳細資訊 {#technical-details}

有關PDF查看器元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

>[!NOTE]
>
>PDF查看器元件利用 [Adobe的文檔服務API](https://www.adobe.io/apis/documentcloud/dcsdk.html) 並要求管理員配置 [上下文感知配置](/help/developing/context-aware-configs.md) 以便使用這些服務。 檢查元件的技術文檔 [有關此配置的詳細資訊。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)

## 配置對話框 {#configure-dialog}

「配置」對話框允許內容作者定義查看者及其行為和對頁面訪問者的顯示方式。

### 配置頁籤 {#configuration-tab}

「配置」頁籤允許作者定義應顯示的PDF。 該路徑可定義為資源中的資AEM產或另一資源的絕對路徑。

![「PDF查看器元件」的「編輯」對話框的「配置」頁籤](/help/assets/pdf-viewer-edit-configuration.png)

### 自定義頁籤 {#customize-tab}

「定制」(Customize)頁籤允許作者定義查看器中可供閱讀器使用的選項以及如何顯示查看器。

![「PDF查看器」元件的「編輯」對話框的「自定義」頁籤](/help/assets/pdf-viewer-edit-customize.png)

可用選項的數量取決於 **類型** 的子菜單。

* [完整窗口](#full-window)  — 查看區域在完整瀏覽器中呈現。 這最適合儲存和生產效率應用程式。
* [大小容器](#sized-container)  — 查看區域在完整瀏覽器中呈現。 這最適合儲存和生產效率應用程式。
* [串聯](#in-line)  — 網頁中以行呈現的所有PDF頁。 這最適合於讀取應用程式。

#### 完整視窗 {#full-window}

查看區域在整個瀏覽器中呈現。 這最適合儲存和生產效率應用程式。

![自定義PDF查看器元件的編輯對話框的頁籤全窗口選項](/help/assets/pdf-viewer-edit-customize-full.png)

* **預設視圖模式**  — 查看器在顯示頁面時的大小
   * 符合頁面
   * 符合寬度
* **全屏**  — 啟用後，查看器將佔用視區的全高/寬度。
* **注釋工具**  — 啟用後，注釋工具可用。
* **左側面板**  — 啟用後，將顯示左側面板。
* **下載PDF**  — 啟用後，將顯示下載按鈕。
* **打印PDF**  — 啟用後，將顯示打印按鈕。
* **頁面控制項**  — 切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 已調整大小的容器 {#sized-container}

查看區域在整個瀏覽器中呈現。 這最適合儲存和生產效率應用程式。

![自定義PDF查看器元件的編輯對話框的頁籤大小容器選項](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **全屏**  — 啟用後，查看器將佔用視區的全高/寬度。
* **下載PDF**  — 啟用後，將顯示下載按鈕。
* **打印PDF**  — 啟用後，將顯示打印按鈕。
* **頁面控制項**  — 切換頁面控制項的行為。
   * 固定
   * 取消固定

#### 內嵌 {#in-line}

所有PDF頁在網頁中以行呈現。 這最適合於讀取應用程式。

![自定義PDF查看器元件的編輯對話框的頁籤大小容器選項](/help/assets/pdf-viewer-edit-customize-inline.png)

* **下載PDF**  — 啟用後，將顯示下載按鈕。
* **打印PDF**  — 啟用後，將顯示打印按鈕。

## 設計對話框 {#design-dialog}

PDF查看器元件沒有「設計」對話框。
