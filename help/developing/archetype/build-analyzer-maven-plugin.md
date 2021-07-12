---
title: AEM as a Cloud ServiceSDK組建Analyzer Maven外掛程式
description: 本機Maven建置分析器外掛程式的檔案
feature: 核心元件、AEM專案原型
role: Architect, Developer, Admin
exl-id: de26b310-a294-42d6-a0db-91f6036a328c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 4%

---

# AEM as a Cloud ServiceSDK組建Analyzer Maven外掛程式 {#maven-analyzer-plugin}

AEM as a Cloud ServiceSDK建置分析器Maven外掛程式會分析各種內容套件專案的結構。

如需如何將Maven外掛程式納入AEM Maven專案的相關資訊，請參閱[Maven外掛程式檔案](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md)。

>[!NOTE]
>
>建議您更新Maven專案，以參考Maven中央存放庫中此位置的最新外掛程式版本：https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/

外掛程式會使用最新可用的SDK，而非專案中設定的SDK。

下表說明在此步驟中執行的分析器。<!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| 模組 | 函式、範例和疑難排解 | 本機SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | 檢查所有OSGI套件組合是否都有其Import-Package聲明由Maven項目中其他包含套件組合的Export-package聲明滿足。 錯誤看起來會像這樣： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>若要進行疑難排解，請查看提供套件的套件組合是否包含在部署中，或查看您要匯出的套件組合資訊清單，以判斷使用的名稱是否錯誤或版本是否錯誤。 | 是 | 是 |
| `requirements-capabilities` | 檢查在OSGI套件組合中生成的所有要求聲明是否由Maven項目中包含的其他套件組合的功能聲明滿足。 錯誤看起來會像這樣： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> 若要進行疑難排解，請查看您希望聲明功能以確定為何缺少該功能的套件清單，或檢查需要套件的清單，以確認其中的要求正確。 | 是 | 是 |
| `bundle-content` | 如果套件組合包含以Sling-Initial-Content指定的初始內容，則會發出警告，這在AEM做為Cloud Service叢集環境時會造成問題。 警告看起來像這樣： <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>若要疑難排解將初始內容轉換為重新指向陳述式，請參閱重新指向檔案。 | 是 | 是 |
| `bundle-resources` | 如果套件組合包含以Sling-Bundle-Resources標題指定的資源，則會發出警告，這在作為Cloud Service叢集環境的AEM中會造成問題。 警告看起來像這樣：<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> 若要疑難排解將資源轉換為重新指向陳述式，請參閱[重新指向檔案](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init)。 | 是 | 是 |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | 這些分析器會檢查與[內容套件相關的一些詳細資訊，這些套件用於建立符合Sling功能模型的成品的特徵模型轉換程式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying)。 應將任何錯誤報告給Adobe客戶支援。 | 是 | 是 |
| `api-regions-crossfeature-dups` | 驗證客戶OSGI套件組合沒有可覆寫AEM作為Cloud Service公用API的匯出套件宣告<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>若要修正，請停止匯出屬於AEM公用API一部分的套件。 | 是 | 是 |
| `repoinit` | 檢查所有重新指向節的語法 | 是 | 是 |
| `bundle-nativecode` | 驗證OSGI套件組合不安裝原生程式碼。 | 是 | 是 |
| `configuration-api` | 驗證重要的OSGi設定。 <p> </p> `Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Configuration is not allowed (com.mysite:mysite.all:1.0.0-SNAPSHOT\|com.mysite:mysite.ui.config:1.0.0-SNAPSHOT)` | 是 | 是 |
| `region-deprecated-api` | 檢查是否使用[已棄用的api](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-apis.html) <p> </p>`[WARNING] com.mysite:mysite.core:1.0.0-SNAPSHOT: Usage of deprecated package found : org.apache.sling.settings : Avoid these features at runtime: run modes, file system access (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | 是 | 是 |

