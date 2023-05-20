---
title: 整合和Adobe客戶端資料層
description: 瞭解Adobe客戶端資料層如何與您的自定義元件整合，以及與Adobe Analytics和Adobe Target的整合如何幫助您深入瞭解您的網站
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: 503dd3dc-fe95-4a17-83f5-1f0c1960993d
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---

# 與Adobe客戶端資料層的整合 {#integrations}

Adobe客戶端資料層通過提供標準化方法來公開和訪問任何指令碼的任何類型的資料，從而減少了對網站進行測試的工作量。

Adobe客戶端資料層可與您的定製元件整合，與Adobe Analytics和Adobe Target的整合可幫助您深入瞭解您的網站。

## 為自定義元件啟用資料層 {#enabling-custom-components}

要自動將自定義元件添加到資料層：

1. 定義需要跟蹤的自定義元件模型的屬性。
1. 添加 `data-cmp-data-layer` 屬性。 例如 `data-cmp-data-layer="${mycomponent.data.json}"`。

自動使資料層觸發 `cmp:click` 每次按一下自定義元件的特定元素時的事件，添加 `data-cmp-clickable` 屬性到要在自定義元件HTL中跟蹤的元素。

的 `data-cmp-data-layer-enabled` 可以查詢客戶端屬性以檢查資料層是否已啟用。

>[!TIP]
>
>有關Adobe客戶端資料層與核心元件整合以及如何在自定義元件上啟用資料層的進一步技術詳細資訊，請參見 [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) 檔案。

## 與Adobe Analytics和Adobe Target {#analytics-target}

與Adobe Analytics和Adobe Target一道，Adobe客戶端資料層成為一個功能強大、靈活的工具集的基礎，可讓您深入瞭解數字型驗。 以下教程將引導您完成示例整合。

### 收集頁面資料與Adobe Analytics {#collect-page-data}

學習使用帶核心元件的Adobe客戶端資料層的內置功AEM能來收集Adobe Experience Manager Sites某頁面的資料。 Experience Platform Launch和Adobe Analytics分機將用於建立向Adobe Analytics發送頁面資料的規則。

[在此查看教程。](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### 跟蹤按一下的元件(帶Adobe Analytics) {#track-clicked-components}

使用帶核心元件的事件驅動Adobe客AEM戶端資料層跟蹤Adobe Experience Manager站點上特定元件的按一下。 瞭解如何使用Experience Platform Launch中的規則來偵聽按一下事件、按元件篩選資料並使用跟蹤連結信標將資料發送到Adobe Analytics。

[在此查看教程。](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
