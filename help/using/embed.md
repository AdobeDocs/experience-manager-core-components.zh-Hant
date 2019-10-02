---
title: 內嵌元件
seo-title: 內嵌元件
description: 「內嵌元件」可讓您將外部內容內嵌至AEM內容頁面。
seo-description: 內嵌元件可讓您將外部內容內嵌至AEM內容頁面。
content-type: 引用
topic-tags: 核心元件
translation-type: tm+mt
source-git-commit: 97f1461b57079806f9f96d325d9b763538e32127

---


# 內嵌元件{#embed-component}

核心元件內嵌元件可讓您將外部內容內嵌至AEM內容頁面。

## 使用狀況 {#usage}

「核心元件內嵌元件」可讓內容作者定義要內嵌在AEM內容頁面中的選取外部內容。 此外，還有一個選項可定義要嵌入的自由格式HTML。

* 可在「配置」對話框中定義元件的 [屬性](#configure-dialog)。
* 將元件新增至頁面時的預設值，可在設計對話方塊中 [定義](#design-dialog)。

## 版本與相容性 {#version-and-compatibility}

目前的內嵌元件版本為v1，此版本於2019年9月隨核心元件2.7.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗內嵌元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](http://opensource.adobe.com/aem-core-wcm-components/library/embed.html)。

## 技術詳細資訊 {#technical-details}

有關內嵌元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## 配置對話框 {#configure-dialog}

「配置」對話框允許內容作者定義要嵌入到頁面上的外部資源。 首先選擇應嵌入的資源類型： **URL**、 **可內嵌**&#x200B;或 **HTML**。

### URL {#url}

最簡單的內嵌方式是URL。 只需將您要內嵌的資源URL貼入「 **URL** 」欄位。 The component will attempt to access the resource and if it can be rendered by one of the processors, it will display a confirmation message below the URL field. **** If not, the field will be marked in error.

嵌入元件隨處理器提供以下資源類型：

* Resources that comply with the oEmbed standard including Facebook Post, Instagram, SoundCloud, Twitter, and YouTube[](https://oembed.com/)
* Pinterest

Developers can add additional URL processors by following the developer documentation of the Embed Component.[](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.08.29.png)

### 內嵌項目 {#embeddable}

Embeddables allow for more customization of the embedded resource, which can be parameterized and include additional information. An author is able to select from pre-configured trusted embeddables and the component ships with a Youtube embeddable out-of-the-box.

The **Embeddable** field defines the type of processor you want to use. In the case of the YouTube embeddable you can then define:

* **Video ID - The unique video ID from YouTube of the resource you want to embed**
* **Width - The width of the embedded video**
* **Height - The height of the embedded video**

Other embeddables would offer similar fields and can be defined by a developer by [following the developer documentation of the Embed Component.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.15.00.png)

>[!NOTE]
>Embeddables must be enabled at the template level via the [Design Dialog](#design-dialog) to be available to the page author.

### HTML {#html}

You can add free-form HTML to your page using the Embed Component.

![](assets/screen-shot-2019-09-25-10.20.00.png)

>[!NOTE]
>任何不安全的標籤（例如指令碼）都會從輸入的HTML中篩選，而不會在產生的頁面上呈現。

## Design Dialog {#design-dialog}

設計對話方塊可讓範本作者定義內容作者可用的選項，內容作者使用內嵌元件，並在放置內嵌元件時設定預設值。

![](assets/screen-shot-2019-09-25-10.25.28.png)

* **停用URL** —— 在選取 **內容作者時** ，停用URL選項
* **禁用嵌入式** -在選中時禁用內 **容作者的「可嵌入** 」選項，而不管允許哪些可嵌入處理器。
* **停用HTML** —— 在選取時停 **用內容作者的HTML** 選項。
* **允許的嵌入** -定義內容作者可以使用哪些可嵌入處理器的多選項，但 **是Embeddable** 選項處於活動狀態。
