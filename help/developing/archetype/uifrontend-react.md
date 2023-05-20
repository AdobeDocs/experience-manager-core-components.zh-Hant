---
title: 前端構建以反SPA應
description: 基於React的項目的前端構建流程的描SPA述
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: dd8ef13a-9686-47a9-b6af-e486ff10c4d8
source-git-commit: 0eea0cd65063c739e5b405b0380b73962a858e48
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---

# 前端構建以反SPA應 {#frontend-react}

本文檔介紹使用原型建立基於React框架的單頁應用程式(SPA)時建立的項目的詳細資訊。 也就是說，當你 `frontendModule` 選項 `react`。

## 概觀 {#overview}

此項目已啟動 [建立反應應用](https://github.com/facebook/create-react-app)。

此應用程式的構建是AEM為了使用站點的模型。 它將使用從 [@adobe/cq-react-editable-components](https://www.npmjs.com/package/@adobe/aem-react-editable-components) 檔案。

## 指令碼 {#scripts}

在項目目錄中，可以運行以下命令：

### npm啟動 {#npm-start}

```shell
npm start
```

此命令通過從運行於http://localhost:4502的本地實例代理JSON模型，在開發模式AEM下運行應用。 這假定整個項目已至少部署到AEM一次(`mvn clean install -PautoInstallPackage` )。

運行後 `npm start` 的 [ui.frontend](uifrontend.md) 目錄，您的應用程式將在瀏覽器中自動開啟（在路徑上） `http://localhost:3000/content/<appId>/<country>/<language>/home.html`)。 如果進行編輯，頁面將重新載入。

如果您收到與CORS相關的錯誤，則可能需要按如AEM下方式配置：

1. 導航到Configuration Manager(http://localhost:4502/system/console/configMgr)
1. 開啟「Adobe花崗岩跨源資源共用策略」配置
1. 使用以下附加值建立新配置：
   * 允許的來源：http://localhost:3000
   * 支援的標頭：授權
   * 允許的方法：OPTIONS

### npmtest {#npm-test}

```shell
npm test
```

此命令將在互動式監視模式下啟動test運行程式。 查看 [對有關運行test的文檔進行反應](https://facebook.github.io/create-react-app/docs/running-tests) 的子菜單。

### npm運行生成 {#npm-run-build}

```shell
npm run build
```

此命令將生產應用生成到生成資料夾。 它捆綁了在生產模式下的反應，並優化了構建以獲得最佳效能。 查看 [對有關部署的文檔作出反應](https://facebook.github.io/create-react-app/docs/deployment) 的子菜單。

此外，AEM使用 [aem-clientlib生成器](https://github.com/wcm-io-frontend/aem-clientlib-generator) 檔案。

## 瀏覽器支援 {#browser-support}

預設情況下，此項目使用 [瀏覽器清單](https://github.com/browserslist/browserslist)的預設選項可標識目標瀏覽器。 此外，它還包括現代語言功能的填充符，以支援較舊的瀏覽器（如Internet Explorer 11）。 如果不需要支援此類瀏覽器，則可以刪除填充依賴項和導入。

## 代碼拆分 {#code-splitting}

React應用程式配置為使用 [代碼拆分](https://webpack.js.org/guides/code-splitting) 預設值。 在構建用於生產的應用程式時，代碼將以幾個塊輸出：

```shell
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

僅在需要時載入塊可以顯著提高應用程式效能。

要使用此功能，應AEM用需要能夠識別需要從由生成的HTML中請求哪些JS和CSS文AEM件。 可以使用asset-manifest.json檔案中的「入口點」鍵來實現此目標。 檔案在clientlib.config.js中分析，並且只將入口點檔案捆綁到ClientLib中。 其餘檔案將放在ClientLib的資源目錄中，並將動態請求，因此僅在實際需要時才載入。

請參閱常規 [ui.frontend模組文檔](uifrontend.md#clientlibs) 有關項目原型AEM如何使用ClientLibs的詳細資訊。
