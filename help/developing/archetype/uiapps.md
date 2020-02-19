---
title: AEM Project Archetype的ui.apps模組
description: AEM Project Archetype的ui.apps模組
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# AEM Project Archetype的ui.apps模組 {#uiapps-module}

ui.apps maven模組(`<src-directory>/<project>/ui.apps`)包含網站下方所需的所有轉譯程式碼 `/apps`。 這包括將儲存為AEM格式（稱為clientlibs）的CSS/JS。 這也包含用於轉譯動態HTML的HTL指令碼。 您可以將ui.apps模組視為JCR中結構的映射，但格式可儲存在檔案系統並提交至來源控制項。

Apache Jackrabbit FileVault Package外掛程式可用來將ui.apps模組的內容編譯為可部署至AEM的AEM套件。 外掛程式的全域組態是在pom.xml父項中定義。

## 父POM {#parent-pom}

[父POM](overview.md#parent-pom) (`<src>/<project>/pom.xml`)包括 `<plugin>` 為項目中使用的插件定義各種配置的部分。 這包括Jackrabbit FileVault Package Plugin `filterSource` 的組態。 指 `filterSource` 向用於定義包 `filter.xml` 括在包中的jcr路徑的檔案的位置。

除了Jackrabbit FileVault Package Plugin外，Content Package Plugin也是其定義，用來將套件推送至AEM。 請注意，使 `aem.host`用的變 `aem.port`量、 `vault.user``vault.password` 、和的變數與同一父POM中定義的全局屬性相對應。

## ui.apps/pom.xml {#uiapps-pom}

ui.apps pom(`<src>/<project>/ui.apps/pom.xml`)提供 `embedded` 的標籤 `filevault-package-maven-plugin`。 標 `embedded` 記包含編譯的核心套件，做為ui.apps套件的一部分，以及安裝它的位置。

請注意，core.wcm.components.all和core.wcm.components.examples套件都包含為子套件。 每次都會部署核心元件套件和WKND程式碼。

core.wcm.components.all和core.wcm.components.examples作為從屬關係清單中的從屬關係包括在內。 但是，作為最佳做法，此處省略了相關性的版本，並在父pom檔案中 [進行管理](overview.md#core-components)。

## filter.xml {#filter}

ui. `filter.xml` apps模組的檔案位於，並 `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` 包含將隨ui.apps套件一起包含和安裝的路徑。
