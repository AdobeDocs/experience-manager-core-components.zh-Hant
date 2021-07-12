---
title: 適用於AngularSPA的前端組建
description: 說明Angular型SPA專案的前端建置程式
feature: 核心元件、AEM專案原型
role: Architect, Developer, Admin
exl-id: 5726e29d-081c-42bb-bf4e-2852043b21d6
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# 適用於AngularSPA的前端組建 {#frontend-angular}

本檔案說明使用原型根據Angular架構建立單頁應用程式(SPA)時，所建立專案的詳細資訊。 亦即當您將`frontendModule`選項設為`angular`時。

## 概覽 {#overview}

此項目已用[AngularCLI](https://github.com/angular/angular-cli)引導。

此應用程式的建置目的是使用網站的AEM模型。 它會使用[@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components)套件中的協助元件自動產生版面。

## 指令碼 {#scripts}

在項目目錄中，可以運行以下命令。

### npm開始 {#npm-start}

```
npm start
```

此命令會從執行於http://localhost:4502的本機AEM例項代理JSON模型，以開發模式執行應用程式。 這假設已將整個專案部署至AEM至少一次（專案根目錄中的`mvn clean install -PautoInstallPackage`）。

在ui.frontend目錄中執行npm開始後，您的應用程式將在瀏覽器中自動開啟(位於路徑http://localhost:4200/content/${appId}/${country}/${language}/home.html)。 如果您進行編輯，頁面會重新載入。

如果您收到與CORS相關的錯誤，您可能想要依下列方式設定AEM:

1. 導覽至Configuration Manager(http://localhost:4502/system/console/configMgr)
1. 開啟「AdobeGranite跨原始資源共用原則」的設定
1. 使用下列其他值建立新設定：
   * 允許的原始項：http://localhost:4200
   * 支援的標題：授權
   * 允許的方法：OPTIONS

### npm測試 {#npm-test}

```shell
npm test
```

此命令將啟動Karma測試運行程式。 如需詳細資訊，請參閱[Angular檔案，了解執行測試的相關資訊。](https://angular.io/guide/testing)

### npm運行測試：debug {#npm-run-test-debug}

```shell
npm run test:debug
```

此命令將在互動式監視模式下啟動Karma測試運行程式。

### npm執行組建 {#npm-run-build}

```shell
npm run build
```

此命令會將生產應用程式建置至組建資料夾。 它在生產模式中捆綁Angular，並最佳化組建以獲得最佳效能。 如需詳細資訊，請參閱[關於部署的Angular檔案](https://angular.io/guide/deployment)。

此外，系統會使用[aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator)套件從應用程式產生AEM ClientLib。

如需關於專案原型如何使用AEM ClientLib的詳細資訊，請參閱一般[ui.frontend模組檔案](uifrontend.md#clientlibs)。

## 瀏覽器支援 {#browser-support}

依預設，此專案使用[Browserslist](https://github.com/browserslist/browserslist)的預設選項來識別目標瀏覽器。 此外，它還包含現代語言功能的填充，以支援舊版瀏覽器（例如Internet Explorer 11）。 如果不需要支援這類瀏覽器，則可移除polyfill相依性和匯入。
