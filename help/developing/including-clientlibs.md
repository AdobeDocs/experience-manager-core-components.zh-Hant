---
title: 包括客戶端庫
description: 根據您的使用案例，有多種不同的方法來包括客戶端庫。
role: Architect, Developer, Admin
exl-id: 84e7c178-247b-42a2-99bf-6d1699ecee14
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# 包括客戶端庫 {#including-client-libraries}

有許多不同的方法可以包括 [客戶端庫](/help/developing/archetype/uifrontend.md#clientlibs) 取決於你的用例。 本文檔提供示例和示例 [HTL片段](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=zh-Hant) 每個。

## 建議的預設用法 {#recommended-default-usage}

如果您沒有時間調查最適合您的情況，請將以下HTL行放在您的頁面中，以包括您的客戶端庫 `head` 元素：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

這將包括頁面中的CSS和JS `head`，但添加 `defer` 屬於您的JS `script` 包括，以便瀏覽器在執行指令碼之前等待DOM就緒，從而優化頁面載入速度。

## 基本用法 {#basic-usage}

包含客戶端庫類別的JS和CSS的基本語法，該類別將生成所有相應的CSS `link` 元素和/或JS `script` 元素，如下所示：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

要同時對多個客戶端庫類別執行相同操作，可以將字串陣列傳遞給 `categories` 參數：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## 僅CSS或JS {#css-js-only}

通常，您希望將CSS包括在HTML中 `head` 元素，而JS包含在 `body` 的子菜單。

在 `head`，只包括CSS而不包括JS，請使用 `cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

在 `body` 關閉，僅包括JS，而不包括CSS，使用 `jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## 屬性 {#attributes}

將屬性應用於生成的CSS `link` 元素和/或JS `script` 元素，可能有多個參數：

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

CSS `link` 可傳遞給的屬性 `jsAndCssIncludes` 和 `cssIncludes`:

* `media`:字串JS `script` 可傳遞給的屬性 `jsAndCssIncludes` 和 `jsIncludes`:
* `async`: 布林值
* `defer`: 布林值
* `onload`: 字串
* `crossorigin`: 字串

## 內襯 {#inlining}

在某些情況下，為優化或電子郵件或 [安培，](amp.md) 可能需要將CSS或JS內嵌到HTML的輸出中。

要在CSS內嵌， `cssInline` 可以使用，在這種情況下，您必須寫入周圍 `style` 元素：

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

同樣，要內嵌JS, `jsInline` 可以使用，在這種情況下，您必須寫入周圍 `script` 元素：

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## 載入上下文感知CSS和JavaScript {#context-aware-loading}

的 [頁面元件](/help/components/page.md) 還支援載入開發人員定義的上下文感知CSS、JavaScript或meta標籤。

通過建立 [上下文感知資源](context-aware-configs.md) 為 `com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig` 使用以下結構：

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

[有關詳細資訊，請參閱頁面元件的技術文檔。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page#loading-of-context-aware-cssjs)
