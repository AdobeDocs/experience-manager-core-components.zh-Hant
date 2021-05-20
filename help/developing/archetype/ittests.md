---
title: it.tests模組的AEM項目原型
description: 如何使用AEM專案原型整合測試
feature: 核心元件、AEM專案原型
role: Architect, Developer, Administrator
exl-id: 0abc0265-3a3f-4323-97e6-3af0c62299ef
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 0%

---

# it.tests AEM專案原型{#ittests-module}的模組

項目中包含三個級別的測試：

* [單元測試](core.md#unit-tests)
* 整合測試
* [UI測試](uitests.md)

本文說明it.tests模組中可用的整合測試。

## 運行整合測試{#running-tests}

伺服器端整合測試可讓類似單元的測試在AEM環境(即AEM伺服器)中執行。 要測試，請執行：

```
mvn clean verify -PintegrationTests
```
