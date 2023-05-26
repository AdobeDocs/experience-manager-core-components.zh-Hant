---
title: AEMas a Cloud ServiceSDK建置分析器Maven外掛程式
description: 本機Maven組建分析器外掛程式的檔案
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: de26b310-a294-42d6-a0db-91f6036a328c
source-git-commit: 60ec9c1643abce0ee75da5368269928476390440
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 4%

---

# AEMas a Cloud ServiceSDK建置分析器Maven外掛程式 {#maven-analyzer-plugin}

AEMas a Cloud ServiceSDK Build Analyzer Maven外掛程式會分析各種內容套件專案的結構。

請參閱 [Maven外掛程式檔案](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md) 瞭解如何將其納入AEM maven專案。

>[!NOTE]
>
>建議您更新Maven專案，以在下列位置參考Maven中央存放庫中最新版本的外掛程式： https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/

外掛程式使用最新可用的SDK，而不是專案中設定的SDK。

下表說明在此步驟中執行的分析器。 <!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| 模組 | 函式、範例及疑難排解 | 本機 SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | 檢查所有OSGI套件組合的Import-Package宣告是否由Maven專案中其他包含套件組合的Export-package宣告滿足。 錯誤可能如下所示： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>若要進行疑難排解，請檢視提供套件的套件是否包含在部署中，或檢視您預期匯出的套件資訊清單，以判斷是否使用了錯誤的名稱或錯誤的版本。 | 是 | 是 |
| `bundle-unversioned-packages` | 檢查OSGi套件組合是否指定了含有匯出套件宣告的版本和含有匯入套件宣告的版本範圍。 錯誤可能如下所示： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is exporting package org.acme.foo without a version.`<p> </p>若要進行疑難排解，請務必新增 `package-info.java` 至該封裝，指定要匯出的版本。 | 是 | 是 |
| `requirements-capabilities` | 檢查OSGI套件組合中提出的所有需求宣告是否由Maven專案中包含的其他套件組合的功能宣告滿足。 錯誤可能如下所示： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> 若要進行疑難排解，請檢視您預期宣告功能的套件資訊清單，以判斷為何遺失該套件，或檢查所需套件的資訊清單，以檢視中的需求是否正確。 | 是 | 是 |
| `bundle-content` | 如果套件包含使用Sling-Initial-Content指定的初始內容，而這些內容在AEMas a Cloud Service叢集環境中有問題，則會提出警告。 警告看起來像這樣： <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>若要疑難排解將初始內容轉換為repoinit陳述式，請參閱Repoinit檔案。 | 是 | 是 |
| `bundle-resources` | 如果套件包含以Sling-Bundle-Resources標頭指定的資源，而這些資源在AEMas a Cloud Service叢集環境中有問題，則會提出警告。 警告看起來像這樣：<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> 若要疑難排解將資源轉換為repoinit陳述式，請參閱 [Repoinit檔案](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init). | 是 | 是 |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | 這些分析器會檢查與 [從內容套件轉換到功能模型的程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying) 建立符合Sling功能模型的成品。 應向Adobe客戶支援報告任何錯誤。 | 是 | 是 |
| `api-regions-crossfeature-dups` | 驗證客戶OSGI套件組合沒有會覆寫AEMas a Cloud Service公用API的Export-package宣告<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>若要修正，請停止匯出屬於AEM公用API的套件。 | 是 | 是 |
| `repoinit` | 檢查所有repoinit區段的語法 | 是 | 是 |
| `bundle-nativecode` | 驗證OSGI套件組合沒有安裝原生程式碼。 | 是 | 是 |
| `configuration-api` | 驗證重要的OSGi設定。 <p> </p> `Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Configuration is not allowed (com.mysite:mysite.all:1.0.0-SNAPSHOT\|com.mysite:mysite.ui.config:1.0.0-SNAPSHOT)` | 是 | 是 |
| `region-deprecated-api` | 檢查是否 [已棄用的api](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-apis.html) 已使用 <p> </p>`[WARNING] com.mysite:mysite.core:1.0.0-SNAPSHOT: Usage of deprecated package found : org.apache.sling.settings : Avoid these features at runtime: run modes, file system access (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | 是 | 是 |
| `artifact-rules` | 驗證套件組合和內容套件等相依性，以防止成品出現已知問題。<p> </p>`[WARNING] [artifact-rules] com.adobe.acs:acs-aem-commons-bundle:5.0.4: Use at least version 5.0.10 (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | 是 | 是 |
| `aem-env-var` | 根據環境變數的使用情況檢查 [變數命名指南](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#variable-naming)<p> </p>`[ERROR] Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Value for property 'port' must not use env vars prefixed with INTERNAL_ or ADOBE_ (com.mysite1:my-site-1.all:1.0.0-SNAPSHOT\|com.mysite1:my-site-1.ui.config:1.0.0-SNAPSHOT)` | 是 | 是 |
| `content-package-validation` | 執行Filevault驗證器。 依預設，會啟用jackrabbit-docviewparser，以檢查將在部署期間安裝的套件中xml的格式正確的內容語法。<p> </p>`[main] WARN org.apache.sling.feature.analyser.task.impl.CheckContentPackages - ValidationViolation: "jackrabbit-docviewparser: Invalid XML found: The reference to entity "se" must end with the ';' delimiter.", filePath=jcr_root/apps/somename/configs/com.adobe.test.Invalid.xml, nodePath=/apps/somename/configs/com.adobe.test.Invalid`<p> </p>若要修正，請檢視分析器命名的檔案以瞭解xml問題。 | 是 | 是 |

{style="table-layout:auto"}

## 已知問題

以下是使用Build Analyzer Maven外掛程式時的已知問題清單。

### 無法在本機SDK中執行組建分析器Maven外掛程式

搭配使用本機SDK時，組建分析器Maven外掛程式版本低於 `1.1.2`，執行外掛程式可能會導致以下錯誤。 在此情況下，請將您的專案更新至外掛程式的最新版本。

```txt
[ERROR] Failed to execute goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse (default-analyse) on project mysite.analyse: Execution default-analyse of goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse failed: arraycopy: source index -1 out of bounds for char[65536] -> [Help 1]
```

如果您使用AEM專案原型來設定專案，請務必調整根Maven中的屬性 `pom.xml` 如下所述。

```xml
   ...
   <properties>
      ...
      <aemanalyser.version>1.1.2</aemanalyser.version> <!-- Make sure to use the latest release -->
      ...
   </properties>
```
