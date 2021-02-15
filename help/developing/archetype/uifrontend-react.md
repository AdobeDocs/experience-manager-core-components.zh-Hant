---
title: React SPA的前端構建
description: 描述基於React的SPA項目的前端構建過程
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---


# React SPA的前端構建{#frontend-react}

本檔案說明使用原型建立以React架構為基礎的單頁應用程式(SPA)時所建立專案的詳細資訊。 例如，將`frontendModule`選項設為`react`時。

## 概覽 {#overview}

此專案是以[create-react-app](https://github.com/facebook/create-react-app)啟動。

此應用程式的建立目的是使用網站的AEM模型。 它會使用[@adobe/cq-react-editable-components](https://www.npmjs.com/package/@adobe/cq-react-editable-components)套件中的輔助元件自動產生版面。

## 指令碼 {#scripts}

在項目目錄中，可以運行以下命令：

### npm start {#npm-start}

```shell
npm start
```

此命令會從執行於http://localhost:4502的本機AEM例項中代理JSON模型，以開發模式執行應用程式。 這假設整個專案已部署至AEM至少一次（在專案根目錄中為`mvn clean install -PautoInstallPackage`）。

在[ui.frontend](uifrontend.md)目錄中執行`npm start`後，您的應用程式會自動在您的瀏覽器中開啟（位於路徑`http://localhost:3000/content/<appId>/<country>/<language>/home.html`）。 如果您進行編輯，頁面會重新載入。

如果您收到與CORS相關的錯誤，您可能想要依下列方式設定AEM:

1. 導覽至Configuration Manager(http://localhost:4502/system/console/configMgr)
1. 開啟「Adobe Granite跨原始資源分享政策」的設定
1. 使用下列附加值建立新設定：
   * 允許的來源：http://localhost:3000
   * 支援的標題：授權
   * 允許的方法：選項

### npm test {#npm-test}

```shell
npm test
```

此命令會在互動式監視模式中啟動測試執行者。 如需詳細資訊，請參閱[關於執行測試的React檔案](https://facebook.github.io/create-react-app/docs/running-tests)。

### npm run build {#npm-run-build}

```shell
npm run build
```

此命令會將生產應用程式建置至組建資料夾。 它以生產模式捆綁了React ，並優化了構建以獲得最佳效能。 如需詳細資訊，請參閱[ React說明檔案](https://facebook.github.io/create-react-app/docs/deployment)。

此外，AEM ClientLib是使用[aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator)套件從應用程式產生。

## 瀏覽器支援{#browser-support}

依預設，此專案會使用[Browserslist](https://github.com/browserslist/browserslist)的預設選項來識別目標瀏覽器。 此外，它還包含現代語言功能的填色，以支援舊版瀏覽器（例如Internet Explorer 11）。 如果不需要支援此類瀏覽器，則可移除填色相依性和匯入。

## 代碼拆分{#code-splitting}

React應用程式依預設設定為使用[程式碼分割](https://webpack.js.org/guides/code-splitting)。 當建立生產用的應用程式時，程式碼會以數個區塊輸出：

```shell
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

只有在需要時載入區塊才能大幅改善應用程式效能。

若要使用此功能，應用程式必須能夠識別需要從AEM產生的HTML請求哪些JS和CSS檔案。 這可使用asset-manifest.json檔案中的「entrypoints」索引鍵來達成。 該檔案在clientlib.config.js中進行解析，並且只將entrypoint檔案捆綁到ClientLib中。 其餘的檔案將放在ClientLib的資源目錄中，並且會動態地請求，因此只有在實際需要時才會載入。

請參閱一般[ui.frontend模組檔案](uifrontend.md#clientlibs)，以進一步瞭解專案原型如何使用AEM ClientLibs。
