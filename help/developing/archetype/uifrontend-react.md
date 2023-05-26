---
title: React SPA的前端建置
description: React型SPA專案的前端建置流程說明
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: dd8ef13a-9686-47a9-b6af-e486ff10c4d8
source-git-commit: 0eea0cd65063c739e5b405b0380b73962a858e48
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---

# React SPA的前端建置 {#frontend-react}

本檔案說明使用原型根據React架構建立單頁應用程式(SPA)時所建立專案的詳細資訊。 即當您設定 `frontendModule` 選項至 `react`.

## 概觀 {#overview}

此專案已透過以下方式啟動： [create-react-app](https://github.com/facebook/create-react-app).

此應用程式建置為使用網站的AEM模型。 它會使用來自的協助程式元件來自動產生版面 [@adobe/cq-react-editable-components](https://www.npmjs.com/package/@adobe/aem-react-editable-components) 封裝。

## 指令碼 {#scripts}

在專案目錄中，您可以執行下列命令：

### npm start {#npm-start}

```shell
npm start
```

此命令會從在http://localhost:4502執行的本機AEM執行個體代理JSON模型，以在開發模式中執行應用程式。 這假設整個專案已部署到AEM至少一次(`mvn clean install -PautoInstallPackage` （位於專案根目錄中）。

執行後 `npm start` 在 [ui.frontend](uifrontend.md) 目錄，您的應用程式將會在瀏覽器中自動開啟(位於路徑 `http://localhost:3000/content/<appId>/<country>/<language>/home.html`)。 如果您進行編輯，頁面將會重新載入。

如果您收到與CORS相關的錯誤，您可以依照以下方式設定AEM：

1. 導覽至Configuration Manager (http://localhost:4502/system/console/configMgr)
1. 開啟「AdobeGranite跨原始資源共用原則」的設定
1. 使用下列其他值建立新設定：
   * 允許的原始項：http://localhost:3000
   * 支援的標頭：Authorization
   * 允許的方法：OPTIONS

### npm test {#npm-test}

```shell
npm test
```

這個指令會在互動式監看模式中啟動測試執行器。 請參閱 [有關執行測試的React檔案](https://facebook.github.io/create-react-app/docs/running-tests) 以取得詳細資訊。

### npm run build {#npm-run-build}

```shell
npm run build
```

此命令會將生產用途的應用程式建置到建置資料夾。 它在生產模式中整合React，並最佳化組建以獲得最佳效能。 請參閱 [有關部署的React檔案](https://facebook.github.io/create-react-app/docs/deployment) 以取得詳細資訊。

此外，AEM ClientLib是透過以下方式從應用程式產生的： [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) 封裝。

## 瀏覽器支援 {#browser-support}

預設情況下，此專案使用 [Browserslist](https://github.com/browserslist/browserslist)的預設值選項來識別目標瀏覽器。 此外，它包含現代語言功能的polyfill，以支援舊版瀏覽器（例如Internet Explorer 11）。 如果不需要支援這類瀏覽器，可以移除polyfill相依性和匯入。

## 程式碼分割 {#code-splitting}

React應用程式已設定為使用 [程式碼分割](https://webpack.js.org/guides/code-splitting) 依預設。 為生產環境建置應用程式時，程式碼將輸出為幾個區塊：

```shell
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

只有在需要時才載入區塊，可顯著改善應用程式效能。

若要讓此功能與AEM搭配使用，應用程式必須能夠識別需要從AEM產生的HTML要求哪些JS和CSS檔案。 這可以使用asset-manifest.json檔案中的「entrypoints」索引鍵來達成。 檔案會在clientlib.config.js中剖析，只有入口點檔案會整合到ClientLib中。 剩餘的檔案會放置在ClientLib的資源目錄中，且會以動態方式要求，因此只有在實際需要時才載入。

請參閱一般 [ui.frontend模組檔案](uifrontend.md#clientlibs) 以進一步瞭解專案原型如何使用AEM ClientLibs。
