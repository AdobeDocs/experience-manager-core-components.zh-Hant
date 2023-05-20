---
title: 擴展Adobe客戶端資料層
description: Adobe客戶端資料層可以按照一些基本模式進行擴展
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# 擴展Adobe客戶端資料層 {#extending-acdl}

您可以使用自定義對話框選項擴展核心元件，這些對話框選項允許內容作者輸入與資料層相關的附加資訊。

要在核心元件提供的資料層中包括這些欄位，必須擴展實現其特定資料層方法的元件模型。

## 示例：標題元件 {#example}

核心元件，如 [標題元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) 延伸 [元件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) 有 `getData` 方法預設返回 [`ComponentData`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` 序列化元件可能實現的預定義欄位，例如 `getDataLayerLinkUrl` 和 `getDataLayerTitle` 為 [`TitleImpl`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

因此，您的自定義Sling模型可能 `getData` 方法返回擴展的對象 `ComponentData` 按鈕。

執行此操作將添加 `data-cmp-data-layer` 屬於元件的HTML元素，其JSON是要填充到資料層的資料。 此時，您可以實現偵聽此資料或相關事件的指令碼。

>[!TIP]
>
>要進一步瞭解資料層的靈活性，請查看有關整合選項的資訊，包括如何為自定義元件啟用資料層。
