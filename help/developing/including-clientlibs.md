---
title: 包括客戶端庫
description: 根據您的使用案例，有許多不同的方法可包含用戶端程式庫。
role: Architect, Developer, Administrator
exl-id: 84e7c178-247b-42a2-99bf-6d1699ecee14
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 3%

---

# 包括客戶端庫{#including-client-libraries}

根據您的使用案例，有許多不同的方法可包含[用戶端程式庫](/help/developing/archetype/uifrontend.md#clientlibs)。 本檔案提供各自的範例和範例[ HTL片段](https://docs.adobe.com/content/help/zh-Hant/experience-manager-htl/using/overview.html)。

## 建議的預設用法{#recommended-default-usage}

如果您沒有時間調查最適合您的情況，請在頁面`head`元素內放置下列HTL行，加入用戶端程式庫：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

這會同時在您的頁面`head`中包含CSS和JS，但會將`defer`屬性新增至您的JS `script`包含，讓瀏覽器在執行指令碼之前等待DOM就緒，進而最佳化頁面載入速度。

## 基本用法{#basic-usage}

包含用戶端程式庫類別的JS和CSS的基本語法（將產生所有對應的CSS `link`元素及/或JS `script`元素）如下：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

若要一次對多個用戶端程式庫類別執行相同操作，可將字串陣列傳遞至`categories`參數：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## 僅限CSS或JS {#css-js-only}

人們通常會想要將CSS包含在HTML `head`元素中，而JS則包含在`body`元素結尾之前。

在`head`中，若要僅包含CSS而不包含JS，請使用`cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

在`body`結尾之前，若要僅包含JS而不包含CSS，請使用`jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## 屬性 {#attributes}

若要將屬性套用至產生的CSS `link`元素及/或JS `script`元素，可以使用數個參數：

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

* `media`:字串 `script` JS屬性，可傳遞至 `jsAndCssIncludes` 和 `jsIncludes`:
* `async`: 布林值
* `defer`: 布林值
* `onload`: 字串
* `crossorigin`: 字串

## 內襯 {#inlining}

在某些情況下，無論是為了最佳化，還是為了電子郵件或[AMP,](amp.md)可能需要將CSS或JS內嵌至HTML的輸出中。

若要內嵌CSS，可使用`cssInline`，在此情況下，您必須撰寫周圍的`style`元素：

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

同樣地，若要內嵌JS，可以使用`jsInline`，在此情況下，您必須寫入周圍的`script`元素：

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## 載入內容感知CSS和JavaScript {#context-aware-loading}

[頁面元件](/help/components/page.md)也支援載入開發人員定義的內容感知CSS、JavaScript或中繼標籤。

要完成此操作，請使用下列結構為`com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig`建立[內容感知資源](context-aware-configs.md):

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
