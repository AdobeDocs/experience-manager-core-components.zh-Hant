---
title: 將Adobe客戶端資料層與核心元件一起使用
description: 將Adobe客戶端資料層與核心元件一起使用
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: 55c984d3-deb7-4eda-a81d-7768791d2b46
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '972'
ht-degree: 5%

---

# 將Adobe客戶端資料層與核心元件一起使用 {#data-layer-core-components}

Adobe客戶端資料層的目標是通過提供標準化方法來公開和訪問任何指令碼的任何類型的資料，從而減少對網站的測試工作量。

Adobe客戶端資料層與平台無關，但完全整合到核心元件中，供使用AEM。

與核心元件一樣，Adobe客戶端資料層的代碼可以在GitHub上以及其開發人員文檔中找到。 本文檔概述了核心元件如何與資料層進行交互，但將全部技術詳細資訊推遲到GitHub文檔中。

>[!TIP]
>
>有關Adobe客戶端資料層的詳細資訊， [請參閱其GitHub儲存庫中的資源。](https://github.com/adobe/adobe-client-data-layer)
>
>有關Adobe客戶端資料層與核心元件整合的進一步技術詳細資訊，請參見 [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) 檔案。

## 安裝和激活 {#installation-activation}

從2.9.0版核心元件開始，資料層與核心元件一起作為客戶AEM端庫分發，無需安裝。 由 [AEM原型V.24+項目](/help/developing/archetype/overview.md) 預設情況下包括已激活的資料層。

要手動激活資料層，必須建立 [上下文感知配置](/help/developing/context-aware-configs.md) 對於它：

1. 在 `/conf/<mySite>` 資料夾，其中 `<mySite>` 是站點項目的名稱：
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * 其中每個節點具有 `jcr:primaryType` 設定為 `nt:unstructured`。
1. 添加名為 `enabled` 並將其設定為 `true`。

   ![DataLayerConfig在WKND參考站點中的位置](/help/assets/datalayer-contextaware-sling-config.png)

   *DataLayerConfig在WKND參考站點中的位置*

1. 添加 `sling:configRef` 屬性 `jcr:content` 下面站點的節點 `/content` (例如 `/content/<mySite>/jcr:content`)並將其設定為 `/conf/<mySite>` 從上一步開始。

1. 啟用後，可以通過載入編輯器外部站點的頁面來驗證激活，例如，使用 **查看為已發佈** 的子菜單。 Inspect的頁面來源和 `<body>` 標籤應包括屬性 `data-cmp-data-layer-enabled`

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

1. 您還可以開啟瀏覽器的開發人員工具，並在控制台中 `adobeDataLayer` JavaScript對象應可用。 輸入以下命令以獲取當前頁的資料層狀態：

   ```javascript
   window.adobeDataLayer.getState();
   ```

## 支援的元件 {#supported-components}

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
* [Page](/help/components/page.md)
* [進度列](/help/components/progress-bar.md)
* [索引標籤](/help/components/tabs.md)
* [Teaser](/help/components/teaser.md)
* [文字](/help/components/text.md)
* [標題](/help/components/title.md)

另請參閱 [由元件觸發的事件。](#events-components)

## 核心元件資料架構 {#data-schemas}

以下是核心元件與資料層一起使用的方案清單。

### 元件/容器項架構 {#item}

元件/容器項架構用於以下元件：

* [階層連結](/help/components/breadcrumb.md)
* [按鈕](/help/components/button.md)
* [語言導覽](/help/components/language-navigation.md)
* [清單](/help/components/list.md)
* [導覽](/help/components/navigation.md)
* [Teaser](/help/components/teaser.md)
* [文字](/help/components/text.md)
* [標題](/help/components/title.md)

元件/容器項架構定義如下。

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

以下 [事件](#events) 與元件/容器項架構相關：

* `cmp:click`

### 頁架構 {#page}

頁面架構由以下元件使用：

* [Page](/help/components/page.md)

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

A `cmp:show` 在頁面載入時觸發事件。 此事件從正好位於開啟位置下方的JavaScript行中調度 `<body>` 標籤，使其成為資料層事件隊列中最早的事件。

### 容器架構 {#container}

容器架構由以下元件使用：

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

以下 [事件](#events) 與容器架構相關：

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### 映像架構 {#image}

以下元件使用映像架構：

* [影像](/help/components/image.md)

映像架構的定義如下。

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

以下 [事件](#events) 與映像架構相關：

* `cmp:click`

### 資產架構 {#asset}

資產架構在 [影像元件。](/help/components/image.md)

資產架構的定義如下。

```javascript
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

以下 [事件](#events) 與資產架構相關：

* `cmp:click`

### 內容片段架構 {#content-fragment}

內容片段架構由 [內容片段元件。](/help/components/content-fragment-component.md)

內容片段架構定義如下。

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

用於內容片段元素的架構如下所示。

```javascript
{
    xdm:title           // title
    xdm:text            // text
}
```

## 核心元件事件 {#events}

核心元件通過資料層觸發了許多事件。 與資料層交互的最佳做法是 [註冊事件偵聽器](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener) 和 *然後* 根據觸發事件的事件類型和/或元件執行操作。 這將避免使用非同步指令碼的潛在競爭條件。

以下是核心元件提供的現成AEM事件：

* **`cmp:click`**  — 按一下可按一下元素(具有 `data-cmp-clickable` 屬性)使資料層觸發 `cmp:click` 的子菜單。
* **`cmp:show`** 和 **`cmp:hide`**  — 操作折疊面板（展開/折疊）、旋轉軸（下一個/上一個按鈕）和制表符（制表符選擇）元件，使資料層觸發 `cmp:show` 和 `cmp:hide` 事件。 A `cmp:show` 事件也會在頁載入時派發，並且應該是第一個事件。
* **`cmp:loaded`**  — 一旦資料層在頁面上填充了核心元件，資料層就會觸發 `cmp:loaded` 的子菜單。

### 元件觸發的事件 {#events-components}

下表列出了觸發事件的標準核心元件以及這些事件。

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

由核心元件觸發的每個資料層事AEM件都將包含具有以下JSON對象的負載：

```json
eventInfo: {
    path: '<component-path>'
}
```

位置 `<component-path>` 是觸發事件的資料層中元件的JSON路徑。  值，可通過 `event.eventInfo.path`，因為它可以用作 `adobeDataLayer.getState(<component-path>)` 它檢索觸發事件的元件的當前狀態，允許自定義代碼訪問其他資料並將其添加到資料層。

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

想更詳細地瞭解資料層和核心元件嗎？ [查看本操作教程](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html)。

>[!TIP]
>
>要進一步瞭解資料層的靈活性，請查看有關整合選項的資訊，包括如何為自定義元件啟用資料層。
