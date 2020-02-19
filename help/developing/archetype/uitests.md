---
title: ui.tests AEM Project Archetype模組
description: 如何使用AEM Project Archetype JUnit測試
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# ui.tests AEM Project Archetype模組 {#uitests-module}

項目包含三個測試級別：

## 設備測試 {#unit-tests}

核心模組中的單元 [測試](core.md) ，展示了對包中代碼的經典單元測試。 要測試，請執行：

```
mvn clean test
```

## 整合測試 {#integration-tests}

伺服器端整合測試可讓裝置式測試在AEM環境（即AEM伺服器）中執行。 要測試，請執行：

```
mvn clean verify -PintegrationTests
```

## 用戶端測試 {#client-side-tests}

測試 `client-side Hobbes.js` 是以JavaScript為基礎的瀏覽器端測試，可驗證瀏覽器端行為。

若要測試，在瀏覽器中檢視您要測試的AEM頁面時，請開啟左側面板並切換至「測試」標籤，然後尋找產生的「 **MyName測試********** 」並執行這些測試，以「開發人員」模式開啟頁面。
