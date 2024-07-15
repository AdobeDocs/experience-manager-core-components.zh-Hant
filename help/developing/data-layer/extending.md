---
title: 擴充Adobe使用者端資料層
description: Adobe使用者端資料層可以依照一些基本模式進行擴充
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---

# 擴充Adobe使用者端資料層 {#extending-acdl}

您可以使用自訂對話方塊選項來擴充核心元件，讓內容作者可以輸入與資料層相關的其他資訊。

若要將這些欄位納入核心元件所提供的資料層中，您必須擴充元件模型，以實作其專屬的資料層方法。

## 範例：標題元件 {#example}

像[標題元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)這樣的核心元件會延伸[元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)，此元件具有依預設會傳回[`ComponentData`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)的`getData`方法

`ComponentData`會序列化您的元件可能實作的預先定義欄位，例如[`TitleImpl`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)的`getDataLayerLinkUrl`和`getDataLayerTitle`

因此，您的自訂Sling模型可能有`getData`方法，該方法會傳回擴充`ComponentData`的物件以傳回更多欄位。

這樣一來，會將`data-cmp-data-layer`屬性新增至元件的HTML元素，以及將會填入資料層之資料的JSON。 此時，您可以實作監聽此資料或相關事件的指令碼。

>[!TIP]
>
>若要進一步探索Data Layer的彈性，請檢閱相關的整合選項，包括如何為自訂元件啟用Data Layer。
