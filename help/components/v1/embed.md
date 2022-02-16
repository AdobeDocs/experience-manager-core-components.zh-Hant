---
title: 嵌入元件(v1)
description: The Embed Component enables embedding external content in an AEM content page.
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 0%

---


# 嵌入元件(v1) {#embed-component}

The Core Components Embed Component allows embedding external content in an AEM content page.

## 使用狀況 {#usage}

核心元件嵌入元件允許內容作者定義要嵌入到內容頁面中的所AEM選外部內容。 此外，還可以選擇定義要嵌入的自由格式HTML。

* 元件的屬性可在 [配置對話框](#configure-dialog)。
* 在將元件添加到頁面時，可以在 [設計對話框](#design-dialog)。

## Version and Compatibility {#version-and-compatibility}

本文檔介紹嵌入元件的v1，該版本於2019年9月隨核心元件2.7.0版推出。

>[!CAUTION]
>
>本文檔介紹嵌入元件的v1。
>
>有關嵌入元件當前版本的詳細資訊，請參閱 [嵌入元件](/help/components/embed.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

要體驗嵌入元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_embed)。

## 技術詳細資訊 {#technical-details}

有關嵌入元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_embed_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## Configure Dialog {#configure-dialog}

通過「配置」對話框，內容作者可以定義要嵌入頁面的外部資源。 First choose which type of resource should be embedded:

* [URL](#url)
* [內嵌項目](#embeddable)
* [HTML](#html)

For each type of embeddable, you can define ad **ID**. 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。

* 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
* 如果指定了ID，則作者有責任確保其唯一。
* 更改ID可能會影響CSS、JS和資料層跟蹤。

### URL {#url}

最簡單的嵌入方式是URL。 只需貼上要嵌入的資源的URL **URL** 的子菜單。 該元件將嘗試訪問該資源，如果該資源可由其中一個處理器呈現，則它將在 **URL** 的子菜單。 否則，將錯誤標籤該欄位。

嵌入式元件隨處理器一起提供，用於以下資源類型：

* 符合 [嵌入標準](https://oembed.com/) 包括Facebook郵報，Instagram，聲雲，Twitter和YouTube
* Pinterest

開發人員可以通過 [遵循嵌入元件的開發人員文檔。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Embed Component&#39;s edit dialog for URL](/help/assets/embed-url.png)

### 內嵌項目 {#embeddable}

Embeddables allow for more customization of the embedded resource, which can be parameterized and include additional information. 作者可以從預先配置的可信嵌入式中進行選擇，並且元件隨YouTube可嵌入式出廠。

的 **可嵌入** 欄位定義要使用的處理器類型。 In the case of the YouTube embeddable you can then define:

* **視頻ID**  — 要嵌入的資源的YouTube的唯一視頻ID
* **Width** - The width of the embedded video
* **高度**  — 嵌入式視頻的高度
* **啟用靜音**  — 此參數指定視頻是否預設播放靜音。 啟用此功能會增加Autoplay在現代瀏覽器中工作的機會。
* **啟用自動播放**  — 此參數指定在播放器載入時初始視頻是否自動開始播放。 這僅對發佈實例或使用 **查看為已發佈** 的子菜單。
* **啟用循環**  — 在單個視頻的情況下，此參數指定播放器是否應重複播放初始視頻。 在播放清單的情況下，播放器播放整個播放清單，然後在第一個視頻處重新開始。
* **啟用內聯播放(iOS)**  — 此參數控制視頻在iOS的HTML5播放器中是內聯播放（開啟）還是全屏播放（關閉）。
* **非限制相關視頻**  — 如果禁用此選項，則相關視頻將來自與剛才播放的視頻相同的頻道，否則它們將來自任何頻道。

請注意，必須通過 [設計對話框](#design-dialog) 可以設定為預設值。

其他可嵌入項將提供類似的欄位，並可由開發者定義 [遵循嵌入元件的開發人員文檔。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Embed Component&#39;s edit dialog for embeddables](/help/assets/embed-embeddable.png)

>[!NOTE]
>Embeddables must be enabled at the template level via the [Design Dialog](#design-dialog) to be available to the page author.

### HTML {#html}

可以使用「嵌入元件」將自由格式HTML添加到頁面。

![嵌入元件的編輯對話框，用於HTML](/help/assets/embed-html.png)

>[!NOTE]
>任何不安全標籤（如指令碼）都將從輸入的HTML中篩選，不會在生成的頁面上呈現。

#### 安全性 {#security}

作者可以輸入的HTML標籤會出於安全目的進行篩選，以避免跨站點指令碼攻擊，例如允許作者獲得管理權限。

*In general,* all script and `style` elements as well as all `on*` and `style` attributes will be removed from the output.

但是，由於嵌入元件遵循全AEM局HTMLAntiSamy衛生框架過濾規則集，因此規則更複雜。 `/libs/cq/xssprotection/config.xml`。 如果需要，開發人員可以為項目特定配置覆蓋此內容。

其他安全資訊可在 [現場AEM安裝的開發人員文檔](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/security.html) 以及 [AEMas a Cloud Service安裝。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>儘管反薩米衛生框架規則可以通過覆蓋來配置 `/libs/cq/xssprotection/config.xml`，這些更改會影響所有HTL和JSP行為，而不僅影響嵌入核心元件。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者可用的選項，內容作者使用「嵌入元件」和放置「嵌入元件」時設定的預設值。

### 可嵌入類型頁籤 {#embeddable-types-tab}

![嵌入元件的設計對話框](/help/assets/embed-design.png)

* **禁用URL**  — 禁用 **URL** 選項
* **Disable Embeddables** - Disables the **Embeddable** option for the content author when selected, regardless of which embeddable processors are allowed.
* **禁用HTML**  — 禁用 **HTML** 的子菜單。
* **Allowed Embeddables** - Multiselect that defines which embeddable processors are available to the content author, provided that the **Embeddable** option is active.

### YouTube頁籤 {#youtube-tab}

![「嵌入元件」設計對話框的「YouTube」頁籤](/help/assets/embed-design-youtube.png)

* **允許配置靜音行為**  — 允許內容作者配置 **啟用靜音** 選項
   * **靜音的預設值**  — 自動設定 **啟用靜音** 選項
* **Allow configuration of autoplay behavior** - Allows content author to configure the **Enable Autoplay** option in the component when the YouTube embed type is selected
   * **自動播放的預設值**  — 自動設定 **啟用自動播放** 選項
* **允許配置循環行為**  — 允許內容作者配置 **啟用循環** 選項
   * **循環的預設值**  — 自動設定 **啟用循環** 選項
* **允許配置內聯播放(iOS)**  — 允許內容作者配置 **啟用內聯播放(iOS)** 選項
   * **Default value of inline playback (iOS)** - Automatically sets **Enable Inline Playback (iOS)** option when the YouTube embed type is selected
* **允許配置內聯視頻**  — 允許內容作者配置 **非限制相關視頻** 選項
   * **非限制相關視頻的預設值**  — 自動設定 **非限制相關視頻** 選項
