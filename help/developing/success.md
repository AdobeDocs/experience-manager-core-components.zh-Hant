---
title: 核心元件的成功途徑
description: 在使用核心元件實施項目時如何成功
role: Architect, Developer, Admin, User
exl-id: 1ea8cd1c-8435-4ded-82dc-5a7896c53e0c
source-git-commit: 888719359f9a1d1c9dccff97fb639b332f2be54c
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# 核心元件的成功途徑 {#paths-to-success}

核心元件功能強大、靈活，易於使用和定制。 按照本文檔中概述的一些關鍵指導原則，將確保您的核心元件項目取得成功。

## 成功的兩條途徑 {#two-paths}

執行核心部分有兩種基本方法，這種方法可能取得成功，但也有各自的取捨，需要逐個項目加以考慮。

1. 將您的設計映射到核心元件並承擔它們提供的HTML。 或
1. 如果您必須遵守已定義的HTML標準，則需要付出更多努力，而不能獲得核心元件的所有好處。

## 構件實施中的常見缺陷 {#common-pitfalls}

導致核心元件無法成功的項目的兩個常見問題是：

* **最終設計**  — 這些內容甚至可能獲得C級批准，並交給開發團隊，以便在不考慮底層技術的情況下實施像素完美技術。
* **全公司HTML風格指南**  — 此類參考線通常必須由從上到下透視應用樣式的元件按教條式遵循。

在這兩種情況下，對元件的要求都非常嚴格和具體，因此很難使核心元件或任何現成的元件符合這些要求，從而導致定制元件的大規模開發。

## 提前開始 {#start-early}

在項目實施階段不僅考慮核心元件，而是在重構和設計階段已從核心元件開始。

### 使用元件庫 {#component-library}

引用 [元件庫](https://adobe.com/go/aem_cmp_library) 已經進入設計階段。 核心元件功能強大且靈活，可以將您作為起點。 只有在真正無法通過核心元件合理實現的真正業務需求時，才添加自定義元件。

### 使用UI套件用於Adobe XD {#ui-kit}

一旦對定制元件有經驗證的需求，就利用 [用於Adobe XD的UI套件](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)  這樣設計人員就可以開始以核心元件為構件來構建線框和設計。

## 不要忽視強大的功能 {#powerful-features}

核心組AEM件的功能非常強大，但也非常微妙，某些功能的可能性對於設計者來說可能不會立即顯現出來。

### 內容片段 {#content-fragments}

[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) 允許您建立通道中性內容以及（可能特定於通道）變體。 然後，在創作內容頁面時，可以使用這些片段及其變體。

與更新的JSON導出器一起，結構化內容片段還可用於通過Content Services將AEM內容傳送到頁面以外的AEM渠道。

### 體驗片段模板 {#experience-fragment-templates}

如果作者希望重新使用頁面的部分（體驗的一部分）。 沒有 [體驗片段，](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html) 作者需要複製並貼上該片段。 建立和維護這些複製/貼上體驗非常耗時且容易出現用戶錯誤。 體驗片段消除了複製/貼上的需要。

### 嵌入元件 {#embed-component}

[嵌入元件](/help/components/embed.md) 不僅允許簡單地包含外部資源，而且還可擴展以允許它容納特定於項目需要的內容。
