---
title: AEM Project Archetype
description: AEM型應用程式的專案範本
translation-type: tm+mt
source-git-commit: 794408e8b643de2234664e69e59e1108cf286cd7
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 3%

---


# AEM Project Archetype {#aem-project-archetype}

AEM Project Archetype是Maven範本，可建立以最簡化、最佳實務為基礎的Adobe Experience Manager(AEM)專案，做為您網站的起點。

>[!TIP]
>
>您可在GitHub](https://github.com/adobe/aem-project-archetype)上找到最新的AEM Project Archetype [。

## 資源 {#resources}

* **原型檔案（本檔案）：原** 型架構及其不同模組概觀。
   * **[使用原型：有關使](using.md)** 用原型和可用模組的詳細資訊
   * **[ui.frontend：如](uifrontend.md)** 何使用前端構建模組
* 以下教學課程是以此原型為基礎：
   * **[WKND網站：](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 瞭解如何開始新網站。
   * **[WKND單頁應用程式：了](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** 解如何建立可在AEM中完全授權的React或Angular網頁應用程式。

## 功能 {#features}

* **最佳實務：** 使用所有Adobe的最新建議實務引導您的網站。
* **低程式碼：** 編輯範本、建立內容、部署CSS，讓您的網站可上線使用。
* **雲端就緒：** 視需要使用 [AEM做為雲端服務，](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) 在數天內上線，並輕鬆調整擴充性和維護。
* **Dispatcher：專** 案只有使用 [Dispatcher](https://docs.adobe.com/content/help/zh-Hant/experience-manager-dispatcher/using/dispatcher.html) 設定才能完成，以確保速度和安全性。
* **多網站：如** 果需要，原型會產生多語 [言和多地區設定的內容結構](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html)。
* **核心元件：** 作者幾乎可以使用我們的多功能標準元件 [集來建立任何版面](/help/introduction.md)。
* **可編輯的範本：** 組合幾乎任何 [不含程式碼的範本](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，並定義作者可編輯的內容。
* **回應式版面：** 在範本或個別頁面上， [定義元素重](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html) 排定義中斷點的方式。
* **頁首和頁尾：使** 用元件的本地化功能，在不使用程式碼的情 [況下組合併本地化它們](https://docs.adobe.com/content/help/en/experience-manager-core-components/using/get-started/localization.html)。
* **樣式系統：** 允許作者套用不同的樣式，以避免 [建立](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) 自訂元件。
* **前端建置：前端開** 發人員可以 [使用Webpack、TypeScript和SASS來模](uifrontend.md#webpack-dev-server) 擬AEM頁 [面並建](uifrontend.md) 立用戶端資料庫。
* **WebApp-Ready：若** 是使用 [](uifrontend-react.md) Reactor  [Angular](uifrontend-angular.md)的網站，請使用 [SPA ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/developing.html) SDK保留在應 [](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)用程式內容製作中。
* **啟用商務：** 針對想要整合 [AEM ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/commerce/home.html) Commerce與商務解決方案(例如 [](https://magento.com/) Magentousing the  [Commerce Core Components)的專案](https://github.com/adobe/aem-core-cif-components)。
* **范常式式碼：** 結帳HelloWorld元件，以及範例模型、servlet、篩選器和排程器。
* **開放來源：** 如果某件事情不如預期，您的改 [](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) 進功能就會有！

## 使用狀況

要生成項目，請根據需要調整以下命令行：

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=24 \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* 將[AEM的`aemVersion=cloud`設為雲端服務](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   為[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署設定`aemVersion=6.5.0`。
「核心元件」相依性僅會針對非雲端版本新增，因為「核心元件」是以雲端服務形式提供給AEM的OOTB。
* 調整`appTitle="My Site"`以定義網站標題和元件群組。
* 調整`appId="mysite"`以定義Maven artifactId、元件、設定和內容資料夾名稱，以及用戶端程式庫名稱。
* 調整`groupId="com.mysite"`以定義Maven groupId和Java Source Package。
* 查閱可用屬性的清單，查看您是否需要調整更多屬性。

## 可用屬性

| 名稱 | 預設 | 說明 |
--------------------------|----------------|--------------------
| `appTitle` |  | 應用程式標題將用於網站標題和元件群組(例如`"My Site"`)。 |
| `appId` |  | 技術名稱將用於元件、設定和內容資料夾名稱，以及用戶端程式庫名稱(例如`"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基本Maven對象ID(例如`"mysite"`)。 |
| `groupId` |  | 基本Maven群組ID(例如`"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java源包(例如`"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 專案版本(例如`1.0-SNAPSHOT`)。 |
| `aemVersion` | `cloud` | 目標AEM版本([AEM的`cloud`可以是Cloud Service的](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);或`6.5.0`，或`6.4.4` for [ Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署)。 |
| `sdkVersion` | `latest` | 當`aemVersion=cloud`[SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)版本可指定時(例如`2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 根據`aemVersion`（可以是`y`或`n`）的值，為雲或AMS/on-premise包含調度器配置。 |
| `frontendModule` | `general` | 包含Webpack前端構建模組，用於生成常規站點的客戶端庫(可以是`general`或`none`;`angular`或`react`是實作[SPA編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/editor-overview.html)的單頁應用程式。 |
| `language` | `en` | 語言程式碼(ISO 639-1)，以建立內容結構，例如`en`, `deu`)。 |
| `country` | `us` | 國家／地區代碼(ISO 3166-1)，以建立內容結構，例如`US`)。 |
| `singleCountry` | `y` | 包含語言主版內容結構（可以是`y`或`n`）。 |
| `includeExamples` | `n` | 包含[元件庫](https://www.aemcomponents.dev/)範例網站（可以是`y`或`n`）。 |
| `includeErrorHandler` | `n` | 包含自訂404回應頁面，該頁面將會對整個例項產生全域性影響（可以是`y`或`n`）。 |
| `includeCommerce` | `n` | 包括[CIF核心元件](https://github.com/adobe/aem-core-cif-components)相關性並生成相應的偽像。 |
| `commerceEndpoint` |  | 僅CIF必需。 要使用的商務系統GraphQL服務的可選端點(例如`https://hostname.com/grapql`)。 |
| `datalayer` | `y` | 啟動與[Adobe用戶端資料層](/help/developing/data-layer/overview.md)的整合。 |
| `amp` | `n` | 啟用對生成的項目模板的[AMP](/help/developing/amp.md)支援。 |

## 系統需求

| 原型 | AEM as a Cloud Service  | AEM 6.5 | AEM 6.4 | Java SE | 馬文 |
|---------|---------|---------|---------|---------|---------|
| [24](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-24) | 持續 | 6.5.5.0+ | 6.4.8.1+ | 8, 11 | 3.3.9+ |

為[AEM設定本機開發環境，以做為Cloud Service SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)或[舊版AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。

### 已知問題

在Windows上運行並生成調度程式配置時，您應在提升的命令提示符或Windows Subsystem for Linux（請參見[#329](https://github.com/adobe/aem-project-archetype/issues/329)）中運行。

在互動模式中執行原型（不含`-B`參數）時，不能變更具有預設值的屬性，除非最終確認被關閉，否則會在問題中加入具有預設值的屬性，以重複問題(請參閱
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)以取得詳細資訊)。

## 進一步閱讀{#further-reading}

有關使用原型的詳細資訊，包括其優點、選項及其模組的工作方式，請參閱[使用原型文檔。](using.md)
