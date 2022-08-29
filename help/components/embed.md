---
title: 嵌入元件
description: 嵌入元件可將外部內容嵌入到內AEM容頁中。
role: Architect, Developer, Admin, User
exl-id: 985fa304-70a3-4329-957e-76d1832a06f1
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 1%

---

# 嵌入元件 {#embed-component}

核心元件嵌入元件允許將外部內容嵌入內AEM容頁中。

## 使用狀況 {#usage}

核心元件嵌入元件允許內容作者定義要嵌入到內容頁面中的所AEM選外部內容。 此外，還可以選擇定義要嵌入的自由格式HTML。

* 元件的屬性可在 [配置對話框](#configure-dialog)。
* 在將元件添加到頁面時，可以在 [設計對話框](#design-dialog)。

## 版本和相容性 {#version-and-compatibility}

嵌入元件的當前版本是v2，該版本於2022年2月隨核心元件2.18.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v2 | - | 相容 | 相容 |
| [v1](v1/embed.md) | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗嵌入元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_embed)。

## 技術詳細資訊 {#technical-details}

有關嵌入元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_embed_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

通過「配置」對話框，內容作者可以定義要嵌入頁面的外部資源。

### 屬性頁籤 {#properties-tab}

首先選擇應嵌入的資源類型：

* [URL](#url)
* [內嵌項目](#embeddable)
* [HTML](#html)

對於每種可嵌入類型，可以定義 **ID**。 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。

* 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
* 如果指定了ID，則作者有責任確保其唯一。
* 更改ID可能會影響CSS、JS和資料層跟蹤。

#### URL {#url}

最簡單的嵌入方式是URL。 只需貼上要嵌入的資源的URL **URL** 的子菜單。 該元件將嘗試訪問該資源，如果該資源可由其中一個處理器呈現，則它將在 **URL** 的子菜單。 否則，將錯誤標籤該欄位。

嵌入式元件隨處理器一起提供，用於以下資源類型：

* 符合 [嵌入標準](https://oembed.com/) 包括Facebook郵報，Instagram，聲雲，Twitter和YouTube
* Pinterest

開發人員可以通過 [遵循嵌入元件的開發人員文檔。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![URL的嵌入元件編輯對話框](/help/assets/embed-url.png)

#### 內嵌項目 {#embeddable}

嵌入式允許對嵌入式資源進行更多的定製，該嵌入式資源可以參數化並包括附加資訊。 作者可以從預先配置的可信嵌入式中進行選擇，並且元件隨YouTube可嵌入式出廠。

的 **可嵌入** 欄位定義要使用的處理器類型。 如果是YouTube可侵佔的，您可以定義：

* **視頻ID**  — 要嵌入的資源的YouTube的唯一視頻ID
* **寬度**  — 嵌入式視頻的寬度
* **高度**  — 嵌入式視頻的高度
* **啟用靜音**  — 此參數指定視頻是否預設播放靜音。 啟用此功能會增加Autoplay在現代瀏覽器中工作的機會。
* **啟用自動播放**  — 此參數指定在播放器載入時初始視頻是否自動開始播放。 這僅對發佈實例或使用 **查看為已發佈** 的子菜單。
* **啟用循環**  — 在單個視頻的情況下，此參數指定播放器是否應重複播放初始視頻。 在播放清單的情況下，播放器播放整個播放清單，然後在第一個視頻處重新開始。
* **啟用內聯播放(iOS)**  — 此參數控制視頻在iOS的HTML5播放器中是內聯播放（開啟）還是全屏播放（關閉）。
* **非限制相關視頻**  — 如果禁用此選項，則相關視頻將來自與剛才播放的視頻相同的頻道，否則它們將來自任何頻道。

其他可嵌入項將提供類似的欄位，並可由開發者定義 [遵循嵌入元件的開發人員文檔。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![嵌入元件的編輯對話框](/help/assets/embed-embeddable.png)

>[!NOTE]
>
>必須通過 [設計對話框](#design-dialog) 可供頁面作者使用。

#### HTML {#html}

可以使用「嵌入元件」將自由格式HTML添加到頁面。

![嵌入元件的編輯對話框，用於HTML](/help/assets/embed-html.png)

>[!NOTE]
>任何不安全標籤（如指令碼）都將從輸入的HTML中篩選，不會在生成的頁面上呈現。

##### 安全性 {#security}

作者可以輸入的HTML標籤會出於安全目的進行篩選，以避免跨站點指令碼攻擊，例如允許作者獲得管理權限。

通常，所有指令碼和 `style` 元素以及所有 `on*` 和 `style` 屬性將從輸出中刪除。

但是，由於嵌入元件遵循全AEM局HTMLAntiSamy衛生框架過濾規則集，因此規則更複雜。 `/libs/cq/xssprotection/config.xml`。 如果需要，開發人員可以為項目特定配置覆蓋此內容。

其他安全資訊可在 [現場AEM安裝的開發人員文檔](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/security.html) 以及 [AEMas a Cloud Service安裝。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>
>儘管反薩米衛生框架規則可以通過覆蓋來配置 `/libs/cq/xssprotection/config.xml`，這些更改會影響所有HTL和JSP行為，而不僅影響嵌入核心元件。

### 樣式頁籤 {#styles-tab-edit}

![「嵌入元件」的「編輯」對話框的「樣式」頁籤](/help/assets/embed-styles.png)

嵌入元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便下拉菜單可用。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者可用的選項，內容作者使用「嵌入元件」和放置「嵌入元件」時設定的預設值。

### 可嵌入類型頁籤 {#embeddable-types-tab}

![嵌入元件的設計對話框](/help/assets/embed-design.png)

* **禁用URL**  — 禁用 **URL** 選項
* **禁用嵌入式**  — 禁用 **可嵌入** 選項，無論允許使用哪個可嵌入處理器。
* **禁用HTML**  — 禁用 **HTML** 的子菜單。
* **允許的嵌入式**  — 定義內容作者可使用哪些可嵌入處理器的多選，前提是 **可嵌入** 選項。

### YouTube頁籤 {#youtube-tab}

![「嵌入元件」設計對話框的「YouTube」頁籤](/help/assets/embed-design-youtube.png)

* **允許配置靜音行為**  — 允許內容作者配置 **啟用靜音** 選項
   * **靜音的預設值**  — 自動設定 **啟用靜音** 選項
* **允許配置自動播放行為**  — 允許內容作者配置 **啟用自動播放** 選項
   * **自動播放的預設值**  — 自動設定 **啟用自動播放** 選項
* **允許配置循環行為**  — 允許內容作者配置 **啟用循環** 選項
   * **循環的預設值**  — 自動設定 **啟用循環** 選項
* **允許配置內聯播放(iOS)**  — 允許內容作者配置 **啟用內聯播放(iOS)** 選項
   * **內聯播放的預設值(iOS)**  — 自動設定 **啟用內聯播放(iOS)** 選項
* **允許配置內聯視頻**  — 允許內容作者配置 **非限制相關視頻** 選項
   * **非限制相關視頻的預設值**  — 自動設定 **非限制相關視頻** 選項
