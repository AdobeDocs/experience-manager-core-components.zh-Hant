---
title: 搭配核心元件使用Adobe用戶端資料層
description: 搭配核心元件使用Adobe用戶端資料層
translation-type: tm+mt
source-git-commit: 24a810ff634f8846881dfa0095e879476d0f16f0
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 4%

---


# 搭配核心元件使用Adobe用戶端資料層 {#data-layer-core-components}

Adobe用戶端資料層的目標，是透過提供標準化方法來公開和存取任何指令碼的任何類型資料，以減少網站的測試工作。

Adobe用戶端資料層不受平台限制，但已完全整合至核心元件，可與AEM搭配使用。

和核心元件一樣，GitHub也提供Adobe用戶端資料層的程式碼及其開發人員檔案。 本檔案概述核心元件與資料層的互動方式，但GitHub檔案會延遲完整的技術詳細資訊。

>[!TIP]
>
>有關Adobe客戶端資料層的詳細信 [息，請參閱其GitHub儲存庫中的資源。](https://github.com/adobe/adobe-client-data-layer)
>
>如需Adobe用戶端資料層與核心元件整合的詳細技術資訊，請參閱核心元 [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) 件儲存庫中的檔案。

## 安裝與啟動 {#installation-activation}

從2.9.0版開始，資料層將作為客戶端庫與核心元件一起分發。 不需要安裝。

不過，資料層依預設不會啟動。 若要啟用資料層，您必須為其 [建立內容感知組態](/help/developing/context-aware-configs.md) :

1. 在節點下建立以下結 `/conf` 構：
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * 節點類型： `nt:unstructured`
1. 新增名為的布林屬 `enabled` 性，並將其設為 `true`。
1. 將屬 `sling:configRef` 性新增至下 `jcr:content` 方網站的節 `/content` 點(例如 `/content/<mySite>/jcr:content`)，並將其設為 `/conf/<mySite>`。

啟用後，您可以在編輯器外載入網站的頁面來驗證啟動。 當您檢查頁面時，會看到Adobe用戶端資料層已載入。

## 核心元件資料結構 {#data-schemas}

以下是核心元件與資料層一起使用的方案清單。

### 元件／容器項目結構 {#item}

元件／容器項模式用於以下元件：

* [階層連結](/help/components/breadcrumb.md)
* [按鈕](/help/components/button.md)
* [語言導覽](/help/components/language-navigation.md)
* [清單](/help/components/list.md)
* [導覽](/help/components/navigation.md)
* [Teaser](/help/components/teaser.md)
* [文字](/help/components/text.md)
* [標題](/help/components/title.md)

元件／容器項方案定義如下。

```
id: {                   // component ID
    @type               // resource type
    repo:modifyDate     // last modified date
    dc:title            // title
    dc:description      // description
    xdm:text            // text
    xdm:linkURL         // link URL
    parentId            // parent component ID
}
```


### 頁面結構 {#page}

頁面架構由下列元件使用：

* [頁面](/help/components/page.md)

頁面結構定義如下。

```
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    xdm:tags            // page tags
    repo:path           // page path
    xdm:template        // page template
    xdm:language        // page language
}
```

### 容器結構 {#container}

Container架構由下列元件使用：

* [折疊式面板](/help/components/accordion.md)
* [索引標籤](/help/components/tabs.md)
* [傳送](/help/components/carousel.md)

容器結構描述的定義如下。

```
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    shownItems          // array of the displayed item IDs
}
```

### 影像結構 {#image}

以下元件使用映像模式：

* [影像](/help/components/image.md)

映像模式定義如下。

```
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    image               // asset detail (see below section)
}
```

### 資產結構 {#asset}

Asset架構用於 [Image元件內。](/help/components/image.md)

資產結構定義如下。

```
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

