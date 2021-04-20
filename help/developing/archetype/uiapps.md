---
title: 專案原型的ui.appsAEM模組
description: 專案原型的ui.appsAEM模組
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%

---


# 專案原型{#uiapps-module}AEM的ui.apps模組

ui.apps maven模組(`<src-directory>/<project>/ui.apps`)包含`/apps`下方網站所需的所有轉換程式碼。 這包括將儲存為[clientlibsAEM格式的CSS/JS。](uifrontend.md#clientlibs) 這也包含用於轉譯動態HTML的HTL指令碼。您可以將ui.apps模組視為JCR中結構的映射，但格式可儲存在檔案系統並提交至來源控制項。

Apache Jackrabbit FileVault Package外掛程式可用來將ui.apps模組的內容編譯為可部AEM署至的套件AEM。 外掛程式的全域組態是在pom.xml父項中定義。

## 父POM {#parent-pom}

[父POM](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`)包 `<plugin>` 括定義項目中使用的插件的各種配置的部分。這包括Jackrabbit FileVault Package Plugin的`filterSource`組態。 `filterSource`指向`filter.xml`檔案的位置，該檔案用於定義包中包含的jcr路徑。

除了Jackrabbit FileVault Package Plugin外，Content Package Plugin也是用來將套件推送至其中的定義AEM。 請注意，`aem.host`、`aem.port`、`vault.user`和`vault.password`的變數會與相同父POM中定義的全域屬性相對應。

## ui.apps/pom.xml {#uiapps-pom}

ui.apps pom(`<src>/<project>/ui.apps/pom.xml`)提供`filevault-package-maven-plugin`的`embedded`標籤。 `embedded`標籤包含編譯的核心套件，做為ui.apps套件的一部分，並將安裝在其中。

請注意，core.wcm.components.all和core.wcm.components.examples套件都包含為子套件。 每次都會部署核心元件套件和WKND程式碼。

core.wcm.components.all和core.wcm.components.examples作為從屬關係清單中的從屬關係包括在內。 但是，作為最佳做法，此處省略了相關性的版本，並在[父pom檔案](/help/developing/archetype/using.md#core-components)中管理這些版本。

## filter.xml {#filter}

ui.apps模組的`filter.xml`檔案位於`<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml`，並包含將隨ui.apps套件一起包含和安裝的路徑。
