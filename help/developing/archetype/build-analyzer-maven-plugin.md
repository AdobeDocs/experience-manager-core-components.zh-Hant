---
title: 作AEM為Cloud ServiceSDK Build Analyzer Maven Plugin
description: 本機Maven組建分析器外掛程式的檔案
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 3%

---


# 作AEM為Cloud ServiceSDK Build Analyzer Maven Plugin {#maven-analyzer-plugin}

作為AEMCloud ServiceSDK Build Analyzer Maven Plugin，可以分析各種內容套件專案的結構。

如需如何將Maven Plugin納入主專案的詳細資訊，請參閱[Maven Plugin檔案&lt;a1/AEM>。](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md)

>[!NOTE]
>
>建議您更新Maven專案，以參考Maven中央儲存庫中的最新版本外掛程式，位於以下位置：https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/

下表說明在此步驟中執行的分析器。<!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| 模組 | 函式、範例與疑難排解 | 本機SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | 檢查所有OSGI捆綁包是否都有其Import-Package聲明，該聲明由Maven項目中其它包含的捆綁包的Export-package聲明滿足。 錯誤如下： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>若要疑難排解，請查看提供套件的套件是否包含在部署中，或查看您預期要匯出的套件資訊清單，以判斷使用的是錯誤名稱或錯誤版本。 | 是 | 是 |
| `requirements-capabilities` | 檢查在OSGI捆綁包中建立的所有要求聲明是否由Maven項目中包含的其他捆綁包的功能聲明滿足。 錯誤如下： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> 若要疑難排解，請查看您預期會宣告其遺失功能之套件清單，或檢查要求套件清單以確認其中的要求正確。 | 是 | 是 |
| `bundle-content` | 如果套件包含以Sling-Initial-Content指定的初始內容，則會發出警告，這在以Cloud Service叢集環AEM境的形式出現問題。 警告如下所示： <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>若要疑難排解將初始內容轉換為重新指向陳述，請參閱重新指向檔案。 | 是 | 是 |
| `bundle-resources` | 如果Bundle包含Sling-Bundle-Resources標題所指定的資源，則會發出警告，這在作為AEMCloud Service叢集環境時會有問題。 警告如下所示：<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> 若要疑難排解將資源轉換為重新指向陳述，請參閱[重新指向檔案](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init)。 | 是 | 是 |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | 這些分析器會檢查與[content package to feature model conversion process](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying)相關的一些詳細資訊，以建立符合Sling Feature Model的工件。 任何錯誤都應報告給Adobe客戶支援。 | 是 | 是 |
| `api-regions-crossfeature-dups` | 驗證客戶OSGI搭售沒有Export-package宣告，會覆寫AEM為Cloud Service的公用API<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>若要修正，請停止匯出屬於公用API一部分的AEM套件。 | 是 | 是 |
| `repoinit` | 檢查所有重新指向節的語法 | 是 | 是 |
| `bundle-nativecode` | 驗證OSGI搭售未安裝原生程式碼。 | 是 | 是 |