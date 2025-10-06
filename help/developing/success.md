---
title: 使用核心元件的成功路徑
description: 如何在專案中實施「核心元件」並獲得成功
role: Architect, Developer, Admin, User
exl-id: 1ea8cd1c-8435-4ded-82dc-5a7896c53e0c
source-git-commit: b1d38310a3f05e2dd2a68de1574a278bac2c78e7
workflow-type: ht
source-wordcount: '541'
ht-degree: 100%

---


# 使用核心元件的成功路徑 {#paths-to-success}

核心元件功能強大、彈性好用，並可輕鬆自訂。遵循本文件中概述的幾個關鍵指導方針，將可確保您運用核心元件的專案獲得成功。

## 獲得成功的兩個途徑 {#two-paths}

實施核心元件有兩種基本方法，雖然可帶來成功，但需要根據個別專案具體情況考量其取捨之處。

1. 將您的設計對應至「核心元件」，並取得這些元件提供的 HTML。或
1. 如果您必須遵循已定義的 HTML 標準，則需加倍努力，且無法獲得核心元件的所有優勢。

## 元件實施中的常見陷阱 {#common-pitfalls}

導致專案無法成功運用核心元件的兩個常見問題是：

* **最終定稿設計** - 這些設計甚至可能已獲得 C 級高層的核准，交由發團隊以像素級精準度實施，而無須顧慮底層技術細節。
* **全公司統一的 HTML 樣式指南** - 此類指南往往被奉為圭臬，要求元件須以由上而下的角度套用樣式。

在這兩種情況下，元件都會有嚴格且具體的需求，以至於「核心元件」或任何立即可用的元件都難以符合這些需求，導致需要大量開發自訂元件。

## 提早開始 {#start-early}

與其在專案實施階段才考量「核心元件」，不如從透視效果和設計階段期間就開始運用核心元件。

### 使用元件庫 {#component-library}

在設計階段就開始參考[元件庫](https://adobe.com/go/aem_cmp_library_tw)。「核心元件」功能強大且靈活，作為起點可讓您事半功倍。只當有實際業務需求，且使用「核心元件」確實無法合理達成時，才新增自訂元件。

### 使用 Adobe XD 的 UI 套件 {#ui-kit}

一旦確認需要自訂元件，請善用 Adobe XD 的 UI 套件，[可由此處下載](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd?lang=zh-Hant)，讓設計人員以「核心元件」作為建置區塊，著手建置透視效果和設計。

## 別讓強大的功能被埋沒 {#powerful-features}

AEM 和「核心元件」的功能非常強大，但有些較不容易察覺，設計人員可能無法立即掌握某些功能的潛力。

### 內容片段 {#content-fragments}

[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html?lang=zh-Hant)可讓您建立管道中立的內容，以及 (視情況建立管道專用) 變化版本。接著，您就可以在編寫內容頁面時，使用這些片段及其變化版本。

將結構化內容片段與更新的 JSON 匯出工具搭配使用，也可用來透過「內容服務」將 AEM 內容傳遞至 AEM 頁面以外的管道。

### 體驗片段範本 {#experience-fragment-templates}

適用於作者想要重複使用部分頁面 (體驗的片段)。沒有[體驗片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html?lang=zh-Hant)時，作者需要複製和貼上該片段。建立及維護這些複製/貼上體驗非常耗時，而且容易發生使用者錯誤。「體驗片段」消除了複製/貼上的需求。

### 嵌入元件 {#embed-component}

[嵌入元件](/help/components/embed.md)不僅允許簡單包含外部資源 (例如 YouTube 影片內容)，而且可擴充以符合特定專案需求的內容。
