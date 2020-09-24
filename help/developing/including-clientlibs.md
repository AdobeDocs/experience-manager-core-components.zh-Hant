---
title: 包括客戶端庫
description: 根據您的使用案例，有許多不同的方式可包含用戶端程式庫。
translation-type: tm+mt
source-git-commit: 24f718be2ba66113eda970c213c6ce4baec51752
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---


# 包括客戶端庫 {#including-client-libraries}

根據您的使用案例，有許多不同 [的方式](/help/developing/archetype/uifrontend.md#clientlibs) ，來包含用戶端程式庫。 本檔案提供各自的範例 [和範例HTL程式碼片段](https://docs.adobe.com/content/help/zh-Hant/experience-manager-htl/using/overview.html) 。

## 建議的預設使用 {#recommended-default-usage}

如果您沒有時間調查最適合您的情況，請在頁面元素中放置下列HTL行，加入您的用戶端程 `head` 式庫：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

這會在您的頁面中同時包含CSS和JS `head`，但是會將屬性新增至JS `defer``script` ，如此瀏覽器就會等到DOM就緒後再執行指令碼，進而最佳化頁面載入速度。

## 基本使用 {#basic-usage}

包含用戶端資料庫類別的JS和CSS（將產生所有對應的CSS元素和／或JS元素）的基本語法如下： `link``script`

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

若要一次對多個用戶端程式庫類別執行相同動作，可將一組字串傳遞至參數 `categories` :

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## 僅限CSS或JS {#css-js-only}

通常，您會想要將CSS包含置於HTML元 `head` 素中，而JS則包含在關閉元素之前 `body` 。&#x200B;
在中， `head`若要僅包含CSS，而非JS，請使用 `cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

在關閉 `body` 之前，若要只包含JS，而不包含CSS，請使用 `jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## 屬性 {#attributes}

若要將屬性套用至產生的CSS `link` 元素和／或JS `script` 元素，可能有許多參數：

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

可傳 `link` 遞至和的CSS屬 `jsAndCssIncludes` 性 `cssIncludes`:

* `media`:字&#x200B;串JS `script` 屬性，可傳遞至 `jsAndCssIncludes` 和 `jsIncludes`:

* `async`: 布林值
* `defer`: 布林值
* `onload`: 字串
* `crossorigin`: 字串

## 內襯 {#inlining}

在某些情況下，為了最佳化，或為了電子郵件或 [AMP,](amp.md) 可能需要將CSS或JS內嵌在HTML的輸出中。&#x200B;
若要內嵌CSS, `cssInline` 可使用，在此情況下，您必須編寫周圍的元 `style` 素：

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

同樣地，若要內嵌JS, `jsInline` 則可使用，此時您必須編寫周圍的元 `script` 素：

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```
