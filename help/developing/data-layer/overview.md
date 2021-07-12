---
title: 搭配核心元件使用Adobe用戶端資料層
description: 搭配核心元件使用Adobe用戶端資料層
feature: 核心元件，Adobe用戶端資料層
role: Architect, Developer, Admin
exl-id: 55c984d3-deb7-4eda-a81d-7768791d2b46
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '980'
ht-degree: 5%

---

# 搭配核心元件使用Adobe用戶端資料層 {#data-layer-core-components}

Adobe用戶端資料層的目標是透過提供標準化方法來公開和存取任何指令碼的任何類型資料，以減少對網站進行檢測的工作量。

Adobe用戶端資料層不受平台限制，但已完全整合至核心元件，以便與AEM搭配使用。

和核心元件一樣，Adobe用戶端資料層的程式碼也可在GitHub及其開發人員檔案中取得。 本檔案概述核心元件與資料層互動的方式，但GitHub檔案會延後提供完整的技術詳細資訊。

>[!TIP]
>
>如需Adobe用戶端資料層的詳細資訊，請[參閱其GitHub存放庫中的資源。](https://github.com/adobe/adobe-client-data-layer)
>
>如需整合Adobe用戶端資料層與核心元件的詳細技術資訊，請參閱核心元件存放庫中的[`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md)檔案。

## 安裝與啟用 {#installation-activation}

自核心元件2.9.0版起，資料層以AEM用戶端程式庫的形式與核心元件一併分佈，不需安裝。 依預設，由[AEM專案原型v. 24+](/help/developing/archetype/overview.md)產生的所有專案都包含已啟用的資料層。

若要手動啟用資料層，您必須為其建立[內容感知設定](/help/developing/context-aware-configs.md):

1. 在`/conf/<mySite>`資料夾下方建立下列結構，其中`<mySite>`為網站專案的名稱：
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * 其中，每個節點的`jcr:primaryType`設定為`nt:unstructured`。
1. 添加名為`enabled`的布爾屬性，並將其設定為`true`。

   ![DataLayerConfig在WKND參考站點中的位置](/help/assets/datalayer-contextaware-sling-config.png)

   *DataLayerConfig在WKND參考站點中的位置*

1. 將`sling:configRef`屬性新增至`/content`下網站的`jcr:content`節點(例如`/content/<mySite>/jcr:content`)，並從上一步驟將其設為`/conf/<mySite>`。

1. 啟用後，您可以在編輯器外部載入網站的頁面，例如使用編輯器中的&#x200B;**以Published**&#x200B;檢視選項來驗證啟動。 Inspect頁面來源和`<body>`標籤應包含屬性`data-cmp-data-layer-enabled`

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

1. 您也可以開啟瀏覽器的開發人員工具，並在主控台中使用`adobeDataLayer` JavaScript物件。 輸入以下命令以取得目前頁面的資料層狀態：

   ```javascript
   window.adobeDataLayer.getState();
   ```

## 支援的元件 {#supported-components}

下列元件支援資料層。

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

另請參閱元件觸發的[事件。](#events-components)

## 核心元件資料結構 {#data-schemas}

以下是核心元件與資料層搭配使用的結構清單。

### 元件/容器項目結構 {#item}

元件/容器項目結構用於下列元件：

* [階層連結](/help/components/breadcrumb.md)
* [按鈕](/help/components/button.md)
* [語言導覽](/help/components/language-navigation.md)
* [清單](/help/components/list.md)
* [導覽](/help/components/navigation.md)
* [Teaser](/help/components/teaser.md)
* [文字](/help/components/text.md)
* [標題](/help/components/title.md)

元件/容器項目架構的定義如下。

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

下列[event](#events)與元件/容器項目架構相關：

* `cmp:click`

### 頁面結構 {#page}

頁面架構由下列元件使用：

* [頁面](/help/components/page.md)

頁面架構的定義如下。

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

頁面載入時會觸發`cmp:show`事件。 此事件會從緊接在開頭`<body>`標籤下方的內嵌JavaScript發送，因此會是資料層事件佇列中最早的事件。

### 容器結構 {#container}

容器結構由下列元件使用：

* [折疊式面板](/help/components/accordion.md)
* [索引標籤](/help/components/tabs.md)
* [傳送](/help/components/carousel.md)

容器架構的定義如下。

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

下列[events](#events)與容器架構相關：

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### 影像結構 {#image}

以下元件使用影像架構：

* [影像](/help/components/image.md)

影像架構的定義如下。

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

下列[event](#events)與影像架構相關：

* `cmp:click`

### 資產結構 {#asset}

資產架構用於[影像元件內。](/help/components/image.md)

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

下列[event](#events)與資產結構相關：

* `cmp:click`

### 內容片段結構 {#content-fragment}

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

## 核心元件事件 {#events}

核心元件會透過資料層觸發許多事件。 與資料層互動的最佳實務是[註冊事件接聽器](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener)和&#x200B;*，然後*&#x200B;根據觸發事件的事件類型和/或元件採取動作。 這樣可避免非同步指令碼的潛在競爭條件。

以下是AEM核心元件提供的現成可用事件：

* **`cmp:click`**  — 按一下可點按的元素(具有屬 `data-cmp-clickable` 性的元素)會導致資料層觸發 `cmp:click` 事件。
* **`cmp:show`** 和 —  **`cmp:hide`** 控制折疊式功能表（展開/折疊）、輪播（下一個/上一個按鈕）和標籤（索引標籤選取）元件，會分別導致資料層 `cmp:show` 觸發和 `cmp:hide` 事件。`cmp:show`事件也會在頁面載入時發送，且應為第一個事件。
* **`cmp:loaded`**  — 當資料層填入頁面上的核心元件時，資料層就會觸發 `cmp:loaded` 事件。

### 元件觸發的事件 {#events-components}

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
| [Teaser](/help/components/teaser.md) | `cmp:click` |

### 事件路徑資訊 {#event-path-info}

AEM核心元件所觸發的每個資料層事件都會包含具有下列JSON物件的裝載：

```json
eventInfo: {
    path: '<component-path>'
}
```

其中`<component-path>`是觸發事件之資料層中元件的JSON路徑。  此值可透過`event.eventInfo.path`取得，因為它可作為`adobeDataLayer.getState(<component-path>)`的參數，以擷取觸發事件之元件的目前狀態，讓自訂程式碼可存取其他資料並將其新增至資料層。

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

想要更詳細地探索資料層和核心元件嗎？ [查看此實作教學課程](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html)。

>[!TIP]
>
>若要進一步探索資料層的彈性，請檢閱整合選項，包括如何為自訂元件啟用資料層。
