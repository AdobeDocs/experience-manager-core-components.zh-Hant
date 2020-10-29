---
title: 擴充Adobe用戶端資料層
description: Adobe用戶端資料層可依照一些基本模式進行擴充
translation-type: tm+mt
source-git-commit: 1ada05d5089ccef95d41d47468776654e397f31d
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---


# 擴充Adobe用戶端資料層 {#extending-acdl}

您可以使用自訂對話方塊選項來擴充核心元件，讓內容作者輸入與資料層相關的其他資訊。

要在核心元件提供的資料層中包含這些欄位，必須擴展實現其特定資料層方法的元件的模型。

## 範例：標題元件 {#example}

Core Component（如Title元件） [擴展了Component](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) （元件），該元件具有預設 [返回的方法](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)`getData`[`ComponentData`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` 序列化元件可能實作的預先定義欄位， `getDataLayerLinkUrl` 例如 `getDataLayerTitle` 和 [`TitleImpl`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

因此，您的自訂Sling模型可能有 `getData` 一種方法可傳回延伸至傳回 `ComponentData` 更多欄位的物件。

執行此動作時， `data-cmp-data-layer` 會新增屬性至元件的HTML元素，並包含將填入資料層的資料JSON。 此時，您可以實作監聽此資料或相關事件的指令碼。

>[!TIP]
>
>若要進一步探索資料層的彈性，請檢視整合選項，包括如何為自訂元件啟用資料層。
