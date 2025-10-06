---
title: 使用 AEM 專案原型進行前端開發
description: 進一步了解 AEM 專案原型的可選用 Webpack 型專用前端建置機制。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: ht
source-wordcount: '654'
ht-degree: 100%

---


# 使用 AEM 專案原型進行前端開發 {#front-end}

AEM 專案原型包括可選用的 Webpack 型專用前端建置機制。因此，ui.frontend 模組成為專案所有前端資源 (包括 JavaScript 和 CSS 檔案) 的中央位置。若要充分利用這項實用且靈活的功能，請務必了解前端開發如何融入 AEM 專案。

本文件著重於前端建置模組的一般使用模式及其對您的作用。如需詳細的建置選項和技術指示，請參閱原型的 GitHub 存放庫中的文件。

>[!TIP]
>
>[在 GitHub 上可找到](https://github.com/adobe/aem-project-archetype)最新的 AEM 專案原型及相關技術文件。

## AEM 前端和後端開發 {#front-end-back-end}

簡而言之，AEM 專案可視為包含兩個獨立但相關的部分：

* 後端開發，用於驅動 AEM 邏輯並產生 Java 程式庫、OSGi 服務等
* 前端開發，可驅動所產生網站的呈現方式和行為，並產生 JavaScript 和 CSS 程式庫

由於這兩個開發流程專注於專案的不同部分，因此後端和前端開發可以同時進行。

![前端工作流程圖](/help/assets/front-end-flow.png)

但是，任何產生的專案都需要使用這兩種開發工作 (即後端和前端) 的輸出。

## 確定標記 {#determining-markup}

無論您決定為專案實施哪個前端開發工作流程，後端開發人員和前端開發人員都必須先就標記達成共識。通常 AEM 會定義核心元件所提供的標記。[不過，如有需要，亦可自訂。](/help/developing/customizing.md#customizing-the-markup)

## 可能的前端開發工作流程 {#possible-workflows}

前端建置模組是實用且非常靈活的工具，但並未提供其用途的詳細說明。以下是&#x200B;*可能*&#x200B;使用方法的兩個範例，但您的個別專案需求可能會指示其他使用模型。

### 使用 Webpack 靜態開發伺服器 {#using-webpack}

使用 Webpack，您可以根據 ui.frontend 模組內 AEM 網頁的靜態輸出設定樣式和開發。

1. 使用頁面預覽模式或在 URL 中傳入 `wcmmode=disabled`，以在 AEM 中預覽頁面
1. 檢視頁面來源，並在 ui.frontend 模組中儲存為靜態 HTML
1. [啟動 webpack](#webpack-dev-server) 並開始樣式化和產生必要的 JavaScript 和 CSS
1. 執行 `npm run dev` 以產生 clientlib

在此流程中，AEM 開發人員可執行第一步和第二步，並將靜態 HTML 傳遞給根據 AEM HTML 輸出進行開發的前端開發人員。

>[!TIP]
>
>您也可以利用[元件庫](https://adobe.com/go/aem_cmp_library)來擷取每個元件的標記輸出範例，以便在元件層級而非頁面層級上運作。

### 使用 Storybook {#using-storybook}

使用 [Storybook](https://storybook.js.org)，您可以執行更多原子前端開發。雖然 Storybook 未包含在 AEM 專案原型中，但您可以安裝並將您的 Storybook 成品儲存在 ui.frontend 模組中。準備好在 AEM 中進行測試時，可以執行 `npm run dev` 將其部署為 clientlib。

>[!NOTE]
>
>[Storybook](https://storybook.js.org) 未包含在 AEM 專案原型中。如果您選擇使用它，則必須另外安裝。

## Clientlib 概觀 {#clientlibs}

前端模組可使用 [AEM clientlib](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)。執行 NPM 建置指令碼時，會建置應用程式，且 `aem-clientlib-generator` 套件會擷取產生的建置輸出，並將其轉換為此類 clientlib。

Clientlib 將由下列檔案和目錄組成：

* `css/`：可在 HTML 中請求的 CSS 檔案
* `css.txt`：告知 AEM `css/` 中檔案的順序和名稱，以便將這些檔案合併
* `js/`：可在 HTML 中請求的 JavaScript 檔案
* `js.txt` 告知 AEM `js/` 中檔案的順序和名稱，以便將這些檔案合併
* `resources/`：來源對應、非端點程式碼區塊 (由程式碼分割產生)、靜態資產 (例如圖示) 等。

>[!TIP]
>
>在 [AEM 開發文件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)中進一步了解 AEM 如何處理 clientlib，並了解如何將其納入[核心元件文件](/help/developing/including-clientlibs.md)。
