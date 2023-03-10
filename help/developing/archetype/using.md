---
title: 使用AEM專案原型
description: AEM專案原型的詳細使用指示
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: ca61d71a2644465e74249058157d8dea2aa71352
workflow-type: tm+mt
source-wordcount: '2198'
ht-degree: 2%

---

# AEM 專案原型 {#aem-project-archetype}

AEM專案原型會建立基於最佳實務的簡化Adobe Experience Manager專案，作為您專屬AEM專案的起點。 使用此原型時必須提供的屬性可讓您指定此專案所有部分的名稱，並控制某些選用功能。

## 為何使用原型 {#why-use-the-archetype}

使用AEM專案原型，只需按幾下鍵，即可建立以最佳實務為基礎的AEM專案。 透過使用原型，所有片段都已就緒，因此雖然產生的專案最少，但已實作所有 [主要功能](#what-you-get) 讓您只需在頂端建置並延伸即可。

當然，有許多元素會進入成功的AEM專案，但使用AEM專案原型是堅實的基礎，且強烈建議用於任何AEM專案。

## 快速入門 {#getting-started}

專案原型可讓您輕鬆開始在AEM上開發。 您可以透過多種方式執行您的第一步。

* WKND教學課程 — 如需AEM開發的絕佳簡介，包括如何運用原型，請參閱 [AEM Sites快速入門 — WKND教學課程](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hant) 此範例會逐步帶您了解如何使用原型來實作簡單的專案。
* WKND事件教學課程 — 如果您對AEM上的單頁應用程式(SPA)開發特別感興趣，請務必結帳 [WKND Events教學課程](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html).
* 自行下載並開始！  — 您可以輕鬆下載GitHub上提供的目前專案原型，並透過 [請依照下列步驟進行](#how-to-use-the-archetype).

## 原型的使用 {#what-you-get}

AEM原型由模組組成：

* **[核心](core.md)**:是Java套件，其中包含所有核心功能，例如OSGi服務、接聽程式和排程程式，以及元件相關的Java程式碼，例如servlet和請求篩選器。
* **[it.tests](ittests.md)**:是Java型整合測試。
* **[ui.apps](uiapps.md)**:包含 `/apps` 和 `/etc` 專案的一部分，例如JS和CSSclientlib、元件和範本。
* **[ui.content](uicontent.md)**:包含使用ui.apps模組中元件的範例內容。
* **ui.config**:包含專案的執行模式專屬OSGi設定。
* **[ui.frontend.general](uifrontend.md)**: **（可選）** 包含使用基於Webpack的常規前端生成模組所需的成品。
* **[ui.frontend.react](uifrontend-react.md)**: **（可選）** 包含使用原型根據React建立SPA專案時所需的成品。
* **[ui.frontend.angular](uifrontend-angular.md)**: **（可選）** 包含使用原型根據Angular建立SPA專案時所需的成品。
* **[ui.tests](uitests.md)**:包含基於硒的UI測試。
* **all**:是單一內容包，它嵌入所有已編譯模組（包和內容包），包括任何供應商依賴項。
* **分析**:在專案上執行分析，這可提供部署至AEM as a Cloud Service的其他驗證。

![](/help/assets/archetype-structure.png)

Maven中呈現的AEM原型模組會部署至AEM，作為代表應用程式、內容和必要OSGi套件組合的內容套件。

## 如何使用原型 {#how-to-use-the-archetype}

若要使用原型，您必須先建立專案，由專案以本機檔案結構產生模組為 [先前描述的](#what-you-get). 在產生專案時，可以定義專案的許多屬性，例如專案名稱、版本等。

使用Maven建立專案會建立可部署至AEM的成品（套件和OSGi套件組合）。 其他Maven命令和設定檔可用來將專案成品部署至AEM執行個體。

### 建立專案 {#create-project}

若要開始使用，您最簡單的方式是 [AEM Eclipse擴充功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/eclipse.html?lang=zh-Hant) 並按照「新建項目」嚮導選擇 **AEM範例多模組專案** 來使用原型的發行版本。

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

* 設定 `XX` 到 [版本編號](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md) 最新AEM專案原型。
* 設定 `aemVersion=cloud` for [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html);\
   設定 `aemVersion=6.5.0` for [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)，或內部部署。
僅會針對非雲端aem版本新增核心元件相依性，因為核心元件是針對AEMas a Cloud Service而提供的OOTB。
* 調整 `appTitle="My Site"` 定義網站標題和元件群組。
* 調整 `appId="mysite"` 要定義Maven工件Id、元件、配置和內容資料夾名稱以及客戶端庫名稱。
* 調整 `groupId="com.mysite"` 來定義Maven groupId和Java源包。
* 查詢可用屬性清單，查看是否有其他需要調整的項目。

>[!NOTE]
>
>最佳實務是新增 `adobe-public` 給您的Maven的個人資料 `settings.xml` 檔案，以自動將repo.adobe.com新增至maven建置程式。
>
>範例POM [可在此處找到](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-17454.html?lang=en).

### 屬性 {#properties}

使用原型建立專案時，可使用下列屬性。

| 名稱 | 預設 | 說明 |
|---------------------------|----------------|--------------------|
| `appTitle` |  | 應用程式標題將用於網站標題和元件群組(例如 `"My Site"`)。 |
| `appId` |  | 技術名稱將用於元件、設定和內容資料夾名稱，以及用戶端程式庫名稱(例如 `"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基Maven工件ID(例如 `"mysite"`)。 |
| `groupId` |  | 基本Maven群組ID(例如 `"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java源包(例如 `"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 專案版本(例如 `1.0-SNAPSHOT`)。 |
| `aemVersion` | `cloud` | Target AEM版本(可以 `cloud` for [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html);或 `6.5.0`，或 `6.4.4` for [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或內部部署)。 |
| `sdkVersion` | `latest` | 當 `aemVersion=cloud` an [SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) 可指定版本(例如 `2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 包含雲端或AMS/內部部署的Dispatcher設定，視 `aemVersion` (可以 `y` 或 `n`)。 |
| `frontendModule` | `general` | 包含Webpack前端建置模組，用於產生用戶端程式庫(可以 `general` 或 `none` （二）固定場所；可以 `angular` 或 `react` 適用於實作 [SPA Editor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/editor-overview.html))。 |
| `language` | `en` | 語言代碼(ISO 639-1)，以從(例如 `en`, `deu`)。 |
| `country` | `us` | 國家/地區代碼(ISO 3166-1)，以從(例如 `US`)。 |
| `singleCountry` | `y` | 包含語言主版內容結構(可以 `y`，或 `n`)。 |
| `includeExamples` | `n` | 包括 [元件庫](https://www.aemcomponents.dev/) 網站範例(可 `y`，或 `n`)。 |
| `includeErrorHandler` | `n` | 包含對整個執行個體具有全域性的自訂404回應頁面(可以是 `y` 或 `n`)。 |
| `includeCommerce` | `n` | 包含 [CIF核心元件](https://github.com/adobe/aem-core-cif-components) 相依性並產生對應的成品。 |
| `commerceEndpoint` |  | 僅CIF為必要。 要使用的商務系統GraphQL服務的選用端點(例如 `https://hostname.com/grapql`)。 |
| `datalayer` | `y` | 啟用與的整合 [Adobe用戶端資料層](/help/developing/data-layer/overview.md). |
| `amp` | `n` | 啟用 [AMP](/help/developing/amp.md) 支援產生的專案範本。 |
| `enableDynamicMedia` | `n` | 在專案原則設定中啟用基礎DynamicMedia元件，並在核心影像元件的原則中啟用Dynamic Media功能。 |
| `enableSSR` | `n` | 為前端項目啟用SSR的選項 |
| `precompiledScripts` | `n` | 選項 [預編譯](/help/developing/archetype/precompiled-bundled-scripts.md) 來自 `ui.apps` 並將它們作為輔助捆綁對象附加到組建中 `ui.apps` 專案。 `aemVersion` 應設為 `cloud`. |

>[!NOTE]
>
> 如果原型是第一次在互動式模式中執行，則無法變更具有預設值的屬性(請參閱 [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) 如需詳細資訊)。 當最終的屬性確認被拒絕且調查表重複時，或通過在命令行中傳遞參數(例如， `-DoptionIncludeExamples=n`)。

>[!NOTE]
>
>在Windows上執行並產生調度程式配置時，您應在提升的命令提示字元或Linux適用的Windows子系統中執行(請參閱 [第329期](https://github.com/adobe/aem-project-archetype/issues/329))。

### 設定檔 {#profiles}

運行時，生成的Maven項目支援不同的部署配置檔案 `mvn install`.

| 設定檔ID | 說明 |
| --------------------------|------------------------------|
| `autoInstallBundle` | 將核心套件搭配maven-sling-plugin安裝至felix主控台 |
| `autoInstallPackage` | 將ui.content和ui.apps內容套件（內容套件 — maven-plugin）安裝至套件管理器，以在localhost，連接埠4502上安裝預設製作例項。 主機名和埠可以使用 `aem.host` 和 `aem.port` 用戶定義的屬性。 |
| `autoInstallPackagePublish` | 將ui.content和ui.apps內容套件（內容套件 — maven-plugin）安裝至套件管理器，以在localhost，連接埠4503上預設發佈執行個體。 主機名和埠可以使用 `aem.host` 和 `aem.port` 用戶定義的屬性。 |
| `autoInstallSinglePackage` | 安裝 `all` 內容套件（連接埠4502），內容套件（連接至content-package-maven-plugin）會連接至套件管理器（連接至localhost上的預設製作例項）。 主機名和埠可以使用 `aem.host` 和 `aem.port` 用戶定義的屬性。 |
| `autoInstallSinglePackagePublish` | 安裝 `all` 內容套件（內容套件包含content-package-maven-plugin），會載入套件管理器，以在localhost，連接埠4503上預設發佈執行個體。 主機名和埠可以使用 `aem.host` 和 `aem.port` 用戶定義的屬性。 |
| `integrationTests` | 在AEM例項上執行提供的整合測試(僅適用於 `verify` 相) |
| `precompiledScripts` | 在專案產生時使用 `precompiledScripts` 屬性設定為 `y`. 預設情況下，配置檔案處於活動狀態，並在內部生成OSGi捆綁 `ui.apps` 與預編譯的指令碼，這些指令碼將包含在 `all` 內容套件。 設定檔可透過 `-DskipScriptPrecompilation=true`. |

### 建置和安裝 {#building-and-installing}

要生成在項目根目錄中運行的所有模組，請使用以下Maven命令。

```shell
mvn clean install
```

如果您有執行中的AEM執行個體，則可以建置並封裝整個專案，並使用下列Maven命令部署至AEM。

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

或者，若只要將套件部署至作者，請執行此命令。

```shell
mvn clean install -PautoInstallBundle
```

## 父POM {#parent-pom}

此 `pom.xml` 位於專案的根(`<src-directory>/<project>/pom.xml`)稱為父POM，可驅動專案的結構，並管理相依性和專案的特定全域屬性。

### 全局項目屬性 {#global-properties}

此 `<properties>` 上層POM的區段定義了數個對於在AEM例項上部署專案很重要的全域屬性，例如使用者名稱/密碼、主機名稱/連接埠等。

這些屬性設定為部署至本機AEM例項，因為這是開發人員最常做的組建。 請注意，有些屬性可部署至製作執行個體和發佈執行個體。 這也是設定憑證以透過AEM例項驗證的地方。 會使用預設管理員：管理員憑證。

設定這些屬性，以便在部署到更高級別環境時可以覆蓋這些屬性。 如此一來，POM檔案就不必變更，而是變數，例如 `aem.host` 和 `sling.password` 可以通過命令行參數來覆蓋：

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模組結構 {#module-structure}

此 `<modules>` 父POM的區段會定義專案將建置的模組。 依預設，專案組建 [先前定義的標準模組](#what-you-get):核心、ui.apps、ui.content、ui.tests和it.launcher。 隨著專案的發展，您隨時都可以新增更多模組。

### 相依性 {#dependencies}

此 `<dependencyManagement>` 上層POM的區段會定義專案中使用的所有相依性和API版本。 版本應在父POM中管理。 核心和ui.apps等子模組不應包含任何版本資訊。

#### Uber-Jar {#uber-jar}

其中一項關鍵相依性為 [AEM Java API Jar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html). 這會包含所有AEM API，其中只包含AEM版本的單一相依性項目。

>[!NOTE]
>
>最佳實務是，您應更新uber-jar版本以符合AEM的目標版本。 例如，如果您打算部署至AEM 6.4，則應將uber-jar的版本更新至6.4.0。

#### 核心元件 {#core-components}

AEM專案原型當然會運用核心元件。

核心元件會以預設執行模式自動安裝於AEM中，並供範例WKND網站使用。 在 [生產執行模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#runmodes) (`nosamplecontent`)無法使用核心元件。

因此，若要在所有部署中運用核心元件，最好將其納入Maven專案。

>[!NOTE]
>
>核心元件的每個版本通常之後都會有AEM專案原型的版本，這樣最新的原型就會使用核心元件的最新版本。
>
>不過，新版本的原型可能不會直接遵循新版本的核心元件，因此您可能會想要將核心元件的相依性更新為最新版本。

>[!NOTE]
>
>core.wcm.components.examples是一組範例頁面，說明核心元件的範例。 作為最佳實務，為生產用途部署專案時，您應移除此相依性和子套件包含。

## 測試 {#testing}

專案中包含三個層級的測試，且由於它們是不同類型的測試，因此會以不同的方式或在不同的位置執行。

* 核心單元測試：這可展示套件中程式碼的傳統單元測試。 要測試，請執行：
   * `mvn clean test`
* 伺服器端整合測試：這些會在AEM環境(即AEM伺服器)中執行類似單元的測試。 要測試，請執行：
   * `mvn clean verify -PintegrationTests`
* 用戶端Hobbes.js測試：這些是以JavaScript為基礎的瀏覽器端測試，可驗證瀏覽器端行為。 要測試：
   1. 在瀏覽器中載入AEM，如同您要編寫頁面一樣。
   1. 在中開啟頁面 [開發人員模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/developer-mode.html)
   1. 開啟左側面板，然後切換至 **測試** 標籤。
   1. 尋找產生的 **MyName測試** 然後運行它們。

## 後續步驟 {#next-steps}

因此，您已建立並安裝AEM專案原型。 現在呢？ 原型很小，但包含許多根據建議最佳實務設定的強大AEM功能範例。 使用這些說明如何在專案中運用這些功能。 針對您可能需要的任何專案：

* [透過擴充現有核心元件來自訂元件](/help/developing/customizing.md)
* [新增其他範本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [調整本地化結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html)
* [了解前端組建模組](uifrontend.md)
