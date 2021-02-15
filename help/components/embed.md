---
title: 內嵌元件
description: 「內嵌元件」可讓您將外部內容內嵌至AEM內容頁面。
translation-type: tm+mt
source-git-commit: 601bee9df2a82255c92fcf30b8dacde70b0583dc
workflow-type: tm+mt
source-wordcount: '1341'
ht-degree: 1%

---


# 內嵌元件{#embed-component}

核心元件內嵌元件可讓您將外部內容內嵌至AEM內容頁面。

## 使用狀況 {#usage}

「核心元件內嵌元件」可讓內容作者定義要內嵌在AEM內容頁面中的選取外部內容。 此外，還有一個選項可定義要嵌入的自由格式HTML。

* 在[configure dialog](#configure-dialog)中可定義元件的屬性。
* 將元件添加到頁面時的預設值可在[設計對話框](#design-dialog)中定義。

## 版本和相容性{#version-and-compatibility}

目前的內嵌元件版本為v1，此版本於2019年9月隨核心元件2.7.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗內嵌元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_embed)。

## 技術詳細資訊{#technical-details}

有關內嵌元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_embed_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

「配置」對話框允許內容作者定義要嵌入到頁面上的外部資源。 首先選擇應嵌入的資源類型：

* [URL](#url)
* [內嵌項目](#embeddable)
* [HTML](#html)

對於每種可嵌入類型，您可以定義ad **ID**。 此選項可控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。

* 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
* 如果指定ID，則作者有責任確保其唯一性。
* 變更ID可能會影響CSS、JS和資料圖層追蹤。

### URL {#url}

最簡單的內嵌方式是URL。 只需將要嵌入的資源的URL貼上到&#x200B;**URL**&#x200B;欄位中即可。 該元件將嘗試訪問資源，如果它可由其中一個處理器呈現，它將在&#x200B;**URL**&#x200B;欄位下顯示確認消息。 否則，欄位將會標籤為錯誤。

嵌入元件隨處理器提供以下資源類型：

* 符合[oEmbed標準](https://oembed.com/)的資源，包括Facebook貼文、Instagram、SoundCloud、Twitter和YouTube
* Pinterest

開發人員可依內嵌元件的開發人員檔案，透過[新增額外的URL處理器。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![URL的內嵌元件編輯對話方塊](/help/assets/embed-url.png)

### 內嵌項目 {#embeddable}

嵌入式允許對嵌入式資源進行更多的定製，該嵌入式資源可以參數化並包括附加資訊。 作者可從預先設定的受信任內嵌項目中選擇，而元件隨附於YouTube可內嵌的現成可用項目。

**Embeddable**&#x200B;欄位定義要使用的處理器類型。 若是YouTube內嵌式，您可以定義：

* **視訊ID**  —— 您要內嵌之資源之YouTube的唯一視訊ID
* **Width**  —— 內嵌視訊的寬度
* **高度** -內嵌視訊的高度
* **啟用靜音** -此參數指定視訊是否預設為靜音播放。啟用此功能可增加自動播放在現代瀏覽器中運作的機會。
* **啟用自動播放** -此參數會指定當播放器載入時，初始視訊是否會自動開始播放。這僅在發佈實例上或在編寫實例上使用&#x200B;**「以發佈方式查看」(View as Published)選項時有效。**
* **啟用回圈** -若是單一視訊，此參數會指定播放器是否應重複播放初始視訊。在播放清單的情況下，播放器會播放整個播放清單，然後在第一個視訊開始。
* **啟用內嵌播放(iOS)** -此參數控制iOS上HTML5播放器中的影片是內嵌（開）或全螢幕（關）播放。
* **不受限制的相關影片** -如果此選項已停用，相關影片將會來自與剛播放的影片相同的頻道，否則會來自任何頻道。

請注意，必須通過[設計對話框](#design-dialog)激活「啟用」選項，並且可以設定為預設值。

其他內嵌項目會提供類似欄位，可由開發人員在內嵌元件的開發人員檔案後，[定義。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![內嵌元件的編輯對話方塊](/help/assets/embed-embeddable.png)

>[!NOTE]
>必須透過[設計對話框](#design-dialog)在範本層級啟用內嵌項，才能讓頁面作者使用。

### HTML {#html}

您可以使用內嵌元件，將自由格式的HTML新增至您的頁面。

![HTML的內嵌元件編輯對話方塊](/help/assets/embed-html.png)

>[!NOTE]
>任何不安全的標籤（例如指令碼）都會從輸入的HTML中篩選，而不會在產生的頁面上呈現。

#### 安全性 {#security}

作者可輸入的HTML標籤會經過篩選，以利安全，以避免跨網站指令碼攻擊，例如允許作者取得管理權限。

*一般而言，* 所有指令 `style` 碼和元素，以 `on*` 及所 `style` 有和屬性都會從輸出中移除。

但是，由於內嵌元件遵循AEM的全域HTML AntiSamy環衛架構篩選規則集，因此規則更複雜，此規則集位於`/libs/cq/xssprotection/config.xml`。 如有需要，開發人員可以覆蓋專案特定組態。

如需其他安全性資訊，請參閱[AEM開發人員檔案中的內部部署安裝](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/security.html)以及[AEM(Cloud Service)安裝。](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>雖然AntiSamy環衛架構規則可透過覆蓋`/libs/cq/xssprotection/config.xml`來設定，但這些變更會影響所有HTL和JSP行為，而不只是內嵌核心元件。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義內容作者可用的選項，內容作者使用內嵌元件，以及放置內嵌元件時設定的預設值。

### 可嵌入類型頁籤{#embeddable-types-tab}

![內嵌元件的設計對話方塊](/help/assets/embed-design.png)

* **停用URL**  —— 在選取 **** 內容作者時停用URL選項
* **禁用嵌入** -在選擇內 **** 容作者時禁用「嵌入」選項，而不管允許哪些嵌入處理器。
* **停用HTML**  —— 在選取時停 **** 用內容作者的HTML選項。
* **允許嵌入** -多選定，定義內容作者可以使用哪些可嵌入的處理器，但 **** Embeddables選項處於活動狀態。

### YouTube標籤{#youtube-tab}

![內嵌元件設計對話方塊的YouTube標籤](/help/assets/embed-design-youtube.png)

* **允許設定靜音行為** -允許內容作者在選取YouTube內嵌類型時，在 **元** 件中設定「啟用Mute」選項
   * **mute的預設值** -選取YouTube內嵌 **類型** 時，自動設定「啟用Muteoption」
* **允許設定自動播放行為** -允許內容作者在選取YouTube內嵌類型 **時** ，在元件中設定「啟用自動播放」選項
   * **autoplay的預設值** -選取YouTube內嵌 **類型** 時，自動設定「啟用自動播放」選項
* **允許設定循環行為** -允許內容作者在選取YouTube內嵌類型 **時** ，在元件中設定「啟用載入」選項
   * **loop的預設值** -選取YouTube內嵌 **類型** 時，自動設定「啟用載入」
* **允許設定內嵌播放(iOS)** -允許內容作者在選取YouTube內嵌類型時，在元件中設定「 **Enable Inline Playback(iOS)** 」選項
   * **內嵌播放(iOS)的預設值** -選取YouTube內嵌類型 **時，自動設** 定「啟用內嵌播放(iOS)」選項
* **允許設定內嵌影片** -允許內容作者在選取YouTube內嵌類型時，在元件中設定「不受 **限制** 的相關影片」選項
   * **非限制相關影片的預設值** -選取YouTube內嵌 **類型時，** 自動設定「不受限制的相關影片」選項
