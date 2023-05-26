---
title: AEM專案原型的it.tests模組
description: 如何使用AEM專案原型整合測試
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 0abc0265-3a3f-4323-97e6-3af0c62299ef
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# AEM專案原型的it.tests模組 {#ittests-module}

專案包含三個層級的測試：

* [單元測試](core.md#unit-tests)
* 整合測試
* [UI測試](uitests.md)

本文說明整合測試，此測試屬於it.tests模組的一部分。

## 執行整合測試 {#running-tests}

伺服器端整合測試允許在AEM環境中(即AEM伺服器上)執行單元測試。 若要測試，請執行：

```
mvn clean verify -PintegrationTests
```
