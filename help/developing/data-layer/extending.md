---
title: 擴充Adobe使用者端資料層
description: Adobe使用者端資料層可依照一些基本模式進行擴充
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# 擴充Adobe使用者端資料層 {#extending-acdl}

您可以使用自訂對話方塊選項來擴充核心元件，讓內容作者輸入與Data Layer相關的其他資訊。

若要將這些欄位納入核心元件所提供的資料層中，您必須擴充元件模型，以實作其專屬的資料層方法。

## 範例：標題元件 {#example}

核心元件，例如 [標題元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) 延伸 [元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) 具有 `getData` 預設會傳回的方法 [`ComponentData`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` 序列化您的元件可能實作的預先定義欄位，例如 `getDataLayerLinkUrl` 和 `getDataLayerTitle` 的 [`TitleImpl`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

因此，您的自訂Sling模型可能會 `getData` 傳回物件的方法，此物件會擴充 `ComponentData` 以傳回更多欄位。

執行此動作會新增 `data-cmp-data-layer` 屬性，屬性為元件的HTML元素，且含有將填入資料層之資料的JSON。 此時，您可以實作監聽此資料或相關事件的指令碼。

>[!TIP]
>
>若要進一步探索Data Layer的彈性，請檢閱整合選項，包括如何為自訂元件啟用Data Layer。
