---
title: 搭配核心元件使用Adobe使用者端資料層
description: 搭配核心元件使用Adobe使用者端資料層
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: 55c984d3-deb7-4eda-a81d-7768791d2b46
source-git-commit: 5994133947ff697f7c866fe61598c58e37e77008
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 4%

---


# 搭配核心元件使用Adobe使用者端資料層 {#data-layer-core-components}

Adobe Client Data Layer的目標是提供標準化方法，公開和存取任何指令碼的任何型別的資料，以減少檢測網站所需的工作量。

Adobe Client Data Layer不受平台限制，但已完全整合至核心元件，以與AEM搭配使用。

和核心元件一樣，Adobe Client Data Layer的程式碼可在GitHub與其開發人員檔案中取得。 本檔案概述核心元件與資料層的互動方式，但完整技術詳細資訊將遞延至GitHub檔案。

>[!TIP]
>
>如需Adobe Client Data Layer的詳細資訊，[請參閱其GitHub存放庫中的資源。](https://github.com/adobe/adobe-client-data-layer)
>
>如需Adobe使用者端資料層與核心元件整合的詳細技術資訊，請參閱核心元件存放庫中的[`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md)檔案。

{{traditional-aem}}

## 安裝及啟用 {#installation-activation}

截至核心元件2.9.0版，Data Layer會作為AEM使用者端程式庫隨核心元件發佈，無需安裝。 [AEM專案原型v. 24+](/help/developing/archetype/overview.md)產生的所有專案預設包含已啟動的資料層。

若要手動啟動資料層，您必須為其建立[內容感知設定](/help/developing/context-aware-configs.md)：

1. 在`/conf/<mySite>`資料夾下方建立下列結構，其中`<mySite>`是您網站的專案名稱：
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * 其中每個節點都將`jcr:primaryType`設定為`nt:unstructured`。
1. 新增名稱為`enabled`的布林值屬性，並將其設定為`true`。

   WKND參照站台中![DataLayerConfig的位置](/help/assets/datalayer-contextaware-sling-config.png)

   WKND參照站台中&#x200B;*DataLayerConfig的位置*

1. 將`sling:configRef`屬性新增至您網站的`jcr:content`節點，位置在`/content` （例如`/content/<mySite>/jcr:content`）下，並將其設定為上一步驟中的`/conf/<mySite>`。

1. 啟用後，您可以在編輯器之外載入網站的頁面，例如使用編輯器中的&#x200B;**以發佈的形式檢視**&#x200B;選項，以驗證啟動。 檢查頁面來源，`<body>`標籤應包含屬性`data-cmp-data-layer-enabled`

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

1. 您也可以開啟瀏覽器的開發人員工具，然後在主控台中，`adobeDataLayer` JavaScript物件應該可供使用。 輸入下列命令以取得目前頁面的「資料層」狀態：

   ```javascript
   window.adobeDataLayer.getState();
   ```

## 支援的元件 {#supported-components}

下列元件支援資料層。

* [折疊面板](/help/components/accordion.md)
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
* [標籤](/help/components/tabs.md)
* [Teaser](/help/components/teaser.md)
* [文字](/help/components/text.md)
* [標題](/help/components/title.md)

另請參閱元件所觸發的[事件。](#events-components)

## 核心元件資料結構描述 {#data-schemas}

以下是核心元件搭配Data Layer使用的結構描述清單。

### 元件/容器專案結構描述 {#item}

元件/容器專案結構用於以下元件中：

* [階層連結](/help/components/breadcrumb.md)
* [按鈕](/help/components/button.md)
* [語言導覽](/help/components/language-navigation.md)
* [清單](/help/components/list.md)
* [導覽](/help/components/navigation.md)
* [Teaser](/help/components/teaser.md)
* [文字](/help/components/text.md)
* [標題](/help/components/title.md)

元件/容器專案結構描述的定義如下。

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

下列[事件](#events)與元件/容器專案結構描述相關：

* `cmp:click`

### 頁面結構描述 {#page}

「頁面」綱要由下列元件使用：

* [頁面](/help/components/page.md)

「頁面」綱要的定義如下。

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

頁面載入時會觸發`cmp:show`事件。 此事件從緊接在開頭`<body>`標籤下方的內嵌JavaScript中傳送，使其成為資料層事件佇列中最早的事件。

### 容器結構描述 {#container}

容器結構描述可供下列元件使用：

* [折疊面板](/help/components/accordion.md)
* [標籤](/help/components/tabs.md)
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

下列[個事件](#events)與容器結構描述相關：

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### 影像結構描述 {#image}

影像結構描述可供下列元件使用：

* [影像](/help/components/image.md)

影像結構的定義如下。

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

下列[事件](#events)與影像結構描述相關：

* `cmp:click`

### 資產結構 {#asset}

資產結構描述用於[影像元件內。](/help/components/image.md)

資產結構的定義如下。

```javascript
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

下列[事件](#events)與資產結構描述相關：

* `cmp:click`

### 內容片段結構描述 {#content-fragment}

內容片段結構描述已由[內容片段元件](/help/components/content-fragment-component.md)使用。

內容片段結構的定義如下。

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

用於內容片段元素的結構描述如下。

```javascript
{
    xdm:title           // title
    xdm:text            // text
}
```

## 核心元件事件 {#events}

核心元件會透過「資料層」觸發許多事件。 與資料層互動的最佳實務是[註冊事件接聽程式](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener)，然後&#x200B;*根據事件型別和/或觸發事件的元件採取動作。*&#x200B;這將避免與非同步指令碼的潛在競爭條件。

以下為AEM核心元件所提供的現成事件：

* **`cmp:click`** — 按一下可點按的元素（具有`data-cmp-clickable`屬性的元素）會導致資料層觸發`cmp:click`事件。
* **`cmp:show`**&#x200B;和&#x200B;**`cmp:hide`** — 操作收合式選單（展開/摺疊）、轉盤（下一個/上一個按鈕）和標籤（索引標籤選取）元件會導致資料層分別觸發`cmp:show`和`cmp:hide`事件。 `cmp:show`事件也會在頁面載入時傳送，且預期會成為第一個事件。
* **`cmp:loaded`** — 使用頁面上的核心元件填入Data Layer之後，Data Layer就會觸發`cmp:loaded`事件。

### 元件觸發的事件 {#events-components}

下表列出會觸發事件以及這些事件的標準核心元件。

| 元件 | 事件 |
|---|---|
| [折疊式面板](/help/components/accordion.md) | `cmp:show`和`cmp:hide` |
| [按鈕](/help/components/button.md) | `cmp:click` |
| [階層連結](/help/components/breadcrumb.md) | `cmp:click` |
| [傳送](/help/components/carousel.md) | `cmp:show`和`cmp:hide` |
| [語言導覽](/help/components/language-navigation.md) | `cmp:click` |
| [導覽](/help/components/navigation.md) | `cmp:click` |
| [頁面](/help/components/page.md) | `cmp:show` |
| [索引標籤](/help/components/tabs.md) | `cmp:show`和`cmp:hide` |
| [Teaser](/help/components/teaser.md) | `cmp:click` |

### 事件路徑資訊 {#event-path-info}

AEM核心元件觸發的每個Data Layer事件將包含具有以下JSON物件的裝載：

```json
eventInfo: {
    path: '<component-path>'
}
```

其中`<component-path>`是資料層中觸發事件的元件的JSON路徑。  值是重要的，可透過`event.eventInfo.path`使用，因為它可以用作`adobeDataLayer.getState(<component-path>)`的引數，它會擷取觸發事件的元件目前狀態，允許自訂程式碼存取其他資料並將其新增到資料層。

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

想要更詳細地探索資料層和核心元件嗎？ [檢視此實作教學課程](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html?lang=zh-Hant)。

>[!TIP]
>
>若要進一步探索Data Layer的彈性，請檢閱相關的整合選項，包括如何為自訂元件啟用Data Layer。
