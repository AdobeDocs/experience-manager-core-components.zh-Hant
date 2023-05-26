---
title: AEM專案原型前端建置
description: AEM應用程式的專案範本
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: 0e8082b0c5db1f2efc7db51f13123b5264a3a608
workflow-type: tm+mt
source-wordcount: '1621'
ht-degree: 0%

---

# AEM專案原型的ui.frontend模組 {#uifrontend-module}

AEM專案原型包括可選的專用前端建置機制（以Webpack為基礎）。 因此，ui.frontend模組成為專案所有前端資源（包括JavaScript和CSS檔案）的中心位置。 若要充分利用這項實用且靈活的功能，請務必瞭解前端開發如何融入AEM專案。

## AEM專案與前端開發 {#aem-and-front-end-development}

簡而言之，AEM專案可視為由兩個獨立但相關的部分組成：

* 後端開發，用於驅動AEM邏輯並產生Java程式庫、OSGi服務等。
* 前端開發，可驅動結果網站的呈現和行為，並產生JavaScript和CSS程式庫

由於這兩個開發流程專注於專案的不同部分，因此後端和前端開發可以同時進行。

![前端工作流程圖表](/help/assets/front-end-flow.png)

但是，任何產生的專案都需要使用這兩種開發工作（即後端和前端）的輸出。

執行中 `npm run dev` 開始前端建置流程，此流程會收集儲存在ui.frontend模組中的JavaScript和CSS檔案，並產生兩個縮制的使用者端程式庫或ClientLibs，稱為 `clientlib-site` 和 `clientlib-dependencies` 並將它們儲存在ui.apps模組中。 ClientLibs可部署至AEM，並允許您將使用者端程式碼儲存在存放庫中。

使用執行整個AEM專案原型時 `mvn clean install -PautoInstallPackage` 然後會將所有專案人工因素（包括ClientLibs）推送至AEM例項。

