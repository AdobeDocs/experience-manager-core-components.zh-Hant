---
title: 使用核心元件獲得成功的途徑
description: 如何使用核心元件實作您的專案時如何成功
role: Architect, Developer, Admin, User
exl-id: 1ea8cd1c-8435-4ded-82dc-5a7896c53e0c
source-git-commit: b1d38310a3f05e2dd2a68de1574a278bac2c78e7
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---


# 使用核心元件獲得成功的途徑 {#paths-to-success}

核心元件功能強大、彈性好用，且易於自訂。 遵循本檔案中概述的幾個關鍵准則將確保您成功使用核心元件的專案。

## 獲得成功的兩個途徑 {#two-paths}

實作核心元件有兩種基本方法，雖然可帶來成功，但需要逐個專案考量各自的利弊。

1. 將您的設計對應至核心元件，並取得這些元件提供的HTML。 或
1. 如果您必須遵循已定義的HTML標準，則需加倍努力，且無法獲得核心元件的所有優點。

## 元件實施中的常見陷阱 {#common-pitfalls}

導致使用核心元件進行專案失敗的兩個常見問題是：

* **已完成設計** — 這些設計甚至可能獲得C層級的核准，並且會被移交給開發團隊以實作畫素完美，而不需要擔心基礎技術。
* **全公司的HTML樣式指南** — 從自上而下的角度套用樣式的元件經常必須教條地遵循這些指南。

在這兩種情況下，元件都會有嚴格而具體的需求，以至於核心元件或任何現成可用的元件都難以符合這些需求，導致需要大量開發自訂元件。

## 提早開始 {#start-early}

線上框化和設計階段從核心元件開始，而不是僅在專案的實作階段考慮核心元件。

### 使用元件資料庫 {#component-library}

參考已經處於設計階段的[元件庫](https://adobe.com/go/aem_cmp_library)。 核心元件功能強大且靈活，可將您視為起點。 只有在有實際業務需求，而使用核心元件確實無法合理達成時，才新增自訂元件。

### 使用Adobe XD UI套件 {#ui-kit}

一旦證明需要自訂元件，請善用Adobe XD的UI套件[，可從這裡下載](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)，讓設計人員開始以核心元件作為建置區塊來建置線框和設計。

## 不要忽視強大的功能 {#powerful-features}

AEM和核心元件的功能非常強大，但也非常微妙，設計人員可能無法立即看出某些功能的可能性。

### 內容片段 {#content-fragments}

[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html)可讓您建立頻道中性的內容，以及（可能是頻道特定的）變化。 接著，您就可以在編寫內容頁面時，使用這些片段及其變數。

結構化內容片段與更新的JSON匯出工具搭配使用，也可用來透過Content Services將AEM內容傳送至AEM頁面以外的管道。

### 體驗片段範本 {#experience-fragment-templates}

如果作者想要重複使用頁面的部分（體驗的片段）。 如果沒有[體驗片段，](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html)作者將需要複製並貼上該片段。 建立及維護這些複製/貼上體驗非常耗時，而且容易發生使用者錯誤。 體驗片段不需要複製/貼上。

### 內嵌元件 {#embed-component}

[內嵌元件](/help/components/embed.md)不僅可允許簡單地包含外部資源(例如YouTube視訊內容)，而且可延伸以符合專案特定需求的內容。
