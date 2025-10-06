---
title: 使用 AEM 專案原型
description: 了解如何使用 AEM 專案原型，依最佳作法建立簡化的 Adobe Experience Manager 專案，作為您專屬 AEM 專案的開端。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: ht
source-wordcount: '1092'
ht-degree: 100%

---


# 使用 AEM 專案原型 {#using-the-archetype}

本文件詳細說明如何使用 AEM 專案原型，依最佳作法建立簡化的 Adobe Experience Manager 專案，作為您專屬 AEM 專案的開端。

它著重於一般使用模式，以及原型對您的作用。如需詳細的建置選項和技術指示，請參閱原型的 GitHub 存放庫中的文件。

>[!TIP]
>
>[在 GitHub 上可找到](https://github.com/adobe/aem-project-archetype)最新的 AEM 專案原型及相關技術文件。

## 快速入門 {#getting-started}

專案原型可讓您在 AEM上輕鬆開始開發。您可以透過多種方式採取處理原型的第一個步驟。

* **WKND 教學課程** - 如需有關在 AEM 上進行開發的精彩說明，包括如何善用原型，請參閱 [AEM Sites 快速入門 - WKND 教學課程](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hant)中的實際範例，以逐步引導您使用原型實施簡單的專案。
* **WKND 事件教學課程** - 如果您對 AEM 上的單一頁面應用程式 (SPA) 開發特別感興趣，請務必檢視專屬的 [WKND 事件教學課程。](https://helpx.adobe.com/tw/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)
* **自行開始！** - 您可以輕鬆下載 [GitHub 上可用的目前專案原型](https://github.com/adobe/aem-project-archetype)，並自行建立您的第一個專案。

## 如何使用原型 {#how-to-use-the-archetype}

使用原型的第一步是建立專案，該專案會在本機檔案結構中產生[模組](#what-you-get)。在專案產生的過程中，可以定義專案的一些屬性，例如專案名稱、版本、啟用各種選項等。

>[!TIP]
>
>每當您建置原型時，它也會產生一系列的讀我檔案，為您提供每個模組的技術詳細資訊和使用方式，如[以下連結](#what-you-get)所示。

使用 Maven 建置專案會建立可部署至 AEM 的成品 (套件和 OSGi 套件組合)。其他 Maven 命令和設定檔可用於將專案成品部署至 AEM 執行個體。

## 使用原型的好處 {#what-you-get}

原型由模組組成，而所有模組在使用原型時自動建立。

* **[core](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)** 是 Java 套件組合，其中包含所有核心功能 (例如 OSGi 服務、監聽程式和排程器) 以及與元件相關的 Java 程式碼 (例如 servlet 和請求篩選器)。
* **[it.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** 是以 Java 為基礎的整合測試。
* **[ui.apps](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.apps)** 包含專案的 `/apps` 和 `/etc` 部分，即 JS 和 CSS clientlib、元件和範本。
* **[ui.content](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.content)** 包含使用 ui.apps 模組元件的範例內容。
* **[ui.config](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.config)** 包含專案的執行模式專用 OSGi 設定。
* **[ui.frontend.general](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.general)** 包含使用一般 Webpack 型前端建置模組 (選擇性) 所需的成品。
* **[ui.frontend.react](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.react)** **(選擇性)** 包含使用原型建立以 React 為基礎的 SPA 專案時所需的成品 (選擇性，取決於建置參數)。
* **[ui.frontend.angular](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.angular)** **(選擇性)** 包含使用原型建立以 Angular 為基礎的 SPA 專案時所需的成品 (選擇性，取決於建置參數)。
* **[ui.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)** 包含以 Selenium 為基礎的 UI 測試。
* **[all](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/all)** 是單一內容套件，內嵌所有已編譯的模組 (套件組合和內容套件)，包括任何廠商相依性。
* **[dispatcher.ams](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.ams)** 包含 AMS/內部部署專案的基本 Dispatcher 設定 (選擇性，取決於建置參數)。
* **[dispatcher.cloud](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.cloud)** 包含 AEMaaCS 專案的基本 Dispatcher 設定 (選擇性，取決於建置參數)。

![內容套件組織](/help/assets/content-package-organization.png)

Maven 中代表的原型模組會部署至 AEM，做為代表應用程式、內容和必要 OSGi 套件組合的內容套件。

## 上層 POM {#parent-pom}

專案 (`<src-directory>/<project>/pom.xml`) 根目錄中的 `pom.xml` 稱為上層 POM，可驅動專案結構並管理專案的相依性和特定全域屬性。

### 全域專案屬性 {#global-properties}

上層 POM 的 `<properties>` 區段定義了在 AEM 執行個體上部署專案所必需的幾個全域屬性，例如使用者名稱/密碼、主機名稱/連接埠等。

這些屬性設定為部署至本機 AEM 執行個體，這是開發人員最常進行的建置。請注意，有一些屬性要部署至作者實例以及發佈執行個體。這也是認證設定為使用 AEM 執行個體進行驗證的地方。已使用預設 `admin:admin` 認證。

設定這些屬性以便在部署至更高層級的環境時，可以覆寫它們。如此一來，POM 檔案就不需要變更，但可透過命令列參數覆寫 `aem.host` 和 `sling.password` 等變數：

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模組結構 {#module-structure}

上層 POM 的 `<modules>` 區段定義專案將建置的模組。預設情況下，專案會建置[先前定義的標準模組。](#what-you-get)專案發展過程中，可以隨時新增更多模組。

### 相依性 {#dependencies}

上層 POM 的 `<dependencyManagement>` 區段會定義專案中使用的 API 的所有相依性和版本。版本應在上層 POM 中進行管理。下層模組不應包含任何版本資訊。

#### Uber-Jar {#uber-jar}

主要相依性之一是 [AEM Java API Jar。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html?lang=zh-Hant)這將包含所有 AEM API，而且只有一個 AEM 版本的相依項目。

>[!NOTE]
>
>最佳做法是更新 uber-jar 版本以符合 AEM 的目標版本。例如，如果您計畫部署至 AEM 6.5，您應該將 uber-jar 的版本更新到 6.5.X，其中 `X` 是最新的 Service Pack。

#### 核心元件 {#core-components}

當然，原型會利用 [核心元件。](/help/introduction.md)因此，若要在所有部署中善用「核心元件」，最佳做法是將它們納入 Maven 專案。

core.wcm.components.examples 是一組範例頁面，說明核心元件的範例。最佳做法是，在部署專案以供生產使用時，您應移除此相依性和下層套件包含。

>[!NOTE]
>
>核心元件和原型會作為單獨 GitHub 專案進行維護，因此其發行版本不同。
>
>每個原型的發行版本都將使用發佈時最新發行版本的核心元件。不過，您可能會希望手動更新核心元件的相依性。

## 測試 {#testing}

專案中包含三個層級的測試，由於測試類型不同，因此會以不同方式或在不同位置執行。

* **[單元測試](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)** - 套件組合中包含之程式碼的傳統單元測試
* **[整合測試](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** - 在 AEM 環境 (亦即 AEM 伺服器) 中執行單元式測試的伺服器端整合測試
* **[UI 測試](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)** - 驗證瀏覽器端行為的 Selenium 型瀏覽器端測試
