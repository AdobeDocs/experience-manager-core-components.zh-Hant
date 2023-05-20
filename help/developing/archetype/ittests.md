---
title: it.項目原型的AEMtest模組
description: 如何利用項AEM目原型整合Test
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 0abc0265-3a3f-4323-97e6-3af0c62299ef
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# it.test項目原型AEM模組 {#ittests-module}

項目中包含三個測試級別：

* [設備Test](core.md#unit-tests)
* 整合Test
* [UITest](uitests.md)

本文介紹了it.test模組中提供的整合test。

## 運行整合Test {#running-tests}

伺服器端整合test允許在環境(即AEM在伺服器上)中運AEM行單元類test。 要test，請執行：

```
mvn clean verify -PintegrationTests
```
