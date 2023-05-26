---
title: angularSPA的前端建置
description: angular型SPA專案的前端建置流程說明
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 5726e29d-081c-42bb-bf4e-2852043b21d6
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---

# angularSPA的前端建置 {#frontend-angular}

本檔案說明使用原型根據Angular架構建立單頁應用程式(SPA)時所建立專案的詳細資訊。 即當您設定 `frontendModule` 選項至 `angular`.

## 概觀 {#overview}

此專案已使用 [ANGULARCLI](https://github.com/angular/angular-cli).

此應用程式建置為使用網站的AEM模型。 它會使用來自的協助程式元件來自動產生版面 [@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components) 封裝。

## 指令碼 {#scripts}

在專案目錄中，您可以執行下列指令。

### npm start {#npm-start}

```
npm start
```

此命令會從在http://localhost:4502執行的本機AEM執行個體代理JSON模型，以在開發模式中執行應用程式。 這假設整個專案已部署到AEM至少一次(`mvn clean install -PautoInstallPackage` （位於專案根目錄中）。

在ui.frontend目錄中執行npm start後，應用程式將自動在瀏覽器中開啟(路徑為http://localhost:4200/content/${appId}/${country}/${language}/home.html)。 如果您進行編輯，頁面將會重新載入。

如果您收到與CORS相關的錯誤，您可以依照以下方式設定AEM：

1. 導覽至Configuration Manager (http://localhost:4502/system/console/configMgr)
1. 開啟「AdobeGranite跨原始資源共用原則」的設定
1. 使用下列其他值建立新設定：
   * 允許的原始項：http://localhost:4200
   * 支援的標頭：Authorization
   * 允許的方法：OPTIONS

### npm test {#npm-test}

```shell
npm test
```

這個指令會啟動Karma測試執行器。 請參閱 [有關執行測試的Angular檔案](https://angular.io/guide/testing) 以取得詳細資訊。

### npm run test：debug {#npm-run-test-debug}

```shell
npm run test:debug
```

這個指令會在互動式監看模式中啟動Karma測試執行器。

### npm run build {#npm-run-build}

```shell
npm run build
```

此命令會將生產用途的應用程式建置到建置資料夾。 它在生產模式下整合Angular，並將組建最佳化以獲得最佳效能。 請參閱 [有關部署的Angular檔案](https://angular.io/guide/deployment) 以取得詳細資訊。

此外，AEM ClientLib是透過以下方式從應用程式產生的： [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) 封裝。

請參閱一般 [ui.frontend模組檔案](uifrontend.md#clientlibs) 以進一步瞭解專案原型如何使用AEM ClientLibs。

## 瀏覽器支援 {#browser-support}

預設情況下，此專案使用 [Browserslist](https://github.com/browserslist/browserslist)的預設值選項來識別目標瀏覽器。 此外，它包含現代語言功能的polyfill，以支援舊版瀏覽器（例如Internet Explorer 11）。 如果不需要支援這類瀏覽器，可以移除polyfill相依性和匯入。
