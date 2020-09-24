---
title: AEM Project Archetype Front-End Build
description: AEM型應用程式的專案範本
translation-type: tm+mt
source-git-commit: d8503d92c2d4948e54b2ad7d5407e4c7c98ebf83
workflow-type: tm+mt
source-wordcount: '1621'
ht-degree: 0%

---


# AEM Project Archetype的ui.frontend模組 {#uifrontend-module}

AEM Project Archetype包含選用、專屬的前端建置機制，以Webpack為基礎。 因此， ui.frontend模組會成為專案所有前端資源（包括JavaScript和CSS檔案）的中心位置。 若要充份運用這項有用而有彈性的功能，請務必瞭解前端開發如何與AEM專案整合。

## AEM專案與前端開發 {#aem-and-front-end-development}

AEM專案可簡化為由兩個獨立但相關的部分組成：

* 後端開發，可驅動AEM的邏輯並產生Java程式庫、OSGi服務等。
* 前端開發，可推動產生的網站的表現和行為，並產生JavaScript和CSS程式庫

由於這兩個開發流程都集中在項目的不同部分，因此後端和前端開發可以並行進行。

![前端工作流程圖](/help/assets/front-end-flow.png)

但是，任何產生的項目都需要使用這兩種開發努力的產出，即後端和前端。

執 `npm run dev` 行會啟動前端建置程式，收集儲存在ui.frontend模組中的JavaScript和CSS檔案，並產生兩個精簡的用戶端程式庫或ClientLibs, `clientlib-site``clientlib-dependencies` 並將它們儲存在ui.apps模組中。 ClientLib可部署至AEM，並可讓您將用戶端代碼儲存在儲存庫中。

當使用所有專案工件（包括ClientLib）執 `mvn clean install -PautoInstallPackage` 行整個AEM專案原型時，就會推送至AEM例項。

