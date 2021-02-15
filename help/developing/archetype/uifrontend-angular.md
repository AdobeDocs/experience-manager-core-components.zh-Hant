---
title: Angular SPA的前端構建
description: Angular-based SPA項目前端構建過程說明
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---


# Angular SPA的前端構建版本{#frontend-angular}

本文檔將說明在使用原型建立基於Angular框架的單頁應用程式(SPA)時建立的項目的詳細資訊。 例如，將`frontendModule`選項設為`angular`時。

## 概覽 {#overview}

此項目是使用[Angular CLI](https://github.com/angular/angular-cli)啟動的。

此應用程式的建立目的是使用網站的AEM模型。 它會使用[@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components)套件中的輔助元件自動產生版面。

## 指令碼 {#scripts}

在項目目錄中，可以運行以下命令。

### npm start {#npm-start}

```
npm start
```

此命令會從執行於http://localhost:4502的本機AEM例項中代理JSON模型，以開發模式執行應用程式。 這假設整個專案已部署至AEM至少一次（在專案根目錄中為`mvn clean install -PautoInstallPackage`）。

在ui.frontend目錄中執行npm start後，您的應用程式將會自動在您的瀏覽器中開啟(位於路徑http://localhost:4200/content/${appId}/${country}/${language}/home.html)。 如果您進行編輯，頁面會重新載入。

如果您收到與CORS相關的錯誤，您可能想要依下列方式設定AEM:

1. 導覽至Configuration Manager(http://localhost:4502/system/console/configMgr)
1. 開啟「Adobe Granite跨原始資源分享政策」的設定
1. 使用下列附加值建立新設定：
   * 允許的來源：http://localhost:4200
   * 支援的標題：授權
   * 允許的方法：選項

### npm test {#npm-test}

```shell
npm test
```

此命令會啟動Karma測試跑者。 如需詳細資訊，請參閱[關於執行測試的Angular檔案](https://angular.io/guide/testing)。

### npm run test:debug {#npm-run-test-debug}

```shell
npm run test:debug
```

此命令會在互動式監視模式中啟動Karma測試執行者。

### npm run build {#npm-run-build}

```shell
npm run build
```

此命令會將生產應用程式建置至組建資料夾。 它以生產模式捆綁了Angular，並優化了構建，以獲得最佳效能。 如需詳細資訊，請參閱[Angular說明檔案關於部署](https://angular.io/guide/deployment)。

此外，AEM ClientLib是使用[aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator)套件從應用程式產生。

請參閱一般[ui.frontend模組檔案](uifrontend.md#clientlibs)，以進一步瞭解專案原型如何使用AEM ClientLibs。

## 瀏覽器支援{#browser-support}

依預設，此專案會使用[Browserslist](https://github.com/browserslist/browserslist)的預設選項來識別目標瀏覽器。 此外，它還包含現代語言功能的填色，以支援舊版瀏覽器（例如Internet Explorer 11）。 如果不需要支援此類瀏覽器，則可移除填色相依性和匯入。
