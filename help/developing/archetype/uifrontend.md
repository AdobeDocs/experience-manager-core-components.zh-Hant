---
title: 項AEM目原型前端構建
description: 基於應用程式AEM的項目模板
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: 0e8082b0c5db1f2efc7db51f13123b5264a3a608
workflow-type: tm+mt
source-wordcount: '1621'
ht-degree: 0%

---

# 項目原型的ui.AEMfronted模組 {#uifrontend-module}

項目AEM原型包括基於Webpack的可選專用前端構建機制。 因此， ui.frontend模組成為項目所有前端資源（包括JavaScript和CSS檔案）的中心位置。 要充分利用這一有用而靈活的功能，瞭解前端開發如何適合項目是非常重AEM要的。

## 項AEM目和前端開發 {#aem-and-front-end-development}

用極簡化的術語AEM來說，項目可以認為由兩個單獨但相關的部分組成：

* 驅動邏輯並產生Java庫AEM、OSGi服務等的後端開發。
* 前端開發，用於驅動生成的網站的演示和行為並生成JavaScript和CSS庫

由於這兩個開發過程都集中在項目的不同部分，因此後端和前端開發可以並行進行。

![前端工作流圖](/help/assets/front-end-flow.png)

然而，任何由此產生的項目都需要利用這些發展努力的產出，即後端和前端。

正在運行 `npm run dev` 啟動前端生成過程，該過程收集儲存在ui.frontend模組中的JavaScript和CSS檔案，並生成兩個名為的微型客戶端庫或ClientLib `clientlib-site` 和 `clientlib-dependencies` 並儲存在ui.apps模組中。 ClientLib可部署AEM到儲存庫中，並允許您將客戶端代碼儲存在儲存庫中。

當整個項AEM目原型使用 `mvn clean install -PautoInstallPackage` 然後，將包括ClientLibs在內的所有項目對象推送到實AEM例。

