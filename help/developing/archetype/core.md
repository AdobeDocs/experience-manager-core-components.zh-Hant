---
title: 項目原型的核AEM心模組
description: 項目原型的核AEM心模組
feature: 核心元件，AEM專案原型
role: 架構師、開發人員、管理員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---


# 項目原型AEM的核心模組{#core-module}

核心主機模組(`<src-directory>/<project>/core`)包含實作所需的所有Java程式碼。 該模組將封裝所有Java代碼並作為OSGi BundleAEM部署到實例中。

`<src-directory>/<project>/core/pom.xml`中定義的Maven Bundle外掛程式負責將Java程式碼編譯為OSGi套件，讓OSGi容器可AEM以辨識。 請注意，這是Sling Models的定義位置。

雖然核心套件在上層環境中必須獨立於ui.apps模組進行部署的情況很少，但直接部署核心套件在本端開發／測試時很有用。 Maven Sling Plugin可讓核心套件部署AEM，直接運用`autoInstallBundle`描述檔，如[父POM](/help/developing/archetype/using.md#parent-pom)中所定義。

```shell
mvn -PautoInstallBundle clean install
```

成功執行後，您應能在`http://<host>:<port>/system/console/bundles`看到Bundles Console。

##  設備測試{#unit-tests}

核心模組中的單元測試展示了對包中代碼的經典單元測試。 要測試，請執行：

```shell
mvn clean test
```
