---
title: AEM專案原型前端組建
description: AEM型應用程式的專案範本
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '1618'
ht-degree: 0%

---

# AEM專案原型的ui.frontend模組 {#uifrontend-module}

AEM專案原型包含以Webpack為基礎的選用專屬前端建置機制。 因此， ui.frontend模組將成為專案所有前端資源（包括JavaScript和CSS檔案）的中央位置。 若要充分運用這項有用且有彈性的功能，請務必了解前端開發如何整合至AEM專案。

## AEM專案和前端開發 {#aem-and-front-end-development}

以簡化的術語來說，AEM專案可視為由兩個個別但相關的部分組成：

* 驅動AEM邏輯並產生Java程式庫、OSGi服務等的後端開發。
* 前端開發，可促進產生網站的呈現方式和行為，並產生JavaScript和CSS程式庫

由於這兩個開發流程都集中在項目的不同部分，因此後端和前端開發可以同時進行。

![前端工作流程圖](/help/assets/front-end-flow.png)

然而，任何由此產生的項目都需要利用這兩種發展努力的產出，即後端和前端。

執行`npm run dev`會啟動前端建置程式，該程式會收集儲存在ui.frontend模組中的JavaScript和CSS檔案，並產生兩個稱為`clientlib-site`和`clientlib-dependencies`的縮制用戶端程式庫或ClientLib，並將它們存放在ui.apps模組中。 ClientLibs可部署至AEM，並可讓您將用戶端代碼儲存在存放庫中。

使用`mvn clean install -PautoInstallPackage`執行整個AEM專案原型時，所有專案成品（包括ClientLib）隨後會推送至AEM例項。

