---
title: 包括客戶端庫
description: 根據您的使用案例，有許多不同的方式可包含用戶端程式庫。
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 3%

---


# 包含客戶端庫{#including-client-libraries}

根據您的使用案例，有許多不同的方式可包含[用戶端程式庫](/help/developing/archetype/uifrontend.md#clientlibs)。 本檔案提供範例和每個範例的[HTL程式碼片段](https://docs.adobe.com/content/help/zh-Hant/experience-manager-htl/using/overview.html)。

## 建議的預設使用{#recommended-default-usage}

如果您沒有時間調查最適合您的情況，請在頁面`head`元素中放置下列HTL行，加入您的用戶端程式庫：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

這會在您的頁面`head`中同時包含CSS和JS，但會將`defer`屬性新增至您的JS `script`包含，如此瀏覽器就會等到DOM就緒後再執行指令碼，進而最佳化頁面載入速度。

## 基本用法{#basic-usage}

包含用戶端程式庫類別的JS和CSS的基本語法（將產生所有對應的CSS `link`元素和／或JS `script`元素）如下：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

若要同時針對多個用戶端程式庫類別執行相同動作，可將字串陣列傳遞至`categories`參數：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## 僅限CSS或JS {#css-js-only}

通常，您會想要將CSS包含置於HTML `head`元素中，而JS包含在`body`元素關閉之前。

在`head`中，若要僅包含CSS而非JS，請使用`cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

在`body`關閉之前，若要僅包含JS，而非CSS，請使用`jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## 屬性 {#attributes}

若要將屬性套用至產生的CSS `link`元素和／或JS `script`元素，可能有許多參數：

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

* `media`:字串JS `script` 屬性，可傳遞至 `jsAndCssIncludes` 和 `jsIncludes`:
* `async`: 布林值
* `defer`: 布林值
* `onload`: 字串
* `crossorigin`: 字串

## 內嵌{#inlining}

在某些情況下，若要最佳化，或是透過電子郵件或[AMP,](amp.md)可能需要將CSS或JS內嵌至HTML輸出。

若要內嵌CSS，可使用`cssInline`，在此情況下，您必須編寫周圍的`style`元素：

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

同樣地，若要內嵌JS，可使用`jsInline`，在此情況下，您必須寫入周圍的`script`元素：

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## 載入內容感應CSS和JavaScript {#context-aware-loading}

[頁面元件](/help/components/page.md)也支援載入開發人員定義的內容感應CSS、JavaScript或中繼標籤。

通過使用以下結構為`com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig`建立[上下文感知資源](context-aware-configs.md)來完成此操作：

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
