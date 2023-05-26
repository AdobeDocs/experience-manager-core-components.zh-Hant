---
title: AEM 專案原型
description: AEM應用程式的專案範本
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: fac7c40919d2c31a8004bd1f47500ac44f99fb61
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 8%

---

# AEM 專案原型 {#aem-project-archetype}

AEM專案原型是Maven範本，可建立依最佳作法為基礎的Adobe Experience Manager (AEM)最小專案，作為您網站的起點。

>[!TIP]
>
>最新的AEM專案原型 [在GitHub上可找到。](https://github.com/adobe/aem-project-archetype)

## 資源 {#resources}

* **原型檔案（本檔案）：** 原型架構及其不同模組的概觀。
   * **[使用原型：](using.md)** 有關使用原型和可用模組的更多詳細資料
   * **[ui.frontend：](uifrontend.md)** 如何使用前端建置模組
* **以下教學課程是根據此原型所建立：**
   * **[WKND網站：](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hant)** 瞭解如何啟動全新的網站。
   * **[WKND單頁應用程式：](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** 瞭解如何建立完全可在AEM中編寫的React或Angular網頁應用程式。

## 功能 {#features}

* **最佳實務：** 使用Adobe的所有最新建議作法Bootstrap您的網站。
* **低程式碼：** 編輯您的範本、建立內容、部署CSS，您的網站就可以上線了。
* **雲端就緒：** 如有需要，請使用 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 可在數天內上線，並簡化擴充性與維護作業。
* **Dispatcher：** 專案完成時需具備 [Dispatcher設定](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=zh-Hant) 可確保速度和安全性。
* **多網站：** 如有需要，原型會產生 [多語言和多區域設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html).
* **核心元件：** 作者可以使用我們的通用功能建立幾乎任何版面 [標準化元件集](/help/introduction.md).
* **可編輯的範本：** 組合幾乎任何一個 [沒有程式碼的範本](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，並定義作者可編輯的內容。
* **回應式佈局：** 在範本或個別頁面上， [定義元素重排的方式](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html) 用於定義的中斷點。
* **頁首與頁尾：** 組合併本地化這些區段，而不使用程式碼，使用 [元件的本地化功能](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html).
* **樣式系統：** 允許作者避免建置自訂元件 [套用不同的樣式](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html) 給他們。
* **前端建置：** 前端開發人員可以 [模擬AEM頁面](uifrontend.md#webpack-dev-server) 和 [建置使用者端程式庫](uifrontend.md) 搭配Webpack、TypeScript和SASS。
* **WebApp就緒：** 針對網站，使用 [React](uifrontend-react.md) 或 [angular](uifrontend-angular.md)，使用 [SPA SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html) 要保留 [應用程式的內容內撰寫](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html).
* **啟用Commerce：** 針對要整合的專案 [AEM商務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html) 商業解決方案，例如 [Magento](https://magento.com/) 使用 [Commerce核心元件](https://github.com/adobe/aem-core-cif-components).
* **範常式式碼：** 請檢視HelloWorld元件，以及範例模型、servlet、篩選器和排程器。
* **開放來源：** 如果有出錯的地方， [contribute](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) 您的改良！

## 使用狀況 {#usage}

若要產生專案，請根據您的需求調整下列命令列：

```shell
mvn -B org.apache.maven.plugins:maven-archetype-plugin:3.2.1:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* Replace `XX` 使用最新 [原型版本號碼。](#requirements)
* 設定 `aemVersion=cloud` 的 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html)；\
   設定 `aemVersion=6.5.0` 的 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署。
僅針對非雲端AEM版本新增核心元件相依性，因為核心元件是針對AEMas a Cloud Service提供的OOTB。
* 調整 `appTitle="My Site"` 以定義網站標題和元件群組。
* 調整 `appId="mysite"` 以定義Maven artifactId、元件、設定和內容資料夾名稱以及使用者端資料庫名稱。
* 調整 `groupId="com.mysite"` 以定義Maven groupId和Java來源套件。
* 查詢可用屬性清單，檢視是否有更多要調整的內容。

## 可用屬性 {#available-properties}

| 名稱 | 預設 | 說明 |
|---------------------------|----------------|--------------------|
| `appTitle` |  | 應用程式標題，將用於網站標題和元件群組(例如 `"My Site"`)。 |
| `appId` |  | 技術名稱，將用於元件、設定和內容資料夾名稱，以及使用者端資料庫名稱(例如 `"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基礎Maven成品ID (例如 `"mysite"`)。 |
| `groupId` |  | 基本Maven群組ID (例如 `"com.mysite"`)。 此值必須為 [有效的Java套件名稱。](https://docs.oracle.com/javase/specs/jls/se6/html/packages.html#7.7) |
| `package` | *`${groupId}`* | Java來源套件(例如 `"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 專案版本(例如 `1.0-SNAPSHOT`)。 |
| `aemVersion` | `cloud` | 目標AEM版本(可以是 `cloud` 的 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html)；或 `6.5.0`，或 `6.4.4` 的 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或內部部署)。 |
| `sdkVersion` | `latest` | 時間 `aemVersion=cloud` 一個 [SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) 可以指定版本(例如 `2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 包含雲端或AMS/內部部署的Dispatcher設定，具體取決於的值 `aemVersion` (可以是 `y` 或 `n`)。 |
| `frontendModule` | `general` | 包含產生使用者端程式庫的Webpack前端組建模組(可以 `general` 或 `none` 用於一般網站；可以是 `angular` 或 `react` 實作的單頁應用程式 [SPA編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/editor-overview.html))。 |
| `language` | `en` | 從中建立內容結構的語言代碼(ISO 639-1) (例如： `en`， `deu`)。 |
| `country` | `us` | 從中建立內容結構的國家/地區代碼(ISO 3166-1) (例如： `US`)。 |
| `singleCountry` | `y` | 包含語言主要內容結構(可以 `y`，或 `n`)。 |
| `includeExamples` | `n` | 包含 [元件資料庫](https://www.aemcomponents.dev/) 網站範例(可以是 `y`，或 `n`)。 |
| `includeErrorHandler` | `n` | 包含自訂404回應頁面，此頁面將為整個執行個體的全域頁面(可以 `y` 或 `n`)。 |
| `includeCommerce` | `n` | 包含 [CIF Core Components](https://github.com/adobe/aem-core-cif-components) 相依性並產生對應的成品。 |
| `commerceEndpoint` |  | 僅適用於CIF。 要使用的商務系統GraphQL服務的選用端點(例如 `https://hostname.com/grapql`)。 |
| `includeFormscommunications` | `n` | 包含 [Forms核心元件](https://github.com/adobe/aem-core-forms-components) 相依性、範本、表單資料模型、主題，並為Forms通訊程式產生對應的成品。 |
| `includeFormsenrollment` | `n` | 包含 [Forms核心元件](https://github.com/adobe/aem-core-forms-components) 相依性、範本、表單資料模型、主題，並為Forms註冊程式產生對應的成品。 |
| `sdkFormsVersion` | `latest` | 時間 `aemVersion=cloud` 和其中一個 `includeFormsenrollment=y` 或 `includeFormscommunications=y`，可指定Forms SDK版本(例如 `2020.12.17.02`)。 |
| `datalayer` | `y` | 啟用與的整合 [Adobe使用者端資料層](/help/developing/data-layer/overview.md). |
| `amp` | `n` | 啟用 [AMP](/help/developing/amp.md) 支援產生的專案範本。 |
| `enableDynamicMedia` | `n` | 在專案原則設定中啟用基礎DynamicMedia元件，並在核心影像元件原則中啟用Dynamic Media功能。 |
| `enableSSR` | `n` | 為前端專案啟用SSR的選項 |
| `precompiledScripts` | `n` | 選項至 [預先編譯](/help/developing/archetype/precompiled-bundled-scripts.md) 來自的伺服器端指令碼 `ui.apps` 並將它們附加至組建作為中的次要套件成品 `ui.apps` 專案。 `aemVersion` 應設為 `cloud`. |
| `includeFormsheadless` | `n` | 包含 [Forms核心元件](https://github.com/adobe/aem-core-forms-components) 相依性， `ui.frontend.react.forms.af`和headless成品。 |

## 系統需求 {#requirements}

| 原型 | AEM as a Cloud Service  | AEM 6.5 | Java SE | Maven |
|---------|---------|---------|---------|---------|
| [41](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-41) | 持續 | 6.5.7.0+ | 8, 11 | 3.3.9+ |

設定您的本機開發環境 [AEMAS A CLOUD SERVICESDK](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html?lang=zh-Hant) 或for [舊版AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

### 已知問題 {#known-issues}

在Windows上執行並產生Dispatcher設定時，您應該在提升許可權的命令提示字元或Linux適用的Windows子系統中執行(請參閱 [#329](https://github.com/adobe/aem-project-archetype/issues/329))。

在互動模式中執行原型時(不含 `-B` 引數)，則無法變更具有預設值的屬性，除非取消最終確認，這接著會在問題中包含具有預設值的屬性來重複問題(請參閱
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) 以取得詳細資訊)。

當您使用開始新專案時，無法在Eclipse中使用此原型 `File -> New -> Maven Project` 自從產生後的指令碼 `archetype-post-generate.groovy` 將不會執行，因為 [Eclipse問題。](https://bugs.eclipse.org/bugs/show_bug.cgi?id=514993) 因應措施是使用上述命令列，然後在Eclipse中使用 `File -> Import -> Existing Maven Project`.

## 延伸閱讀 {#further-reading}

如需有關使用原型的更多詳細資訊，包括其優點、選項及其模組如何運作，請參閱 [使用原型檔案。](using.md)
