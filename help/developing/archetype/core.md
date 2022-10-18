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

核心Maven模組(`<src-directory>/<project>/core`)包含實作所需的所有Java程式碼。 模組會封裝所有Java程式碼，並以OSGi套件組合的形式部署至AEM執行個體。

Maven套件外掛程式定義於 `<src-directory>/<project>/core/pom.xml` 負責將Java程式碼編譯為可由AEM OSGi容器辨識的OSGi套件組合。 請注意，這是定義Sling模型位置的位置。

雖然核心套件組合在上層環境中需要部署時，與ui.apps模組無關的情況很少，但直接部署核心套件組合在本機開發/測試期間相當實用。 Maven Sling外掛程式可讓核心套件組合部署至AEM，直接運用 `autoInstallBundle` 設定檔，如 [父POM](/help/developing/archetype/using.md#parent-pom).

```shell
mvn -PautoInstallBundle clean install
```

成功執行後，您應該可以在 `http://<host>:<port>/system/console/bundles`.

## 單元測試 {#unit-tests}

核心模組中的單元測試會展示套件中所包含程式碼的傳統單元測試。 要測試，請執行：

```shell
mvn clean test
```
