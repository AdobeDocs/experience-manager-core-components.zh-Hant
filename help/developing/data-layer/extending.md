---
title: 擴充 Adobe Client Data Layer
description: Adobe Client Data Layer 可以依據一些基本模式進行擴充
feature: Core Components, Adobe Client Data Layer
role: Developer, Admin
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
TQID: 'https://experienceleague.adobe.com/67YSpRfwNRMDgcBARHKLz51-Er6xb4vp1rXX0r0sbfE'
product_v2:
  - id: c45915cf-e157-4af7-a80d-97b905bcb3a5
    internal-label: Experience Manager Sites
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: d9d38edd-df1b-480c-8f5e-72b62576f390
    internal-label: Site and page features
  - id: d429a63e-ade4-4117-b04e-9b996d1c94ef
    internal-label: Integrations
subfeature_v2:
  - id: c43ff1f6-5a6d-4e8c-b3cc-6bdb3fa6e092
    internal-label: Core components
  - id: a94e5c13-4138-47ec-b9c8-e804e17aaca2
    internal-label: Adobe Client Data Layer
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: 025b8134f7675b4515f4586910a94a2732bfa2ee
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 100%
---
# 擴充 Adobe Client Data Layer {#extending-acdl}

您可以使用自訂對話框選項，讓內容作者能夠輸入與「資料層」相關的額外資訊，從而擴充「核心元件」。

若要在「核心元件」提供的「資料層」中包含這些欄位，您必須擴充實施其專屬資料層方法的元件模型。

## 範例：標題元件 {#example}

像[標題元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)這樣的「核心元件」會擴充[元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)，該元件具備根據預設會回傳 [`ComponentData`](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java) 的 `getData` 方法。

`ComponentData` 會序列化您的元件可能實施的預先定義欄位，例如 [`TitleImpl`](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java) 的 `getDataLayerLinkUrl` 和 `getDataLayerTitle`。

因此，您的自訂 Sling 模型可能具備 `getData` 方法，該方法會回傳可擴充 `ComponentData` 的物件，以回傳更多欄位。

透過這樣做，將會新增 `data-cmp-data-layer` 屬性至元件的 HTML 元素中，以及將填入至資料層的資料 JSON。 此時，您可以實施監聽此資料或相關事件的指令碼。

>[!TIP]
>
>若要進一步探索「資料層」的彈性，請檢閱相關的整合選項，包括如何為您的自訂元件啟用「資料層」。
