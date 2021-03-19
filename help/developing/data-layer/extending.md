---
title: 擴展Adobe客戶端資料層
description: Adobe客戶端資料層可以按照一些基本模式進行擴展
feature: 核心元件，Adobe客戶端資料層
role: 架構師、開發人員、管理員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# 擴展Adobe客戶端資料層{#extending-acdl}

您可以使用自訂對話方塊選項來擴充核心元件，讓內容作者輸入與資料層相關的其他資訊。

要在核心元件提供的資料層中包含這些欄位，必須擴展實現其特定資料層方法的元件的模型。

## 範例：標題元件{#example}

[標題元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)等核心元件延伸[元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)，該元件`getData`方法預設返回[`ComponentData`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` 序列化元件可能實作的預先定義欄位， `getDataLayerLinkUrl` 如 `getDataLayerTitle` 和 [`TitleImpl`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

因此，您的自訂Sling模型可能有`getData`方法，可傳回延伸`ComponentData`以傳回更多欄位的物件。

執行此動作時，會將`data-cmp-data-layer`屬性新增至元件的HTML元素，並包含將填入資料層的資料JSON。 此時，您可以實作監聽此資料或相關事件的指令碼。

>[!TIP]
>
>若要進一步探索資料層的彈性，請檢視整合選項，包括如何為自訂元件啟用資料層。
