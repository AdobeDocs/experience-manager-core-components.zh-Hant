---
title: React SPA的前端版本編號
description: 說明React型SPA專案的前端建置程式
feature: 核心元件、AEM專案原型
role: Architect, Developer, Administrator
exl-id: dd8ef13a-9686-47a9-b6af-e486ff10c4d8
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 0%

---

# React SPA的前端構建{#frontend-react}

本檔案說明使用原型根據React架構建立單頁應用程式(SPA)時所建立專案的詳細資訊。 亦即當您將`frontendModule`選項設為`react`時。

## 概覽 {#overview}

此項目已用[create-react-app](https://github.com/facebook/create-react-app)引導。

此應用程式的建置目的是使用網站的AEM模型。 它會使用[@adobe/cq-react-editable-components](https://www.npmjs.com/package/@adobe/cq-react-editable-components)套件中的輔助元件自動產生版面。

## 指令碼 {#scripts}

在項目目錄中，可以運行以下命令：

### npm開始{#npm-start}

```shell
npm start
```

此命令會從執行於http://localhost:4502的本機AEM例項代理JSON模型，以開發模式執行應用程式。 這假設已將整個專案部署至AEM至少一次（專案根目錄中的`mvn clean install -PautoInstallPackage`）。

在[ui.frontend](uifrontend.md)目錄中執行`npm start`後，您的應用程式會在瀏覽器中自動開啟（位於路徑`http://localhost:3000/content/<appId>/<country>/<language>/home.html`）。 如果您進行編輯，頁面會重新載入。

如果您收到與CORS相關的錯誤，您可能想要依下列方式設定AEM:

1. 導覽至Configuration Manager(http://localhost:4502/system/console/configMgr)
1. 開啟「AdobeGranite跨原始資源共用原則」的設定
1. 使用下列其他值建立新設定：
   * 允許的原始項：http://localhost:3000
   * 支援的標題：授權
   * 允許的方法：OPTIONS

### npm測試{#npm-test}

```shell
npm test
```

此命令將在交互監視模式下啟動測試運行器。 如需詳細資訊，請參閱[ React檔案中關於執行測試](https://facebook.github.io/create-react-app/docs/running-tests) 。

### npm運行build {#npm-run-build}

```shell
npm run build
```

此命令會將生產應用程式建置至組建資料夾。 It將React捆綁在生產模式中，並最佳化組建以獲得最佳效能。 如需詳細資訊，請參閱[ React部署相關檔案](https://facebook.github.io/create-react-app/docs/deployment) 。

此外，系統會使用[aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator)套件從應用程式產生AEM ClientLib。

## 瀏覽器支援{#browser-support}

依預設，此專案使用[Browserslist](https://github.com/browserslist/browserslist)的預設選項來識別目標瀏覽器。 此外，它還包含現代語言功能的填充，以支援舊版瀏覽器（例如Internet Explorer 11）。 如果不需要支援這類瀏覽器，則可移除polyfill相依性和匯入。

## 代碼拆分{#code-splitting}

React應用程式依預設會使用[程式碼分割](https://webpack.js.org/guides/code-splitting)。 建置生產用應用程式時，程式碼會以數個區塊輸出：

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

若要使用AEM，應用程式必須能夠識別需要從AEM產生的HTML請求哪些JS和CSS檔案。 這可使用asset-manifest.json檔案中的「entrypoints」索引鍵來達成。 檔案在clientlib.config.js中進行剖析，且只有entrypoint檔案會整合至ClientLib中。 其餘檔案將放在ClientLib的資源目錄中，並將動態地請求，因此只有在實際需要時才載入。

如需關於專案原型如何使用AEM ClientLib的詳細資訊，請參閱一般[ui.frontend模組檔案](uifrontend.md#clientlibs)。
