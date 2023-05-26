---
title: AEM專案原型的ui.tests模組
description: 如何使用AEM專案原型UI測試
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: eb3c9b34-f10e-410f-bcf3-34f94f124c7c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 8%

---

# AEM專案原型的ui.tests模組 {#uitests-module}

專案包含三個層級的測試：

* [單元測試](core.md#unit-tests)
* [整合測試](ittests.md)
* UI測試

本文說明作為ui.tests模組的一部分提供的UI測試。

## 執行UI測試 {#running-tests}

若要測試，請執行：

```shell
mvn verify -Pui-tests-local-execution
```

執行後，報告和記錄可用於 `target/reports` 資料夾。

## 其他選項 {#additional-options}

UI測試可以使用許多不同的選項執行，包括對本地瀏覽器的無標題測試和作為Docker映像。 請參閱 [ui.tests模組的README.md檔案](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests) 以取得進一步資訊。
