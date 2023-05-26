---
title: 搭配核心元件使用Adobe Client Data Layer
description: 搭配核心元件使用Adobe Client Data Layer
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: 55c984d3-deb7-4eda-a81d-7768791d2b46
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '972'
ht-degree: 5%

---

# 搭配核心元件使用Adobe Client Data Layer {#data-layer-core-components}

Adobe使用者端資料層的目標是提供標準化方法，公開和存取任何指令碼的任何型別的資料，以減少檢測網站所需的工作量。

Adobe Client Data Layer不受平台限制，但已完全整合至核心元件，以與AEM搭配使用。

和核心元件一樣，GitHub上也提供Adobe Client Data Layer的程式碼以及其開發人員檔案。 本檔案概述核心元件與Data Layer的互動方式，但完整技術詳細資訊將推遲至GitHub檔案說明。

>[!TIP]
>
>如需Adobe使用者端資料層的詳細資訊， [請參閱其GitHub存放庫中的資源。](https://github.com/adobe/adobe-client-data-layer)
>
>如需Adobe使用者端資料層與核心元件整合的詳細技術資訊，請參閱 [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) 檔案中設定的完整路徑。

## 安裝與啟用 {#installation-activation}

截至核心元件2.9.0版，Data Layer以AEM使用者端程式庫形式隨核心元件發佈，無需安裝。 所有產生的專案 [AEM專案原型v. 24+](/help/developing/archetype/overview.md) 預設會包含已啟動的資料層。

若要手動啟動資料層，您必須建立 [內容感知設定](/help/developing/context-aware-configs.md) 適用於：

1. 在下方建立下列結構 `/conf/<mySite>` 資料夾，其中 `<mySite>` 是您網站的專案名稱：
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * 其中每個節點都有 `jcr:primaryType` 設定為 `nt:unstructured`.
1. 新增布林值屬性，稱為 `enabled` 並將其設定為 `true`.

   ![WKND參考網站中DataLayerConfig的位置](/help/assets/datalayer-contextaware-sling-config.png)

   *WKND參考網站中DataLayerConfig的位置*

1. 新增 `sling:configRef` 屬性至 `jcr:content` 您的網站節點在下 `/content` (例如： `/content/<mySite>/jcr:content`)並設為 `/conf/<mySite>` 上一步驟中的。

1. 啟用後，您可以在編輯器之外載入網站的頁面，以驗證啟用狀態，例如，使用 **檢視已發佈** 選項中設定的預設值。 Inspect頁面來源和 `<body>` 標籤應包含屬性 `data-cmp-data-layer-enabled`

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

1. 您也可以開啟瀏覽器的開發人員工具，並在主控台中 `adobeDataLayer` JavaScript物件應該可以使用。 輸入下列命令以取得目前頁面的「資料層」狀態：

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
* [Page](/help/components/page.md)
* [進度列](/help/components/progress-bar.md)
* [索引標籤](/help/components/tabs.md)
* [Teaser](/help/components/teaser.md)
* [文字](/help/components/text.md)
* [標題](/help/components/title.md)

另請參閱 [元件觸發的事件。](#events-components)

## 核心元件資料結構描述 {#data-schemas}

以下是核心元件搭配Data Layer使用的結構描述清單。

### 元件/容器專案結構描述 {#item}

元件/容器專案結構描述會用於下列元件中：

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

下列專案 [事件](#events) 與元件/容器專案結構描述相關：

* `cmp:click`

### 頁面結構描述 {#page}

「頁面」綱要由下列元件使用：

* [Page](/help/components/page.md)

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

A `cmp:show` 事件會在頁面載入時觸發。 此事件會從緊接在開頭下方的內嵌JavaScript傳送 `<body>` 標籤，使其成為Data Layer事件佇列中最早的事件。

### 容器結構描述 {#container}

容器結構描述可供下列元件使用：

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

下列專案 [事件](#events) 與容器結構描述相關：

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### 影像結構描述 {#image}

影像結構描述由以下元件使用：

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

下列專案 [事件](#events) 與影像結構描述相關：

* `cmp:click`

### 資產結構 {#asset}

此資產結構描述會用於 [影像元件。](/help/components/image.md)

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

下列專案 [事件](#events) 與資產結構描述相關：

* `cmp:click`

### 內容片段結構描述 {#content-fragment}

內容片段結構描述是由 [內容片段元件。](/help/components/content-fragment-component.md)

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

核心元件會透過Data Layer觸發許多事件。 與資料層互動的最佳實務是 [註冊事件監聽器](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener) 和 *則* 根據事件型別和/或觸發事件的元件採取動作。 這將避免與非同步指令碼發生可能的競爭情況。

以下為AEM核心元件所提供的現成事件：

* **`cmp:click`**  — 按一下可點按的元素(具有 `data-cmp-clickable` attribute)讓資料層觸發 `cmp:click` 事件。
* **`cmp:show`** 和 **`cmp:hide`**  — 操作摺疊式功能表（展開/摺疊）、輪播（下一個/上一個按鈕）和標籤（標籤選取）元件會導致資料層觸發 `cmp:show` 和 `cmp:hide` 個事件。 A `cmp:show` 事件也會在頁面載入時傳送，且預期為第一個事件。
* **`cmp:loaded`**  — 使用頁面上的核心元件填入Data Layer後， Data Layer會立即觸發 `cmp:loaded` 事件。

### 元件觸發的事件 {#events-components}

下表列出觸發事件的標準核心元件以及這些事件。

| Component | 事件 |
|---|---|
| [折疊式面板](/help/components/accordion.md) | `cmp:show` 和 `cmp:hide` |
| [按鈕](/help/components/button.md) | `cmp:click` |
| [階層連結](/help/components/breadcrumb.md) | `cmp:click` |
| [傳送](/help/components/carousel.md) | `cmp:show` 和 `cmp:hide` |
| [語言導覽](/help/components/language-navigation.md) | `cmp:click` |
| [導覽](/help/components/navigation.md) | `cmp:click` |
| [頁面](/help/components/page.md) | `cmp:show` |
| [索引標籤](/help/components/tabs.md) | `cmp:show` 和 `cmp:hide` |
| [Teaser](/help/components/teaser.md) | `cmp:click` |

### 事件路徑資訊 {#event-path-info}

AEM核心元件觸發的每個Data Layer事件將包含具有以下JSON物件的裝載：

```json
eventInfo: {
    path: '<component-path>'
}
```

位置 `<component-path>` 是資料層中觸發事件的元件的JSON路徑。  值，可透過以下方式取得： `event.eventInfo.path`，這點很重要，因為它可作為引數用於 `adobeDataLayer.getState(<component-path>)` 會擷取觸發事件的元件目前狀態，允許自訂程式碼存取其他資料並將其新增至Data Layer。

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

想要更詳細地探索資料層和核心元件嗎？ [請檢視此實作教學課程](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html).

>[!TIP]
>
>若要進一步探索Data Layer的彈性，請檢閱整合選項，包括如何為自訂元件啟用Data Layer。
