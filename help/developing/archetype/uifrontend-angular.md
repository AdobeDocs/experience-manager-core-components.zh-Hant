---
title: 前端構建用於Angular SPA
description: 描述基於Angular的項目的前端構建過SPA程
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---


# 用於AngularSPA{#frontend-angular}的前端構建

本檔案說明使用原型以根據Angular架構建立單頁應用程式(SPA)時所建立專案的詳細資訊。 例如，將`frontendModule`選項設為`angular`時。

## 概覽 {#overview}

此項目是使用[AngularCLI](https://github.com/angular/angular-cli)啟動的。

此應用程式的建立AEM目的是使用網站的模型。 它會使用[@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components)套件中的協助元件自動產生版面。

## 指令碼 {#scripts}

在項目目錄中，可以運行以下命令。

### npm start {#npm-start}

```
npm start
```

此命令會從執行於http://localhost:4502的本機例項中代理JSON模型，以開發模式AEM執行應用程式。 這假定整個項目已部署至AEM少一次（在項目根目錄中為`mvn clean install -PautoInstallPackage`）。

在ui.frontend目錄中執行npm start後，您的應用程式將會自動在您的瀏覽器中開啟(位於路徑http://localhost:4200/content/${appId}/${country}/${language}/home.html)。 如果您進行編輯，頁面會重新載入。

如果您收到與CORS相關的錯誤，您可能會想要設定AEM如下：

1. 導覽至Configuration Manager(http://localhost:4502/system/console/configMgr)
1. 開啟「Adobe花崗岩跨原始資源共用政策」的設定
1. 使用下列附加值建立新設定：
   * 允許的來源：http://localhost:4200
   * 支援的標題：授權
   * 允許的方法：OPTIONS

### npm test {#npm-test}

```shell
npm test
```

此命令會啟動Karma測試跑者。 如需詳細資訊，請參閱[執行測試的Angular檔案](https://angular.io/guide/testing)。

### npm run test:debug {#npm-run-test-debug}

```shell
npm run test:debug
```

此命令會在互動式監視模式中啟動Karma測試執行者。

### npm run build {#npm-run-build}

```shell
npm run build
```

此命令會將生產應用程式建置至組建資料夾。 它以生產模式捆綁Angular，並優化構建以獲得最佳效能。 如需詳細資訊，請參閱[有關部署的Angular檔案](https://angular.io/guide/deployment)。

此外，AEM使用[aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator)套件從應用程式產生ClientLib。

有關項目原型如何使用AEMClientLibs的詳細資訊，請參閱一般[ui.frontend模組檔案](uifrontend.md#clientlibs)。

## 瀏覽器支援{#browser-support}

依預設，此專案會使用[Browserslist](https://github.com/browserslist/browserslist)的預設選項來識別目標瀏覽器。 此外，它還包含現代語言功能的填色，以支援舊版瀏覽器（例如Internet Explorer 11）。 如果不需要支援此類瀏覽器，則可移除填色相依性和匯入。
