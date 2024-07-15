---
title: 使用者端程式庫與核心元件
description: 核心元件隨附許多使用者端資料庫，並提供包含您自己的資料庫的功能。
role: Architect, Developer, Admin
exl-id: 84e7c178-247b-42a2-99bf-6d1699ecee14
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---


# 使用者端程式庫與核心元件 {#client-libraries}

核心元件隨附許多使用者端資料庫，並提供包含您自己的資料庫的功能。

## 提供的使用者端資料庫 {#provided}

核心元件提供下列現成可用的使用者端程式庫。

* **網站** clientlibs提供要套用至網站的元件之最小功能行為。
   * 它們可作為加速專案的起點，並鼓勵實施延伸並[自訂它們](/help/developing/customizing.md)以獲得想要的外觀和功能。
* **編輯器** clientlibs已套用至編寫對話方塊，以確保其預期的功能和外觀。
* 以編輯模式載入時，**editorhook** clientlibs會套用至網站。
   * 這些檔案包含在編輯器觸發的事件上執行的JavaScript程式碼，有助於初始化動態功能。
* 某些元件可能有針對特定情況而設計的特定其他clientlibs，例如搭配[Dynamic Media](/help/components/image.md#dynamic-media)使用時。

## 包含使用者端資料庫 {#including}

根據您的使用案例，有多種不同的方式來包含[使用者端資料庫](/help/developing/archetype/front-end.md#clientlibs)。 以下範例包含每個的範例[HTL代碼片段](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html)。

### 建議的預設使用方式 {#recommended-default-usage}

如果您沒時間調查您所處情況下的最佳使用，請將下列HTL行放入頁面`head`元素中，以包含使用者端資料庫：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

這會將CSS和JS納入您的頁面`head`，但將`defer`屬性新增至您的JS `script` include，讓瀏覽器等候DOM就緒後再執行指令碼，進而最佳化頁面載入速度。

### 基本用途 {#basic-usage}

包含使用者端程式庫類別之JS和CSS的基本語法（將產生所有對應的CSS `link`元素和/或JS `script`元素）如下：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

若要一次對多個使用者端程式庫類別執行相同操作，可將字串陣列傳遞至`categories`引數：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

### 僅限CSS或JS {#css-js-only}

通常，需要將CSS includes放在HTML`head`元素中，並將JS includes放在`body`元素的結尾之前。

在`head`中，若只要包含CSS而非JS，請使用`cssIncludes`：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

在`body`結束之前，若只要包含JS而非CSS，請使用`jsIncludes`：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

### 屬性 {#attributes}

若要將屬性套用至產生的CSS `link`元素及/或JS `script`元素，可以有許多引數：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base',
    media='print',
    async=true,
    defer=true,
    onload='console.log(\'loaded: \' + this.src)',
    crossorigin='anonymous'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

可傳遞至`jsAndCssIncludes`和`cssIncludes`的CSS `link`屬性：

* `media`：字串JS `script`屬性，可傳遞至`jsAndCssIncludes`和`jsIncludes`：
* `async`：布林值
* `defer`：布林值
* `onload`：字串
* `crossorigin`：字串

### 內嵌 {#inlining}

在某些情況下，針對最佳化、電子郵件或[AMP，](amp.md)，可能需要將CSS或JS內嵌到HTML輸出中。

若要內嵌CSS，可使用`cssInline`，在此情況下，您必須編寫周圍的`style`元素：

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

同樣地，若要內嵌JS，可以使用`jsInline`，在此情況下，您必須編寫周圍的`script`元素：

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

### 載入內容感知CSS和JavaScript {#context-aware-loading}

[頁面元件](/help/components/page.md)也支援載入開發人員定義的內容感知CSS、JavaScript或中繼標籤。

若要這麼做，請使用下列結構為`com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig`建立[內容感知資源](context-aware-configs.md)：

```text
com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig
    - prefixPath="/some/path"
    + item01
        - element=["link"|"script"|"meta"]
        - location=["header"|"footer"]
        + attributes
            - attributeName01="attributeValue01"
            - attributeName02="attributeValue02"
            ...
    + item02
        ...
    ...
```

[如需詳細資訊，請參閱頁面元件的技術檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page#loading-of-context-aware-cssjs)
