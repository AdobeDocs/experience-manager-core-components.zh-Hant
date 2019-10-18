---
title: AEM項目原型的核心模組
seo-title: AEM項目原型的核心模組
description: AEM項目原型的核心模組
seo-description: AEM項目原型的核心模組
contentOwner: 博納特
content-type: 引用
topic-tags: 核心元件
translation-type: tm+mt
source-git-commit: 0a61f4e6d1ad8b4d5e3778018838dc70d496e1fc

---


# AEM項目原型的核心模組 {#core-module}

核心主控模組(`<src-directory>/<project>/core`)包含實作所需的所有Java程式碼。 此模組將封裝所有Java程式碼，並以OSGi Bundle的形式部署至AEM例項。

定義於中的Maven Bundle外掛程式 `<src-directory>/<project>/core/pom.xml` 負責將Java程式碼編譯為OSGi套件，AEM的OSGi容器可辨識。 請注意，這是Sling Models的定義位置。

雖然核心套件在上層環境中必須獨立於ui.apps模組進行部署的情況很少，但直接部署核心套件在本端開發／測試時很有用。 Maven Sling Plugin可讓核心套件直接部署至AEM，並運用父POM中 `autoInstallBundle` 定義的描述 [檔](archetype.md#parent-pom)。

```
mvn -PautoInstallBundle clean install
```

成功執行後，您應該可以在上查看Bundels Console `http://<host>:<port>/system/console/bundles`。
