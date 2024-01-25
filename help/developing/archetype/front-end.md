---
title: 使用AEM專案原型的前端開發
description: 瞭解AEM專案原型選用的基於Webpack的專用前端建置機制。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 0%

---


# 使用AEM專案原型的前端開發 {#front-end}

AEM專案原型包括可選用的基於Webpack的專用前端建置機制。 因此，ui.frontend模組成為專案所有前端資源（包括JavaScript和CSS檔案）的中央位置。 若要充分利用這項實用且靈活的功能，請務必瞭解前端開發如何融入AEM專案。

本檔案著重於前端建置模組的一般使用模式及其對您的作用。 如需詳細的建置選項和技術指示，請參閱原型的GitHub存放庫中的檔案。

>[!TIP]
>
>最新AEM專案原型和相關技術檔案 [在GitHub上可找到。](https://github.com/adobe/aem-project-archetype)

## AEM前端和後端開發 {#front-end-back-end}

簡而言之，AEM專案可視為包含兩個獨立但相關的部分：

* 後端開發，用於驅動AEM邏輯並產生Java程式庫、OSGi服務等
* 前端開發，用於驅動所產生網站的呈現和行為，並產生JavaScript和CSS程式庫

由於這兩個開發流程專注於專案的不同部分，因此後端和前端開發可以同時進行。

![前端工作流程圖表](/help/assets/front-end-flow.png)

但是，任何產生的專案都需要使用這兩種開發工作（即後端和前端）的輸出。

## 決定標籤 {#determining-markup}

無論您決定為專案實施哪個前端開發工作流程，後端開發人員和前端開發人員都必須先同意標籤。 通常AEM會定義核心元件所提供的標籤。 [不過，如有需要，也可自訂。](/help/developing/customizing.md#customizing-the-markup)

## 可能的前端開發工作流程 {#possible-workflows}

前端建置模組是實用且非常靈活的工具，但並未提供其使用方式的詳細說明。 以下是兩個範例 *可能* 使用情況，但您的個別專案需求可能會指示其他使用模型。

### 使用Webpack靜態開發伺服器 {#using-webpack}

使用Webpack，您可以根據ui.frontend模組內AEM網頁的靜態輸出來進行樣式設定和開發。

1. 使用頁面預覽模式或傳入，在AEM中預覽頁面 `wcmmode=disabled` 在URL中
1. 檢視頁面來源，並在ui.frontend模組中儲存為靜態HTML
1. [啟動webpack](#webpack-dev-server) 並開始樣式化和產生必要的JavaScript和CSS
1. 執行 `npm run dev` 產生clientlibs

在此流程中，AEM開發人員可執行第一步和第二步，並將靜態HTML傳遞給根據AEMHTML輸出進行開發的前端開發人員。

>[!TIP]
>
>您也可以運用 [元件資料庫](https://adobe.com/go/aem_cmp_library) 擷取每個元件的標籤輸出範例，以便在元件層級（而非頁面層級）上運作。

### 使用Storybook {#using-storybook}

使用 [Storybook](https://storybook.js.org) 您可以執行更多原子前端開發。 雖然Storybook未包含在AEM專案原型中，但您可以安裝它並將您的Storybook成品儲存在ui.frontend模組中。 準備好在AEM中進行測試時，可以透過執行將其部署為clientlibs `npm run dev`.

>[!NOTE]
>
>[Storybook](https://storybook.js.org) AEM專案原型中未含有。 如果您選擇使用它，則必須另外安裝。

## Clientlibs概述 {#clientlibs}

前端模組可使用 [AEM clientlib。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)。執行NPM建置指令碼時，系統會建置應用程式，且 `aem-clientlib-generator` 套件會擷取產生的組建輸出，並將其轉換為這類clientlib。

clientlib將包含下列檔案和目錄：

* `css/`：可用HTML請求的CSS檔案
* `css.txt`：告知AEM中的檔案順序和名稱 `css/` 以便合併
* `js/`：可用HTML請求的JavaScript檔案
* `js.txt` 告知AEM中的檔案順序和名稱 `js/` 以便合併
* `resources/`：來源對應、非入口點程式碼區塊（由程式碼分割產生）、靜態資產（例如圖示）等

>[!TIP]
>
>進一步瞭解AEM如何在中處理clientlibs [AEM開發檔案](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html) 有關如何將它們加入至 [核心元件檔案。](/help/developing/including-clientlibs.md)
