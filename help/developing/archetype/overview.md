---
title: AEM 專案原型
description: AEM型應用程式的專案範本
feature: 核心元件、AEM專案原型
role: Architect, Developer, Administrator
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 32679158dd71c361f01904b4462a6ec8b33d305c
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 7%

---

# AEM 專案原型 {#aem-project-archetype}

AEM專案原型是Maven範本，可建立以最佳實務為基礎的簡化Adobe Experience Manager(AEM)專案，作為網站的起點。

>[!TIP]
>
>您可以在GitHub](https://github.com/adobe/aem-project-archetype)上找到最新的AEM專案原型[。

## 資源 {#resources}

* **原型檔案（本檔案）:** 原型架構及其不同模組的概述。
   * **[使用原型：](using.md)** 使用原型和可用模組的詳細資訊
   * **[ui.frontend:](uifrontend.md)** 如何使用前端組建模組
* 下列教學課程是以此原型為基礎：
   * **[WKND網站：](https://docs.adobe.com/content/help/zh-Hant/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 了解如何開始全新的網站。
   * **[WKND單頁應用程式：](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** 了解如何建置完全可在AEM中授權的React或Angular網頁應用程式。

## 功能 {#features}

* **最佳作法：** 使用所有Adobe的最新建議作法Bootstrap您的網站。
* **低程式碼：** 編輯範本、建立內容、部署CSS，而您的網站已可上線。
* **雲端就緒：** 如有需要， [請使用AEM as a ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) Cloud Service，在數天內上線，並簡化擴充性和維護作業。
* **Dispatcher:** 專案只有以可確保速度與安全 [性](https://docs.adobe.com/content/help/zh-Hant/experience-manager-dispatcher/using/dispatcher.html) 的Dispatcher設定完成。
* **多網站：** 如有需要，原型會為多語言和多 [區域設定產生內容結構](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html)。
* **核心元件：** 作者可以使用多功能的標準元件集，建立幾乎 [任何版面配置](/help/introduction.md)。
* **可編輯的範本：** 幾乎可組合任 [何不含程式碼的範本](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，並定義作者可編輯的項目。
* **回應式配置：** 在範本或個別頁面上， [定義元素對已定](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html) 義斷點的重排方式。
* **頁首與頁尾：** 不使用程式碼，使用元件的本 [地化功能來組合和本地化](https://docs.adobe.com/content/help/zh-Hant/experience-manager-core-components/using/get-started/localization.html)。
* **樣式系統：** 允許作者套用不同樣式來避免建 [立自](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) 訂元件。
* **前端建置：** 前端開發人員可 [以透過Webpack、](uifrontend.md#webpack-dev-server) TypeScript和 [SASS模擬AEM頁](uifrontend.md) 面並建立用戶端程式庫。
* **WebApp-Ready:** 針對使用 [](uifrontend-react.md) Reactor  [Angular](uifrontend-angular.md)的網站，請使用 [SPA ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/developing.html) SDK [保留應用程](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)式的內容內編寫。
* **啟用商務：** 針對要將AEM Commerce與商務解決 [方](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/commerce/home.html) 案(如管理商務核 [](https://magento.com/) 心元件) [整合的專案](https://github.com/adobe/aem-core-cif-components)。
* **范常式式碼：** 結帳HelloWorld元件，以及範例模型、servlet、篩選器和排程器。
* **開放來源：** 如果某個項目不如預期，將有助於 [](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) 您的改善！

## 使用狀況

若要產生專案，請根據您的需求調整下列命令列：

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=27 \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* 為[AEM設定`aemVersion=cloud`作為Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   為[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署設定`aemVersion=6.5.0`。
僅會針對非雲端aem版本新增核心元件相依性，因為AEM會以Cloud Service的形式提供核心元件。
* 調整`appTitle="My Site"`以定義網站標題和元件群組。
* 調整`appId="mysite"`以定義Maven工件Id、元件、配置和內容資料夾名稱，以及客戶端庫名稱。
* 調整`groupId="com.mysite"`以定義Maven groupId和Java源包。
* 查詢可用屬性清單，查看是否有其他需要調整的項目。

## 可用屬性

| 名稱 | 預設 | 說明 |
--------------------------|----------------|--------------------
| `appTitle` |  | 應用程式標題將用於網站標題和元件群組(例如`"My Site"`)。 |
| `appId` |  | 技術名稱將用於元件、設定和內容資料夾名稱，以及用戶端程式庫名稱(例如`"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基Maven工件ID(例如`"mysite"`)。 |
| `groupId` |  | 基本Maven群組ID(例如`"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java源包(例如`"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 專案版本(例如`1.0-SNAPSHOT`)。 |
| `aemVersion` | `cloud` | Target AEM版本(對於[AEM as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)，可以是`cloud`;或`6.5.0`，或`6.4.4`（適用於[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署）。 |
| `sdkVersion` | `latest` | 當`aemVersion=cloud`可指定[ SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)版本時(例如`2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 包含雲端或AMS/內部部署的Dispatcher設定，視`aemVersion`值而定（可以是`y`或`n`）。 |
| `frontendModule` | `general` | 包括Webpack前端構建模組，用於生成常規站點的客戶端庫(可以是`general`或`none`;可為`angular`或`react`，適用於實作[SPA編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/editor-overview.html)的單頁應用程式。 |
| `language` | `en` | 語言代碼(ISO 639-1)，以從(例如`en`, `deu`)。 |
| `country` | `us` | 國家/地區代碼(ISO 3166-1)，以從(例如`US`)。 |
| `singleCountry` | `y` | 包含語言主版內容結構（可以是`y`或`n`）。 |
| `includeExamples` | `n` | 包含[元件庫](https://www.aemcomponents.dev/)示例站點（可以是`y`或`n`）。 |
| `includeErrorHandler` | `n` | 包含對整個執行個體具有全域性的自訂404回應頁面（可以是`y`或`n`）。 |
| `includeCommerce` | `n` | 包含[CIF核心元件](https://github.com/adobe/aem-core-cif-components)相依性並產生對應的成品。 |
| `commerceEndpoint` |  | 僅CIF為必要。 要使用的商務系統GraphQL服務的可選端點(例如`https://hostname.com/grapql`)。 |
| `datalayer` | `y` | 啟動與[Adobe客戶端資料層](/help/developing/data-layer/overview.md)的整合。 |
| `amp` | `n` | 對生成的項目模板啟用[AMP](/help/developing/amp.md)支援。 |

## 系統需求

| 原型 | AEM as a Cloud Service  | AEM 6.5 | AEM 6.4 | Java SE | 馬文 |
|---------|---------|---------|---------|---------|---------|
| [26](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-27) | 持續 | 6.5.5.0+ | 6.4.8.1+ | 8, 11 | 3.3.9+ |

為[AEM as aCloud ServiceSDK](https://docs.adobe.com/content/help/zh-Hant/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)或為[舊版AEM](https://docs.adobe.com/content/help/zh-Hant/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)設定本機開發環境。

### 已知問題

在Windows上執行並產生調度程式配置時，您應在提升的命令提示字元或Linux的Windows子系統中執行(請參閱[#329](https://github.com/adobe/aem-project-archetype/issues/329))。

在互動式模式中執行原型時（沒有`-B`參數），具有預設值的屬性無法變更，除非最終確認被解除，然後確認會將具有預設值的屬性納入問題中以重複問題(請參閱
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)以取得詳細資訊)。

## 進一步閱讀{#further-reading}

如需使用原型的詳細資訊，包括其優點、選項及其模組的運作方式，請參閱[使用原型檔案。](using.md)
