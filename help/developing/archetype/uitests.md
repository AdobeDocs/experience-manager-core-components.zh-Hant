---
title: ui.tests模組的AEM專案原型
description: 如何使用AEM專案原型UI測試
feature: 核心元件、AEM專案原型
role: Architect, Developer, Administrator
exl-id: eb3c9b34-f10e-410f-bcf3-34f94f124c7c
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# ui.testsAEM專案原型{#uitests-module}的模組

項目中包含三個級別的測試：

* [單元測試](core.md#unit-tests)
* [整合測試](ittests.md)
* UI測試

本文說明ui.tests模組中可用的UI測試。

## 運行UI測試{#running-tests}

要測試，請執行：

```shell
mvn verify -Pui-tests-local-execution
```

執行後，報告和日誌可在`target/reports`資料夾中使用。

## 其他選項{#additional-options}

UI測試可以使用許多不同的選項來執行，包括針對本機瀏覽器和作為Docker影像進行無頭式測試。 如需詳細資訊，請參閱ui.tests模組](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests)的[README.md檔案。
