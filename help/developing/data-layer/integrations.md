---
title: 整合與Adobe使用者端資料層
description: 瞭解Adobe Client Data Layer如何與您的自訂元件整合，以及與Adobe Analytics和Adobe Target的整合如何協助您深入瞭解網站
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: 503dd3dc-fe95-4a17-83f5-1f0c1960993d
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%

---

# 與Adobe使用者端資料層的整合 {#integrations}

Adobe Client Data Layer提供標準化方法，可公開和存取任何指令碼的任何型別的資料，減少檢測網站所需的工作量。

Adobe Client Data Layer可與您的自訂元件整合，並與Adobe Analytics和Adobe Target整合，以協助您深入瞭解網站。

## 為自訂元件啟用資料層 {#enabling-custom-components}

自動將自訂元件新增至資料層：

1. 定義需要追蹤之自訂元件模型的屬性。
1. 將`data-cmp-data-layer`屬性新增到自訂元件HTL。 例如`data-cmp-data-layer="${mycomponent.data.json}"`。

若要在每次點按自訂元件的特定元素時自動讓資料層觸發`cmp:click`事件，請新增`data-cmp-clickable`屬性至要在自訂元件HTL中追蹤的元素。

可在使用者端查詢`data-cmp-data-layer-enabled`屬性，以檢查資料層是否已啟用。

>[!TIP]
>
>如需有關Adobe Client Data Layer與核心元件整合的詳細技術資訊，以及如何在自訂元件上啟用Data Layer，請參閱核心元件存放庫中的[`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md)檔案。

## 整合Adobe Analytics和Adobe Target {#analytics-target}

Adobe Client Data Layer搭配Adobe Analytics和Adobe Target，成為功能強大且彈性十足的工具集基礎，協助您深入瞭解數位體驗。 下列教學課程會引導您進行範例整合。

### 使用Adobe Analytics收集頁面資料 {#collect-page-data}

瞭解如何搭配使用Adobe Client Data Layer的內建功能與AEM核心元件，收集Adobe Experience Manager Sites中某個頁面的相關資料。 Experience Platform Launch和Adobe Analytics擴充功能將用於建立規則，以將頁面資料傳送至Adobe Analytics。

[在此檢視教學課程。](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html?lang=zh-Hant)

### 使用Adobe Analytics追蹤已點按的元件 {#track-clicked-components}

使用事件導向的Adobe使用者端資料層搭配AEM核心元件，追蹤Adobe Experience Manager網站上特定元件的點按次數。 瞭解如何使用Experience Platform Launch中的規則來監聽點選事件、依元件篩選資料，以及透過追蹤連結信標將資料傳送至Adobe Analytics。

[在此檢視教學課程。](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html?lang=zh-Hant)
