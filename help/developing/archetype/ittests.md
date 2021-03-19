---
title: it.tests項目原型AEM模組
description: 項目原型集AEM成測試的使用
feature: 核心元件，AEM專案原型
role: 架構師、開發人員、管理員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 0%

---


# it.tests Project Archetype AEM {#ittests-module}的模組

項目包含三個測試級別：

* [設備測試](core.md#unit-tests)
* 整合測試
* [UI測試](uitests.md)

本文說明it.tests模組中提供的整合測試。

## 執行整合測試{#running-tests}

伺服器端整合測試可讓類似裝置的測試在AEM環境（即伺服器）中執AEM行。 要測試，請執行：

```
mvn clean verify -PintegrationTests
```
