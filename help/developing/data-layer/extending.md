---
title: 擴充 Adobe Client Data Layer
description: Adobe Client Data Layer 可以依據一些基本模式進行擴充
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '201'
ht-degree: 100%

---

# 擴充 Adobe Client Data Layer {#extending-acdl}

您可以使用自訂對話框選項，讓內容作者能夠輸入與「資料層」相關的額外資訊，從而擴充「核心元件」。

若要在「核心元件」提供的「資料層」中包含這些欄位，您必須擴充實施其專屬資料層方法的元件模型。

## 範例：標題元件 {#example}

像[標題元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)這樣的「核心元件」會擴充[元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)，該元件具備根據預設會回傳 [`ComponentData`](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java) 的 `getData` 方法。

`ComponentData` 會序列化您的元件可能實施的預先定義欄位，例如 [`TitleImpl`](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java) 的 `getDataLayerLinkUrl` 和 `getDataLayerTitle`。

因此，您的自訂 Sling 模型可能具備 `getData` 方法，該方法會回傳可擴充 `ComponentData` 的物件，以回傳更多欄位。

透過這樣做，將會新增 `data-cmp-data-layer` 屬性至元件的 HTML 元素中，以及將填入至資料層的資料 JSON。此時，您可以實施監聽此資料或相關事件的指令碼。

>[!TIP]
>
>若要進一步探索「資料層」的彈性，請檢閱相關的整合選項，包括如何為您的自訂元件啟用「資料層」。
