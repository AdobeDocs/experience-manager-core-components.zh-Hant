---
title: AEM Project Archetype
description: AEM型應用程式的專案範本
translation-type: tm+mt
source-git-commit: c9ec069a9eb12b8625be09d1c38dcaaf437bd5cb
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 3%

---


# AEM Project Archetype {#aem-project-archetype}

AEM Project Archetype是Maven範本，可建立以最簡化、最佳實務為基礎的Adobe Experience Manager(AEM)專案，做為您網站的起點。

>[!TIP]
>
>您可在GitHub上找到最 [新的AEM Project Archetype](https://github.com/adobe/aem-project-archetype)。

## 資源 {#resources}

* **原型檔案（本檔案）:** 總結了原型體系結構及其不同模組。
   * **[使用原型：](using.md)** 有關使用原型和可用模組的詳細資訊
   * **[ui.frontend:](uifrontend.md)** 如何使用前端構建模組
* 以下教學課程是以此原型為基礎：
   * **[WKND網站：](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 瞭解如何開始建立全新的網站。
   * **[WKND單頁應用程式：](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** 瞭解如何建立可在AEM中完全授權的React或Angular網路應用程式。

## 功能 {#features}

* **最佳實務：** 使用所有Adobe建議的最新實務引導您的網站。
* **低程式碼：** 編輯範本、建立內容、部署CSS，讓您的網站可上線使用。
* **雲端就緒：** 視需要， [將AEM當做雲端服務](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) ，在數天內上線，並輕鬆擴充和維護。
* **Dispatcher:** 專案只有使用 [Dispatcher組態才能完成](https://docs.adobe.com/content/help/zh-Hant/experience-manager-dispatcher/using/dispatcher.html) ，以確保速度和安全性。
* **多網站：** 如果需要，原型生成多語言和多 [區域設定的內容結構](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html)。
* **核心元件：** 作者幾乎可以使用我們的多功能標準元件集 [來建立任何版面](/help/introduction.md)。
* **可編輯的範本：** 組合幾乎任何 [範本，毋需編寫程式碼](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，並定義作者可編輯的項目。
* **自適應版面：** 在範本或個別頁面上，定 [義元素如何重排已定義的中斷點](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html) 。
* **頁首和頁尾：** 使用元件的本地化功能，不需編寫程式 [碼即可進行組合和本地化](https://docs.adobe.com/content/help/en/experience-manager-core-components/using/get-started/localization.html)。
* **樣式系統：** 允許作者套用不同的樣式，以避免 [建立自訂元件](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) 。
* **前端構建：** 前端開發人員可 [以使用Webpack](uifrontend.md#webpack-dev-server) 、TypeScript [和SASS來模擬AEM頁面並](uifrontend.md) 建立用戶端程式庫。
* **WebApp-Ready:** 對於使用 [React](uifrontend-react.md) 或 [Angular](uifrontend-angular.md)的網站，請使用 [SPA SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/developing.html) ，在應用程 [](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)式內容製作中保留。
* **啟用商務：** 針對想要整合 [AEM Commerce](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/commerce/home.html) 與商務解決方案(例如 [Magento](https://magento.com/) )的專案，請使 [用Commerce Core Components](https://github.com/adobe/aem-core-cif-components)。
* **范常式式碼：** 結帳HelloWorld元件，以及範例模型、servlet、篩選器和排程器。
* **未結來源：** 如果事情不如預期，請 [改進](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) !

## 使用狀況

要生成項目，請根據需要調整以下命令行：

```
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=24 \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* Set `aemVersion=cloud` for [AEM as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   為 `aemVersion=6.5.0` Adobe Managed Services [](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)，或內部部署設定。
「核心元件」相依性僅會針對非雲端版本新增，因為「核心元件」是以雲端服務形式提供給AEM的OOTB。
* 調整 `appTitle="My Site"` 以定義網站標題和元件群組。
* 調整 `appId="mysite"` 以定義Maven artifactId、元件、設定和內容資料夾名稱，以及用戶端程式庫名稱。
* 調整 `groupId="com.mysite"` 以定義Maven groupId和Java Source Package。
* 查閱可用屬性的清單，查看您是否需要調整更多屬性。

## 可用屬性

| 名稱 | 預設 | 說明 |
--------------------------|----------------|--------------------
| `appTitle` |  | 應用程式標題將用於網站標題和元件群組(例如 `"My Site"`)。 |
| `appId` |  | 技術名稱將用於元件、設定和內容資料夾名稱，以及用戶端程式庫名稱(例如 `"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基本Maven對象ID(例如 `"mysite"`)。 |
| `groupId` |  | 基本Maven群組ID(例如 `"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java源包(例如 `"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 專案版本(例如 `1.0-SNAPSHOT`)。 |
| `aemVersion` | `cloud` | Target AEM版本(可以 `cloud` 用 [於AEM做為雲端服務](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);或 `6.5.0`，或 `6.4.4` 是 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或內部部署)。 |
| `sdkVersion` | `latest` | 當可 `aemVersion=cloud` 以指 [定SDK版本時](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) (例如 `2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 包含針對雲或AMS/on-premise的調度程式配置，具體取決於 `aemVersion` (可以是 `y` 或 `n`)。 |
| `frontendModule` | `general` | 包含Webpack前端構建模組，用於生成客戶端庫(可以是常規 `general` 站點 `none` 的客戶端庫；可以是實 `angular` 作 `react` SPA編輯器的單頁應用程 [式](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/editor-overview.html))。 |
| `language` | `en` | 語言程式碼(ISO 639-1)，以建立內容結構，例如 `en`, `deu`)。 |
| `country` | `us` | 國家／地區代碼(ISO 3166-1)，以建立內容結構，例如 `US`)。 |
| `singleCountry` | `y` | 包含語言主版內容結構(可 `y`以是 `n`或)。 |
| `includeExamples` | `n` | 包含元 [件庫](https://www.aemcomponents.dev/) (可以 `y`是或 `n`)示例站點。 |
| `includeErrorHandler` | `n` | 包含自訂的404回應頁面，該頁面將會是整個例項的全域(可以是 `y` 或 `n`)。 |
| `includeCommerce` | `n` | 包括 [CIF核心元件相依性](https://github.com/adobe/aem-core-cif-components) ，並生成相應的對象。 |
| `commerceEndpoint` |  | 僅CIF必需。 要使用的商務系統GraphQL服務的可選端點(例如 `https://hostname.com/grapql`)。 |
| `datalayer` | `y` | 啟動與 [Adobe用戶端資料層的整合](/help/developing/data-layer/overview.md)。 |
| `amp` | `n` | 啟用 [AMP](/help/developing/amp.md) ，支援產生的專案範本。 |

## Analyzer模組 {#analyzer-module}

AEM Analyzer Maven增效模組會分析各種內容套件專案的結構。

如需如 [何將AEM Analyzer Maven Plugin專案包含在AEM Maven專案中的詳細資訊](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md) ，請參閱AEM Analyzer Maven Plugin檔案。 外掛程式已包含在AEM Maven原型第25版及更新版本中。

下表說明在此步驟中執行的分析器。 請注意，有些會在本機SDK中執行，而有些則只會在Cloud Manager管道部署期間執行。

| 模組 | 函式、範例與疑難排解 | 本機SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | 檢查所有OSGI捆綁包是否都有其Import-Package聲明，該聲明由Maven項目中其它包含的捆綁包的Export-package聲明滿足。 <p> </p> 若要疑難排解，請查看您要匯出的套件資訊清單，以判斷使用的是錯誤名稱或版本。 | 是 | 是 |
| `requirements-capabilities` | 檢查在OSGI捆綁包中建立的所有要求聲明是否由Maven項目中包含的其他捆綁包的功能聲明滿足。 <p> </p> 若要疑難排解，請查看您預期會宣告功能包的資訊清單，以判斷其遺失的原因。 | 是 | 是 |
| `bundle-content` | 如果搭售包含以Sling-Initial-Content指定的初始內容，則會發出警告，這在AEM中是Cloud Service叢集環境。 | 是 | 是 |
| `api-regions-crossfeature-dups` | 驗證客戶OSGI搭售沒有將AEM覆寫為雲端服務之公開API的匯出套件宣告 | 是 | 是 |

## 系統需求

| 原型 | AEM as a Cloud Service  | AEM 6.5 | AEM 6.4 | Java SE | 馬文 |
|---------|---------|---------|---------|---------|---------|
| [24](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-24) | 持續 | 6.5.5.0+ | 6.4.8.1+ | 8, 11 | 3.3.9+ |

將您的本機開發環境設 [定為AEM(Cloud Service SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) )或 [舊版AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。

### 已知問題

在Windows上運行並生成調度程式配置時，您應在提升的命令提示符或Linux的Windows子系統中運行(請參 [見#329](https://github.com/adobe/aem-project-archetype/issues/329))。

在交互模式下執行原型時(無參數 `-B` )，不能更改具有預設值的屬性，除非最終確認被關閉，然後通過將具有預設值的屬性包括在問題中來重複問題(有關詳細資訊，請參閱[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) )。

## 進一步閱讀 {#further-reading}

有關使用原型的詳細資訊，包括其優點、選項及其模組的工作方式，請參閱使 [用原型文檔。](using.md)
