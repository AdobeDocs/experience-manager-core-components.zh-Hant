---
title: 擴充Adobe用戶端資料層
description: Adobe用戶端資料層可依照一些基本模式進行擴充
feature: 核心元件，Adobe用戶端資料層
role: Architect, Developer, Administrator
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---

# 擴展Adobe客戶端資料層{#extending-acdl}

您可以使用自訂對話方塊選項擴充核心元件，讓內容作者輸入與資料層相關的其他資訊。

若要在核心元件提供的資料層中加入這些欄位，您必須擴充實作其特定資料層方法的元件模型。

## 範例：標題元件 {#example}

[標題元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)之類的核心元件擴展[元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)，該元件`getData`方法預設返回[`ComponentData`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` 序列化元件可實作的預先定義欄位， `getDataLayerLinkUrl` 如 `getDataLayerTitle` 和 [`TitleImpl`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

因此，您的自訂Sling模型可能有`getData`方法，可傳回延伸`ComponentData`以傳回更多欄位的物件。

執行此動作時，會使用要填入資料層之資料的JSON，將`data-cmp-data-layer`屬性新增至元件的HTML元素。 此時，您可以實作會監聽此資料或相關事件的指令碼。

>[!TIP]
>
>若要進一步探索資料層的彈性，請檢閱整合選項，包括如何為自訂元件啟用資料層。
