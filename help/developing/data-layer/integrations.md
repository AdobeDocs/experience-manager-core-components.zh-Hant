---
title: 與 Adobe Client Data Layer 整合
description: 了解 Adobe Client Data Layer 如何與您的自訂元件整合，以及與 Adobe Analytics 和 Adobe Target 整合將如何協助您深入了解網站
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: 503dd3dc-fe95-4a17-83f5-1f0c1960993d
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: ht
source-wordcount: '390'
ht-degree: 100%

---

# 與 Adobe Client Data Layer 整合 {#integrations}

「Adobe Client Data Layer」透過提供標準化方法，公開和存取任何指令碼的任何資料類型，減少檢測網站所需的工作量。

Adobe Client Data Layer 可與您的自訂元件整合，並與 Adobe Analytics 和 Adobe Target 整合，以協助您深入了解網站。

## 為自訂元件啟用資料層 {#enabling-custom-components}

若要自動將自訂元件新增至資料層：

1. 定義需要追蹤之自訂元件模型的屬性。
1. 將 `data-cmp-data-layer` 屬性新增至自訂元件 HTL。例如 `data-cmp-data-layer="${mycomponent.data.json}"`。

若要在每次點按自訂元件的特定元素時，讓資料層自動觸發 `cmp:click` 事件，請將 `data-cmp-clickable` 屬性新增至要在自訂元件 HTL 中追蹤的元素。

可在用戶端查詢 `data-cmp-data-layer-enabled` 屬性，以檢查資料層是否已啟用。

>[!TIP]
>
>如需有關 Adobe Client Data Layer 與核心元件整合的進一步技術詳細資訊，以及如何在自訂元件上啟用資料層，請參閱核心元件存放庫中的 [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) 檔案。

## 與 Adobe Analytics 和 Adobe Target 整合 {#analytics-target}

Adobe Client Data Layer 與 Adobe Analytics 和 Adobe Target 配對後，成為功能強大且彈性十足的工具集基礎，協助您深入了解數位體驗。下列教學課程會引導您進行範例整合。

### 使用 Adobe Analytics 收集頁面資料 {#collect-page-data}

了解如何搭配使用 Adobe Client Data Layer 的內建功能與 AEM 核心元件，收集 Adobe Experience Manager Sites 中某頁面的相關資料。Experience Platform Launch 和 Adobe Analytics 擴充功能將用於建立規則，以將頁面資料傳送至 Adobe Analytics。

[請至這裡檢視教學課程。](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html?lang=zh-Hant)

### 使用 Adobe Analytics 追蹤已點按的元件 {#track-clicked-components}

使用事件導向的 Adobe Client Data Layer 搭配 AEM 核心元件，追蹤 Adobe Experience Manager 網站上特定元件的點按次數。了解如何使用 Experience Platform Launch 中的規則來監聽點按事件、依元件篩選資料，以及透過追蹤連結信標將資料傳送至 Adobe Analytics。

[請至這裡檢視教學課程。](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html?lang=zh-Hant)
