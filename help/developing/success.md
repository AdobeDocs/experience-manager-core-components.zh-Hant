---
title: 使用核心元件取得成功的途徑
description: 如何使用核心元件實作您的專案時如何成功
role: Architect, Developer, Admin, User
exl-id: 1ea8cd1c-8435-4ded-82dc-5a7896c53e0c
source-git-commit: 888719359f9a1d1c9dccff97fb639b332f2be54c
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# 使用核心元件取得成功的途徑 {#paths-to-success}

核心元件功能強大、彈性好用，且易於使用與自訂。 遵循本檔案中概述的幾個關鍵准則將確保您成功使用核心元件的專案。

## 獲得成功的兩個途徑 {#two-paths}

實作核心元件有兩種基本方法，雖然可帶來成功，但須逐個專案考量各自的利弊。

1. 將您的設計對應至核心元件，並取得這些元件提供的HTML。 或
1. 如果您必須遵循已定義的HTML標準，則需要付出更多努力，才能享有核心元件的所有優點。

## 元件實施中的常見陷阱 {#common-pitfalls}

導致使用核心元件進行專案失敗的兩個常見問題是：

* **已完成設計**  — 這些甚至可能獲得C層級的核准，並移交開發團隊以實作畫素完美，無需考慮基礎技術。
* **全公司HTML風格指南**  — 從自上而下的角度套用樣式的元件經常必須教條地遵循此類參考線。

在這兩種情況下，對元件的要求都非常嚴格和具體，以至於核心元件或任何現成可用元件都難以符合這些要求，從而導致大量自訂元件的開發。

## 提早開始 {#start-early}

線上框化和設計階段從核心元件開始，而不是只在專案的實作階段考慮核心元件。

### 使用元件資料庫 {#component-library}

參考 [元件資料庫](https://adobe.com/go/aem_cmp_library) 已經處於設計階段。 核心元件功能強大且富有彈性，可讓您發揮最大效用。 只有在有實際業務需求，而核心元件確實無法合理達成時，才新增自訂元件。

### 使用Adobe XD UI Kit {#ui-kit}

一旦證明需要自訂元件，請利用 [Adobe XD的UI套件](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)  好讓設計人員開始以核心元件作為建置組塊，建置線框和設計。

## 不要忽視強大的功能 {#powerful-features}

AEM和核心元件的功能可能非常強大，但也非常微妙，設計人員可能無法立即得知某些功能的可能性。

### 內容片段 {#content-fragments}

[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) 可讓您建立管道中性內容，以及（可能特定於管道的）變數。 然後，您就可以在編寫內容頁面時使用這些片段及其變數。

結構化內容片段與更新的JSON匯出工具搭配使用，也可用於透過Content Services將AEM內容傳送至AEM頁面以外的管道。

### 體驗片段範本 {#experience-fragment-templates}

如果作者想要重複使用頁面的部分（體驗的片段）。 不含 [體驗片段，](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html) 作者需要複製並貼上該片段。 建立和維護這些複製/貼上體驗非常耗時，而且容易發生使用者錯誤。 體驗片段不需要複製/貼上。

### 內嵌元件 {#embed-component}

[內嵌元件](/help/components/embed.md) 不僅可讓您輕鬆包含外部資源(例如YouTube視訊內容)，而且可延伸以因應專案需求的特定內容。
