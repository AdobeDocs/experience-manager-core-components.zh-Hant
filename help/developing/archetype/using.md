---
title: 使用專AEM案原型
description: 專案原型的詳細使AEM用指示
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '2072'
ht-degree: 1%

---


# AEM 專案原型 {#aem-project-archetype}

Project AEM Archetype會建立以最佳實務為基礎的最簡化Adobe Experience Manager專案，做為您自己專案的起AEM點。 使用此原型時必須提供的屬性允許您指定此項目所有部分的名稱，並控制某些可選特徵。

## 為什麼使用原型{#why-use-the-archetype}

使用AEMProject Archetype，您只需按幾下按鍵，就可建立最佳實務AEM專案。 通過使用原型，所有部件都已經到位，這樣，雖然生成的項目是最小的，但它已經實現了[的所有關鍵功能](#what-you-get)AEM，因此您只需在頂部和擴展上構建即可。

當然，有許多元素會進入成功的AEM專案，但使用AEMProject Archetype是穩固的基礎，強烈建議用於任何專AEM案。

## 快速入門 {#getting-started}

項目原型使開發變得容易AEM。 您可以透過多種方式採取第一步。

* WKND教學課程——如需有關開發的絕佳簡介，包括如何運用原型，請參閱[《AEM Sites快速入門》- WKND教學課程](https://docs.adobe.com/content/help/zh-Hant/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)，以取得實用範例，逐步帶您使用原型來實作簡單的專案。
* WKND事件教學課程——如果您對單頁應用程式(SPA)開發特別感興趣AEM，請務必查看專屬的[WKND事件教學課程](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)。
* 自行下載並開始！ -您可以輕鬆下載GitHub上提供的目前專案原型，並依照[以下的簡單步驟建立您的第一個專案。](#how-to-use-the-archetype)

## 使用原型得到什麼{#what-you-get}

原AEM型由模組組成：

* **[核心](core.md)**:是包含所有核心功能（例如OSGi服務、偵聽程式和排程程式），以及元件相關Java程式碼（例如servlet和請求篩選器）的Java套件。
* **[it.tests](ittests.md)**:是Java整合測試。
* **[ui.apps](uiapps.md)**:包含 `/apps` 專 `/etc` 案的和部分，例如JS和CSSclientlibs、元件和範本。
* **[ui.content](uicontent.md)**:包含使用ui.apps模組中元件的範例內容。
* **ui.config**:包含專用於項目的運行模式特定OSGi配置。
* **[ui.frontend.general](uifrontend.md)**: **（可選）** 包含使用一般基於Webpack的前端構建模組所需的對象。
* **[ui.frontend.react](uifrontend-react.md)**: **（可選）** 包含使用原型建立以React為基礎的專案時SPA所需的工件。
* **[ui.frontend.angular](uifrontend-angular.md)**: **（可選）** 包含使用原型建立基於Angular的項SPA目時所需的工件。
* **[ui.tests](uitests.md)**:包含Selenium架構的UI測試。
* **全部**:是內嵌所有已編譯模組（包和內容包）的單一內容包，包括任何供應商相關性。
* **分析**:對專案執行分析，提供將其部署為Cloud Service的AEM額外驗證。

![](/help/assets/archetype-structure.png)

Maven中表示AEM的Archetype模組被部署為表示AEM應用程式、內容和必需的OSGi組合的內容包。

## 如何使用原型{#how-to-use-the-archetype}

要使用原型，首先需要建立項目，該項目將本地檔案結構中的模組生成為[先前描述的](#what-you-get)。 在項目生成過程中，可以定義項目的一些屬性，如項目名稱、版本等。

使用Maven建立專案會建立可部署至的物件（封裝和OSGi組合）AEM。 可以使用其他Maven命令和配置檔案將項目對象部署到實AEM例。

### 建立項目{#create-project}

要開始使用，您最簡單的方式是使用[AEM Eclipse擴充功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/eclipse.html)，然後依照「新增專案」精靈並選擇&#x200B;**AEM Sample Multi-Module Project**&#x200B;來使用已發行版本的原型。

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

* 將`XX`設為最新專案原型的[版本號&lt;a2/AEM>。](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md)
* 將`aemVersion=cloud`的[設AEM置為Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   為[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署設定`aemVersion=6.5.0`。
核心元件相依性僅會針對非雲端版本新增，因為核心元件是以雲端形式提供AEM的OOTB
服務。
* 調整`appTitle="My Site"`以定義網站標題和元件群組。
* 調整`appId="mysite"`以定義Maven artifactId、元件、設定和內容資料夾名稱，以及用戶端程式庫名稱。
* 調整`groupId="com.mysite"`以定義Maven groupId和Java Source Package。
* 查閱可用屬性的清單，查看您是否需要調整更多屬性。

>[!NOTE]
>
>最好將`adobe-public`描述檔新增至Maven `settings.xml`檔案，以便自動將repo.adobe.com新增至maven建置程式。
>
>可在此處找到示例POM [。](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html)

### 屬性 {#properties}

使用原型建立項目時，可使用以下屬性。

| 名稱 | 預設 | 說明 |
--------------------------|----------------|--------------------
| `appTitle` |  | 應用程式標題將用於網站標題和元件群組(例如`"My Site"`)。 |
| `appId` |  | 技術名稱將用於元件、設定和內容資料夾名稱，以及用戶端程式庫名稱(例如`"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基本Maven對象ID(例如`"mysite"`)。 |
| `groupId` |  | 基本Maven群組ID(例如`"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java源包(例如`"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 專案版本(例如`1.0-SNAPSHOT`)。 |
| `aemVersion` | `6.5.0` | 目AEM標版本([可以是`cloud`AEM作為Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);或`6.5.0`，或`6.4.4` for [ Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署)。 |
| `sdkVersion` | `latest` | 當`aemVersion=cloud`[SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)版本可指定時(例如`2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 根據`aemVersion`（可以是`y`或`n`）的值，為雲或AMS/on-premise包含調度器配置。 |
| `frontendModule` | `none` | 包含Webpack前端構建模組，用於生成常規站點的客戶端庫(可以是`general`或`none`;`angular`或`react`是實作[編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/introduction.html)的單頁應SPA用程式的縮圖。 |
| `languageCountry` | `en_us` | 語言和國家／地區程式碼，以建立內容結構(例如`en_us`)。 |
| `singleCountry` | `y` | 包含語言主版內容結構（可以是`y`或`n`）。 |
| `includeExamples` | `y` | 包含[元件庫](https://www.aemcomponents.dev/)範例網站（可以是`y`或`n`）。 |
| `includeErrorHandler` | `n` | 包含自訂404回應頁面，該頁面將會對整個例項產生全域性影響（可以是`y`或`n`）。 |

>[!NOTE]
>
> 如果原型是第一次在互動模式中執行，則無法變更具有預設值的屬性（如需詳細資訊，請參閱[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)）。 當結束時的屬性確認被拒絕且調查表被重複時，或通過在命令行中傳遞參數(例如，`-DoptionIncludeExamples=n`)。

>[!NOTE]
>
>在Windows上運行並生成調度程式配置時，您應在提升的命令提示符或Windows Subsystem for Linux（請參見[期刊329](https://github.com/adobe/aem-project-archetype/issues/329)）中運行。

### 設定檔 {#profiles}

當運行`mvn install`時，生成的Maven項目支援不同的部署配置檔案。

| 描述檔ID | 說明 |
--------------------------|------------------------------
| `autoInstallBundle` | 將內含maven-sling-plugin的核心套件安裝至felix主控台 |
| `autoInstallPackage` | 將ui.content和ui.apps內容套件與content-package-maven-plugin一起安裝至套件管理員，以在localhost，連接埠4502上安裝預設作者例項。 主機名和埠可以使用`aem.host`和`aem.port`用戶定義的屬性進行更改。 |
| `autoInstallPackagePublish` | 將包含content-package-maven-plugin的ui.content和ui.apps內容套件安裝至套件管理員，以在localhost，連接埠4503上預設發佈例項。 主機名和埠可以使用`aem.host`和`aem.port`用戶定義的屬性進行更改。 |
| `autoInstallSinglePackage` | 將內容包與content-package-maven-plugin一起安裝到包管理器，以在localhost, port 4502上安裝預設的作者實例。 `all`主機名和埠可以使用`aem.host`和`aem.port`用戶定義的屬性進行更改。 |
| `autoInstallSinglePackagePublish` | 將包含content-package-maven-plugin的`all`內容套件安裝至封裝管理員，以在localhost, port 4503上預設發佈例項。 主機名和埠可以使用`aem.host`和`aem.port`用戶定義的屬性進行更改。 |
| `integrationTests` | 在實例上運行提供的集AEM成測試（僅適用於`verify`階段） |

### 構建和安裝{#building-and-installing}

要構建在項目根目錄中運行的所有模組，請使用以下Maven命令。

```shell
mvn clean install
```

如果您有執行中的AEM執行中例項，則可以建立並封裝整個專案，並使用下列Maven命AEM令進行部署。

```shell
mvn clean install -PautoInstallPackage
```

若要將它部署至發佈例項，請執行此命令。

```shell
mvn clean install -PautoInstallPackagePublish
```

或者，要部署到發佈實例，請運行此命令。

```shell
mvn clean install -PautoInstallPackage -Daem.port=4503
```

或者，若要只將套件部署至作者，請執行此命令。

```shell
mvn clean install -PautoInstallBundle
```

## 父POM {#parent-pom}

項目(`<src-directory>/<project>/pom.xml`)根部的`pom.xml`稱為父POM，可驅動項目的結構，並管理依賴項和項目的某些全局屬性。

### 全局項目屬性{#global-properties}

父POM的`<properties>`部分定義了對於在實例上部署項目非常重要的幾個全局屬性AEM，如用戶名／口令、主機名／埠等。

這些屬性已設定為部署至本機AEM執行個體，因為這是開發人員最常用的建置。 請注意，有些屬性可部署至作者例項以及發佈例項。 此外，認證也會設定為透過例項進行AEM驗證。 使用預設的admin:admin憑證。

這些屬性已設定好，以便在部署至較高層級的環境時可覆寫。 這樣，POM檔案不必進行更改，但`aem.host`和`sling.password`等變數可以通過命令行參數被覆蓋：

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模組結構{#module-structure}

父POM的`<modules>`部分定義了項目將構建的模組。 預設情況下，項目生成[以前定義的標準模組](#what-you-get):core、ui.apps、ui.content、ui.tests和it.launcher。 隨著專案的發展，您隨時都可新增更多模組。

### 相依關係 {#dependencies}

父POM的`<dependencyManagement>`部分定義了項目中使用的所有依賴項和API版本。 版本應在父POM中管理。 核心和ui.apps等子模組不應包含任何版本資訊。

#### Uber-Jar {#uber-jar}

關鍵依賴項之一是[AEMuber-jar](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/ht-projects-maven.html#ExperienceManagerAPIDependencies)。 這將包含所有API,AEM其中只包含版本的單一相依項AEM目。

>[!NOTE]
>
>作為最佳做法，您應更新uber-jar版本以符合的目標版本AEM。 例如，如果您計畫部署至AEM6.4，則應將uber-jar版本更新至6.4.0。

#### 核心元件 {#core-components}

項目原AEM型當然會利用核心元件。

核心元件會自動以預AEM設執行模式安裝，並由範例WKND網站使用。 在[生產運行模式](https://docs.adobe.com/content/help/en/experience-manager-65/administering/security/production-ready.html)(`nosamplecontent`)中，核心元件不可用。

因此，為了在所有部署中充分利用核心元件，最好將它們作為Maven項目的一部分加入。

>[!NOTE]
>
>每個核心元件版本之後通常都會有一個項目原型AEM版本，以便最新原型使用最新版的核心元件。
>
>但是，新版本的原型可能不會直接跟隨新版本的核心元件，因此您可能希望將對核心元件的依賴性更新為最新版本。

>[!NOTE]
>
>core.wcm.components.examples是一組範例頁面，可說明核心元件的範例。 作為最佳做法，在為生產部署項目時，您應刪除此相關性和子包包含。

## 測試 {#testing}

專案中包含三個測試層級，由於它們是不同類型的測試，因此會以不同的方式或在不同的位置執行。

* 核心單元測試：此展示套件中程式碼的經典單元測試。 要測試，請執行：
   * `mvn clean test`
* 伺服器端整合測試：這些在環境(即在服AEM務器上)中運行設備樣式AEM測試。 要測試，請執行：
   * `mvn clean verify -PintegrationTests`
* 用戶端Hobbes.js測試：這些是以JavaScript為基礎的瀏覽器端測試，可驗證瀏覽器端行為。 要測試：
   1. 載入AEM瀏覽器就像您要建立頁面一樣。
   1. 在[開發人員模式](https://docs.adobe.com/content/help/en/experience-manager-65/developing/components/developer-mode.html)中開啟頁面
   1. 開啟左面板並切換到&#x200B;**Tests**&#x200B;頁籤。
   1. 尋找產生的&#x200B;**MyName測試**&#x200B;並執行它們。

## 後續步驟{#next-steps}

所以你已經建立並安裝了AEMProject Archetype。 現在呢？ 原型很小，但包含許多根據建議最佳實務設定AEM的強大功能範例。 使用這些說明如何在專案中運用這些功能。 對於您可能需要的任何專案：

* [擴充現有核心元件，以自訂元件](/help/developing/customizing.md)
* [新增其他範本](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [調整本地化結構](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/tc-prep.html)
* [瞭解前端構建模組](uifrontend.md)