>[!TIP]
>
>在[AEM開發檔案](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)中了解AEM如何處理ClientLib的詳細資訊，如何[包含這些ID](/help/developing/including-clientlibs.md)，或參閱下方的[中ui.frontend模組如何使用這些ID。](#clientlib-generation)

## ClientLibs概述 {#clientlibs}

前端模組可使用[AEM ClientLib](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)使用。 執行NPM組建指令碼時，應用程式會建置，而aem-clientlib-generator套件會擷取產生的組建輸出，並將其轉換為此類ClientLib。

ClientLib將包含下列檔案和目錄：

* `css/`:可在HTML中請求的CSS檔案
* `css.txt`:告訴AEM中檔案的順序和名 `css/` 稱，以便合併
* `js/`:可在HTML中請求的JavaScript檔案
* `js.txt` 告訴AEM中檔案的順序和名 `js/` 稱，以便合併
* `resources/`:原始碼映射、非入口點代碼塊（由程式碼分割產生）、靜態資產（例如圖示）等。

## 可能的前端開發工作流程 {#possible-workflows}

前端構建模組是一種有用且非常靈活的工具，但對如何使用它沒有特定意見。 以下是&#x200B;*可能的*&#x200B;使用的兩個範例，但您的個別專案需求可能會決定其他使用模型。

### 使用Webpack靜態開發伺服器 {#using-webpack}

使用Webpack，您可以根據ui.frontend模組內AEM網頁的靜態輸出來設定樣式和開發。

1. 使用頁面預覽模式在AEM中預覽頁面，或在URL中傳入`wcmmode=disabled`
1. 在ui.frontend模組中檢視頁面來源並儲存為靜態HTML
1. [開](#webpack-dev-server) 始WebPackag和開始樣式，並產生必要的JavaScript和CSS
1. 運行`npm run dev`以生成ClientLib

在此流程中，AEM開發人員可執行步驟一和步驟二，並將靜態HTML傳遞給根據AEM HTML輸出開發的前端開發人員。

>[!TIP]
>
>您也可以利用[元件庫](https://adobe.com/go/aem_cmp_library)來捕獲每個元件的標籤輸出樣本，以便在元件級別而不是頁面級別工作。

### 使用Storybook {#using-storybook}

使用[Storybook](https://storybook.js.org)可執行更多原子前端開發。 雖然AEM專案原型中未包含Storybook，但您可以安裝它，並將您的Storybook成品儲存在ui.frontend模組中。 準備好在AEM內進行測試時，可執行`npm run dev`，以部署為ClientLib。

>[!NOTE]
>
>[](https://storybook.js.org) AEM專案原型中不包含Storybook。如果您選擇使用它，則必須單獨安裝它。

### 確定標籤 {#determining-markup}

無論您決定為您的專案實作哪個前端開發工作流程，後端開發人員和前端開發人員必須先同意標籤。 通常AEM會定義由核心元件提供的標籤。 [不過，如有需要，您可以自訂此項目](/help/developing/customizing.md#customizing-the-markup)。

## ui.frontend模組 {#ui-frontend-module}

AEM專案原型包含選用的專用前端建置機制，以Webpack為基礎，並具備下列功能。

* 完整TypeScript、ES6和ES5支援（含適用的Webpack包裝函式）
* 使用TSLint規則集進行TypeScript和JavaScript連結
* ES5輸出，以支援舊版瀏覽器
* 萬用字元
   * 無需隨處新增匯入
   * 現在，所有JS和CSS檔案都可新增至每個元件。
      * 最佳實務是在`/clientlib/js`、`/clientlib/css`或`/clientlib/scss`下
   * 無需`.content.xml`或`js.txt`/`css.txt`檔案，因為所有內容都通過Webpack運行。
   * 全域會提取`/component/`資料夾下的所有JS檔案。
      * Webpack可讓CSS/SCSS檔案透過JS檔案連結在中。
      * 它們會透過`sites.js`和`vendors.js`這兩個進入點被拉入。
   * AEM使用的唯一檔案是`/clientlib-site`中的輸出檔案`site.js`和`site.css`，以及`/clientlib-dependencies`中的`dependencies.js`和`dependencies.css`
* 區塊
   * 主要（網站js/css）
   * 廠商（相依性js/css）
* 完整Sass/Scs支援（Sass會透過Webpack編譯為CSS）
* 內建Proxy至AEM本機例項的靜態WebPack開發伺服器

>[!NOTE]
>
>如需ui.frontend模組的詳細技術資訊，請參閱GitHub上的[檔案。](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md)

## 安裝 {#installation}

1. 全域安裝[NodeJS](https://nodejs.org/en/download/)(v10+)。 這也會安裝npm。
1. 導覽至專案中的ui.frontend ，然後執行`npm install`。

>[!NOTE]
>
>您必須有[執行原型](overview.md)並搭配選項`-DoptionIncludeFrontendModule=y`，才能填入ui.frontend資料夾。

## 使用狀況 {#usage}

以下npm指令碼驅動前端工作流：

* `npm run dev`  — 已停用JS最佳化的完整建置（樹狀結構等）和已啟用來源地圖，並停用CSS最佳化。
* `npm run prod`  — 已啟用JS最佳化的完整建置（樹狀結構等）、已停用來源地圖及已啟用CSS最佳化。
* `npm run start`  — 啟動本地開發的靜態WebPack開發伺服器，對AEM的依賴性最低。

## 輸出 {#output}

ui.frontend模組會編譯`ui.frontend/src`資料夾下的程式碼，並輸出已編譯的CSS和JS，以及`ui.frontend/dist`資料夾下的任何資源。

* **站點**  — 在clientlib-site資 `site.js`料夾中建 `site.css` 立與佈局相關的影像和字型的資 `resources/`  `dist/`料夾和資料夾。
* **相依性**  - `dependencies.js` 和 `dependencies.css` 會在資料夾 `dist/clientlib-dependencies` 中建立。

### JavaScript {#javascript}

* 最佳化 — 針對生產組建，會移除所有未使用或未呼叫的JS。

### CSS {#css}

* 自動預修 — 所有CSS都會透過預修程式執行，而任何需要預修的屬性都會自動將那些新增至CSS中。
* 最佳化 — 在發佈時，所有CSS都會透過最佳化程式(cssnano)執行，這會根據下列預設規則將其標準化：
   * 盡可能減少CSS計算運算式，確保瀏覽器相容性和壓縮
在等效長度、時間和角度值之間轉換。 請注意，預設情況下不會轉換長度值。
   * 移除規則、選取器和宣告中及周圍的註解
   * 移除重複的規則、at-rules和宣告
      * 請注意，這隻適用於完全重複的項目。
   * 移除含有空選取器的空規則、媒體查詢和規則，因為它們不會影響輸出
   * 由選取器和重疊的屬性/值組合併相鄰的規則
   * 確保CSS檔案中只有一個@charset，並將其移動到文檔的頂部
   * 當產生的輸出較小時，以實際值取代CSS初始關鍵字
   * 使用SVGO壓縮內嵌SVG定義
* 清除 — 包含明確的清除任務，可依需求清除產生的CSS、JS和Map檔案。
* 源映射 — 僅開發構建

>[!NOTE]
>
>前端構建選項利用共用通用配置檔案的僅開發和僅生產的Webpack配置檔案。 這樣可獨立修改開發和生產設定。

### 客戶端庫生成 {#clientlib-generation}

ui.frontend模組建置程式會利用[aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator)外掛程式，將已編譯的CSS、JS和任何資源移入ui.apps模組。 aem-clientlib-generator設定定義於`clientlib.config.js`中。 將生成以下客戶端庫：

* **clientlib-site**  -  `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-dependencies**  -  `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### 在頁面上包含用戶端程式庫 {#clientlib-inclusion}

`clientlib-site` 和類 `clientlib-dependencies` 別是透過頁面原則設定在 [頁](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/components-templates/templates.html#template-definitions) 面上納入為預設範本的一部分。要查看策略，請編輯&#x200B;**內容頁面模板>頁面資訊>頁面策略**。

網站頁面上最終包含用戶端程式庫如下：

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

當然，可以更新頁面原則及/或修改個別用戶端程式庫的類別和內嵌屬性來修改上述包含。

### 靜態Webpack開發伺服器 {#webpack-dev-server}

ui.frontend模組中包含的是Webpack-dev-server，可提供即時重新載入，以便在AEM外部進行快速前端開發。 安裝程式會利用html-webpack-plugin自動將從ui.frontend模組編譯的CSS和JS插入靜態HTML範本中。

#### 重要檔案 {#important-files}

* `ui.frontend/webpack.dev.js`
   * 這包含webpack-dev-serve的設定，並指向要使用的html範本。
   * 它也包含運行於localhost:4502的AEM實例的代理配置。
* `ui.frontend/src/main/webpack/static/index.html`
   * 這是伺服器將針對的靜態HTML。
   * 這可讓開發人員進行CSS/JS變更，並看到它們立即反映在標籤中。
   * 假定此檔案中放置的標籤準確反映AEM元件生成的標籤。
   * 此檔案中的標籤沒有與AEM元件標籤自動同步。
   * 此檔案也包含儲存在AEM中之用戶端程式庫的參考，例如核心元件CSS和回應式格線CSS。
   * Webpack開發伺服器的設定是根據`ui.frontend/webpack.dev.js`中的設定，從本機執行的AEM例項代理這些CSS/JS。

#### 使用 {#using-webpack-server}

1. 從項目根目錄中運行命令`mvn -PautoInstallSinglePackage clean install` ，將整個項目安裝到運行在`localhost:4502`的AEM實例。
1. 在`ui.frontend`資料夾內導覽。
1. 運行以下命令`npm run start`以啟動Webpack開發伺服器。 啟動後，應該會開啟瀏覽器（`localhost:8080`或下一個可用埠）。

您現在可以修改CSS、JS、SCS和TS檔案，並查看Webpack開發伺服器上立即反映的更改。
