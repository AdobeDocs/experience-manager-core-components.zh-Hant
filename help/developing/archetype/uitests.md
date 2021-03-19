---
title: 項目原型的AEMui.tests模組
description: 如何使用專AEM案原型UI測試
feature: 核心元件，AEM專案原型
role: 架構師、開發人員、管理員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 0%

---


# ui.tests專案原AEM型{#uitests-module}的模組

項目包含三個測試級別：

* [設備測試](core.md#unit-tests)
* [整合測試](ittests.md)
* UI測試

本文說明UI測試是ui.tests模組的一部分。

## 執行UI測試{#running-tests}

要測試，請執行：

```shell
mvn verify -Pui-tests-local-execution
```

執行後，`target/reports`資料夾中會提供報表和記錄檔。

## 其他選項{#additional-options}

UI測試可使用許多不同的選項執行，包括針對本機瀏覽器和Docker影像進行無頭測試。 如需詳細資訊，請參閱ui.tests模組](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests)的[README.md檔案。
