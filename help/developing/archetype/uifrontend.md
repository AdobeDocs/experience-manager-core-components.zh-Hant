---
title: AEM Project Archetype Front-End Build
description: AEM型應用程式的專案範本
translation-type: tm+mt
source-git-commit: 10090b836397af3c9428f99bba72313263f34596
workflow-type: tm+mt
source-wordcount: '1620'
ht-degree: 0%

---


# AEM Project Archetype {#uifrontend-module}的ui.frontend模組

AEM Project Archetype包含選用、專屬的前端建置機制，以Webpack為基礎。 因此， ui.frontend模組會成為專案所有前端資源（包括JavaScript和CSS檔案）的中心位置。 若要充份運用這項有用而有彈性的功能，請務必瞭解前端開發如何與AEM專案整合。

## AEM Projects和前端開發{#aem-and-front-end-development}

AEM專案可簡化為由兩個獨立但相關的部分組成：

* 後端開發，可驅動AEM的邏輯並產生Java程式庫、OSGi服務等。
* 前端開發，可推動產生的網站的表現和行為，並產生JavaScript和CSS程式庫

由於這兩個開發流程都集中在項目的不同部分，因此後端和前端開發可以並行進行。

![前端工作流程圖](/help/assets/front-end-flow.png)

但是，任何產生的項目都需要使用這兩種開發努力的產出，即後端和前端。

執行`npm run dev`會啟動前端建置程式，收集儲存在ui.frontend模組中的JavaScript和CSS檔案，並產生兩個稱為`clientlib-site`和`clientlib-dependencies`的精簡用戶端程式庫或ClientLibs，並將它們儲存在ui.apps模組中。 ClientLib可部署至AEM，並可讓您將用戶端代碼儲存在儲存庫中。

當使用`mvn clean install -PautoInstallPackage`執行整個AEM專案原型時，所有專案對象（包括ClientLib）都會推送至AEM例項。

