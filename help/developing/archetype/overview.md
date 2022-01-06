---
title: AEM 專案原型
description: AEM型應用程式的專案範本
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 9ae35572f7ef60ea5140a7b48be087f34e39ce3a
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 2%

---

# AEM 專案原型 {#aem-project-archetype}

AEM專案原型是Maven範本，可建立以最佳實務為基礎的簡化Adobe Experience Manager(AEM)專案，作為網站的起點。

>[!TIP]
>
>最新的AEM專案原型 [可在GitHub上找到。](https://github.com/adobe/aem-project-archetype)

## 資源 {#resources}

* **原型檔案（本檔案）:** 概述原型架構及其不同模組。
   * **[使用原型：](using.md)** 有關使用原型的詳細資訊，以及可用的模組
   * **[ui.frontend:](uifrontend.md)** 如何使用前端構建模組
* **下列教學課程是以此原型為基礎：**
   * **[WKND站點：](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 了解如何建立全新的網站。
   * **[WKND單頁應用：](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** 了解如何建立完全可在AEM中授權的React或Angular網頁應用程式。

## 功能 {#features}

* **最佳實務：** Bootstrap您的網站，並提供所有Adobe的最新建議實務。
* **低碼：** 編輯範本、建立內容、部署CSS，而您的網站已可上線。
* **雲就緒：** 如果需要，請使用 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 在幾天內上線，並簡化可擴充性和維護。
* **Dispatcher:** 專案僅會以 [Dispatcher設定](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=zh-Hant) 確保速度和安全性。
* **多站點：** 如有需要，原型會產生 [多語言和多區域設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html).
* **核心元件：** 作者可以使用多功能 [標準化元件集](/help/introduction.md).
* **可編輯的範本：** 幾乎任何組合 [不含代碼的範本](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，並定義可供作者編輯的內容。
* **回應式版面：** 在範本或個別頁面上， [定義元素重排的方式](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html) 用於定義的斷點。
* **頁首與頁尾：** 無需編寫程式碼，即可組合併將其本地化，請使用 [元件的本地化功能](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html).
* **樣式系統：** 允許作者建立自訂元件，避免建立自訂元件 [應用不同的樣式](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html) 敬他們。
* **前端構建：** 前端開發人員可 [模擬AEM頁面](uifrontend.md#webpack-dev-server) 和 [建置用戶端程式庫](uifrontend.md) 和SASS。
* **WebApp-Ready:** 針對使用 [React](uifrontend-react.md) 或 [Angular](uifrontend-angular.md)，請使用 [SPA SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/headless/spa/developing.html) 保留 [應用程式的內容內容製作](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html).
* **啟用商務：** 針對要整合的專案 [AEM Commerce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html) 搭配商務解決方案，如 [Magento](https://magento.com/) 使用 [商務核心元件](https://github.com/adobe/aem-core-cif-components).
* **范常式式碼：** 結帳HelloWorld元件，以及範例模型、servlet、篩選器和排程器。
* **開放來源：** 如果事情不如預期， [貢獻](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) 你的改進！

## 使用狀況 {#usage}

若要產生專案，請根據您的需求調整下列命令列：

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* 取代 `XX` 最新 [原型版本號碼。](#requirements)
* 設定 `aemVersion=cloud` for [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html);\
   設定 `aemVersion=6.5.0` for [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)，或內部部署。
僅會針對非雲端aem版本新增核心元件相依性，因為核心元件是針對AEMas a Cloud Service而提供的OOTB。
* 調整 `appTitle="My Site"` 定義網站標題和元件群組。
* 調整 `appId="mysite"` 要定義Maven工件Id、元件、配置和內容資料夾名稱以及客戶端庫名稱。
* 調整 `groupId="com.mysite"` 來定義Maven groupId和Java源包。
* 查詢可用屬性清單，查看是否有其他需要調整的項目。

## 可用屬性 {#available-properties}

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
| `frontendModule` | `general` | 包含Webpack前端建置模組，用於產生用戶端程式庫(可以 `general` 或 `none` （二）固定場所；可以 `angular` 或 `react` 適用於實作 [SPA Editor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/headless/spa/editor-overview.html))。 |
| `language` | `en` | 語言代碼(ISO 639-1)，以從(例如 `en`, `deu`)。 |
| `country` | `us` | 國家/地區代碼(ISO 3166-1)，以從(例如 `US`)。 |
| `singleCountry` | `y` | 包含語言主版內容結構(可以 `y`，或 `n`)。 |
| `includeExamples` | `n` | 包括 [元件庫](https://www.aemcomponents.dev/) 網站範例(可 `y`，或 `n`)。 |
| `includeErrorHandler` | `n` | 包含對整個執行個體具有全域性的自訂404回應頁面(可以是 `y` 或 `n`)。 |
| `includeCommerce` | `n` | 包含 [CIF核心元件](https://github.com/adobe/aem-core-cif-components) 相依性並產生對應的成品。 |
| `commerceEndpoint` |  | 僅CIF為必要。 要使用的商務系統GraphQL服務的可選端點(例如 `https://hostname.com/grapql`)。 |
| `datalayer` | `y` | 啟用與的整合 [Adobe用戶端資料層](/help/developing/data-layer/overview.md). |
| `amp` | `n` | 啟用 [AMP](/help/developing/amp.md) 支援產生的專案範本。 |
| `enableDynamicMedia` | `n` | 在專案原則設定中啟用基礎DynamicMedia元件，並在核心影像元件的原則中啟用Dynamic Media功能。 |
| `enableSSR` | `n` | 為前端項目啟用SSR的選項 |
| `precompiledScripts` | `n` | 選項 [預編譯](/help/developing/archetype/precompiled-bundled-scripts.md) 來自 `ui.apps` 並將它們作為輔助捆綁對象附加到組建中 `ui.apps` 專案。 `aemVersion` 應設為 `cloud`. |
| `includeFormscommunications` | `n` | 包含 [Forms核心元件](https://github.com/adobe/aem-core-forms-components) 相依性、範本、表單資料模型、主題，以及為Forms通訊程式產生對應的成品。 |
| `includeFormsenrollment` | `n` | 包含 [Forms核心元件](https://github.com/adobe/aem-core-forms-components) 相依性、範本、表單資料模型、主題，以及為Forms註冊方案產生對應的成品。 |

## 系統需求 {#requirements}

| 原型 | AEM as a Cloud Service  | AEM 6.5 | Java SE | 馬文 |
|---------|---------|---------|---------|---------|
| [34](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-34) | 持續 | 6.5.7.0+ | 8, 11 | 3.3.9+ |

設定您的本機開發環境，以 [AEMas a Cloud ServiceSDK](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) 或 [舊版AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

### 已知問題 {#known-issues}

在Windows上執行並產生調度程式配置時，您應在提升的命令提示字元或Linux適用的Windows子系統中執行(請參閱 [#329](https://github.com/adobe/aem-project-archetype/issues/329))。

在互動式模式中執行原型時(不使用 `-B` 參數)，則無法變更具有預設值的屬性，除非最終確認被關閉，然後重複問題，將具有預設值的屬性加入問題中(請參閱
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) 詳細資訊)。

以啟動新專案時，您無法在Eclipse中使用此原型 `File -> New -> Maven Project` 自後代指令碼開始 `archetype-post-generate.groovy` 不會執行，因為 [Eclipse問題。](https://bugs.eclipse.org/bugs/show_bug.cgi?id=514993) 因應措施是使用上述命令列，然後在Eclipse中使用 `File -> Import -> Existing Maven Project`.

## 進一步閱讀 {#further-reading}

如需使用原型的詳細資訊，包括其優點、選項及其模組的運作方式，請參閱 [使用原型檔案。](using.md)
