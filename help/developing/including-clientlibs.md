---
title: 包含使用者端資料庫
description: 根據您的使用案例，包含使用者端資料庫的方式有很多種。
role: Architect, Developer, Admin
exl-id: 84e7c178-247b-42a2-99bf-6d1699ecee14
source-git-commit: 39a5dee1666fa2645e0579fdfac0400f7fcbdc27
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 0%

---

# 包含使用者端資料庫 {#including-client-libraries}

要包含的方法有很多種 [使用者端資料庫](/help/developing/archetype/front-end.md#clientlibs) 視您的使用案例而定。 本檔案提供範例和範例 [HTL代碼片段](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html) （每個）。

## 建議的預設使用方式 {#recommended-default-usage}

如果您沒時間調查您所處情況下的最佳使用，請在頁面中放入下列HTL行，以包含使用者端程式庫 `head` 元素：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

這會將CSS和JS納入您的頁面 `head`，但新增 `defer` 屬性至您的JS `script` 包含，讓瀏覽器等候DOM準備就緒再執行指令碼，進而將頁面載入速度最佳化。

## 基本用途 {#basic-usage}

包含使用者端資料庫類別的JS和CSS的基本語法，會產生所有對應的CSS `link` 元素和/或JS `script` 元素如下所示：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

若要一次對多個使用者端程式庫類別執行相同操作，可將字串陣列傳遞至 `categories` 引數：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## 僅限CSS或JS {#css-js-only}

通常，需要將CSS包含的內容放入HTML中 `head` 元素，且JS包含在 `body` 元素。

在 `head`，僅包含CSS而非JS，請使用 `cssIncludes`：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

早於 `body` 關閉，若只要包含JS而非CSS，請使用 `jsIncludes`：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## 屬性 {#attributes}

若要將屬性套用至產生的CSS `link` 元素和/或JS `script` 元素中，可以有許多引數：

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

CSS `link` 可傳遞到的屬性 `jsAndCssIncludes` 和 `cssIncludes`：

* `media`：字串JS `script` 可傳遞到的屬性 `jsAndCssIncludes` 和 `jsIncludes`：
* `async`：布林值
* `defer`：布林值
* `onload`：字串
* `crossorigin`：字串

## 內嵌 {#inlining}

在某些情況下，針對最佳化，或針對電子郵件或 [AMP、](amp.md) 可能需要將CSS或JS內嵌至HTML的輸出中。

若要內嵌CSS， `cssInline` 可使用，在此情況下，您必須編寫周圍的 `style` 元素：

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

同樣地，若要內嵌JS， `jsInline` 可使用，在此情況下，您必須編寫周圍的 `script` 元素：

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## 載入內容感知CSS和JavaScript {#context-aware-loading}

此 [頁面元件](/help/components/page.md) 也支援載入開發人員定義的內容感知CSS、JavaScript或中繼標籤。

這可透過建立 [內容感知資源](context-aware-configs.md) 的 `com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig` 使用下列結構：

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