>[!TIP]
>
>進一步瞭解AEM如何在[AEM開發檔案](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)中處理ClientLibs、如何[包含它們](/help/developing/including-clientlibs.md)，或參閱[下方的ui.frontend模組如何使用它們。](#clientlib-generation)

## ClientLibs概述{#clientlibs}

前端模組是使用[AEM ClientLib](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)提供。 當執行NPM組建指令碼時，應用程式會建立，而aem-clientlib-generator套件會擷取產生的組建輸出，並將它轉換為此類的ClientLib。

ClientLib將包含下列檔案和目錄：

* `css/`:可在HTML中要求的CSS檔案
* `css.txt`:告訴AEM檔案的順序和名稱， `css/` 以便合併
* `js/`:可在HTML中要求的JavaScript檔案
* `js.txt` 告訴AEM檔案的順序和名稱， `js/` 以便合併
* `resources/`:原始碼地圖、非登入點程式碼區塊（由程式碼分割產生）、靜態資產（例如圖示）等。

## 可能的前端開發工作流程{#possible-workflows}

前端構建模組是一種實用、靈活的工具，但對應如何使用它沒有特別意見。 以下是&#x200B;*可能的*&#x200B;使用情形的兩個範例，但您的個別專案需求可能會決定其他使用模式。

### 使用Webpack Static Development Server {#using-webpack}

使用Webpack，您可以根據ui.frontend模組內AEM網頁的靜態輸出，來設定樣式並進行開發。

1. 在AEM中使用頁面預覽模式或在URL中傳入`wcmmode=disabled`來預覽頁面
1. 在ui.frontend模組中檢視頁面來源並儲存為靜態HTML
1. [開始](#webpack-dev-server) WebPackag並開始設定樣式並產生必要的JavaScript和CSS
1. 運行`npm run dev`以生成ClientLibs

在此流程中，AEM開發人員可執行步驟1和步驟2，並將靜態HTML傳遞給根據AEM HTML輸出進行開發的前端開發人員。

>[!TIP]
>
>您也可以利用[元件庫](https://adobe.com/go/aem_cmp_library)來擷取每個元件的標籤輸出範例，以便在元件層級而非頁面層級工作。

### 使用Storybook {#using-storybook}

使用[Storybook](https://storybook.js.org)，您可以執行更多原子前端開發。 雖然Storybook未包含在AEM Project Archetype中，但您可以將它安裝並儲存在ui.frontend模組中的Storybook檔案。 當準備好在AEM中進行測試時，可執行`npm run dev`，將它們部署為ClientLibs。

>[!NOTE]
>
>[AEM Project ](https://storybook.js.org) Archetype中未包含Storybook。如果您選擇使用它，則必須個別安裝它。

### 確定標籤{#determining-markup}

不論您決定為您的專案實作的前端開發工作流程為何，後端開發人員和前端開發人員必須先同意標籤。 通常，AEM會定義由核心元件提供的標籤。 [不過，如有必要，可自訂此項](/help/developing/customizing.md#customizing-the-markup)。

## ui.frontend模組{#ui-frontend-module}

AEM Project Archetype包含選用的專屬前端建立機制，以Webpack為基礎，具備下列功能。

* 完整TypeScript、ES6和ES5支援（含適用的Webpack包裝函式）
* 使用TSLint規則集的TypeScript和JavaScript連結
* ES5輸出，以支援舊版瀏覽器
* 萬用字元
   * 無需隨處新增匯入
   * 現在，所有JS和CSS檔案都可新增至每個元件。
      * 最佳做法是在`/clientlib/js`、`/clientlib/css`或`/clientlib/scss`下
   * 由於所有內容都通過Webpack運行，因此不需要`.content.xml`或`js.txt`/`css.txt`檔案。
   * 全局提取`/component/`資料夾下的所有JS檔案。
      * Webpack可讓CSS/SCSS檔案透過JS檔案連結。
      * 它們被拉進兩個入口點，`sites.js`和`vendors.js`。
   * AEM使用的唯一檔案是`/clientlib-site`中的輸出檔案`site.js`和`site.css`，以及`/clientlib-dependencies`中的`dependencies.js`和`dependencies.css`
* 區塊
   * 主要（網站js/css）
   * 廠商（相依性js/css）
* 完整的Sass/Scss支援（Sass會透過Webpack編譯為CSS）
* 將內建Proxy的靜態網路套件開發伺服器內建至AEM的本機執行個體

>[!NOTE]
>
>有關ui.frontend模組的更多技術資訊，請參閱GitHub](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md)上的[檔案。

## 安裝{#installation}

1. 全域安裝[NodeJS](https://nodejs.org/en/download/)(v10+)。 這也將安裝npm。
1. 導覽至專案中的ui.frontend，然後執行`npm install`。

>[!NOTE]
>
>您必須使用[運行帶有`-DoptionIncludeFrontendModule=y`選項的原型](overview.md)來填入ui.frontend資料夾。

## 使用狀況 {#usage}

以下NPM指令碼驅動前端工作流：

* `npm run dev` -已停用JS最佳化（樹狀結構等）和來源地圖，並停用CSS最佳化的完整建置。
* `npm run prod` -啟用JS最佳化（樹狀結構等）、停用來源地圖和啟用CSS最佳化的完整建置。
* `npm run start` -啟動靜態網頁套件開發伺服器以進行本機開發，且對AEM的依賴性最小。

## 輸出 {#output}

ui.frontend模組會編譯`ui.frontend/src`資料夾下的程式碼，並輸出已編譯的CSS和JS，以及名為`ui.frontend/dist`資料夾下的任何資源。

* **網站** -和 `site.js`版面相依影像和字型的資料 `site.css` 夾會建立在clientlib-site資料 `resources/`  `dist/`夾中。
* **相依性** - `dependencies.js` 並 `dependencies.css` 在資料夾中創 `dist/clientlib-dependencies` 建。

### JavaScript {#javascript}

* 最佳化——對於生產組建，所有未使用或呼叫的JS都會移除。

### CSS {#css}

* 自動預修——所有CSS都會透過預修器執行，而任何需要預修的屬性都會自動將這些屬性加入CSS中。
* 最佳化——在貼文時，所有CSS都會透過最佳化程式(cssnano)執行，並根據下列預設規則將它標準化：
   * 盡可能減少CSS計算運算式，確保瀏覽器相容性和壓縮性
在等效長度、時間和角度值之間轉換。 請注意，預設情況下，不會轉換長度值。
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

### 客戶端庫生成{#clientlib-generation}

ui.frontend模組建立程式運用[aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator)外掛程式，將編譯的CSS、JS和任何資源移入ui.apps模組。 aem-clientlib-generator組態定義於`clientlib.config.js`。 將生成以下客戶端庫：

* **clientlib-site** -  `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-dependences** -  `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### 在{#clientlib-inclusion}頁面上包含客戶端庫

`clientlib-site` 而類 `clientlib-dependencies` 別則會透過「頁面原則 [設定」](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#template-definitions) 作為預設範本的一部分包含在頁面上。若要檢視原則，請編輯&#x200B;**內容頁面範本>頁面資訊>頁面原則**。

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

### 靜態Webpack開發伺服器{#webpack-dev-server}

ui.frontend模組包含webpack-dev-server，可提供即時重新載入，以便在AEM以外快速進行前端開發。 此設定會運用html-webpack-plugin，自動將從ui.frontend模組編譯的CSS和JS插入靜態HTML範本。

#### 重要檔案{#important-files}

* `ui.frontend/webpack.dev.js`
   * 這包含webpack-dev-serve的設定，並指向要使用的html範本。
   * 它也包含在localhost:4502上執行之AEM例項的Proxy設定。
* `ui.frontend/src/main/webpack/static/index.html`
   * 這是伺服器將針對的靜態HTML。
   * 這可讓開發人員進行CSS/JS變更，並立即在標籤中反映。
   * 假設定入此檔案的標籤會準確反映AEM元件產生的標籤。
   * 此檔案中的標籤不會自動與AEM元件標籤同步。
   * 此檔案也包含儲存在AEM中的用戶端程式庫參考，例如核心元件CSS和回應式格線CSS。
   * Webpack開發伺服器已設定為根據`ui.frontend/webpack.dev.js`中的設定，從本機執行的AEM例項來代理這些CSS/JS。

#### 使用 {#using-webpack-server}

1. 從專案的根目錄執行命令`mvn -PautoInstallSinglePackage clean install`，將整個專案安裝至執行於`localhost:4502`的AEM例項。
1. 在`ui.frontend`資料夾內導覽。
1. 運行以下命令`npm run start`以啟動webpack dev伺服器。 啟動後，應開啟瀏覽器（`localhost:8080`或下一個可用埠）。

您現在可以修改CSS、JS、SCSS和TS檔案，並立即在webpack dev伺服器中看到這些變更。
