---
title: it.tests AEM Project Archetype模組
description: 如何使用AEM Project原型整合測試
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---


# it.tests AEM Project Archetype {#ittests-module}的模組

項目包含三個測試級別：

* [設備測試](core.md#unit-tests)
* 整合測試
* [UI測試](uitests.md)

本文說明it.tests模組中提供的整合測試。

## 執行整合測試{#running-tests}

伺服器端整合測試可讓裝置式測試在AEM環境（即AEM伺服器）中執行。 要測試，請執行：

```
mvn clean verify -PintegrationTests
```
