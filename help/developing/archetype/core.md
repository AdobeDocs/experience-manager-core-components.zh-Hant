---
title: AEM專案原型的核心模組
description: AEM專案原型的核心模組
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 49e80d8c-2b41-4c42-b45e-c2e3b4b16a59
source-git-commit: 531a7858dd26d32ef189c459c5e7035b6ae0b524
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# AEM專案原型的核心模組 {#core-module}

核心maven模組(`<src-directory>/<project>/core`)包含實作所需的所有Java程式碼。 此模組會封裝所有Java程式碼，並以OSGi套件的形式部署至AEM執行個體。

在中定義的Maven套件外掛程式 `<src-directory>/<project>/core/pom.xml` 負責將Java程式碼編譯成可由AEM OSGi容器識別的OSGi套件組合。 請注意，這是Sling模型的定義位置。

雖然在上層環境中很少需要獨立於ui.apps模組部署核心套件組合，但在本機開發/測試期間直接部署核心套件組合會很有用。 Maven Sling外掛程式允許直接利用將核心套件組合部署到AEM `autoInstallBundle` 設定檔定義 [父級POM](/help/developing/archetype/using.md#parent-pom).

```shell
mvn -PautoInstallBundle clean install
```

在成功執行後，您應該可以在以下位置檢視套件組合主控台： `http://<host>:<port>/system/console/bundles`.

## 單元測試 {#unit-tests}

核心模組中的單元測試會展示套件組合中包含之程式碼的典型單元測試。 若要測試，請執行：

```shell
mvn clean test
```
