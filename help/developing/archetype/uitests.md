---
title: ui.tests AEM Project Archetype模組
description: 如何使用AEM Project原型UI測試
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---


# ui.tests AEM Project Archetype {#uitests-module}的模組

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
