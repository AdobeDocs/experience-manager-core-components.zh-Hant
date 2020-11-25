---
title: AEM as a Cloud Service SDK Build Analyzer Maven Plugin
description: 本機Maven組建分析器外掛程式的檔案
translation-type: tm+mt
source-git-commit: a58434ebf7ae72472989f2e55d40bfa22fd99208
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 3%

---


# AEM as a Cloud Service SDK Build Analyzer Maven Plugin {#maven-analyzer-plugin}

AEM Analyzer Maven增效模組會分析各種內容套件專案的結構。

如需如 [何將AEM Analyzer Maven Plugin專案包含在AEM Maven專案中的詳細資訊](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md) ，請參閱AEM Analyzer Maven Plugin檔案。

下表說明在此步驟中執行的分析器。 請注意，有些會在本機SDK中執行，而有些則只會在Cloud Manager管道部署期間執行。

| 模組 | 函式、範例與疑難排解 | 本機SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | 檢查所有OSGI捆綁包是否都有其Import-Package聲明，該聲明由Maven項目中其它包含的捆綁包的Export-package聲明滿足。 錯誤如下： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>若要疑難排解，請查看提供套件的套件是否包含在部署中，或查看您預期要匯出的套件資訊清單，以判斷使用的是錯誤名稱或錯誤版本。 | 是 | 是 |
| `requirements-capabilities` | 檢查在OSGI捆綁包中建立的所有要求聲明是否由Maven項目中包含的其他捆綁包的功能聲明滿足。 錯誤如下： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> 若要疑難排解，請查看您預期會宣告其遺失功能之套件清單，或檢查要求套件清單以確認其中的要求正確。 | 是 | 是 |
| `bundle-content` | 如果搭售包含以Sling-Initial-Content指定的初始內容，則會發出警告，這在AEM中是Cloud Service叢集環境。 警告如下所示： <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>若要疑難排解將初始內容轉換為重新指向陳述，請參閱重新指向檔案。 | 是 | 是 |
| `bundle-resources` | 如果Bundle包含以Sling-Bundle-Resources標題指定的資源，則會發出警告，這在AEM中會成為Cloud Service叢集環境。 警告如下所示：<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> 若要疑難排解將資源轉換為重新指向陳述，請參 [閱重新指向檔案](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init)。 | 是 | 是 |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | 這些分析者會檢查功能中API區域設定的相關詳細資訊。 對於客戶，API地區設定是由他們產生而非直接指定，因此這些分析器會啟用，因為它們也會在AEMaCS中啟用。 但是，這些程式碼產生的故障，表示內容封裝中出現錯誤，導致功能模型轉換程式發生錯誤。 | 是 | 是 |
| `api-regions-crossfeature-dups` | 驗證客戶OSGI搭售沒有將AEM覆寫為雲端服務之公開API的Export-package宣告<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>若要修正，請停止匯出屬於AEM公用API一部分的套件。 | 是 | 是 |