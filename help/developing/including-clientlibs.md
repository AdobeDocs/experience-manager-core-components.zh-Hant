---
title: 用戶端程式庫和核心元件
description: 核心元件隨附許多用戶端程式庫，也可支援加入您自訂的資料庫。
role: Architect, Developer, Admin
exl-id: 84e7c178-247b-42a2-99bf-6d1699ecee14
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: ht
source-wordcount: '518'
ht-degree: 100%

---


# 用戶端程式庫和核心元件 {#client-libraries}

核心元件隨附許多用戶端程式庫，也可支援加入您自訂的資料庫。

## 提供的用戶端程式庫 {#provided}

核心元件提供下列立即可用的用戶端程式庫。

* **網站** clientlib 提供要套用至網站的元件之最精簡功能行為。
   * 它們作為加速專案的起點，並鼓勵在實施時進行擴充和[自訂](/help/developing/customizing.md)，以獲得想要的外觀和功能。
* **編輯器** clientlib 已套用至編寫對話框，以確保其預期的功能和外觀。
* 以編輯模式載入時，**editorhook** clientlib 會套用至網站。
   * 其中包含在編輯器觸發事件上執行的 JavaScript 程式碼，有助於初始化動態功能。
* 某些元件可能有針對特定情況而設計的專用額外 clientlib，例如搭配 [Dynamic Media](/help/components/image.md#dynamic-media) 使用時。

## 加入用戶端程式庫 {#including}

根據您的使用案例，有多種不同的方式可加入[用戶端程式庫](/help/developing/archetype/front-end.md#clientlibs)。以下每個範例中均包含樣本 [HTL 片段](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html)。

### 建議的預設使用方式 {#recommended-default-usage}

如果您沒時間判斷哪種方式最符合你的需求，請將下列 HTL 指令行放入頁面 `head` 元素中，以加入您的用戶端資料庫：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

這會將 CSS 和 JS 加入您的頁面 `head`，而 `defer` 屬性則新增至您的 JS `script` includes，讓瀏覽器等候 DOM 就緒後再執行指令碼，進而最佳化頁面載入速度。

### 基本用途 {#basic-usage}

要同時加入用戶端程式庫類別的 JS 和 CSS，進而產生所有對應的 CSS `link` 元素和/或 JS `script` 元素，其基本語法如下：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

若要一次對多個用戶端程式庫類別執行相同操作，可將字串陣列傳遞至 `categories` 參數：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

### 僅限 CSS 或 JS {#css-js-only}

通常，需要將 CSS includes 放在 HTML `head` 元素中，並將 JS includes 放在 `body` 元素的結尾之前。

在 `head` 中，若只要加入 CSS 但不含 JS 時，請使用 `cssIncludes`：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

在 `body` 結尾前，若只要加入 JS 但不含 CSS 時，請使用 `jsIncludes`：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

### 屬性 {#attributes}

若要將屬性套用至產生的 CSS `link` 元素及/或 JS `script` 元素，有多個參數可使用：

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

可傳遞至 `jsAndCssIncludes` 和 `cssIncludes` 的 CSS `link` 屬性：

* `media`：可傳遞至 `jsAndCssIncludes` 和 `jsIncludes` 的字串 JS `script` 屬性：
* `async`：布林值
* `defer`：布林值
* `onload`：字串
* `crossorigin`：字串

### 內嵌 {#inlining}

某些情況下，針對最佳化、電子郵件或 [AMP](amp.md)，可能需要將 CSS 或 JS 內嵌到 HTML 輸出中。

若要內嵌 CSS，可使用 `cssInline`，在此情況下，您必須自行撰寫外圍的 `style` 元素：

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

若要內嵌 JS，則可使用 `jsInline`，在此情況下，同樣必須自行撰寫外圍的 `script` 元素：

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

### 載入內容感知 CSS 和 JavaScript {#context-aware-loading}

[頁面元件](/help/components/page.md)也支援載入開發人員定義的內容感知 CSS、JavaScript 或後設標記。

做法是使用下列結構為 `com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig` 建立[內容感知資源](context-aware-configs.md)：

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

[如需詳細資訊，請參閱頁面元件的技術文件。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page#loading-of-context-aware-cssjs)
