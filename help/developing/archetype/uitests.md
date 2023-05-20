---
title: ui.test項AEM目原型
description: 如何使用項AEM目原型UITest
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: eb3c9b34-f10e-410f-bcf3-34f94f124c7c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 8%

---

# ui.test項目原AEM型模組 {#uitests-module}

項目中包含三個測試級別：

* [設備Test](core.md#unit-tests)
* [整合Test](ittests.md)
* UITest

本文介紹作為ui.test模組一部分的UItest。

## 運行UITest {#running-tests}

要test，請執行：

```shell
mvn verify -Pui-tests-local-execution
```

執行後，可在 `target/reports` 的子菜單。

## 其他選項 {#additional-options}

UItest可以使用許多不同的選項運行，包括針對本地瀏覽器和作為Docker映像進行無頭測試。 查看 [ui.test模組的README.md檔案](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests) 的上界。
