---
title: AEM項目原型的核心模組
description: AEM項目原型的核心模組
translation-type: tm+mt
source-git-commit: 6f7166c46940ed451721e0760d565d58efe412ab
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 0%

---


# AEM Project Archetype {#core-module}的核心模組

核心主機模組(`<src-directory>/<project>/core`)包含實作所需的所有Java程式碼。 此模組將封裝所有Java程式碼，並以OSGi Bundle的形式部署至AEM例項。

`<src-directory>/<project>/core/pom.xml`中定義的Maven Bundle外掛程式負責將Java程式碼編譯為OSGi套件，AEM的OSGi容器可加以辨識。 請注意，這是Sling Models的定義位置。

雖然核心套件在上層環境中必須獨立於ui.apps模組進行部署的情況很少，但直接部署核心套件在本端開發／測試時很有用。 Maven Sling Plugin可讓核心套件直接部署至AEM，並運用[父POM](/help/developing/archetype/using.md#parent-pom)中定義的`autoInstallBundle`描述檔。

```
mvn -PautoInstallBundle clean install
```

成功執行後，您應能在`http://<host>:<port>/system/console/bundles`看到Bundles Console。
