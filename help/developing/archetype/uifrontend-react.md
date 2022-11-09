---
title: React SPA的前端版本編號
description: 說明React型SPA專案的前端建置程式
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: dd8ef13a-9686-47a9-b6af-e486ff10c4d8
source-git-commit: 0eea0cd65063c739e5b405b0380b73962a858e48
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---

# React SPA的前端版本編號 {#frontend-react}

本檔案說明使用原型根據React架構建立單頁應用程式(SPA)時所建立專案的詳細資訊。 即當您設定 `frontendModule` 選項 `react`.

## 總覽 {#overview}

這個項目是由 [create-react-app](https://github.com/facebook/create-react-app).

此應用程式的建置目的是使用網站的AEM模型。 它會使用 [@adobe/cq-react-editable-components](https://www.npmjs.com/package/@adobe/aem-react-editable-components) 包。

## 指令碼 {#scripts}

在項目目錄中，可以運行以下命令：

### npm開始 {#npm-start}

```shell
npm start
```

此命令會從執行於http://localhost:4502的本機AEM例項代理JSON模型，以開發模式執行應用程式。 這假設已將整個專案部署至AEM至少一次(`mvn clean install -PautoInstallPackage` （在專案根目錄中）。

執行後 `npm start` 在 [ui.frontend](uifrontend.md) 目錄，您的應用程式將在瀏覽器中自動開啟(在路徑 `http://localhost:3000/content/<appId>/<country>/<language>/home.html`)。 如果您進行編輯，頁面會重新載入。

如果您收到與CORS相關的錯誤，您可能想要依下列方式設定AEM:

1. 導覽至Configuration Manager(http://localhost:4502/system/console/configMgr)
1. 開啟「AdobeGranite跨原始資源共用原則」的設定
1. 使用下列其他值建立新設定：
   * 允許的原始項：http://localhost:3000
   * 支援的標題：授權
   * 允許的方法：OPTIONS

### npm測試 {#npm-test}

```shell
npm test
```

此命令將在交互監視模式下啟動測試運行器。 請參閱 [執行測試的React檔案](https://facebook.github.io/create-react-app/docs/running-tests) 以取得更多資訊。

### npm執行組建 {#npm-run-build}

```shell
npm run build
```

此命令會將生產應用程式建置至組建資料夾。 It將React捆綁在生產模式中，並最佳化組建以獲得最佳效能。 請參閱 [React有關部署的檔案](https://facebook.github.io/create-react-app/docs/deployment) 以取得更多資訊。

此外，系統會使用從應用程式產生AEM ClientLib [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) 包。

## 瀏覽器支援 {#browser-support}

依預設，此專案會使用 [Browserslist](https://github.com/browserslist/browserslist)用於識別目標瀏覽器的預設選項。 此外，它還包含現代語言功能的填充，以支援舊版瀏覽器（例如Internet Explorer 11）。 如果不需要支援這類瀏覽器，則可移除polyfill相依性和匯入。

## 程式碼分割 {#code-splitting}

React應用程式設定為使用 [代碼拆分](https://webpack.js.org/guides/code-splitting) 依預設。 建置生產用應用程式時，程式碼會以數個區塊輸出：

```shell
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

僅在需要時載入區塊可大幅改善應用程式效能。

若要使用AEM，應用程式必須能夠識別需要從AEM產生的HTML中請求哪些JS和CSS檔案。 這可使用asset-manifest.json檔案中的「entrypoints」索引鍵來達成。 檔案在clientlib.config.js中進行剖析，且只有entrypoint檔案會整合至ClientLib中。 其餘檔案將放在ClientLib的資源目錄中，並將動態地請求，因此只有在實際需要時才載入。

請參閱一般 [ui.frontend模組檔案](uifrontend.md#clientlibs) 如需如何由專案原型使用AEM ClientLib的詳細資訊。
