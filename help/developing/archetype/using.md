---
title: 使用AEM專案原型
description: 瞭解如何使用AEM專案原型來建立依最佳作法為基礎的Adobe Experience Manager專案，作為您專屬AEM專案的開端。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---


# 使用AEM專案原型 {#using-the-archetype}

本檔案說明如何使用AEM專案原型，建立依最佳作法為基礎的Adobe Experience Manager專案，作為您專屬AEM專案的開端。

它著重於一般使用模式以及原型對您的作用。 如需詳細的建置選項和技術指示，請參閱原型的GitHub存放庫中的檔案。

>[!TIP]
>
>最新AEM專案原型和相關技術檔案 [在GitHub上可找到。](https://github.com/adobe/aem-project-archetype)

## 快速入門 {#getting-started}

專案原型可讓您在AEM上輕鬆開始開發。 您可以透過多種方式採取處理原型的第一個步驟。

* **WKND教學課程**  — 如需在AEM上進行開發的詳細介紹，包括如何利用原型，請參閱 [AEM Sites - WKND教學課程快速入門](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) 此實用範例將逐步說明如何使用原型來實作簡單專案。
* **WKND事件教學課程**  — 如果您特別想知道如何在AEM上開發單頁應用程式(SPA)，請務必檢視專屬的 [WKND事件教學課程。](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)
* **自力更生！**  — 您可輕鬆下載 [GitHub上可用的目前專案原型](https://github.com/adobe/aem-project-archetype) 並自行建立您的第一個專案。

## 如何使用原型 {#how-to-use-the-archetype}

使用原型的第一個步驟是建立專案，這會產生 [模組](#what-you-get) 在本機檔案結構中。 作為專案產生的一部分，可以定義專案的一些屬性，例如專案名稱、版本、啟用各種選項等。

>[!TIP]
>
>每當您建置原型時，它也會產生一系列的readme，為您提供每個模組的技術細節和使用方式，如 [連結如下。](#what-you-get)

使用Maven建置專案會建立可部署至AEM的成品（套件和OSGi套件組合）。 其他Maven命令和設定檔可用於將專案成品部署到AEM執行個體。

## 使用原型的好處 {#what-you-get}

原型由模組組成，所有模組在使用原型時自動建立。

* **[核心](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)** 是一個Java套件組合，包含所有核心功能（例如OSGi服務、監聽器和排程器）以及與元件相關的Java程式碼（例如servlet和請求篩選器）。
* **[it.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** 是以Java為基礎的整合測試。
* **[ui.apps](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.apps)** 包含 `/apps` 和 `/etc` 專案的一部分，即JS和CSS clientlibs、元件和範本。
* **[ui.content](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.content)** 包含使用ui.apps模組元件的範例內容。
* **[ui.config](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.config)** 包含專案的執行模式特定OSGi設定。
* **[ui.frontend.general](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.general)** 包含使用一般Webpack型前端建置模組所需的成品（選用）。
* **[ui.frontend.react](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.react)** **（選擇性）** 包含根據React使用原型建立SPA專案時所需的成品（選擇性，取決於建置引數）。
* **[ui.frontend.angular](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.angular)** **（選擇性）** 包含根據Angular使用原型建立SPA專案時所需的成品（選擇性，取決於建置引數）。
* **[ui.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)** 包含以Selenium為基礎的UI測試。
* **[全部](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/all)** 是單一內容套件，內嵌所有已編譯的模組（套件組合和內容套件），包括任何廠商相依性。
* **[dispatcher.ams](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.ams)** 包含AMS/內部部署專案的基本Dispatcher設定（選用，取決於組建引數）。
* **[dispatcher.cloud](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.cloud)** 包含AEMaaCS專案的基本Dispatcher設定（選用，取決於建置引數）。

![內容封裝組織](/help/assets/content-package-organization.png)

Maven中代表的原型模組會部署到AEM，做為代表應用程式、內容和必要OSGi套裝的內容套件。

## 父級POM {#parent-pom}

此 `pom.xml` 在專案的根目錄(`<src-directory>/<project>/pom.xml`)稱為上層POM，可驅動專案結構並管理專案的相依性和某些全域屬性。

### 全域專案屬性 {#global-properties}

此 `<properties>` 上層POM的區段會定義在AEM執行個體上部署專案所必需的幾個全域屬性，例如使用者名稱/密碼、主機名稱/連線埠等。

這些屬性設定為部署至本機AEM執行個體，因為這是開發人員最常進行的建置。 請注意，有一些屬性要部署至作者執行個體以及發佈執行個體。 這也是認證設定為使用AEM執行個體進行驗證的地方。 預設 `admin:admin` 已使用認證。

設定這些屬性以便在部署到更高級別的環境時可以覆寫它們。 如此一來，POM檔案就不需要變更，變數如下 `aem.host` 和 `sling.password` 可透過命令列引數覆寫：

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模組結構 {#module-structure}

此 `<modules>` 上層POM的區段會定義專案將建立的模組。 預設會建置專案 [先前定義的標準模組。](#what-you-get) 隨著專案發展，永遠可以新增更多模組。

### 相依性 {#dependencies}

此 `<dependencyManagement>` 上層POM的區段會定義專案中使用的API的所有相依性和版本。 版本應在父POM中進行管理。 子模組不應包含任何版本資訊。

#### Uber-Jar {#uber-jar}

主要相依性之一是 [AEM Java API Jar。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) 這將包括所有AEM API，而AEM版本只有一個相依性專案。

>[!NOTE]
>
>最佳實務是更新uber-jar版本以符合AEM的目標版本。 例如，如果您計畫部署到AEM 6.5，您應該將uber-jar的版本更新到6.5.X，其中 `X` 是最新的service pack。

#### 核心元件 {#core-components}

當然，原型會利用 [核心元件。](/help/introduction.md) 因此，若要在所有部署中運用核心元件，最佳實務是將它們納入Maven專案。

core.wcm.components.examples是一組範例頁面，說明核心元件的範例。 最佳實務是，在部署專案以供生產使用時，您應移除此相依性和子套件包含。

>[!NOTE]
>
>核心元件和原型會維護為單獨的GitHub專案，因此其發行版本不同。
>
>每個原型版本都將使用發佈時最新版本的核心元件。 不過，您可能想要手動更新核心元件的相依性。

## 測試 {#testing}

專案中包含三個層級的測試，由於測試型別不同，因此會以不同方式或在不同位置執行。

* **[單元測試](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)**  — 套件組合中包含之程式碼的傳統單元測試
* **[整合測試](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)**  — 在AEM環境中(即在AEM伺服器上)執行單元測試的伺服器端整合測試
* **[UI測試](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)**  — 驗證瀏覽器端行為的Selenium型瀏覽器端測試
