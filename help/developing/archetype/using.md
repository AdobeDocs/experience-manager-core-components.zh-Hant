---
title: 使用AEM專案原型
description: AEM專案原型的詳細使用指示
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: e0dff3b15c9637292eb2bb89836215afc0fcf8f9
workflow-type: tm+mt
source-wordcount: '2201'
ht-degree: 2%

---

# AEM 專案原型 {#aem-project-archetype}

AEM專案原型會建立依最佳作法為基礎所簡化的Adobe Experience Manager專案，作為您專屬AEM專案的開端。 使用此原型時必須提供的屬性可讓您指定此專案所有部分的名稱，以及控制某些選擇性功能。

## 為何使用原型 {#why-use-the-archetype}

使用AEM專案原型，您只需按幾下滑鼠，即可建立以最佳實務為基礎的AEM專案。 使用原型時，所有片段都已準備就緒，因此雖然產生的專案最小，但已實施所有 [主要功能](#what-you-get) AEM的URL編號，因此您只需要在上方建置並延伸。

當然，成功的AEM專案涉及許多元素，但使用AEM專案原型是堅實的基礎，強烈建議對任何AEM專案使用。

## 快速入門 {#getting-started}

專案原型可讓您在AEM上輕鬆開始開發。 您可以透過多種方式邁出第一步。

* WKND教學課程 — 如需在AEM上進行開發的詳細介紹，包括如何運用原型，請參閱 [AEM Sites - WKND教學課程快速入門](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hant) 此實用範例將逐步說明如何使用原型來實作簡單專案。
* WKND事件教學課程 — 如果您特別想知道如何在AEM上開發單頁應用程式(SPA)，請務必檢視專屬的 [WKND事件教學課程](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html).
* 自行下載並開始使用！  — 您可以輕鬆下載GitHub上可用的目前專案原型，並透過以下方式建立您的第一個專案 [請依照下列簡單步驟操作](#how-to-use-the-archetype).

## 使用原型的好處 {#what-you-get}

AEM原型由模組組成：

* **[核心](core.md)**：此Java套件組合包含所有核心功能（例如OSGi服務、監聽器和排程器）以及與元件相關的Java程式碼（例如servlet和請求篩選器）。
* **[it.tests](ittests.md)**：是以Java為基礎的整合測試。
* **[ui.apps](uiapps.md)**：包含 `/apps` 和 `/etc` 專案的一部分，即JS和CSS clientlibs、元件和範本。
* **[ui.content](uicontent.md)**：包含使用ui.apps模組元件的範例內容。
* **ui.config**：包含專案的執行模式專用OSGi設定。
* **[ui.frontend.general](uifrontend.md)**： **（選擇性）** 包含使用一般Webpack型前端建置模組所需的成品。
* **[ui.frontend.react](uifrontend-react.md)**： **（選擇性）** 包含使用原型根據React建立SPA專案時所需的成品。
* **[ui.frontend.angular](uifrontend-angular.md)**： **（選擇性）** 包含使用原型根據Angular建立SPA專案時所需的成品。
* **[ui.tests](uitests.md)**：包含以Selenium為基礎的UI測試。
* **全部**：是單一內容套件，內嵌所有已編譯的模組（套件組合和內容套件），包括任何廠商相依性。
* **分析**：對專案執行分析，這為部署至AEMas a Cloud Service提供額外的驗證。

![內容封裝組織](/help/assets/content-package-organization.png)

Maven中表示的AEM原型模組會部署到AEM，作為代表應用程式、內容和必要OSGi套裝的內容套件。

## 如何使用原型 {#how-to-use-the-archetype}

若要使用原型，您首先需要建立一個專案，該專案會在本機檔案結構中產生模組，如下所示 [先前已說明](#what-you-get). 作為專案產生的一部分，可以定義專案的一些屬性，例如專案名稱、版本等。

使用Maven建置專案會建立可部署至AEM的成品（套件和OSGi套件組合）。 其他Maven命令和設定檔可用於將專案成品部署到AEM執行個體。

### 建立專案 {#create-project}

若要開始使用，您只需使用 [AEM Eclipse擴充功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/eclipse.html?lang=zh-Hant) 並依照新增專案精靈的指示選擇 **AEM範例多模組專案** 以使用原型的發行版本。

當然，您也可以直接叫用Maven。

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

* 設定 `XX` 至 [版本號碼](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md) 最新AEM專案原型的。
* 設定 `aemVersion=cloud` 的 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html)；\
  設定 `aemVersion=6.5.0` 的 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署。
僅針對非雲端AEM版本新增核心元件相依性，因為核心元件是針對AEMas a Cloud Service提供的OOTB。
* 調整 `appTitle="My Site"` 以定義網站標題和元件群組。
* 調整 `appId="mysite"` 以定義Maven artifactId、元件、設定和內容資料夾名稱以及使用者端資料庫名稱。
* 調整 `groupId="com.mysite"` 以定義Maven groupId和Java來源套件。
* 查詢可用屬性清單，檢視是否有更多要調整的內容。

>[!NOTE]
>
>最佳實務是新增 `adobe-public` 您的Maven設定檔 `settings.xml` 以將repo.adobe.com自動新增至maven建置流程。
>
>範例POM [可在此處找到](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-17454.html?lang=en).

### 屬性 {#properties}

使用原型建立專案時，可使用下列屬性。

| 名稱 | 預設 | 說明 |
|---------------------------|----------------|--------------------|
| `appTitle` |                | 應用程式標題，將用於網站標題和元件群組(例如 `"My Site"`)。 |
| `appId` |                | 技術名稱，將用於元件、設定和內容資料夾名稱，以及使用者端資料庫名稱(例如 `"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基礎Maven成品ID (例如 `"mysite"`)。 |
| `groupId` |                | 基礎Maven群組ID (例如 `"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java來源套件(例如 `"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 專案版本(例如 `1.0-SNAPSHOT`)。 |
| `aemVersion` | `cloud` | 目標AEM版本(可以 `cloud` 的 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html)；或 `6.5.0`，或 `6.4.4` 的 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或內部部署)。 |
| `sdkVersion` | `latest` | 時間 `aemVersion=cloud` 一個 [SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) 可以指定版本(例如 `2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 包括用於雲端或AMS/內部部署的Dispatcher設定，具體取決於的值 `aemVersion` (可以是 `y` 或 `n`)。 |
| `frontendModule` | `general` | 包含可產生使用者端程式庫的Webpack前端組建模組(可以 `general` 或 `none` 用於一般網站；可以是 `angular` 或 `react` 實作的單頁應用程式 [SPA編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/editor-overview.html))。 |
| `language` | `en` | 用來建立內容結構的語言代碼(ISO 639-1)，例如 `en`， `deu`)。 |
| `country` | `us` | 從中建立內容結構的國家/地區代碼(ISO 3166-1) (例如： `US`)。 |
| `singleCountry` | `y` | 包含語言主導的內容結構(可以 `y`，或 `n`)。 |
| `includeExamples` | `n` | 包含 [元件資料庫](https://www.aemcomponents.dev/) 網站範例(可以是 `y`，或 `n`)。 |
| `includeErrorHandler` | `n` | 包含自訂404回應頁面，此頁面將為整個執行個體的全域頁面(可以 `y` 或 `n`)。 |
| `includeCommerce` | `n` | 包含 [CIF核心元件](https://github.com/adobe/aem-core-cif-components) 相依性並產生對應的成品。 |
| `commerceEndpoint` |                | 僅對於CIF為必要。 要使用的商務系統GraphQL服務的選用端點(例如 `https://hostname.com/grapql`)。 |
| `datalayer` | `y` | 啟用與的整合 [Adobe使用者端資料層](/help/developing/data-layer/overview.md). |
| `amp` | `n` | 啟用 [AMP](/help/developing/amp.md) 支援產生的專案範本。 |
| `enableDynamicMedia` | `n` | 在專案原則設定中啟用基礎DynamicMedia元件，並在核心影像元件原則中啟用Dynamic Media功能。 |
| `enableSSR` | `n` | 為前端專案啟用SSR的選項 |
| `precompiledScripts` | `n` | 選項至 [預先編譯](/help/developing/archetype/precompiled-bundled-scripts.md) 來自的伺服器端指令碼 `ui.apps` 並將它們附加至組建作為中的次要束成品 `ui.apps` 專案。 `aemVersion` 應設為 `cloud`. |

>[!NOTE]
>
> 如果原型第一次在互動模式中執行，則無法變更具有預設值的屬性(請參閱 [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) 以取得詳細資訊)。 如果最後的屬性確認被拒絕且調查表重複，或在命令列中傳遞引數(例如 `-DoptionIncludeExamples=n`)。

>[!NOTE]
>
>在Windows上執行並產生Dispatcher設定時，您應在提升許可權的命令提示字元或適用於Linux的Windows子系統中執行(請參閱 [第329期](https://github.com/adobe/aem-project-archetype/issues/329))。

### 設定檔 {#profiles}

執行時，產生的maven專案支援不同的部署設定檔 `mvn install`.

| 設定檔ID | 說明 |
| --------------------------|------------------------------|
| `autoInstallBundle` | 將包含maven-sling-plugin的核心套件組合安裝至felix主控台 |
| `autoInstallPackage` | 將包含content-package-maven-plugin的ui.content和ui.apps內容套件安裝到套件管理員上的localhost預設作者執行個體（連線埠4502）。 可使用變更主機名稱和連線埠 `aem.host` 和 `aem.port` 使用者定義的屬性。 |
| `autoInstallPackagePublish` | 將包含content-package-maven-plugin的ui.content和ui.apps內容套件安裝到封裝管理員，以在localhost上預設發佈執行個體，連線埠4503。 可使用變更主機名稱和連線埠 `aem.host` 和 `aem.port` 使用者定義的屬性。 |
| `autoInstallSinglePackage` | 安裝 `all` 將包含content-package-maven-plugin的內容套件透過封裝管理員新增至localhost上的預設製作執行個體（連線埠4502）。 可使用變更主機名稱和連線埠 `aem.host` 和 `aem.port` 使用者定義的屬性。 |
| `autoInstallSinglePackagePublish` | 安裝 `all` 將具有content-package-maven-plugin的內容封裝到封裝管理員，以在localhost上預設發佈執行個體，連線埠4503。 可使用變更主機名稱和連線埠 `aem.host` 和 `aem.port` 使用者定義的屬性。 |
| `integrationTests` | 在AEM執行個體上執行提供的整合測試(僅針對 `verify` 階段) |
| `precompiledScripts` | 使用產生專案時自動定義 `precompiledScripts` 屬性設定為 `y`. 設定檔預設為作用中，並在其中產生OSGi套件組合 `ui.apps` 以及預先編譯的指令碼，這些指令碼將包含在 `all` 內容封裝。 設定檔可透過以下方式停用 `-DskipScriptPrecompilation=true`. |

### 建置和安裝 {#building-and-installing}

若要建置在專案根目錄中執行的所有模組，請使用以下Maven命令。

```shell
mvn clean install
```

如果您有正在執行的AEM執行個體，您可以建置並封裝整個專案，並使用以下Maven命令部署到AEM中。

```shell
mvn clean install -PautoInstallPackage
```

若要將其部署到發佈執行個體，請執行此命令。

```shell
mvn clean install -PautoInstallPackagePublish
```

或者，若要部署到發佈執行個體，請執行此命令。

```shell
mvn clean install -PautoInstallPackage -Daem.port=4503
```

或者，若要僅將套件組合部署至作者，請執行此命令。

```shell
mvn clean install -PautoInstallBundle
```

## 父級POM {#parent-pom}

此 `pom.xml` 在專案的根目錄(`<src-directory>/<project>/pom.xml`)稱為上層POM，可驅動專案結構並管理專案的相依性和某些全域屬性。

### 全域專案屬性 {#global-properties}

此 `<properties>` 上層POM的區段會定義在AEM執行個體上部署專案所必需的幾個全域屬性，例如使用者名稱/密碼、主機名稱/連線埠等。

這些屬性設定為部署至本機AEM執行個體，因為這是開發人員最常進行的建置。 請注意，有一些屬性要部署至作者執行個體以及發佈執行個體。 這也是認證設定為使用AEM執行個體進行驗證的地方。 使用預設的admin：admin憑證。

設定這些屬性以便在部署到更高級別的環境時可以覆寫它們。 如此一來，POM檔案就不需要變更，變數如下 `aem.host` 和 `sling.password` 可透過命令列引數覆寫：

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模組結構 {#module-structure}

此 `<modules>` 上層POM的區段會定義專案將建立的模組。 預設會建置專案 [先前定義的標準模組](#what-you-get)： core、ui.apps、ui.content、ui.tests和it.launcher。 隨著專案發展，永遠可以新增更多模組。

### 相依性 {#dependencies}

此 `<dependencyManagement>` 上層POM的區段會定義專案中使用的API的所有相依性和版本。 應在父級POM中管理版本。 core和ui.apps之類的子模組不應包含任何版本資訊。

#### Uber-Jar {#uber-jar}

主要相依性之一是 [AEM Java API Jar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html). 這將包括所有AEM API，而AEM版本只有一個相依性專案。

>[!NOTE]
>
>最佳實務是更新uber-jar版本以符合AEM的目標版本。 例如，如果您計畫部署到AEM 6.4，您應該將uber-jar的版本更新為6.4.0。

#### 核心元件 {#core-components}

AEM專案原型當然會運用核心元件。

核心元件會在預設執行模式下自動安裝在AEM中，並由範例WKND網站使用。 在 [生產執行模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#runmodes) (`nosamplecontent`)核心元件無法使用。

因此，若要在所有部署中運用核心元件，最佳實務是將它們納入Maven專案。

>[!NOTE]
>
>核心元件的每個版本通常都會緊接著AEM專案原型版本，以便最新的原型使用最新版本的核心元件。
>
>不過，原型的新版本可能不會直接緊隨核心元件的新版本，因此您可能希望將核心元件的相依性更新至最新版本。

>[!NOTE]
>
>core.wcm.components.examples是一組範例頁面，說明核心元件的範例。 最佳實務是，在部署專案以供生產使用時，您應移除此相依性和子套件包含。

## 測試 {#testing}

專案中包含三個層級的測試，由於測試型別不同，因此會以不同方式或在不同位置執行。

* core中的單元測試：此測試會示範套件組合中包含之程式碼的典型單元測試。 若要測試，請執行：
   * `mvn clean test`
* 伺服器端整合測試：這些會在AEM環境中(亦即AEM伺服器上)執行單元測試。 若要測試，請執行：
   * `mvn clean verify -PintegrationTests`
* 使用者端Hobbes.js測試：這些是驗證瀏覽器端行為的JavaScript瀏覽器端測試。 若要測試：
   1. 在瀏覽器中載入AEM，就像編寫頁面一樣。
   1. 在中開啟頁面 [開發人員模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/developer-mode.html)
   1. 開啟左側面板並切換至 **測試** 標籤。
   1. 尋找產生的 **MyName測試** 並執行它們。

## 後續步驟 {#next-steps}

因此您已建置並安裝AEM專案原型。 現在該怎麼辦？ 雖然原型很小，但包含許多根據建議最佳實務設定的強大AEM功能範例。 這些範本可指示您如何在專案中利用這些功能。 對於任何專案，您可能需要：

* [透過擴充現有核心元件來自訂元件](/help/developing/customizing.md)
* [新增其他範本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [調整本地化結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html)
* [瞭解前端建置模組](uifrontend.md)
