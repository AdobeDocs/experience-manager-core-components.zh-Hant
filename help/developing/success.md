---
title: 使用核心元件的成功路徑
description: 使用核心元件實作專案時如何成功
role: Architect, Developer, Admin, User
exl-id: 1ea8cd1c-8435-4ded-82dc-5a7896c53e0c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# 使用核心元件的成功路徑 {#paths-to-success}

核心元件功能強大、靈活，易於使用和定制。 依照本檔案中概述的幾項重要准則，將能確保您的核心元件專案成功。

## 成功的兩種途徑 {#two-paths}

執行核心部分有兩種基本方法，這種方法可能會取得成功，但也有各自的取捨，需要逐項加以考慮。

1. 將您的設計對應至核心元件，並取用其提供的HTML。 或
1. 如果您必須遵循已定義的HTML標準，您將需要付出更多努力，而無法獲得核心元件的所有優點。

## 元件實施中的常見陷阱 {#common-pitfalls}

導致核心元件無法成功實施專案的兩個常見問題：

* **最終設計**  — 這些設計甚至可能獲得C級批准，並交給開發團隊，以便在不考慮底層技術的情況下實施像素級完美設計。
* **公司範圍的HTML樣式指南**  — 這類參考線通常必須由自上而下的觀點套用樣式的元件教條式遵循。

在這兩種情況下，對元件的要求都非常嚴格和具體，因此很難使核心元件或任何現成可用的元件符合這些要求，從而導致定制元件的大規模開發。

## 提早開始 {#start-early}

除了在專案實作階段只考慮核心元件，線上框設計階段已從核心元件開始。

### 使用元件庫 {#component-library}

參考已在設計階段中的[元件庫](https://adobe.com/go/aem_cmp_library)。 核心元件功能強大且靈活，可帶您遠為開端。 只有在真正有業務需求，且核心元件無法合理達成時，才新增自訂元件。

### 使用適用於Adobe XD的UI套件 {#ui-kit}

只要對自訂元件有經證實的需求，請立即使用適用於Adobe XD](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)的[ UI套件，讓設計人員能以核心元件作為建置組塊，開始建立線框和設計。

## 不要忽略功能強大 {#powerful-features}

AEM和核心元件的功能可能非常強大，但也非常微妙，設計人員可能不會立即發現某些功能的可能性。

### 內容片段 {#content-fragments}

[內](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) 容片段可讓您建立管道中性內容，以及（可能是管道特定的）變化。然後，您可以在編寫內容頁面時使用這些片段及其變體。

結構化內容片段與更新的JSON匯出工具一起，也可用來透過內容服務將AEM內容傳送至AEM頁面以外的管道。

### 體驗片段範本 {#experience-fragment-templates}

如果作者想要重複使用頁面的部分（體驗的片段）。 若沒有[體驗片段，](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html)作者將需要複製並貼上該片段。 建立和維護這些複製/貼上體驗非常耗時，且容易發生使用者錯誤。 體驗片段不需要複製/貼上。

### 內嵌元件 {#embed-component}

[內嵌元](/help/components/embed.md) 件不僅可讓您輕鬆包含外部資源，例如YouTube視訊內容，而且可擴充，以因應專案需求的特定內容。
