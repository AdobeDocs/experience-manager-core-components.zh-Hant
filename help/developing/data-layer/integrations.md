---
title: 整合與Adobe用戶端資料層
description: 瞭解Adobe客戶資料層如何與您的自訂元件整合，以及與Adobe Analytics和Adobe Target的整合如何協助您獲得網站的深入資訊
translation-type: tm+mt
source-git-commit: ea7a0e08ea1b769b400fce275c8ce7e0db6f9407
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---


# 與Adobe用戶端資料層{#integrations}的整合

Adobe用戶端資料層提供標準化方法，讓您針對任何指令碼公開和存取任何類型的資料，以減少對網站進行測試的工作量。

Adobe用戶端資料層可與您的自訂元件整合，而與Adobe Analytics和Adobe Target的整合可協助您獲取網站的見解。

## 為自定義元件啟用資料層{#enabling-custom-components}

要自動向資料層添加自定義元件，請執行以下操作：

1. 定義需要追蹤的自訂元件模型屬性。
1. 將`data-cmp-data-layer`屬性新增至自訂元件HTL。 例如，`data-cmp-data-layer="${mycomponent.data.json}"`。

若要在每次點按自訂元件的特定元素時自動讓資料層觸發`cmp:click`事件，請將`data-cmp-clickable`屬性新增至自訂元件HTL中要追蹤的元素。

可以向客戶端查詢`data-cmp-data-layer-enabled`屬性，以檢查資料層是否已啟用。

>[!TIP]
>
>如需有關Adobe用戶端資料層與核心元件整合以及如何啟用自訂元件上資料層的詳細技術資訊，請參閱核心元件儲存庫中的[`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md)檔案。

## 與Adobe Analytics和Adobe Target整合{#analytics-target}

Adobe用戶端資料層與Adobe Analytics和Adobe Target搭配使用，成為強大且有彈性的工具集的基礎，讓您深入洞察數位體驗。 下列教學課程可引導您完成範例整合。

### 使用Adobe Analytics {#collect-page-data}收集頁面資料

瞭解如何搭配使用Adobe用戶端資料層的內建功能與AEM核心元件，以收集Adobe Experience Manager Sites中某頁面的相關資料。 Experience Platform Launch和Adobe Analytics擴充功能將用來建立規則，以傳送頁面資料至Adobe Analytics。

[在這裡檢視教學課程。](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### 使用Adobe Analytics {#track-clicked-components}追蹤已點按的元件

搭配AEM核心元件使用事件導向的Adobe客戶資料層，以追蹤Adobe Experience Manager網站上特定元件的點按次數。 瞭解如何使用Experience Platform Launch中的規則來監聽點按事件、依元件篩選資料，以及將資料傳送至具有追蹤連結信標的Adobe Analytics。

[在這裡檢視教學課程。](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
