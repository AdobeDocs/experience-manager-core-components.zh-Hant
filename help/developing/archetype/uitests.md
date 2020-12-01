---
title: ui.tests AEM Project Archetype模組
description: 如何使用AEM Project Archetype JUnit測試
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---


# ui.tests AEM Project Archetype {#uitests-module}的模組

項目包含三個測試級別：

## 設備測試{#unit-tests}

[核心模組](core.md)中的單元測試展示了套件中包含的代碼的經典單元測試。 要測試，請執行：

```
mvn clean test
```

## 整合測試{#integration-tests}

伺服器端整合測試可讓裝置式測試在AEM環境（即AEM伺服器）中執行。 要測試，請執行：

```
mvn clean verify -PintegrationTests
```

## 用戶端測試{#client-side-tests}

`client-side Hobbes.js`測試是以JavaScript為基礎的瀏覽器端測試，可驗證瀏覽器端行為。

若要測試，在瀏覽器中檢視您要測試的AEM頁面時，請開啟左側面板並切換至「測試」標籤，以「**開發人員模式」**&#x200B;開啟頁面，並尋找產生的&#x200B;**MyName測試**&#x200B;並執行它們。****
