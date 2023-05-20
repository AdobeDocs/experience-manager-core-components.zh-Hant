---
title: 前端構建用於Angular SPA
description: 基於Angular的項目的前端構建流程的說SPA明
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 5726e29d-081c-42bb-bf4e-2852043b21d6
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---

# 前端構建用於Angular SPA {#frontend-angular}

本文檔介紹使用原型建立基於Angular框架的單頁應用程式(SPA)時建立的項目的詳細資訊。 也就是說，當你 `frontendModule` 選項 `angular`。

## 概觀 {#overview}

這個項目是由 [AngularCLI](https://github.com/angular/angular-cli)。

此應用程式的構建是AEM為了使用站點的模型。 它將使用從 [@adobe/cq-angular可編輯的元件](https://www.npmjs.com/package/@adobe/cq-angular-editable-components) 檔案。

## 指令碼 {#scripts}

在項目目錄中，可以運行以下命令。

### npm啟動 {#npm-start}

```
npm start
```

此命令通過從運行於http://localhost:4502的本地實例代理JSON模型，在開發模式AEM下運行應用。 這假定整個項目已至少部署到AEM一次(`mvn clean install -PautoInstallPackage` )。

在ui.frontend目錄中運行npm啟動後，將在瀏覽器中自動開啟您的應用(路徑http://localhost:4200/content/${appId}/${country}/${language}/home.html)。 如果進行編輯，頁面將重新載入。

如果您收到與CORS相關的錯誤，則可能需要按如AEM下方式配置：

1. 導航到Configuration Manager(http://localhost:4502/system/console/configMgr)
1. 開啟「Adobe花崗岩跨源資源共用策略」配置
1. 使用以下附加值建立新配置：
   * 允許的來源：http://localhost:4200
   * 支援的標頭：授權
   * 允許的方法：OPTIONS

### npmtest {#npm-test}

```shell
npm test
```

此命令將啟動Karmatest。 查看 [Angular文檔關於運行test](https://angular.io/guide/testing) 的子菜單。

### npm運行test：調試 {#npm-run-test-debug}

```shell
npm run test:debug
```

此命令在互動式監視模式下啟動Karmatest運行器。

### npm運行生成 {#npm-run-build}

```shell
npm run build
```

此命令將生產應用生成到生成資料夾。 它將Angular捆綁在生產模式中，並優化構建以獲得最佳效能。 查看 [Angular有關部署的文檔](https://angular.io/guide/deployment) 的子菜單。

此外，AEM使用 [aem-clientlib生成器](https://github.com/wcm-io-frontend/aem-clientlib-generator) 檔案。

請參閱常規 [ui.frontend模組文檔](uifrontend.md#clientlibs) 有關項目原型AEM如何使用ClientLibs的詳細資訊。

## 瀏覽器支援 {#browser-support}

預設情況下，此項目使用 [瀏覽器清單](https://github.com/browserslist/browserslist)的預設選項可標識目標瀏覽器。 此外，它還包括現代語言功能的填充符，以支援較舊的瀏覽器（如Internet Explorer 11）。 如果不需要支援此類瀏覽器，則可以刪除填充依賴項和導入。