>[!TIP]
>
>進一步瞭解AEM如何處理 [AEM開發檔案](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)，操作說明 [包含它們](/help/developing/including-clientlibs.md)，或參閱下文 [ui.frontend模組如何使用它們。](#clientlib-generation)

## ClientLibs概述 {#clientlibs}

前端模組可使用 [AEM ClientLib](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html). 執行NPM建置指令碼時，會建置應用程式，而aem-clientlib-generator套件會擷取產生的建置輸出，並將其轉換為這類ClientLib。

ClientLib將包含下列檔案和目錄：

* `css/`：可在HTML中請求的CSS檔案
* `css.txt`：告知AEM中檔案的順序和名稱 `css/` 以便合併
* `js/`：可在HTML中請求的JavaScript檔案
* `js.txt` 告知AEM中檔案的順序和名稱 `js/` 以便合併
* `resources/`：來源對應、非入口點程式碼區塊（由程式碼分割產生）、靜態資產（例如圖示）等。

## 可能的前端開發工作流程 {#possible-workflows}

前端建置模組是實用且非常彈性的工具，但並未提供其使用方式的特別意見。 以下是兩個範例 *可能* 使用情況，但您的個別專案需求可能會指示其他使用模式。

### 使用Webpack靜態開發伺服器 {#using-webpack}

使用Webpack，您可以根據ui.frontend模組內AEM網頁的靜態輸出來進行樣式設定和開發。

1. 使用頁面預覽模式或傳入在AEM中預覽頁面 `wcmmode=disabled` 在URL中
1. 檢視頁面來源，並在ui.frontend模組中儲存為靜態HTML
1. [啟動webpack](#webpack-dev-server) 並開始樣式化和產生必要的JavaScript和CSS
1. 執行 `npm run dev` 產生ClientLibs

在此流程中，AEM開發人員可執行第一步和第二步，並將靜態HTML傳遞給根據AEMHTML輸出進行開發的前端開發人員。

>[!TIP]
>
>您也可以運用 [元件資料庫](https://adobe.com/go/aem_cmp_library) 擷取每個元件的標籤輸出範例，以便在元件層級（而非頁面層級）運作。

### 使用Storybook {#using-storybook}

使用 [Storybook](https://storybook.js.org) 您可以執行更多原子前端開發。 雖然Storybook未包含在AEM專案原型中，但您可以安裝它並將您的Storybook成品儲存在ui.frontend模組中。 準備好在AEM中進行測試時，可以透過執行將它們部署為ClientLibs `npm run dev`.

>[!NOTE]
>
>[Storybook](https://storybook.js.org) 未包含在AEM專案原型中。 如果您選擇使用它，則必須另外安裝。

### 決定標籤 {#determining-markup}

無論您決定為專案實施哪個前端開發工作流程，後端開發人員和前端開發人員都必須先同意標籤。 AEM通常會定義核心元件所提供的標籤。 [不過，如有需要，可自訂此專案](/help/developing/customizing.md#customizing-the-markup).

## ui.frontend模組 {#ui-frontend-module}

AEM專案原型包含選用的專用前端建置機制，該機制以Webpack為基礎，並具有下列功能。

* 完整TypeScript、ES6和ES5支援（搭配適用的Webpack包裝函式）
* 使用TSLint規則集的TypeScript和JavaScript Linting
* ES5輸出，支援舊版瀏覽器
* 萬用字元
   * 無需在任何地方新增匯入
   * 所有JS和CSS檔案現在都可以新增至每個元件。
      * 最佳實務低於 `/clientlib/js`， `/clientlib/css`，或 `/clientlib/scss`
   * 否 `.content.xml` 或 `js.txt`/`css.txt` 檔案是必要的，因為一切都是透過Webpack執行。
   * globber會將所有JS檔案提取到 `/component/` 資料夾。
      * Webpack可透過JS檔案鏈結CSS/SCSS檔案。
      * 它們會透過兩個入口點被拉入， `sites.js` 和 `vendors.js`.
   * AEM使用的唯一檔案是輸出檔案 `site.js` 和 `site.css` 在 `/clientlib-site` 以及 `dependencies.js` 和 `dependencies.css` 在 `/clientlib-dependencies`
* 區塊
   * 主要（網站js/css）
   * 廠商（相依性js/css）
* 完整Sass/Scss支援（Sass會透過Webpack編譯為CSS）
* 內建Proxy至AEM本機執行個體的靜態Webpack開發伺服器

>[!NOTE]
>
>如需ui.frontend模組的詳細技術資訊，請參閱 [有關GitHub的檔案](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md).

## 安裝 {#installation}

1. 安裝 [NodeJS](https://nodejs.org/en/download/) (v10+)，全球。 這也會安裝npm。
1. 導覽至專案中的ui.frontend並執行 `npm install`.

>[!NOTE]
>
>您必須擁有 [執行原型](overview.md) 包含選項 `-DoptionIncludeFrontendModule=y` 填入ui.frontend資料夾。

## 使用狀況 {#usage}

以下npm指令碼會驅動前端工作流程：

* `npm run dev`  — 完整建置，其中停用JS最佳化（tree shaking等）、啟用來源對應並停用CSS最佳化。
* `npm run prod`  — 完整建置，啟用JS最佳化（tree shaking等）、停用來源地圖並啟用CSS最佳化。
* `npm run start`  — 啟動靜態Webpack開發伺服器以進行本機開發，並且對AEM的依賴性最小。

## 輸出 {#output}

ui.frontend模組會編譯 `ui.frontend/src` 資料夾並輸出編譯的CSS和JS，以及名為的資料夾下的任何資源 `ui.frontend/dist`.

* **網站** - `site.js`， `site.css` 和 `resources/` 與版面相關的影像和字型的資料夾建立於 `dist/`clientlib-site資料夾。
* **相依性** - `dependencies.js` 和 `dependencies.css` 在中建立 `dist/clientlib-dependencies` 資料夾。

### JavaScript {#javascript}

* 最佳化 — 對於生產組建，所有未使用或呼叫的JS都會被移除。

### CSS {#css}

* 自動加上前置詞 — 所有CSS都是透過前置詞執行，而任何需要加上前置詞的屬性都會自動加入CSS中。
* 最佳化 — 在發佈時，所有CSS都會透過最佳化工具(cssnano)執行，該工具會根據以下預設規則將其標準化：
   * 儘可能減少CSS計算運算式，確保瀏覽器相容性和壓縮在相等的長度、時間和角度值之間轉換。 請注意，依預設，不會轉換長度值。
   * 移除規則、選取器和宣告中及其周圍的註解
   * 移除重複的規則、at規則和宣告
      * 請注意，這僅適用於完全相同的重複專案。
   * 移除空白規則、媒體查詢和具有空白選取器的規則，因為它們不會影響輸出
   * 透過選取器和重疊的屬性/值配對合併相鄰規則
   * 確保CSS檔案中只有單一@charset案，並將它移動到檔案頂端
   * 當產生的輸出較小時，將CSS初始關鍵字替換為實際值
   * 使用SVGO壓縮內嵌SVG定義
* 清除 — 包含明確清除工作，以便視需要清除產生的CSS、JS和Map檔案。
* 來源對應 — 僅開發組建

>[!NOTE]
>
>前端建置選項利用dev-only和prod-only webpack組態檔案，這些檔案共用一個通用組態檔案。 如此一來，即可獨立修改開發及生產設定。

### 使用者端程式庫產生 {#clientlib-generation}

ui.frontend模組建置程式會利用 [aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator) 外掛程式，以將編譯後的CSS、JS及任何資源移入ui.apps模組。 aem-clientlib-generator設定定義於 `clientlib.config.js`. 會產生下列使用者端程式庫：

* **clientlib-site** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-dependencies** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### 在頁面上包含使用者端資料庫 {#clientlib-inclusion}

`clientlib-site` 和 `clientlib-dependencies` 類別可透過以下方式包含在頁面上： [頁面原則設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#template-definitions) 做為預設範本的一部分。 若要檢視原則，請編輯 **內容頁面範本>頁面資訊>頁面原則**.

網站頁面上最終包含的使用者端程式庫如下：

```html
<HTML>
    <head>
        <link rel="stylesheet" href="clientlib-base.css" type="text/css">
        <script type="text/javascript" src="clientlib-dependencies.js"></script>
        <link rel="stylesheet" href="clientlib-dependencies.css" type="text/css">
        <link rel="stylesheet" href="clientlib-site.css" type="text/css">
    </head>
    <body>
        ....
        <script type="text/javascript" src="clientlib-site.js"></script>
        <script type="text/javascript" src="clientlib-base.js"></script>
    </body>
</HTML>
```

當然，您可以更新頁面原則及/或修改個別使用者端程式庫的類別和內嵌屬性，以修改上述包含。

### 靜態Webpack開發伺服器 {#webpack-dev-server}

ui.frontend模組中包含一個webpack-dev-server，可為AEM外部的快速前端開發提供即時重新載入。 安裝程式會利用html-webpack-plugin，自動將從ui.frontend模組編譯的CSS和JS插入靜態HTML範本中。

#### 重要檔案 {#important-files}

* `ui.frontend/webpack.dev.js`
   * 這包含webpack-dev-serve的設定，並指向要使用的html範本。
   * 它也包含在localhost：4502上執行之AEM執行個體的Proxy設定。
* `ui.frontend/src/main/webpack/static/index.html`
   * 這是伺服器將針對的靜態HTML。
   * 如此一來，開發人員就能進行CSS/JS變更，並立即在標籤中反映出來。
   * 假設放置在此檔案中的標籤準確地反映了AEM元件產生的標籤。
   * 此檔案中的標籤不會自動與AEM元件標籤同步。
   * 此檔案也包含儲存在AEM中的使用者端資料庫參考，例如核心元件CSS和回應式格線CSS。
   * webpack開發伺服器已設定為根據中的設定，從本機執行的AEM執行個體代理這些CSS/JS includes `ui.frontend/webpack.dev.js`.

#### 使用 {#using-webpack-server}

1. 從專案的根目錄中執行命令 `mvn -PautoInstallSinglePackage clean install` 將整個專案安裝至執行位置的AEM執行個體 `localhost:4502`.
1. 在 `ui.frontend` 資料夾。
1. 執行以下命令 `npm run start` 以啟動webpack開發伺服器。 開始後，應該會開啟瀏覽器(`localhost:8080` 或下一個可用的連線埠)。

您現在可以修改CSS、JS、SCSS和TS檔案，且變更會立即反映在webpack開發伺服器中。