>[!TIP]
>
>瞭解有關如何處理AEMClientLib的詳細資訊 [AEM開發文檔](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)，如何 [包括](/help/developing/including-clientlibs.md)，請參閱下面 [ui.frontend模組如何使用它們。](#clientlib-generation)

## ClientLibs概述 {#clientlibs}

前端模組使用 [客戶AEM端庫](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)。 執行NPM生成指令碼時，將生成應用程式，並且aem-clientlib-generator包將獲取生成的生成輸出並將其轉換為這樣的ClientLib。

ClientLib將包含以下檔案和目錄：

* `css/`:可在HTML中請求的CSS檔案
* `css.txt`:指示AEM中檔案的順序和名稱 `css/` 這樣它們就可以合併
* `js/`:可在HTML中請求的JavaScript檔案
* `js.txt` 指示AEM中檔案的順序和名稱 `js/` 這樣它們就可以合併
* `resources/`:源映射、非入口點代碼塊（由代碼拆分產生）、靜態資產（如表徵圖）等。

## 可能的前端開發工作流 {#possible-workflows}

前端構建模組是一種有用且非常靈活的工具，但並未就如何使用它提出具體意見。 以下是兩個示例 *可能* 使用情況，但您的單個項目需要可能決定其他使用模式。

### 使用Webpack Static Development Server {#using-webpack}

使用Webpack，您可以根據ui.frontend模組內AEM網頁的靜態輸出來設計和開發。

1. 使用頁面預AEM覽模式或傳遞時預覽頁面 `wcmmode=disabled` 的子菜單。
1. 查看頁面源並另存為ui.frontend模組中的靜態HTML
1. [啟動WebPack](#webpack-dev-server) 並開始設計樣式並生成必要的JavaScript和CSS
1. 運行 `npm run dev` 生成ClientLib

在該流中，AEM顯影劑可執行步驟1和2，並將靜態HTML傳遞給基於HTML輸出進行開發的前AEM端顯影劑。

>[!TIP]
>
>你也可以利用 [元件庫](https://adobe.com/go/aem_cmp_library) 捕獲每個元件的標籤輸出的示例，以便在元件級別而不是頁面級別工作。

### 使用情節提要 {#using-storybook}

使用 [故事書](https://storybook.js.org) 可以進行更多原子前端開發。 儘管Storybook未包括在項AEM目原型中，但您可以安裝它，並將Storybook檔案儲存在ui.frontend模組中。 當準備在中進行測AEM試時，可以通過運行將其部署為ClientLibs `npm run dev`。

>[!NOTE]
>
>[故事書](https://storybook.js.org) 未包含在項AEM目原型中。 如果選擇使用它，則必須單獨安裝它。

### 確定標籤 {#determining-markup}

無論您決定為您的項目實施哪個前端開發流程，後端開發人員和前端開發人員都必須首先就標籤達成一致。 通常AEM定義由核心元件提供的標籤。 [但是，如有必要，可以自定義此項](/help/developing/customizing.md#customizing-the-markup)。

## ui.frontend模組 {#ui-frontend-module}

項目AEM原型包括基於Webpack的可選專用前端構建機制，具有以下功能。

* 完全支援TypeScript、ES6和ES5（含適用的Webpack包裝）
* 使用TSLint規則集的TypeScript和JavaScript連結
* ES5輸出，用於舊式瀏覽器支援
* 萬用字元
   * 無需在任何位置添加導入
   * 現在，所有JS和CSS檔案都可以添加到每個元件中。
      * 最佳做法 `/clientlib/js`。 `/clientlib/css`或 `/clientlib/scss`
   * 否 `.content.xml` 或 `js.txt`/`css.txt` 所有內容都通過Webpack運行時，需要檔案。
   * 全局伺服器將所有JS檔案 `/component/` 的子菜單。
      * Webpack允許通過JS檔案將CSS/SCSS檔案連結到。
      * 他們被從兩個入口點拉進， `sites.js` 和 `vendors.js`。
   * 唯一使用的文AEM件是輸出檔案 `site.js` 和 `site.css` 在 `/clientlib-site` 以及 `dependencies.js` 和 `dependencies.css` 在 `/clientlib-dependencies`
* 區塊
   * 主（站點js/css）
   * 供應商（依賴項js/css）
* 完全Sass/Scss支援（Sass通過Webpack編譯到CSS）
* 具有內置代理的靜態WebPack開發伺服器，該代理用於

>[!NOTE]
>
>有關ui.frontend模組的詳細資訊，請參閱 [GitHub上的文檔](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md)。

## 安裝 {#installation}

1. 安裝 [節點JS](https://nodejs.org/en/download/) (v10+)，全局。 這也將安裝npm。
1. 在項目中導航到ui.frontend並運行 `npm install`。

>[!NOTE]
>
>你一定有 [運行原型](overview.md) 選項 `-DoptionIncludeFrontendModule=y` 填充ui.frontend資料夾。

## 使用狀況 {#usage}

以下npm指令碼驅動前端工作流：

* `npm run dev`  — 禁用JS優化（樹搖動等）和啟用源映射並禁用CSS優化的完全生成。
* `npm run prod`  — 啟用JS優化（樹搖動等）、禁用源映射和啟用CSS優化的完全生成。
* `npm run start`  — 啟動靜態WebPack開發伺服器，以便進行本地開發，並且對它的依賴性AEM最小。

## 輸出 {#output}

ui.frontend模組在 `ui.frontend/src` 資料夾，並輸出已編譯的CSS和JS以及名為 `ui.frontend/dist`。

* **站點** - `site.js`。 `site.css` 和 `resources/` 用於佈局相關影像和字型的資料夾 `dist/`客戶端lib站點資料夾。
* **依賴項** - `dependencies.js` 和 `dependencies.css` 在 `dist/clientlib-dependencies` 的子菜單。

### JavaScript {#javascript}

* 優化 — 對於生產生成，所有未使用或未調用的JS將被刪除。

### CSS {#css}

* 自動預修復 — 所有CSS都通過預修復器運行，任何需要預修復的屬性都將自動將那些屬性添加到CSS中。
* 優化 — 在發佈時，所有CSS都通過優化程式(cssnano)運行，該優化程式根據以下預設規則對其進行歸一化：
   * 盡可能減少CSS計算表達式，確保瀏覽器相容性和壓縮在等效長度、時間和角度值之間轉換。 請注意，預設情況下，長度值不會轉換。
   * 刪除規則、選擇器和聲明中及周圍的注釋
   * 刪除重複的規則、at-rules和聲明
      * 請注意，這隻適用於精確的重複項。
   * 刪除空規則、媒體查詢和具有空選擇器的規則，因為它們不影響輸出
   * 按選擇器和重疊屬性/值對合併相鄰規則
   * 確保CSS檔案中僅存在@charset，並將其移到文檔頂部
   * 當結果輸出較小時，將CSS初始關鍵字替換為實際值
   * 使用SVGO壓縮內聯SVG定義
* Cleaning — 包括顯式清除任務，用於按需清除生成的CSS、JS和映射檔案。
* 源映射 — 僅生成開發

>[!NOTE]
>
>前端生成選項利用共用公共配置檔案的僅開發和僅生產webpack配置檔案。 這樣可以獨立地修改開發和生產設定。

### 客戶端庫生成 {#clientlib-generation}

ui.frontend模組生成過程利用 [aem-clientlib生成器](https://www.npmjs.com/package/aem-clientlib-generator) 插件，用於將編譯的CSS、JS和任何資源移入ui.apps模組。 aem-clientlib-generator配置在中定義 `clientlib.config.js`。 將生成以下客戶端庫：

* **客戶端庫站點** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **客戶端庫依賴項** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### 包括頁面上的客戶端庫 {#clientlib-inclusion}

`clientlib-site` 和 `clientlib-dependencies` 類別通過 [頁面策略配置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#template-definitions) 作為預設模板的一部分。 要查看策略，請編輯 **內容頁面模板>頁面資訊>頁面策略**。

最終將客戶端庫包含在站點頁面中如下：

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

當然，可以通過更新頁面策略和/或修改各客戶端庫的類別和嵌入屬性來修改上述包含。

### 靜態Webpack開發伺服器 {#webpack-dev-server}

ui.frontend模組中包括webpack-dev-server，它提供即時重裝，以便在外部進行快速前端開AEM發。 安裝程式利用html-webpack-plugin自動將從ui.frontend模組編譯的CSS和JS注入靜態HTML模板。

#### 重要檔案 {#important-files}

* `ui.frontend/webpack.dev.js`
   * 這包含webpack-dev-serve的配置，並指向要使用的html模板。
   * 它還包含運行在localhost:4502AEM上的實例的代理配置。
* `ui.frontend/src/main/webpack/static/index.html`
   * 這是伺服器將針對的靜態HTML。
   * 這允許開發人員進行CSS/JS更改，並查看它們立即反映在標籤中。
   * 假定放置在此檔案中的標籤準確地反映由元件生成的AEM標籤。
   * 此檔案中的標籤不會自動與元件標AEM記同步。
   * 此檔案還包含對儲存在中的客戶端庫(AEM如核心元件CSS和響應網格CSS)的引用。
   * Webpack開發伺服器被設定為根據在中找到的配置從本地運行AEM實例代理這些CSS/JS `ui.frontend/webpack.dev.js`。

#### 使用 {#using-webpack-server}

1. 從項目根目錄中運行命令 `mvn -PautoInstallSinglePackage clean install` 將整個項目安裝到運行AEM於 `localhost:4502`。
1. 在 `ui.frontend` 的子菜單。
1. 運行以下命令 `npm run start` 啟動webpack dev伺服器。 啟動後應開啟瀏覽器(`localhost:8080` 或下一個可用埠)。

現在，您可以修改CSS、JS、SCSS和TS檔案，並查看立即反映在webpack dev伺服器中的更改。
