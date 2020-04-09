---
title: 核心元件的成功途徑
description: 如何使用核心元件實作專案時獲得成功
translation-type: tm+mt
source-git-commit: c338428a681f652d17bb972fb6a2abf216a338c3

---


# 核心元件的成功途徑 {#paths-to-success}

核心元件功能強大、靈活，而且易於使用和自訂。 遵循本檔案中概述的幾項主要准則，可確保您的核心元件專案成功。

## 成功的兩條途徑 {#two-paths}

執行核心部分有兩種基本方法，這可以帶來成功，但需要逐個項目來考慮它們各自的權衡取捨。

1. 將您的設計對應至核心元件，並取得其提供的HTML。 或
1. 如果您必須符合已定義的HTML標準，則需要付出更多努力，而不是取得核心元件的所有優點。

## 元件實作中的常見缺陷 {#common-pitfalls}

導致項目無法成功使用核心元件的兩個常見問題是：

* **已完成的設計** -這些設計甚至可能經過C級批准，並交給開發團隊，以便在不考慮基礎技術的情況下實施像素精確的設計。
* **全公司的HTML樣式指南** -此類參考線通常必須遵循從上到下角度套用樣式的元件。

在這兩種情況下，對元件的要求都非常嚴格且特別，所以很難讓核心元件或任何現成可用的元件符合它們，導致大量開發自訂元件。

## 提早開始 {#start-early}

在您的專案實施階段，您不必只考慮核心元件，而是從核心元件開始，線上架構和設計階段。

### 使用元件庫 {#component-library}

參考已 [經處於設計階段的「元件庫](https://adobe.com/go/aem_cmp_library) 」(Component Library)。 核心元件功能強大且有彈性，可讓您從頭開始。 只有當真正有業務需求且無法透過核心元件合理達成時，才能新增自訂元件。

### 使用Adobe XD的UI套件 {#ui-kit}

一旦對自訂元件有證實可行的需求，就可運用Adobe XD [](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd) UI Kit，讓設計人員開始以核心元件為建置區塊來建立線框和設計。

## 不要忽略強大的功能 {#powerful-features}

AEM和核心元件的功能可能非常強大，但也非常微妙，而設計人員可能無法立即看出某些功能的可能性。

### 內容片段 {#content-fragments}

[內容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) 可讓您建立不受頻道影響的內容，以及（可能是特定頻道的）變化。 然後，您可以在製作內容頁面時使用這些片段及其變化。

結合更新的JSON匯出器，結構化內容片段也可用來透過Content Services將AEM內容傳送至AEM頁面以外的通道。

### 體驗片段範本 {#experience-fragment-templates}

如果作者想要重複使用頁面的部分（體驗的片段）。 沒有 [體驗片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html) ，作者將需要複製並貼上該片段。 建立和維護這些複製／貼上體驗不但耗時，而且容易發生使用者錯誤。 體驗片段可免除複製／貼上的需求。

### 內嵌元件 {#embed-component}

[內嵌元件](/help/components/embed.md) 不僅可簡單包含外部資源，例如YouTube視訊內容，而且可擴充，以容納專案特定的內容。