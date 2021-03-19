---
title: 將Adobe客戶端資料層與核心元件一起使用
description: 將Adobe客戶端資料層與核心元件一起使用
feature: 核心元件，Adobe客戶端資料層
role: 架構師、開發人員、管理員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 5%

---


# 將Adobe客戶機資料層與核心元件{#data-layer-core-components}一起使用

Adobe用戶端資料層的目標，是透過提供標準化方法來公開和存取任何指令碼的任何類型資料，以減少對網站的測量工作。

Adobe客戶端資料層不受平台限制，但完全整合到核心元件中以便與一起使AEM用。

和核心元件一樣，Adobe用戶端資料層的程式碼也可在GitHub及其開發人員檔案上取得。 本檔案概述核心元件與資料層的互動方式，但GitHub檔案會延遲完整的技術詳細資訊。

>[!TIP]
>
>有關Adobe客戶端資料層的詳細資訊，請[參考其GitHub儲存庫中的資源。](https://github.com/adobe/adobe-client-data-layer)
>
>有關Adobe客戶端資料層與核心元件整合的詳細技術資訊，請參閱核心元件儲存庫中的[`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md)檔案。

## 安裝與啟動{#installation-activation}

從2.9.0版開始，資料層與核心元件一起作為客戶端庫AEM分發，無需安裝。 [AEM Project Archetype v. 24+](/help/developing/archetype/overview.md)產生的所有專案預設都包含已啟動的資料層。

要手動激活資料層，您必須為其建立[上下文感知配置](/help/developing/context-aware-configs.md):

1. 在`/conf/<mySite>`資料夾下建立下列結構，其中`<mySite>`是您網站專案的名稱：
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * 其中，每個節點的`jcr:primaryType`設定為`nt:unstructured`。
1. 添加名為`enabled`的布爾屬性，並將其設定為`true`。

   ![DataLayerConfig在WKND參考網站中的位置](/help/assets/datalayer-contextaware-sling-config.png)

   *DataLayerConfig在WKND參考網站中的位置*

1. 將`sling:configRef`屬性新增至`/content`下方網站的`jcr:content`節點(例如`/content/<mySite>/jcr:content`)，並從上一步驟設定為`/conf/<mySite>`。

1. 啟用後，您可以在編輯器外載入網站的頁面來驗證啟動，例如使用編輯器中的「檢視為已發佈」選項。 **** Inspect頁面來源和`<body>`標籤應包含屬性`data-cmp-data-layer-enabled`

   ```html
   <body class="page basicpage" id="page-id" data-cmp-data-layer-enabled>
       <script>
         window.adobeDataLayer = window.adobeDataLayer || [];
         adobeDataLayer.push({
             page: JSON.parse("{\x22page\u002D6c5d4b9fdd\x22:{\x22xdm:language\x22:\x22en\x22,\x22repo:path\x22:\x22\/content\/wknd\/language\u002Dmasters\/en.html\x22,\x22xdm:tags\x22:[],\x22xdm:template\x22:\x22\/conf\/wknd\/settings\/wcm\/templates\/landing\u002Dpage\u002Dtemplate\x22,\x22@type\x22:\x22wknd\/components\/page\x22,\x22dc:description\x22:\x22WKND is a collective of outdoors, music, crafts, adventure sports, and travel enthusiasts that want to share our experiences, connections, and expertise with the world.\x22,\x22dc:title\x22:\x22WKND Adventures and Travel\x22,\x22repo:modifyDate\x22:\x222020\u002D09\u002D29T07:50:13Z\x22}}"),
             event:'cmp:show',
             eventInfo: {
                 path: 'page.page\u002D6c5d4b9fdd'
             }
         });
       </script>
   ```

1. 您也可以開啟瀏覽器的開發人員工具，在主控台中，`adobeDataLayer` JavaScript物件應可供使用。 輸入以下命令以獲取當前頁面的資料層狀態：

   ```javascript
   window.adobeDataLayer.getState();
   ```

## 支援的元件{#supported-components}

以下元件支援資料層。

* [折疊式面板](/help/components/accordion.md)
* [階層連結](/help/components/breadcrumb.md)
* [按鈕](/help/components/button.md)
* [傳送](/help/components/carousel.md)
* [內容片段](/help/components/content-fragment-component.md)
* [影像](/help/components/image.md)
* [語言導覽](/help/components/language-navigation.md)
* [清單](/help/components/list.md)
* [導覽](/help/components/navigation.md)
* [頁面](/help/components/page.md)
* [進度列](/help/components/progress-bar.md)
* [索引標籤](/help/components/tabs.md)
* [Teaser](/help/components/teaser.md)
* [文字](/help/components/text.md)
* [標題](/help/components/title.md)

另請參閱由元件觸發的[事件。](#events-components)

## 核心元件資料結構{#data-schemas}

以下是核心元件與資料層一起使用的方案清單。

### 元件／容器項方案{#item}

元件／容器項模式用於以下元件：

* [階層連結](/help/components/breadcrumb.md)
* [按鈕](/help/components/button.md)
* [語言導覽](/help/components/language-navigation.md)
* [清單](/help/components/list.md)
* [導覽](/help/components/navigation.md)
* [摘要](/help/components/teaser.md)
* [文字](/help/components/text.md)
* [標題](/help/components/title.md)

元件／容器項方案定義如下。

```javascript
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

以下[event](#events)與元件／容器項模式相關：

* `cmp:click`

### 頁面結構{#page}

頁面架構由下列元件使用：

* [頁面](/help/components/page.md)

頁面結構定義如下。

```javascript
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

頁面載入時會觸發`cmp:show`事件。 此事件會從緊接在`<body>`開頭標籤下方的內嵌JavaScript中傳送，使它成為資料層事件佇列中最早的事件。

### 容器結構{#container}

Container架構由下列元件使用：

* [折疊式面板](/help/components/accordion.md)
* [索引標籤](/help/components/tabs.md)
* [傳送](/help/components/carousel.md)

容器結構描述的定義如下。

```javascript
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

下列[events](#events)與容器結構描述相關：

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### 映像架構{#image}

以下元件使用映像模式：

* [影像](/help/components/image.md)

映像模式定義如下。

```javascript
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

以下[event](#events)與映像架構相關：

* `cmp:click`

### 資產結構{#asset}

資產架構用於[Image元件內。](/help/components/image.md)

資產結構定義如下。

```javascript
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

以下[event](#events)與資產結構相關：

* `cmp:click`

### 內容片段結構{#content-fragment}

內容片段架構由[內容片段元件使用。](/help/components/content-fragment-component.md)

內容片段架構的定義如下。

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    elements            // array of the Content Fragment elements
}
```

用於「內容片段」元素的架構如下。

```javascript
{
    xdm:title           // title
    xdm:text            // text
}
```

## 核心元件事件{#events}

核心元件會透過資料層觸發許多事件。 與資料層交互的最佳實踐是：[註冊事件偵聽器](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener)和&#x200B;*，然後*&#x200B;根據觸發事件的事件類型和／或元件採取操作。 這將避免使用非同步指令碼的潛在競爭條件。

以下是核心元件提供的現成可用AEM事件：

* **`cmp:click`** -按一下可點按的元素(具有屬性的 `data-cmp-clickable` 元素)會使資料層觸發 `cmp:click` 事件。
* **`cmp:show`** 和 **`cmp:hide`** -控制accordion（展開／收合）、轉盤（下一個／上一個按鈕）和標籤（標籤選擇）元件，會分別觸發資料層 `cmp:show` 和事 `cmp:hide` 件。`cmp:show`事件也會在頁面載入時派發，並預期會是第一個事件。
* **`cmp:loaded`** -當資料層填入頁面上的核心元件時，資料層就會觸發 `cmp:loaded` 事件。

### 元件{#events-components}觸發的事件

下表列出觸發事件的標準核心元件以及這些事件。

| 元件 | 事件 |
|---|---|
| [折疊式面板](/help/components/accordion.md) | `cmp:show`與`cmp:hide` |
| [按鈕](/help/components/button.md) | `cmp:click` |
| [階層連結](/help/components/breadcrumb.md) | `cmp:click` |
| [傳送](/help/components/carousel.md) | `cmp:show`與`cmp:hide` |
| [語言導覽](/help/components/language-navigation.md) | `cmp:click` |
| [導覽](/help/components/navigation.md) | `cmp:click` |
| [頁面](/help/components/page.md) | `cmp:show` |
| [索引標籤](/help/components/tabs.md) | `cmp:show`與`cmp:hide` |
| [摘要](/help/components/teaser.md) | `cmp:click` |

### 事件路徑資訊{#event-path-info}

由核心元件觸發的每個資料層事AEM件都會包含具有下列JSON物件的裝載：

```json
eventInfo: {
    path: '<component-path>'
}
```

其中`<component-path>`是觸發事件之資料層中元件的JSON路徑。  此值可透過`event.eventInfo.path`取用，因為它可用作`adobeDataLayer.getState(<component-path>)`的參數，以擷取觸發事件之元件的目前狀態，讓自訂程式碼可存取其他資料並將其新增至資料層。

例如：

```javascript
function logEventObject(event) {
    if(event.hasOwnProperty("eventInfo") && event.eventInfo.hasOwnProperty("path")) {
        var dataObject = window.adobeDataLayer.getState(event.eventInfo.path);
        console.debug("The component that triggered this event: ");
        console.log(dataObject);
    }
}

window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function (dl) {
     dl.addEventListener("cmp:show", logEventObject);
});
```

## 教學課程

想要更詳細地探索資料層和核心元件嗎？ [查看本實作教學課程](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html)。

>[!TIP]
>
>若要進一步探索資料層的彈性，請檢視整合選項，包括如何為自訂元件啟用資料層。
