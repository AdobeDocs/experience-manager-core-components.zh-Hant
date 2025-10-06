---
title: AEM as a Cloud Service SDK 建置分析器 Maven 外掛程式
description: 本機 Maven 建置分析器外掛程式的文件
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: de26b310-a294-42d6-a0db-91f6036a328c
source-git-commit: eafbe18b13830edde3535fbb67d9ef62b7d045f3
workflow-type: ht
source-wordcount: '656'
ht-degree: 100%

---

# AEM as a Cloud Service SDK 建置分析器 Maven 外掛程式 {#maven-analyzer-plugin}

AEM as a Cloud Service SDK 建置分析器 Maven 外掛程式會分析各種內容套件專案的結構。

欲了解如何將其加入 AEM Maven 專案的資訊，請參閱 [Maven 外掛程式文件](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md)。

>[!NOTE]
>
>建議您更新 Maven 專案，以參照 [Maven 中央存放庫](https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/)中找到的外掛程式的最新版本。

外掛程式會使用最新可用的 SDK，而非專案中設定的 SDK。

下表說明在此步驟中執行的分析器。<!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| 模組 | 函式、範例及疑難排解 | 本機 SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | 檢查所有 OSGi 套件組合的匯入套件宣告，是否由 Maven 專案中其他包含套件組合的匯出套件宣告滿足。錯誤可能如下所示： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>若要進行疑難排解，請檢視提供套件的套件組合是否包含在部署中，或檢視您預期匯出的套件組合資訊清單，以判斷使用的名稱或版本是否有誤。 | 是 | 是 |
| `bundle-unversioned-packages` | 檢查 OSGi 套件組合是否在匯出套件宣告中指定版本，並在匯入套件宣告中指定版本範圍。錯誤可能如下所示： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is exporting package org.acme.foo without a version.`<p> </p>若要進行疑難排解，請確認將 `package-info.java` 新增至該套件，並指定要匯出的版本。 | 是 | 是 |
| `requirements-capabilities` | 檢查 OSGi 套件組合中提出的所有要求宣告，是否由 Maven 專案中包含的其他套件組合的功能宣告滿足。錯誤可能如下所示： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> 若要進行疑難排解，請檢視您預期宣告某功能的套件組合資訊清單，以判斷為何遺失該功能，或檢查要求該功能的套件組合資訊清單，確認其中的要求是否正確。 | 是 | 是 |
| `bundle-resources` | 如果套件組合包含以 Sling-Bundle-Resources 標頭指定的資源，而這些資源在 AEM as a Cloud Service 叢集環境中有問題，則會提出警告。警告如下所示：<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> 若要疑難排解將資源轉換為 repoinit 陳述式，請參閱[Repoinit 文件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=zh-hant#repo-init)。 | 是 | 是 |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | 這些分析器會檢查與[內容套件至功能模型轉換流程](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=zh-hant#deploying)相關的一些細節，這些流程會建立符合 Sling 功能模型的成品。任何錯誤都應向 Adobe 客戶支援回報。 | 是 | 是 |
| `api-regions-crossfeature-dups` | 驗證客戶 OSGi 套件組合沒有會覆寫 AEM as a Cloud Service 公用 API 的匯出套件宣告<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>若要修正，請停止匯出屬於 AEM 公用 API 的套件。 | 是 | 是 |
| `repoinit` | 檢查所有 repoinit 區段的語法 | 是 | 是 |
| `bundle-nativecode` | 驗證 OSGi 套件組合沒有安裝原生程式碼。 | 是 | 是 |
| `configuration-api` | 驗證重要的 OSGi 設定。 <p> </p> `Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Configuration is not allowed (com.mysite:mysite.all:1.0.0-SNAPSHOT\|com.mysite:mysite.ui.config:1.0.0-SNAPSHOT)` | 是 | 是 |
| `region-deprecated-api` | 檢查是否已使用[已棄用 API](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-apis.html) <p> </p>`[WARNING] com.mysite:mysite.core:1.0.0-SNAPSHOT: Usage of deprecated package found : org.apache.sling.settings : Avoid these features at runtime: run modes, file system access (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | 是 | 是 |
| `artifact-rules` | 驗證套件組合和內容套件等相依性，以防止成品出現已知問題。<p> </p>`[WARNING] [artifact-rules] com.adobe.acs:acs-aem-commons-bundle:5.0.4: Use at least version 5.0.10 (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | 是 | 是 |
| `aem-env-var` | 根據[變數命名指南](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#variable-naming)檢查環境變數的使用方式<p> </p>`[ERROR] Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Value for property 'port' must not use env vars prefixed with INTERNAL_ or ADOBE_ (com.mysite1:my-site-1.all:1.0.0-SNAPSHOT\|com.mysite1:my-site-1.ui.config:1.0.0-SNAPSHOT)` | 是 | 是 |
| `content-package-validation` | 執行 Filevault 驗證工具。預設情況下，會啟用 jackrabbit-docviewparser，以檢查部署期間安裝的套件中 xml 的內容語法是否格式正確。<p> </p>`[main] WARN org.apache.sling.feature.analyser.task.impl.CheckContentPackages - ValidationViolation: "jackrabbit-docviewparser: Invalid XML found: The reference to entity "se" must end with the ';' delimiter.", filePath=jcr_root/apps/somename/configs/com.adobe.test.Invalid.xml, nodePath=/apps/somename/configs/com.adobe.test.Invalid`<p> </p>若要修正，請檢視分析器命名的檔案以了解 xml 問題。 | 是 | 是 |
| `aem-provider-type` | 檢查應用程式程式碼是否從 AEM (產品) 實作或擴充「ProviderType」介面/類別，請參閱[CQBP-84](https://experienceleague.adobe.com/docs/experience-manager-cloud-manager/using/how-to-use/custom-code-quality-rules.html?lang=zh-hant#product-apis-annotated-with-providertype-should-not-be-implemented-or-extended-by-customers) | 是 | 是 |
| `configurations-basic` | 檢查 OSGi 設定是否有常見錯誤，例如未指定「service.ranking」屬性的正確類型。 | 是 | 是 |

{style="table-layout:auto"}

## 已知問題

以下是使用建置分析器 Maven 外掛程式時的已知問題清單。

### 無法在本機 SDK 中執行建置分析器 Maven 外掛程式

使用的本機 SDK 如搭配版本低於 `1.1.2` 的建置分析器 Maven 外掛程式時，執行外掛程式可能會導致以下錯誤。在此情況下，請將您的專案更新至外掛程式的最新版本。

```txt
[ERROR] Failed to execute goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse (default-analyse) on project mysite.analyse: Execution default-analyse of goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse failed: arraycopy: source index -1 out of bounds for char[65536] -> [Help 1]
```

如果您使用 AEM 專案原型來設定專案，請務必調整根 Maven`pom.xml`中的屬性，如下所示。

```xml
   ...
   <properties>
      ...
      <aemanalyser.version>1.1.2</aemanalyser.version> <!-- Make sure to use the latest release -->
      ...
   </properties>
```
