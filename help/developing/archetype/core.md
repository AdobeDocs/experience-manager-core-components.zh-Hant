---
title: 項目原型的AEM核心模組
description: 項目原型的AEM核心模組
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 49e80d8c-2b41-4c42-b45e-c2e3b4b16a59
source-git-commit: 531a7858dd26d32ef189c459c5e7035b6ae0b524
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# 項目原型的AEM核心模組 {#core-module}

核心主機模組(`<src-directory>/<project>/core`)包含實現所需的所有Java代碼。 該模組將打包所有Java代碼並作為OSGi包AEM部署到實例中。

在 `<src-directory>/<project>/core/pom.xml` 負責將Java代碼編譯到OSGi包中，OSGi容器可以識AEM別該包。 請注意，這是定義「吊具模型」的位置。

雖然在上級環境中需要獨立於ui.apps模組部署核心捆綁包的情況很少，但直接部署核心捆綁包在本地開發/測試期間非常有用。 Maven Sling插件允許部署核心捆綁包以直AEM接利用 `autoInstallBundle` 定義的配置檔案 [父POM](/help/developing/archetype/using.md#parent-pom)。

```shell
mvn -PautoInstallBundle clean install
```

成功執行後，您應能在 `http://<host>:<port>/system/console/bundles`。

## 設備Test {#unit-tests}

核心模組中的單元test展示了對包中代碼的經典單元測試。 要test，請執行：

```shell
mvn clean test
```
