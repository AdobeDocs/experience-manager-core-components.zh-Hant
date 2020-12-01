---
title: 使用AEM Project Archetype
description: AEM Project Archetype的詳細使用指示
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '2057'
ht-degree: 0%

---


# AEM Project Archetype {#aem-project-archetype}

AEM專案原型會建立以最簡化、最佳實務為基礎的Adobe Experience Manager專案，做為您自己AEM專案的起點。 使用此原型時必須提供的屬性允許您指定此項目所有部分的名稱，並控制某些可選特徵。

## 為什麼使用原型{#why-use-the-archetype}

使用AEM Project Archetype，您只需按幾下按鍵，就可建立最佳實務AEM專案。 透過使用原型，所有片段都已就緒，如此雖然產生的專案最少，但它已實作AEM的所有[主要功能](#what-you-get)，讓您只需在上面建立並延伸即可。

當然，有許多元素會加入成功的AEM專案，但使用AEM Project Archetype是可靠的基礎，強烈建議用於任何AEM專案。

## 快速入門 {#getting-started}

專案原型可讓您輕鬆開始在AEM上開發。 您可以透過多種方式採取第一步。

* WKND教學課程——如需AEM開發的絕佳簡介，包括如何運用原型，請參閱[AEM網站快速入門- WKND教學課程](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)，以取得實用範例，逐步帶您使用原型來實作簡單專案。
* WKND事件教學課程——如果您對AEM上的單頁應用程式(SPA)開發特別感興趣，請務必查看專屬的[WKND事件教學課程](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)。
* 自行下載並開始！ -您可以輕鬆下載GitHub上提供的目前專案原型，並依照[以下的簡單步驟建立您的第一個專案。](#how-to-use-the-archetype)

## 使用原型得到什麼{#what-you-get}

AEM Archetype由模組組成：

* **[核心](core.md)**:是包含所有核心功能（例如OSGi服務、偵聽程式和排程程式），以及元件相關Java程式碼（例如servlet和請求篩選器）的Java套件。
* **[ui.apps](uiapps.md)**:包含 `/apps` 專 `/etc` 案的和部分，例如JS和CSSclientlibs、元件、範本、執行模式專用的設定，以及Hobbes測試。
* **[ui.content](uicontent.md)**:包含使用ui.apps模組中元件的範例內容。
* **[ui.tests](uitests.md)**:是一個Java包，包含伺服器端執行的JUnit測試。此套件不會部署在生產上。
* **ui.launcher**:包含將ui.tests包（和相依包）部署到伺服器並觸發遠程JUnit執行的粘合代碼。
* **[ui.frontend.general](uifrontend.md)**: **（可選）** 包含使用一般基於Webpack的前端構建模組所需的對象。
* **[ui.frontend.react](uifrontend-react.md)**: **（可選）** 包含使用原型建立基於React的SPA項目時所需的工件。
* **[ui.frontend.angular](uifrontend-angular.md)**: **（可選）** 包含使用原型建立基於Angular的SPA項目時所需的工件。

![](/help/assets/archetype-structure.png)

以Maven表示的AEM Archetype模組會部署至AEM，做為代表應用程式、內容和必要OSGi組合的內容套件。

## 如何使用原型{#how-to-use-the-archetype}

要使用原型，首先需要建立項目，該項目將本地檔案結構中的模組生成為[先前描述的](#what-you-get)。 在項目生成過程中，可以定義項目的一些屬性，如項目名稱、版本等。

使用Maven建立專案會建立可部署至AEM的工件（封裝和OSGi組合）。 其他Maven命令和描述檔可用來將專案對象部署至AEM例項。

### 建立項目{#create-project}

若要開始使用，您最簡單的方式是使用[AEM Eclipse擴充功能](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/aem-eclipse.html)，然後依「新增專案」精靈並選擇「AEM範例多模組專案」**，以使用已發行版本的原型。**

當然，您也可以直接叫用Maven。

```
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.granite.archetypes \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D aemVersion=cloud \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
 -D frontendModule=general \
 -D includeExamples=n
```

* 將`XX`設為最新AEM專案原型的[版本編號](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md)。
* 將[AEM的`aemVersion=cloud`設為雲端服務](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   為[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署設定`aemVersion=6.5.0`。
「核心元件」相依性僅針對非雲端版本新增，因為「核心元件」是以AEM的OOTB提供，做為雲端
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
| `aemVersion` | `6.5.0` | 目標AEM版本([AEM的`cloud`可以是Cloud Service的](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);或`6.5.0`，或`6.4.4` for [ Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署)。 |
| `sdkVersion` | `latest` | 當`aemVersion=cloud`[SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)版本可指定時(例如`2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 根據`aemVersion`（可以是`y`或`n`）的值，為雲或AMS/on-premise包含調度器配置。 |
| `frontendModule` | `none` | 包含Webpack前端構建模組，用於生成常規站點的客戶端庫(可以是`general`或`none`;`angular`或`react`是實作[SPA編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/introduction.html)的單頁應用程式。 |
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
| `integrationTests` | 在AEM例項上執行提供的整合測試（僅適用於`verify`階段） |

### 構建和安裝{#building-and-installing}

要構建在項目根目錄中運行的所有模組，請使用以下Maven命令。

```
mvn clean install
```

如果您有執行中的AEM例項，則可以使用下列Maven命令建立並封裝整個專案並部署至AEM。

```
mvn clean install -PautoInstallPackage
```

若要將它部署至發佈例項，請執行此命令。

```
mvn clean install -PautoInstallPackagePublish
```

或者，要部署到發佈實例，請運行此命令。

```
mvn clean install -PautoInstallPackage -Daem.port=4503
```

或者，若要只將套件部署至作者，請執行此命令。

```
mvn clean install -PautoInstallBundle
```

## 父POM {#parent-pom}

項目(`<src-directory>/<project>/pom.xml`)根部的`pom.xml`稱為父POM，可驅動項目的結構，並管理依賴項和項目的某些全局屬性。

### 全局項目屬性{#global-properties}

父POM的`<properties>`部分定義了對於在AEM實例上部署項目而言非常重要的幾個全局屬性，如用戶名／口令、主機名／埠等。

這些屬性已設定為部署至本機AEM例項，因為這是開發人員最常用的建置。 請注意，有些屬性可部署至作者例項以及發佈例項。 此外，認證也會設定為透過AEM例項進行驗證。 使用預設的admin:admin憑證。

這些屬性已設定好，以便在部署至較高層級的環境時可覆寫。 這樣，POM檔案不必進行更改，但`aem.host`和`sling.password`等變數可以通過命令行參數被覆蓋：

```
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模組結構{#module-structure}

父POM的`<modules>`部分定義了項目將構建的模組。 預設情況下，項目生成[以前定義的標準模組](#what-you-get):core、ui.apps、ui.content、ui.tests和it.launcher。 隨著專案的發展，您隨時都可新增更多模組。

### 相依關係 {#dependencies}

父POM的`<dependencyManagement>`部分定義了項目中使用的所有依賴項和API版本。 版本應在父POM中管理。 核心和ui.apps等子模組不應包含任何版本資訊。

#### Uber-Jar {#uber-jar}

其中一個關鍵依賴項是[AEM uber-jar](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/ht-projects-maven.html#ExperienceManagerAPIDependencies)。 這將包含所有AEM API，而且只包含AEM版本的單一相依項目。

>[!NOTE]
>
>您最好更新uber-jar版本，以符合AEM的目標版本。 例如，如果您打算部署至AEM 6.4，您應將uber-jar版本更新至6.4.0。

#### 核心元件 {#core-components}

AEM Project Archetype當然會運用核心元件。

核心元件會自動以預設執行模式安裝在AEM中，並由範例WKND網站使用。 在[生產運行模式](https://docs.adobe.com/content/help/en/experience-manager-65/administering/security/production-ready.html)(`nosamplecontent`)中，核心元件不可用。

因此，為了在所有部署中充分利用核心元件，最好將它們作為Maven項目的一部分加入。

>[!NOTE]
>
>每個核心元件版本之後通常都會有AEM Project Archetype的版本，如此最新的原型就會使用最新版本的核心元件。
>
>但是，新版本的原型可能不會直接跟隨新版本的核心元件，因此您可能希望將對核心元件的依賴性更新為最新版本。

>[!NOTE]
>
>core.wcm.components.examples是一組範例頁面，可說明核心元件的範例。 作為最佳做法，在為生產部署項目時，您應刪除此相關性和子包包含。

## 測試 {#testing}

專案中包含三個測試層級，由於它們是不同類型的測試，因此會以不同的方式或在不同的位置執行。

* 核心單元測試：此展示套件中程式碼的經典單元測試。 要測試，請執行：
   * `mvn clean test`
* 伺服器端整合測試：這些測試會在AEM環境（即在AEM伺服器上）中執行類似單位的測試。 要測試，請執行：
   * `mvn clean verify -PintegrationTests`
* 用戶端Hobbes.js測試：這些是以JavaScript為基礎的瀏覽器端測試，可驗證瀏覽器端行為。 要測試：
   1. 將AEM載入您的瀏覽器，就像您要編寫頁面一樣。
   1. 在[開發人員模式](https://docs.adobe.com/content/help/en/experience-manager-65/developing/components/developer-mode.html)中開啟頁面
   1. 開啟左面板並切換到&#x200B;**Tests**&#x200B;頁籤。
   1. 尋找產生的&#x200B;**MyName測試**&#x200B;並執行它們。

## 後續步驟{#next-steps}

所以您已建立並安裝AEM Project Archetype。 現在呢？ 其原型雖小，但包含許多根據建議最佳實務設定之強大AEM功能的範例。 使用這些說明如何在專案中運用這些功能。 對於您可能需要的任何專案：

* [擴充現有核心元件，以自訂元件](/help/developing/customizing.md)
* [新增其他範本](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [調整本地化結構](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/tc-prep.html)
* [瞭解前端構建模組](uifrontend.md)
