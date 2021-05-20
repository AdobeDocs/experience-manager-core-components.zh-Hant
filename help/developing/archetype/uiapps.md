---
title: AEM專案原型的ui.apps模組
description: AEM專案原型的ui.apps模組
feature: 核心元件、AEM專案原型
role: Architect, Developer, Administrator
exl-id: fc63a19a-3253-44ee-96e2-bb5544c2235b
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# AEM專案原型的ui.apps模組{#uiapps-module}

ui.apps maven模組(`<src-directory>/<project>/ui.apps`)包含`/apps`下方網站所需的所有轉譯程式碼。 這包括將以名為[clientlibs的AEM格式儲存的CSS/JS。](uifrontend.md#clientlibs) 這也包含轉譯動態HTML的HTL指令碼。您可以將ui.apps模組視為JCR中結構的對應，但格式可儲存在檔案系統上並提交至原始碼控制項。

Apache Jackrabbit FileVault套件外掛程式用於將ui.apps模組的內容編譯為可部署至AEM的AEM套件。 外掛程式的全域設定是在上層pom.xml中定義。

## 父POM {#parent-pom}

[父POM](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`)包含區段， `<plugin>` 這些區段會為專案中使用的外掛程式定義各種設定。這包括Jackrabbit FileVault套件外掛程式的`filterSource`設定。 `filterSource`指向`filter.xml`檔案的位置，該檔案用於定義包中包含的jcr路徑。

除了Jackrabbit FileVault套件外掛程式外，還有內容套件外掛程式的定義，用於將套件推送至AEM。 請注意，使用`aem.host`、`aem.port`、`vault.user`和`vault.password`的變數時，會與相同父POM中定義的全域屬性相對應。

## ui.apps/pom.xml {#uiapps-pom}

ui.apps pom(`<src>/<project>/ui.apps/pom.xml`)提供`filevault-package-maven-plugin`的`embedded`標籤。 `embedded`標籤包含編譯的核心套件組合，此套件是ui.apps套件的一部分，且將安裝於其中。

請注意，core.wcm.components.all和core.wcm.components.examples套件是以子套件的形式包含。 每次都會部署核心元件套件及WKND程式碼。

core.wcm.components.all和core.wcm.components.examples在相依性清單中包含為相依性。 不過，根據最佳實務，此處會忽略相依性的版本，並在[父pom檔案](/help/developing/archetype/using.md#core-components)中進行管理。

## filter.xml {#filter}

ui.apps模組的`filter.xml`檔案位於`<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml`，其中包含將隨ui.apps套件一併安裝的路徑。
