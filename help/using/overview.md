---
title: AEM Project Archetype
seo-title: AEM Project Archetype
description: AEM型應用程式的專案範本
seo-description: AEM型應用程式的專案範本
contentOwner: 博納特
content-type: 引用
topic-tags: 核心元件
translation-type: tm+mt
source-git-commit: 488132fdc077985cdc3f369e1e127e8bff8e80c7

---


# AEM Project Archetype {#aem-project-archetype}

AEM專案原型會建立以最簡化、最佳實務為基礎的Adobe Experience Manager專案，做為您自己AEM專案的起點。 使用此原型時必須提供的屬性允許您指定此項目所有部分的名稱，並控制某些可選特徵。

>[!NOTE]
>
>您可在GitHub上找到最新的AEM Project Archetype [和完整的技術細節](https://github.com/adobe/aem-project-archetype)。

>[!NOTE]
>
>請參閱AEM [檔案中的「AEM Sites - WKND快速入門教學課程」](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) ，以取得實用範例，逐步帶您使用架構類型來建置簡單專案。

## 功能 {#features}

原型有一些數字功能，可為新的AEM專案提供方便的起點：

* 包含範例內容的英文和法文頁面
* 基於可編輯的模板功能的內容模板以及示例內容策略
* 基於 [AEM Page Core Component的頁面元件](page.md)
* 使用建議的Proxy模式實作的內容元件範例和範例Helloworld自訂元件，全都以 [AEM Core Components為基礎](introduction.md)。
* 表單元 [件範例](form-container.md)
* 裝置模擬器、拖放設定和國際化的組態
* 遵循BEM命名慣例的客戶端庫以及元件特定樣式
* 範例組合，包括範例模型、伺服器、篩選器和排程器
* 單元、整合和用戶端測試

## 為什麼使用原型 {#why-use-the-archetype}

使用AEM Project Archetype，您只需按幾下按鍵，就可建立最佳實務AEM專案。 透過使用原型，所有部分都已就緒，如此雖然產生的專案最少，但它已建置了 [AEM](#features) 的所有主要功能，讓您只需在上面建立並延伸即可。

當然，有許多元素會加入成功的AEM專案，但使用AEM Project Archetype是可靠的基礎，強烈建議用於任何AEM專案。

## 你用原型得到什麼 {#what-you-get}

AEM Archetype由模組組成：

* **[核心](core.md)**:是包含所有核心功能（例如OSGi服務、偵聽程式和排程程式），以及元件相關Java程式碼（例如servlet和請求篩選器）的Java套件。
* **[ui.apps](uiapps.md)**:包含專 `/apps` 案的 `/etc` 和部分，例如JS和CSSclientlibs、元件、範本、執行模式專用的設定，以及Hobbes測試。
* **[ui.content](uicontent.md)**:包含使用ui.apps模組中元件的範例內容。
* **ui.tests**:是一個Java包，包含伺服器端執行的JUnit測試。 此套件不會部署在生產上。
* **ui.launcher**:包含將ui.tests包（和相依包）部署到伺服器並觸發遠程JUnit執行的粘合代碼。
* **[ui.frontend](front-end-build.md)**: **（可選）** ，包含使用基於Webpack的前端構建模組所需的對象。

![](assets/project-pom.png)

以Maven表示的AEM Archetpye模組會部署至AEM，做為代表應用程式、內容和必要OSGi組合的內容頁面。

## 需求 {#requirements}

目前的原型版本有下列要求：

* Adobe Experience Manager 6.3.3.0或更新版本
* Apache Maven（3.3.9或更新版本）
* Maven設定中的Adobe Public Maven Repository。 如需詳細 [資訊，請參閱此知識庫文章](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html)。

如需舊版原型支援的AEM版本清單，請參閱歷 [史支援的AEM版本](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md)。

## 如何使用原型 {#how-to-use-the-archetype}

若要使用原型，您首先需要建立專案，如先前所述，在本機檔案結構中產生 [模組](#what-you-get)。 在項目生成過程中，可以定義項目的一些屬性，如項目名稱、版本等。

使用Maven建立專案會建立可部署至AEM的工件（封裝和OSGi組合）。 其他Maven命令和描述檔可用來將專案對象部署至AEM例項。

### 建立專案 {#create-project}

若要開始使用，您只需使用 [AEM Eclipse擴充功能](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/aem-eclipse.html) ，然後依照「新專案」精靈的指示，並選擇 **AEM Sample Multi-Module Project** ，即可使用已發行版本的原型。

當然，您也可以直接叫用Maven。

```
mvn archetype:generate \
 -DarchetypeGroupId=com.adobe.granite.archetypes \
 -DarchetypeArtifactId=aem-project-archetype \
 -DarchetypeVersion=XX
```

其中 `XX` 是最 [新](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md) AEM Project Archetype的版本號碼。

>[!NOTE]
>
>將描述檔新增至Maven檔 `adobe-public` 案中，以 `settings.xml` 便自動將repo.adobe.com新增至Maven建立程式，這是最佳實務。
>
>這裡可 [以找到示例POM](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html)。

### 屬性 {#properties}

使用原型建立項目時，可使用以下屬性。

| 名稱 | 預設 | 說明 |
----------------------------|---------|--------------------
| `groupId` |  | 馬文基地 `groupId` |
| `artifactId` |  | 基本Maven ArtifactId |
| `version` |  | 版本 |
| `package` |  | Java源包 |
| `appsFolderName` |  | `/apps` 資料夾名稱 |
| `artifactName` |  | Maven項目名稱 |
| `componentGroupName` |  | AEM元件群組名稱 |
| `contentFolderName` |  | `/content` 資料夾名稱 |
| `confFolderName` |  | `/conf` 資料夾名稱 |
| `cssId` |  | 生成的css中使用的前置詞 |
| `packageGroup` |  | 內容套件群組名稱 |
| `siteName` |  | AEM網站名稱 |
| `optionAemVersion` | 6.5.0 | Target AEM版本 |
| `optionIncludeExamples` | y | 包含元 [件庫](http://opensource.adobe.com/aem-core-wcm-components/library.html) 示例站點 |
| `optionIncludeErrorHandler` | n | 包含自訂404回應頁面 |
| `optionIncludeFrontendModule` | n | [包括專用的前端模組](front-end-build.md) |

>[!NOTE]
> 如果原型是第一次在互動模式中執行，則無法變更具有預設值的屬性(如需詳細資訊，請參閱 [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) )。 當結束時的屬性確認被拒絕且調查表被重複時，或通過在命令行中傳遞參數(例如， `-DoptionIncludeExamples=n`)。

### 設定檔 {#profiles}

當執行時，產生的Maven專案支援不同的部署設定檔 `mvn install`。

| 描述檔ID | 說明 |
--------------------------|------------------------------
| `autoInstallBundle` | 安裝包含maven-sling-plugin至OSGi的核心套件 |
| `autoInstallPackage` | 將ui.content和ui.apps內容套件與content-package-maven-plugin一起安裝至localhost, port 4502上預設作者例項的套件管理器。 主機名和埠可以使用和用 `aem.host` 戶定 `aem.port` 義的屬性進行更改。 |
| `autoInstallPackagePublish` | 將包含content-package-maven-plugin的ui.content和ui.apps內容套件安裝至套件管理員，以在localhost，連接埠4503上預設發佈例項。 主機名和埠可以使用和用 `aem.host` 戶定 `aem.port` 義的屬性進行更改。 |
| `integrationTests` | 在AEM例項上執行提供的整合測試(僅適用於階 `verify` 段) |

### 建立和安裝 {#building-and-installing}

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

項 `pom.xml` 目(`<src-directory>/<project>/pom.xml`)的根目錄稱為父POM，它驅動項目的結構，並管理依賴項和項目的某些全局屬性。

### 全域專案屬性 {#global-properties}

父 `<properties>` POM的部分定義了幾個對於在AEM實例上部署項目非常重要的全局屬性，如用戶名／密碼、主機名／埠等。

這些屬性已設定為部署至本機AEM例項，因為這是開發人員最常用的建置。 請注意，有些屬性可部署至作者例項以及發佈例項。 此外，認證也會設定為透過AEM例項進行驗證。 使用預設的admin:admin憑證。

這些屬性已設定好，以便在部署至較高層級的環境時可覆寫。 這樣，POM檔案不必進行更改，但可以通過命令行參數 `aem.host` 來覆 `sling.password` 蓋諸如和的變數：

````
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
````

### 模組結構 {#module-structure}

父 `<modules>` POM的部分定義了項目將構建的模組。 預設情況下，項目會 [生成以前定義的標準模組](#what-you-get):core、ui.apps、ui.content、ui.tests和it.launcher。 隨著專案的發展，您隨時都可新增更多模組。

### 相依關係 {#dependencies}

父 `<dependencyManagement>` POM的部分定義了項目中使用的所有依賴項和API版本。 版本應在父POM中管理。 核心和ui.apps等子模組不應包含任何版本資訊。

#### Uber-Jar {#uber-jar}

其中一個關鍵依賴項是 [AEM uber-jar](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/ht-projects-maven.html#ExperienceManagerAPIDependencies)。 這將包含所有AEM API，而且只包含AEM版本的單一相依項目。

>[!NOTE]
>
>您最好更新uber-jar版本，以符合AEM的目標版本。 例如，如果您打算部署至AEM 6.4，您應將uber-jar版本更新至6.4.0。

#### 核心元件 {#core-components}

AEM Project Archetype當然會運用核心元件。

核心元件會自動以預設執行模式安裝在AEM中，並由範例We.Retail網站使用。 在生產 [運行模式](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/production-ready.html) (`nosamplecontent`)中，核心元件不可用。

因此，為了在所有部署中充分利用核心元件，最好將它們作為Maven項目的一部分加入。

>[!NOTE]
>
>每個核心元件版本之後通常都會有AEM Project Archtype版本，如此最新的架構就會使用最新版本的核心元件。
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
   1. 在「開發人員」模式中 [開啟頁面](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/developer-mode.html)
   1. 開啟左側面板，並切換至「 **Tests** 」標籤。
   1. 尋找產生的 **MyName測試** ，然後執行測試。

## 後續步驟 {#next-steps}

因此，您已建立並安裝AEM Project Archetype。 現在呢？ 其原型雖小，但包含許多根據建議最佳實務設定之強大AEM功能的範例。 使用這些說明如何在專案中運用這些功能。 對於您可能需要的任何專案：

* [自訂元件以擴充現有的核心元件](customizing.md)
* [新增其他範本](https://helpx.adobe.com/content/help/en/experience-manager/6-5/sites/authoring/using/templates.html)
* [調整本地化結構](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html)
* [瞭解前端構建模組](front-end-build.md)
