---
title: 使用項AEM目原型
description: 項目原型的詳細使AEM用說明
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: ca61d71a2644465e74249058157d8dea2aa71352
workflow-type: tm+mt
source-wordcount: '2198'
ht-degree: 2%

---

# AEM 專案原型 {#aem-project-archetype}

「項AEM目原型」將建立一個基於最佳做法的最小的Adobe Experience Manager項目，作為您自己項目的AEM起點。 使用此原型時必須提供的屬性允許您指定此項目所有部分的名稱以及控制某些可選特徵。

## 為什麼使用原型 {#why-use-the-archetype}

使用「AEM項目原型」，您只需按幾下鍵，即可構建基於最佳實踐AEM的項目。 通過使用原型，所有的部件都已經到位，這樣，雖然最終的項目是最小的，但它已經實現了 [關鍵功能](#what-you-get) 你AEM只需在上面建並延伸。

當然，在一個成功的項目中，有許AEM多要素，但使AEM用「項目原型」是一個堅實的基礎，強烈建議任何項AEM目使用。

## 快速入門 {#getting-started}

項目原型使得開始開發變得容易AEM。 您可以通過多種方式來採取您的第一步。

* WKND教程 — 有關開發(包括如AEM何利用原型)的重要介紹，請參閱 [AEM Sites入門 — WKND教程](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hant) 例如，用原型來實現一個簡單的項目。
* WKND事件教程 — 如果您對上的單頁應用程式(SPA)開發特別感興趣AEM，請務必簽出專用 [WKND事件教程](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)。
* 下載並自行啟動！  — 您可以輕鬆下載GitHub上提供的當前項目原型，並通過 [執行以下簡單步驟](#how-to-use-the-archetype)。

## 使用原型得到什麼 {#what-you-get}

原型AEM由模組組成：

* **[核](core.md)**:是包含所有核心功能（如OSGi服務、偵聽器和調度程式）的Java包，以及與元件相關的Java代碼（如servlet和請求篩選器）。
* **[it.test](ittests.md)**:是基於Java的整合test。
* **[ui.apps](uiapps.md)**:包含 `/apps` 和 `/etc` 項目的部分，即JS和CSS客戶端、元件和模板。
* **[ui.content](uicontent.md)**:包含使用ui.apps模組中元件的示例內容。
* **ui.config**:包含項目的運行模式特定的OSGi配置。
* **[ui.frontend.general](uifrontend.md)**: **（可選）** 包含使用基於Webpack的常規前端生成模組所需的對象。
* **[ui.frontend.react](uifrontend-react.md)**: **（可選）** 包含使用原型建立基於「反應」(React)的項SPA目時所需的工件。
* **[ui.frontend.angular](uifrontend-angular.md)**: **（可選）** 包含使用原型建立基於Angular的項SPA目時所需的工件。
* **[ui.test](uitests.md)**:包含基於硒的UItest。
* **全部**:是一個內容包，它嵌入所有已編譯模組（包和內容包），包括任何供應商依賴項。
* **分析**:對項目運行分析，為部署到AEMas a Cloud Service提供附加驗證。

![](/help/assets/archetype-structure.png)

Maven中表示的AEMArchetype模組被部署成AEM表示應用程式、內容和必要的OSGi包的內容包。

## 如何使用原型 {#how-to-use-the-archetype}

要使用原型，首先需要建立一個項目，該項目將本地檔案結構中的模組生成為 [以前](#what-you-get)。 作為項目生成的一部分，可以定義項目的許多屬性，如項目名稱、版本等。

使用Maven構建項目會建立可部署到的工件（包和OSGi捆綁包）AEM。 可以使用其他Maven命令和配置檔案將項目對象部署到實AEM例。

### 建立項目 {#create-project}

要開始使用，您只需使用 [Eclipse擴AEM展](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/eclipse.html?lang=zh-Hant) 並按照「新建項目」嚮導選擇 **多模AEM塊項目示例** 使用原型的已發佈版本。

當然，你也可以直接調用Maven。

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D aemVersion=cloud \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
 -D frontendModule=general \
 -D includeExamples=n
```

* 設定 `XX` 到 [版本號](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md) 最新的原型AEM計畫。
* 設定 `aemVersion=cloud` 為 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html);\
   設定 `aemVersion=6.5.0` 為 [Adobe托管服務](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署。
只為非雲版本添加核心元件依賴項，因為為AEMas a Cloud Service提供核心元件。
* 調整 `appTitle="My Site"` 定義網站標題和元件組。
* 調整 `appId="mysite"` 定義Maven artifactId、元件、配置和內容資料夾名稱以及客戶端庫名稱。
* 調整 `groupId="com.mysite"` 定義Maven groupId和Java源包。
* 查找可用屬性清單，查看是否要調整更多屬性。

>[!NOTE]
>
>最佳做法是 `adobe-public` Maven的檔案 `settings.xml` 檔案，以便自動將repo.adobe.com添加到maven生成過程。
>
>POM示例 [可在此處找到](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-17454.html?lang=en)。

### 屬性 {#properties}

使用原型建立項目時，以下屬性可用。

| 名稱 | 預設 | 說明 |
|---------------------------|----------------|--------------------|
| `appTitle` |  | 應用程式標題將用於網站標題和元件組(例如 `"My Site"`)。 |
| `appId` |  | 技術名稱將用於元件、配置和內容資料夾名稱以及客戶端庫名稱(例如 `"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基Maven項目ID(例如 `"mysite"`)。 |
| `groupId` |  | 基本Maven組ID(例如 `"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java源包(例如 `"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 項目版本(例如 `1.0-SNAPSHOT`)。 |
| `aemVersion` | `cloud` | 目AEM標版本(可以 `cloud` 為 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html);或 `6.5.0`或 `6.4.4` 為 [Adobe托管服務](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或內部)。 |
| `sdkVersion` | `latest` | 當 `aemVersion=cloud` 一個 [SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) 可以指定版本(例如 `2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 包括針對雲或AMS/本地的調度程式配置，具體取決於 `aemVersion` (可以 `y` 或 `n`)。 |
| `frontendModule` | `general` | 包括生成客戶端庫的Webpack前端生成模組(可以 `general` 或 `none` 對於常規場所；可以 `angular` 或 `react` 用於實現 [編SPA輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/editor-overview.html))。 |
| `language` | `en` | 語言代碼(ISO 639-1)，用於從(例如 `en`。 `deu`)。 |
| `country` | `us` | 國家（地區）代碼(ISO 3166-1)，用於建立內容結構，例如 `US`)。 |
| `singleCountry` | `y` | 包括語言主體內容結構(可以 `y`或 `n`)。 |
| `includeExamples` | `n` | 包括 [元件庫](https://www.aemcomponents.dev/) 示例站點(可以 `y`或 `n`)。 |
| `includeErrorHandler` | `n` | 包括將對整個實例全局的自定義404響應頁(可以是 `y` 或 `n`)。 |
| `includeCommerce` | `n` | 包括 [CIF核心元件](https://github.com/adobe/aem-core-cif-components) 依賴項並生成相應的偽像。 |
| `commerceEndpoint` |  | 僅CIF必需。 要使用的商業系統GraphQL服務的可選端點(例如 `https://hostname.com/grapql`)。 |
| `datalayer` | `y` | 激活與 [Adobe客戶端資料層](/help/developing/data-layer/overview.md)。 |
| `amp` | `n` | 啟用 [安培](/help/developing/amp.md) 支援生成的項目模板。 |
| `enableDynamicMedia` | `n` | 在項目策略設定中啟用基礎DynamicMedia元件，並在核心映像元件的策略中激活Dynamic Media功能。 |
| `enableSSR` | `n` | 為前端項目啟用SSR的選項 |
| `precompiledScripts` | `n` | 選項 [預編](/help/developing/archetype/precompiled-bundled-scripts.md) 伺服器端指令碼 `ui.apps` 並將它們作為次捆綁對象連接到 `ui.apps` 項目。 `aemVersion` 應設定為 `cloud`。 |

>[!NOTE]
>
> 如果首次在交互模式下執行原型，則不能更改具有預設值的屬性(請參見 [原型308](https://issues.apache.org/jira/browse/ARCHETYPE-308) )的正平方根。 當結束處的屬性確認被拒絕且調查表重複時，或通過在命令行中傳遞參數(例如， `-DoptionIncludeExamples=n`)。

>[!NOTE]
>
>在Windows上運行並生成調度程式配置時，應在提升的命令提示符或Windows Subsystem for Linux中運行(請參見 [第329期](https://github.com/adobe/aem-project-archetype/issues/329))。

### 設定檔 {#profiles}

運行時生成的主項目支援不同的部署配置檔案 `mvn install`。

| 配置檔案ID | 說明 |
| --------------------------|------------------------------|
| `autoInstallBundle` | 將帶有maven-sling-plugin的核心捆綁包安裝到felix控制台 |
| `autoInstallPackage` | 將包含content-package-maven-plugin的ui.content和ui.apps內容包安裝到包管理器，以在localhost埠4502上預設作者實例。 可以使用 `aem.host` 和 `aem.port` 用戶定義的屬性。 |
| `autoInstallPackagePublish` | 將包含content-package-maven-plugin的ui.content和ui.apps內容包安裝到包管理器，以在localhost（埠4503）上預設發佈實例。 可以使用 `aem.host` 和 `aem.port` 用戶定義的屬性。 |
| `autoInstallSinglePackage` | 安裝 `all` 內容包，內容包包含內容包 — maven-plugin，可以添加到包管理器，以預設本地主機上的作者實例，埠4502。 可以使用 `aem.host` 和 `aem.port` 用戶定義的屬性。 |
| `autoInstallSinglePackagePublish` | 安裝 `all` 內容包，內容包包含內容包 — maven-plugin，可以添加到包管理器，以預設在localhost上發佈實例，埠4503。 可以使用 `aem.host` 和 `aem.port` 用戶定義的屬性。 |
| `integrationTests` | 在實例上運行提供的集AEM成test(僅適用於 `verify` 相位) |
| `precompiledScripts` | 在生成項目時自動定義 `precompiledScripts` 屬性設定為 `y`。 預設情況下，配置檔案處於活動狀態，並在內部生成OSGi束 `ui.apps` 預編譯的指令碼，這些指令碼將包含在 `all` 內容包。 配置式可通過 `-DskipScriptPrecompilation=true`。 |

### 構建和安裝 {#building-and-installing}

要生成在項目根目錄中運行的所有模組，請使用以下Maven命令。

```shell
mvn clean install
```

如果有正在運行的AEM實例，則可以生成並打包整個項目，然後使用以AEM下Maven命令進行部署。

```shell
mvn clean install -PautoInstallPackage
```

要將其部署到發佈實例，請運行此命令。

```shell
mvn clean install -PautoInstallPackagePublish
```

或者，要部署到發佈實例，請運行此命令。

```shell
mvn clean install -PautoInstallPackage -Daem.port=4503
```

或者，要僅將捆綁包部署到作者，請運行此命令。

```shell
mvn clean install -PautoInstallBundle
```

## 父POM {#parent-pom}

的 `pom.xml` 項目根(`<src-directory>/<project>/pom.xml`)稱為父POM，驅動項目的結構，並管理項目的依賴關係和某些全局屬性。

### 全局項目屬性 {#global-properties}

的 `<properties>` 父POM的部分定義了幾個對在實例上部署項目非常重要的全局屬AEM性，如用戶名/密碼、主機名/埠等。

這些屬性設定為部署到本地實AEM例，因為這是開發人員將執行的最常見的生成。 請注意，存在要部署到作者實例和發佈實例的屬性。 這也是將憑據設定為向實例進行身份驗證的AEM地方。 使用預設admin:admin憑據。

設定這些屬性，以便在部署到更高級別環境時可以覆蓋這些屬性。 這樣，POM檔案就不必更改，而是變數，如 `aem.host` 和 `sling.password` 可通過命令行參數覆蓋：

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模組結構 {#module-structure}

的 `<modules>` 父POM的部分定義項目將構建的模組。 預設情況下，項目生成 [先前定義的標準模組](#what-you-get):core、ui.apps、ui.content、ui.test和it.launcher。 隨著項目的發展，始終可以添加更多模組。

### 相依性 {#dependencies}

的 `<dependencyManagement>` 父POM的部分定義項目中使用的所有依賴項和API版本。 應在父POM中管理版本。 core和ui.apps等子模組不應包含任何版本資訊。

#### 優步 — 賈爾 {#uber-jar}

關鍵依賴項之一是 [AEMJava API Jar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)。 這將包括所有API,AEM只有版本的一個依賴項AEM。

>[!NOTE]
>
>作為最佳做法，您應更新uber-jar版本以與的目標版本相AEM匹配。 例如，如果您計畫部署到AEM6.4，則應將uber-jar的版本更新為6.4.0。

#### 核心元件 {#core-components}

本課AEM程的「項目原型」利用了「核心元件」。

核心元件以預設運行AEM模式自動安裝，並由示例WKND站點使用。 在 [生產運行模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#runmodes) (`nosamplecontent`)核心元件不可用。

因此，為了在所有部署中利用核心元件，最好將其納入Maven項目。

>[!NOTE]
>
>每個核心元件版本通常隨後都會發佈項目原型AEM，以便最新原型使用最新版本的核心元件。
>
>但是，新版本的原型可能不會直接跟隨新版本的核心元件，因此您可能希望將對核心元件的依賴性更新為最新版本。

>[!NOTE]
>
>core.wcm.components.examples是一組示例頁，用於說明核心元件的示例。 作為最佳做法，在為生產用途部署項目時，應刪除此依賴項和子包包含。

## 測試 {#testing}

項目中包含三個級別的測試，由於它們是不同類型的test，因此它們以不同的方式或在不同的位置執行。

* 核心單元test:這展示了捆綁包中包含的代碼的經典單元測試。 要test，請執行：
   * `mvn clean test`
* 伺服器端整合test:這些test在環AEM境（即在伺服器上）中運AEM行。 要test，請執行：
   * `mvn clean verify -PintegrationTests`
* 客戶端Hobbes.jstest:這些是基於JavaScript的瀏覽器端test，用於驗證瀏覽器端行為。 test:
   1. 在AEM瀏覽器中載入，就像您編寫頁面一樣。
   1. 在中開啟頁面 [開發人員模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/developer-mode.html)
   1. 開啟左面板並切換到 **Test** 頁籤。
   1. 查找生成的 **MyNameTest** 然後跑。

## 後續步驟 {#next-steps}

所以你建造並安裝了AEMProject Archetype。 現在怎麼辦？ 原型很小，但是包含許多根據推薦的最佳實踐AEM配置的強大功能示例。 使用這些功能可以說明如何在項目中利用這些功能。 對於您可能需要的任何項目：

* [通過擴展現有核心元件來定制元件](/help/developing/customizing.md)
* [添加其他模板](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [適應本地化結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html)
* [瞭解前端生成模組](uifrontend.md)