>[!TIP]
>
>在 [AEM開發檔案中進一步瞭解AEM如何處理ClientLib](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/clientlibs.html)、如何加 [入Client](/help/developing/including-clientlibs.md)，或 [在下方查看ui.frontend模組的使用方式。](#clientlib-generation)

## ClientLibs概觀 {#clientlibs}

前端模組是使用 [AEM ClientLib提供](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)。 當執行NPM組建指令碼時，應用程式會建立，而aem-clientlib-generator套件會擷取產生的組建輸出，並將它轉換為此類的ClientLib。

ClientLib將包含下列檔案和目錄：

* `css/`:可在HTML中要求的CSS檔案
* `css.txt`:告訴AEM檔案的順序和名稱， `css/` 以便合併
* `js/`:可在HTML中要求的JavaScript檔案
* `js.txt` 告訴AEM檔案的順序和名稱， `js/` 以便合併
* `resources/`:原始碼地圖、非登入點程式碼區塊（由程式碼分割產生）、靜態資產（例如圖示）等。

## 可能的前端開發工作流程 {#possible-workflows}

前端構建模組是一種實用、靈活的工具，但對應如何使用它沒有特別意見。 以下是兩個可能的使 *用範例* ，但您個別專案的需求可能會決定其他使用模式。

### 使用Webpack Static Development Server {#using-webpack}

使用Webpack，您可以根據ui.frontend模組內AEM網頁的靜態輸出，來設定樣式並進行開發。

1. 在AEM中使用頁面預覽模式或在URL中傳 `wcmmode=disabled` 入預覽頁面
1. 在ui.frontend模組中檢視頁面來源並儲存為靜態HTML
1. [開始Web Pack](#webpack-dev-server) ，開始設定樣式並產生必要的JavaScript和CSS
1. 執行 `npm run dev` 以產生ClientLib

在此流程中，AEM開發人員可執行步驟1和步驟2，並將靜態HTML傳遞給根據AEM HTML輸出進行開發的前端開發人員。

>[!TIP]
>
>您也可以利用 [Component Library](https://adobe.com/go/aem_cmp_library) ，擷取每個元件的標籤輸出範例，以便在元件層級而非頁面層級工作。

### 使用Storybook {#using-storybook}

使用 [Storybook](https://storybook.js.org) ，您就可以執行更多原子前端開發。 雖然Storybook未包含在AEM Project Archetype中，但您可以將它安裝並儲存在ui.frontend模組中的Storybook檔案。 當準備好在AEM中進行測試時，您可以執行這些測試，將它們部署為ClientLibs `npm run dev`。

>[!NOTE]
>
>[Storybook](https://storybook.js.org) 不包含在AEM Project Archetype中。 如果您選擇使用它，則必須個別安裝它。

### 確定標籤 {#determining-markup}

不論您決定為您的專案實作的前端開發工作流程為何，後端開發人員和前端開發人員必須先同意標籤。 通常，AEM會定義由核心元件提供的標籤。 [不過，如有必要，可自訂此項](/help/developing/customizing.md#customizing-the-markup)。

## ui.frontend模組 {#ui-frontend-module}

AEM Project Archetype包含選用的專屬前端建立機制，以Webpack為基礎，具備下列功能。

* 完整TypeScript、ES6和ES5支援（含適用的Webpack包裝函式）
* 使用TSLint規則集的TypeScript和JavaScript連結
* ES5輸出，以支援舊版瀏覽器
* 萬用字元
   * 無需隨處新增匯入
   * 現在，所有JS和CSS檔案都可新增至每個元件。
      * 最佳實務是 `/clientlib/js`在、 `/clientlib/css`或 `/clientlib/scss`
   * 由於 `.content.xml` 所有內 `js.txt`容都透過Webpack執行，因此不需要任何或/`css.txt` 檔案。
   * 全域提取資料夾下的所有JS `/component/` 檔案。
      * Webpack可讓CSS/SCSS檔案透過JS檔案連結。
      * 它們被拉進兩個入口 `sites.js` 處 `vendors.js`。
   * AEM使用的唯一檔案是輸出 `site.js` 檔 `site.css` 案 `/clientlib-site` 以及 `dependencies.js` 和 `dependencies.css` 中 `/clientlib-dependencies`
* 區塊
   * 主要（網站js/css）
   * 廠商（相依性js/css）
* 完整的Sass/Scss支援（Sass會透過Webpack編譯為CSS）
* 將內建Proxy的靜態網路套件開發伺服器內建至AEM的本機執行個體

>[!NOTE]
>
>如需ui.frontend模組的詳細技術資訊，請參閱GitHub [上的檔案](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md)。

## 安裝 {#installation}

1. 全 [域安裝NodeJS](https://nodejs.org/en/download/) (v10+)。 這也將安裝npm。
1. 導覽至專案中的ui.frontend並執行 `npm install`。

>[!NOTE]
>
>您必須已 [使用填入ui.frontend檔](overview.md)`-DoptionIncludeFrontendModule=y` 案夾的選項執行原型。

## 使用狀況 {#usage}

以下NPM指令碼驅動前端工作流：

* `npm run dev` -已停用JS最佳化（樹狀結構等）和來源地圖，並停用CSS最佳化的完整建置。
* `npm run prod` -啟用JS最佳化（樹狀結構等）、停用來源地圖和啟用CSS最佳化的完整建置。
* `npm run start` -啟動靜態網頁套件開發伺服器以進行本機開發，且對AEM的依賴性最小。

## 輸出 {#output}

ui.frontend模組會編譯資料夾下的程式碼， `ui.frontend/src` 並輸出已編譯的CSS和JS，以及資料夾下的任何資源 `ui.frontend/dist`。

* **網站** -和 `site.js`版面相依影像和字型的資料夾會建立在 `site.css``resources/``dist/`clientlib-site資料夾中。
* **相依性** - `dependencies.js` 並在 `dependencies.css` 資料夾中創 `dist/clientlib-dependencies` 建。

### JavaScript {#javascript}

* 最佳化——對於生產組建，所有未使用或呼叫的JS都會移除。

### CSS {#css}

* 自動預修——所有CSS都會透過預修器執行，而任何需要預修的屬性都會自動將這些屬性加入CSS中。
* 最佳化——在貼文時，所有CSS都會透過最佳化程式(cssnano)執行，並根據下列預設規則將它標準化：
   * 盡可能減少CSS計算運算式，以確保瀏覽器相容性和壓縮在等效長度、時間和角度值之間轉換。 請注意，預設情況下，不會轉換長度值。
   * 移除規則、選擇器與宣告中及周圍的注釋
   * 刪除重複的規則、at-rules和聲明
      * 請注意，這隻適用於完全重複的檔案。
   * 移除空的規則、媒體查詢和具有空選擇器的規則，因為它們不會影響輸出
   * 由選擇器和重疊的屬性／值對合併相鄰規則
   * 確保CSS檔案中只有單一@charset，並將它移至檔案頂端
   * 當產生的輸出較小時，以實際值取代CSS初始關鍵字
   * 使用SVGO壓縮內嵌SVG定義
* 清除——包含明確的清除工作，以視需要清除產生的CSS、JS和Map檔案。
* 源映射——僅構建開發

>[!NOTE]
>
>前端構建選項利用共用公共配置檔案的僅開發和僅生產webpack配置檔案。 這樣，可以單獨修改開發和生產設定。

### 用戶端程式庫開發 {#clientlib-generation}

ui.frontend模組建立程式利用 [aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator) plugin，將編譯的CSS、JS和任何資源移入ui.apps模組。 aem-clientlib-generator組態定義於 `clientlib.config.js`。 將生成以下客戶端庫：

* **clientlib-site** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-dependencies** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### 在頁面上包含用戶端程式庫 {#clientlib-inclusion}

`clientlib-site` 而類 `clientlib-dependencies` 別則會透過「頁面原則 [設定](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/page-templates-editable.html#template-definitions) 」包含在頁面上，作為預設範本的一部分。 若要檢視原則，請編輯「內 **容頁面範本>頁面資訊>頁面原則」**。

在網站頁面上最終加入用戶端程式庫如下：

```
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

當然，上述包含可通過更新頁面策略和／或修改各客戶端庫的類別和嵌入屬性來修改。

### Static Webpack Development Server {#webpack-dev-server}

ui.frontend模組包含webpack-dev-server，可提供即時重新載入，以便在AEM以外快速進行前端開發。 此設定會運用html-webpack-plugin，自動將從ui.frontend模組編譯的CSS和JS插入靜態HTML範本。

#### 重要檔案 {#important-files}

* `ui.frontend/webpack.dev.js`
   * 這包含webpack-dev-serve的設定，並指向要使用的html範本。
   * 它也包含在localhost:4502上執行之AEM例項的Proxy設定。
* `ui.frontend/src/main/webpack/static/index.html`
   * 這是伺服器將針對的靜態HTML。
   * 這可讓開發人員進行CSS/JS變更，並立即在標籤中反映。
   * 假設定入此檔案的標籤會準確反映AEM元件產生的標籤。
   * 此檔案中的標籤不會自動與AEM元件標籤同步。
   * 此檔案也包含儲存在AEM中的用戶端程式庫參考，例如核心元件CSS和回應式格線CSS。
   * Webpack開發伺服器的設定是根據中的設定，從本機執行的AEM例項來代理這些CSS/JS `ui.frontend/webpack.dev.js`。

#### 使用 {#using-webpack-server}

1. 從專案的根目錄執行命令，將 `mvn -PautoInstallSinglePackage clean install` 整個專案安裝至執行於的AEM例項 `localhost:4502`。
1. 在資料夾內導 `ui.frontend` 覽。
1. 運行以下命 `npm run start` 令以啟動webpack dev server。 啟動後，應開啟瀏覽器(`localhost:8080` 或下一個可用埠)。

您現在可以修改CSS、JS、SCSS和TS檔案，並立即在webpack dev伺服器中看到這些變更。
