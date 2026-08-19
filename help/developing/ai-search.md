---
title: 設定內容AI 搜尋元件
description: 內容AI 搜尋元件可為您的網站訪客提供可產生的AI支援搜尋。 瞭解如何為內容作者啟用此元件。
role: Developer, Admin
product_v2: id: c45915cf-e157-4af7-a80d-97b905bcb3a5id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: e2c1b6d3-bb7e-4fe8-8c72-f7b403298e91
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: c18d9e03-ac7d-4811-9c92-3e92ddc70ade
source-git-commit: 865622469555a773138d3ff1b54138f2b76994b0
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 2%

---


# 設定內容AI 搜尋元件 {#configure-content-ai-search-component}

內容AI 搜尋元件可為您的網站訪客提供可產生的AI支援搜尋。 瞭解如何為內容作者啟用此元件。

## 先決條件 {#prerequisites}

* 至少已建立一個[內容Source](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/contentsources)，狀態為&#x200B;**可用**。
* **AEM Content AI Client** OSGi設定(`ContentAIClientImpl`)已同時設定在作者和發佈上，具有有效的API認證和&#x200B;**預設內容Source**&#x200B;值。 請參閱檔案[設定Adobe Developer Console專案](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/setup-adc-project)以瞭解如何取得認證。

## 建立Proxy元件 {#proxy-component}

如同所有核心元件，建議您為AEM隨附的預設內容AI 搜尋元件建立Proxy元件。 藉由將您專案特定的變更保留在`/apps`下的Proxy元件中，Adobe會自動更新`/libs`下的基礎元件，而您的專案元件會自動繼承這些更新。 如需詳細資訊，請參閱檔案[使用核心元件](/help/get-started/using.md#aemaacs)和[元件指導方針](/help/developing/guidelines.md)。

## 設定使用者端資料庫 {#clientlib}

內容AI 搜尋元件未遵循[將使用者端程式庫納入核心元件的標準模式。](/help/developing/including-clientlibs.md) 請按照以下步驟進行操作。

將下列專案新增至專案的頁面元件`customheaderlibs.html` （適用於CSS）和`customfooterlibs.html` （適用於JS）：

```html
<sly data-sly-use.clientLib="/libs/granite/sightly/templates/clientlib.html"
     data-sly-call="${clientLib.css @ categories='core.wcm.components.contentaisearch.v1'}"></sly>
```

如果您的專案在上方圖層有自己的品牌樣式，請在此類別之後為您專案自己的使用者端資料庫新增第二個類別。

## 使用內容AI 搜尋元件 {#using}

您的內容作者現在可以將內容AI 搜尋元件放置在其頁面上。 如需詳細資訊，請參閱檔案[內容AI 搜尋元件](/help/components/ai-search.md)。

## 元件如何使用Content AI {#how-it-works}

* 標準搜尋查詢的擷取層與「內容Source」的索引相同，會從設定的來源傳回相符的頁面、片段或資產。
* 啟用AI產生的摘要時，元件會額外呼叫AEM Content AI產生的端點，將回應納入相同的索引內容中，並在摘要旁邊顯示來源，讓訪客可以驗證。
* 由於這兩項功能都是從相同的受管內容Source中讀取，因此結果和摘要會與目前編制索引的內容保持一致。 重新執行贏取（請參閱[控制您的內容來源](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/contentsources)）會重新整理兩者。

## 後續步驟 {#next-steps}

* [控制您的內容來源](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/contentsources) — 建立並管理此元件搜尋的內容Source。
* [設定Adobe Developer Console專案](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/setup-adc-project) — 取得OSGi Content AI使用者端組態所使用的認證。
* [Content AI API參考](https://developer.adobe.com/experience-cloud/experience-manager-apis/api/experimental/contentai/) — 瞭解此元件呼叫的基本搜尋和產生式摘要端點。
