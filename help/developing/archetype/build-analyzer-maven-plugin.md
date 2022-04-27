---
title: AEMas a Cloud ServiceSDK生成Analyzer Maven插件
description: 本地Maven生成分析器插件的文檔
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: de26b310-a294-42d6-a0db-91f6036a328c
source-git-commit: 98d8fac2a626a1f89ef1b109aa8cba27abf8203a
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 4%

---

# AEMas a Cloud ServiceSDK生成Analyzer Maven插件 {#maven-analyzer-plugin}

as a Cloud ServiceAEM的SDK生成分析器Maven插件分析各種內容包項目的結構。

查看 [Maven插件文檔](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md) 有關如何將其包含在maven項目中AEM的資訊。

>[!NOTE]
>
>建議您更新Maven項目，以參考在Maven中央儲存庫中找到的插件的最新版本，該位置為：https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/

插件使用最新的可用SDK，而不是項目中配置的SDK。

下表描述了作為此步驟一部分執行的分析器。 <!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| 模組 | 函式、示例和故障排除 | 本地SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | 檢查所有OSGI捆綁包是否都有其「導入包」聲明符合Maven項目中其它包含捆綁包的「導出包」聲明。 錯誤將如下所示： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>要進行故障排除，請查看提供軟體包的捆綁包是否包含在部署中，或者查看您期望導出的捆綁包的清單以確定使用的名稱錯誤或版本錯誤。 | 是 | 是 |
| `requirements-capabilities` | 檢查OSGI捆綁包中的所有要求聲明是否都滿足Maven項目中包含的其他捆綁包的權能聲明。 錯誤將如下所示： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> 要進行故障排除，請查看您希望聲明功能以確定缺少該功能的捆綁包的清單，或檢查要求捆綁包的清單以查看其中的要求是否正確。 | 是 | 是 |
| `bundle-content` | 如果捆綁包包含用Sling-Initial-Content指定的初始內容，則發出警告，這在as a Cloud Service群集環境AEM中是有問題的。 警告如下： <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>要排除將初始內容轉換為重定點語句的故障，請參閱重定點文檔。 | 是 | 是 |
| `bundle-resources` | 如果捆綁包包含使用Sling-Bundle-Resources標頭指定的資源，則會發出警告，這在as a Cloud Service群集環境AEM中是有問題的。 警告如下：<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> 要排除將資源轉換為重點語句的故障，請參見 [重定位文檔](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init)。 | 是 | 是 |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | 這些分析器檢查與 [內容包到特徵模型轉換過程](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying) 建立符合「吊具特徵模型」的工件。 應將任何錯誤報告給Adobe客戶支援。 | 是 | 是 |
| `api-regions-crossfeature-dups` | 驗證客戶OSGI捆綁包沒有覆蓋as a Cloud Service的公AEM用API的Export-package聲明<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>要修復，請停止導出屬於公共API的AEM包。 | 是 | 是 |
| `repoinit` | 檢查所有重定位節的語法 | 是 | 是 |
| `bundle-nativecode` | 驗證OSGI捆綁包是否未安裝本機代碼。 | 是 | 是 |
| `configuration-api` | 驗證重要的OSGi配置。 <p> </p> `Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Configuration is not allowed (com.mysite:mysite.all:1.0.0-SNAPSHOT\|com.mysite:mysite.ui.config:1.0.0-SNAPSHOT)` | 是 | 是 |
| `region-deprecated-api` | 檢查 [棄用的api](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-apis.html) 已使用 <p> </p>`[WARNING] com.mysite:mysite.core:1.0.0-SNAPSHOT: Usage of deprecated package found : org.apache.sling.settings : Avoid these features at runtime: run modes, file system access (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | 是 | 是 |
| `artifact-rules` | 驗證依賴項（如捆綁包和內容包），以防止對象中的已知問題。<p> </p>`[WARNING] [artifact-rules] com.adobe.acs:acs-aem-commons-bundle:5.0.4: Use at least version 5.0.10 (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | 是 | 是 |
| `content-package-validation` | 執行檔案驗證器。 預設情況下，啟用jackrabbit-docviewparser，它檢查在部署期間將安裝的包內xml的格式良好的內容語法。<p> </p>`[main] WARN org.apache.sling.feature.analyser.task.impl.CheckContentPackages - ValidationViolation: "jackrabbit-docviewparser: Invalid XML found: The reference to entity "se" must end with the ';' delimiter.", filePath=jcr_root/apps/somename/configs/com.adobe.test.Invalid.xml, nodePath=/apps/somename/configs/com.adobe.test.Invalid`<p> </p>要修復，請檢查分析器命名的檔案以瞭解xml問題。 | 是 | 是 |

{style=&quot;table-layout:auto&quot;}

## 已知問題

下面是使用生成分析器Maven插件時已知問題的清單。

### 無法在本地SDK中執行生成Analyzer Maven插件

當將本地SDK與低於版本的Build AnalyzerMaven插件一起使用時 `1.1.2`，運行插件可能導致以下錯誤。 在這種情況下，請將項目更新為插件的最新版本。

```txt
[ERROR] Failed to execute goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse (default-analyse) on project mysite.analyse: Execution default-analyse of goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse failed: arraycopy: source index -1 out of bounds for char[65536] -> [Help 1]
```

如果使用「項AEM目原型」設定項目，請確保調整根Maven中的屬性 `pom.xml` 比如下面。

```xml
   ...
   <properties>
      ...
      <aemanalyser.version>1.1.2</aemanalyser.version> <!-- Make sure to use the latest release -->
      ...
   </properties>
```
