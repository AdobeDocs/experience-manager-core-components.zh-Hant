---
title: AEM 專案原型
description: 基於應用程式AEM的項目模板
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 01890b368b083b09b5be8a9b6efad55a5d8d4f9e
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 5%

---

# AEM 專案原型 {#aem-project-archetype}

「項AEM目原型」是Maven模板，它建立基於最小、最佳做法的Adobe Experience Manager(AEM)項目，作為網站的起點。

>[!TIP]
>
>最新的項AEM目原型 [中。](https://github.com/adobe/aem-project-archetype)

## 資源 {#resources}

* **原型文檔（本文檔）:** 原型體系結構及其各模組概述。
   * **[使用原型：](using.md)** 有關使用原型和可用模組的進一步詳情
   * **[ui.frontend:](uifrontend.md)** 如何使用前端生成模組
* **以下教程基於此原型：**
   * **[WKND站點：](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 瞭解如何啟動新網站。
   * **[WKND單頁應用：](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** 瞭解如何構建完全可在中授權的React或AngularWeb應AEM用。

## 功能 {#features}

* **最佳實踐：** Bootstrap您的站點，包括所有Adobe的最新建議做法。
* **低代碼：** 編輯模板、建立內容、部署CSS，並且您的站點已準備好投入使用。
* **雲就緒：** 如果需要，請使用 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 可在幾天內投入使用，並且易於擴展和維護。
* **調度程式：** 項目僅與 [調度程式配置](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=zh-Hant) 確保速度和安全。
* **多站點：** 如果需要，原型為 [多語言多區域設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html)。
* **核心元件：** 作者幾乎可以通過我們的多功能建立任何佈局 [標準化元件集](/help/introduction.md)。
* **可編輯模板：** 幾乎可以組裝任何 [無代碼模板](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，並定義允許作者編輯的內容。
* **響應佈局：** 在模板或單個頁面上， [定義元素重排方式](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html) 的子菜單。
* **頁眉和頁腳：** 使用 [元件的本地化特徵](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html)。
* **樣式系統：** 通過允許作者建立自定義元件 [應用不同樣式](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html) 敬他們。
* **前端構建：** 前端開發人員可以 [模AEM擬頁](uifrontend.md#webpack-dev-server) 和 [構建客戶端庫](uifrontend.md) 和SASS。
* **WebApp就緒：** 對於使用 [反應](uifrontend-react.md) 或 [Angular](uifrontend-angular.md)，使用 [SDKSPA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html) 保留 [應用的上下文創作](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。
* **已啟用商業：** 對於要整合的項目 [商AEM業](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html) 用商業解決方案 [Magento](https://magento.com/) 使用 [商業核心元件](https://github.com/adobe/aem-core-cif-components)。
* **示例代碼：** 簽出HelloWorld元件以及示例模型、Servlet、篩選器和調度程式。
* **開源：** 如果事情不如預期， [貢獻](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) 你的改進！

## 使用狀況 {#usage}

要生成項目，請根據需要調整以下命令行：

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* 替換 `XX` 最新 [原型版本號。](#requirements)
* 設定 `aemVersion=cloud` 為 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html);\
   設定 `aemVersion=6.5.0` 為 [Adobe托管服務](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或內部部署。
只為非雲版本添加核心元件依賴項，因為為AEMas a Cloud Service提供核心元件。
* 調整 `appTitle="My Site"` 定義網站標題和元件組。
* 調整 `appId="mysite"` 定義Maven artifactId、元件、配置和內容資料夾名稱以及客戶端庫名稱。
* 調整 `groupId="com.mysite"` 定義Maven groupId和Java源包。
* 查找可用屬性清單，查看是否要調整更多屬性。

## 可用屬性 {#available-properties}

| 名稱 | 預設 | 說明 |
|---------------------------|----------------|--------------------|
| `appTitle` |  | 應用程式標題將用於網站標題和元件組(例如 `"My Site"`)。 |
| `appId` |  | 技術名稱將用於元件、配置和內容資料夾名稱以及客戶端庫名稱(例如 `"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基Maven項目ID(例如 `"mysite"`)。 |
| `groupId` |  | 基本Maven組ID(例如 `"com.mysite"`)。 此值必須是 [有效的Java包名稱。](https://docs.oracle.com/javase/specs/jls/se6/html/packages.html#7.7) |
| `package` | *`${groupId}`* | Java源包(例如 `"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 項目版本(例如 `1.0-SNAPSHOT`)。 |
| `aemVersion` | `cloud` | 目AEM標版本(可以 `cloud` 為 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html);或 `6.5.0`或 `6.4.4` 為 [Adobe托管服務](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或內部)。 |
| `sdkVersion` | `latest` | 當 `aemVersion=cloud` 一個 [SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) 可以指定版本(例如 `2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 包括針對雲或AMS/本地的調度程式配置，具體取決於 `aemVersion` (可以 `y` 或 `n`)。 |
| `frontendModule` | `general` | 包括生成客戶端庫的Webpack前端生成模組(可以 `general` 或 `none` 對於常規場所；可以 `angular` 或 `react` 用於實現 [編SPA輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/editor-overview.html))。 |
| `language` | `en` | 語言代碼(ISO 639-1)，用於從(例如 `en`。 `deu`)。 |
| `country` | `us` | 國家（地區）代碼(ISO 3166-1)，用於建立內容結構，例如 `US`)。 |
| `singleCountry` | `y` | 包括語言主體內容結構(可以 `y`或 `n`)。 |
| `includeExamples` | `n` | 包括 [元件庫](https://www.aemcomponents.dev/) 示例站點(可以 `y`或 `n`)。 |
| `includeErrorHandler` | `n` | 包括將對整個實例全局的自定義404響應頁(可以是 `y` 或 `n`)。 |
| `includeCommerce` | `n` | 包括 [CIF核心元件](https://github.com/adobe/aem-core-cif-components) 依賴項並生成相應的偽像。 |
| `commerceEndpoint` |  | 僅CIF必需。 要使用的商業系統GraphQL服務的可選端點(例如 `https://hostname.com/grapql`)。 |
| `datalayer` | `y` | 激活與 [Adobe客戶端資料層](/help/developing/data-layer/overview.md)。 |
| `amp` | `n` | 啟用 [安培](/help/developing/amp.md) 支援生成的項目模板。 |
| `enableDynamicMedia` | `n` | 在項目策略設定中啟用基礎DynamicMedia元件，並在核心映像元件的策略中激活Dynamic Media功能。 |
| `enableSSR` | `n` | 為前端項目啟用SSR的選項 |
| `precompiledScripts` | `n` | 選項 [預編](/help/developing/archetype/precompiled-bundled-scripts.md) 伺服器端指令碼 `ui.apps` 並將它們作為次捆綁對象連接到 `ui.apps` 項目。 `aemVersion` 應設定為 `cloud`。 |
| `includeFormscommunications` | `n` | 包括 [Forms核心元件](https://github.com/adobe/aem-core-forms-components) 依賴項、模板、表單資料模型、主題，以及為Forms通信程式生成相應的工件。 |
| `includeFormsenrollment` | `n` | 包括 [Forms核心元件](https://github.com/adobe/aem-core-forms-components) 依賴項、模板、表單資料模型、主題，並為Forms註冊方案生成相應的項目。 |

## 系統要求 {#requirements}

| 原型 | AEM as a Cloud Service  | AEM 6.5 | Java SE | 馬文 |
|---------|---------|---------|---------|---------|
| [37](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-37) | 連續 | 6.5.7.0+ | 8、11 | 3.3.9+ |

設定本地開發環境 [AEMas a Cloud ServiceSDK](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) 或 [舊版本AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。

### 已知問題 {#known-issues}

在Windows上運行並生成調度程式配置時，應在提升的命令提示符或Windows Subsystem for Linux中運行(請參見 [#329](https://github.com/adobe/aem-project-archetype/issues/329))。

在交互模式下執行原型時(沒有 `-B` 參數)中，不能更改具有預設值的屬性，除非最終確認被撤消，然後，確認會通過在問題中包括具有預設值的屬性來重複問題(請參閱
[原型308](https://issues.apache.org/jira/browse/ARCHETYPE-308) )。

在啟動新項目時，不能在Eclipse中使用此原型 `File -> New -> Maven Project` 自後代指令碼 `archetype-post-generate.groovy` 將因 [Eclipse問題。](https://bugs.eclipse.org/bugs/show_bug.cgi?id=514993) 解決方法是使用上述命令行，然後在Eclipse中使用 `File -> Import -> Existing Maven Project`。

## 進一步閱讀 {#further-reading}

有關使用原型的更多詳細資訊，請參閱 [使用原型文檔。](using.md)
