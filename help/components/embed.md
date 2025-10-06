---
title: 嵌入元件
description: 嵌入元件可讓外部內容嵌入至 AEM 內容頁面。
role: Architect, Developer, Admin, User
exl-id: 985fa304-70a3-4329-957e-76d1832a06f1
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '1343'
ht-degree: 100%

---


# 嵌入元件 {#embed-component}

核心元件嵌入元件允許將外部內容嵌入至 AEM 內容頁面。

{{traditional-aem}}

## 用途 {#usage}

核心元件嵌入元件可讓內容作者定義要嵌入至 AEM 內容頁面中的已選取外部內容。此外，也可以選擇定義要嵌入的自由格式 HTML。

* 該元件的屬性可在[設定對話框](#configure-dialog)中定義。
* 將元件新增至頁面時，可在[設計對話框](#design-dialog)中定義預設值。

## 版本和相容性 {#version-and-compatibility}

嵌入元件的目前版本為 v2，此版本於 2022 年 2 月隨著核心元件 2.18.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v2 | - | 相容 | 相容 | 相容 |
| [v1](v1/embed.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「嵌入元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_embed)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_embed_v2)有關嵌入元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義要嵌入至頁面的外部資源。

### 屬性索引標籤 {#properties-tab}

首先選擇應該嵌入的資源類型：

* [URL](#url)
* [嵌入式項目](#embeddable)
* [HTML](#html)

針對各嵌入式項目的類型，您可以定義其 **ID**。此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。

* 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
* 若已指定 ID，則作者應確保其為唯一識別碼。
* 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

#### URL {#url}

最簡單的嵌入是 URL。只需將您要嵌入之資源的 URL 貼到 **URL** 欄位中即可。元件將嘗試存取資源，如果可由其中一個處理器轉譯，則會在 **URL** 欄位下方顯示確認訊息。如無法進行，該欄位將會標示為錯誤。

嵌入元件隨附下列資源類型的處理器：

* 符合 [oEmbed 標準](https://oembed.com/)的資源，包括 Facebook 貼文、Instagram、SoundCloud、Twitter 和 YouTube
* Pinterest

開發人員可以[根據嵌入元件的開發人員文件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)新增其他 URL 處理器。

![嵌入元件的 URL 編輯對話框](/help/assets/embed-url.png)

#### 嵌入式項目 {#embeddable}

嵌入式項目允許嵌入資源的更多自訂，這些自訂可以參數化並包含其他資訊。作者能從預先設定的受信任嵌入式項目中進行選取，此元件也隨附立即可用的 YouTube 嵌入式項目。

**嵌入式項目**&#x200B;欄位定義您要使用的處理器類型。在使用 YouTube 嵌入式項目的情況下，您可以定義：

* **影片 ID** - 您要嵌入之資源來自 YouTube 的唯一影片 ID
* **寬度** - 嵌入影片的寬度
* **高度** - 嵌入影片的高度
* **啟用靜音** - 此參數會指定影片在預設情況下是否將靜音播放。啟用此項會增加自動播放在現代瀏覽器中運作的機會。
* **啟用自動播放** - 此參數會指定在播放器載入後，初始影片是否將自動開始播放。這只有在發佈執行個體上或在編寫執行個體上使用&#x200B;**以發佈頁面形式檢視**&#x200B;選項時有效。
* **啟用循環播放** - 在單一影片的情況下，此參數會指定播放器是否應重複播放初始影片。若是播放清單，播放器會播放整個播放清單，然後從第一個影片重新開始。
* **啟用內嵌播放 (iOS)** - 此參數會控制在 iOS 上的 HTML5 播放器中，影片會內嵌播放 (開) 還是全螢幕播放 (關)。
* **不受限制的相關影片** - 如果停用此選項，則相關影片將來自與剛剛播放的影片相同的頻道，否則將來自任何頻道。

其他嵌入式項目將提供類似的欄位，並可由開發人員[根據嵌入元件的開發人員文件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)定義。

![嵌入元件的嵌入式項目編輯對話框](/help/assets/embed-embeddable.png)

>[!NOTE]
>
>嵌入式項目必須透過[設計對話框](#design-dialog) 在範本層級啟用，頁面作者才能使用。

#### HTML {#html}

您可以使用嵌入元件，將自由格式的 HTML 新增至您的頁面。

![嵌入元件的 HTML 編輯對話框](/help/assets/embed-html.png)

>[!NOTE]
>任何不安全的標籤 (例如指令碼) 將會從輸入的 HTML 中篩除，且不會在產生的頁面上轉譯。

##### 安全性 {#security}

基於安全考量，作者可以輸入的 HTML 標記會進行篩選，以免受跨網站指令碼攻擊，例如允許作者取得管理許可權限。

一般來說，所有指令碼和 `style` 元素以及所有 `on*` 和 `style` 屬性都將從輸出中移除。

不過，規則其實更為複雜，因為嵌入元件會遵循 AEM 的全域 HTML AntiSamy 清理框架篩選規則集，此規範可以在 `/libs/cq/xssprotection/config.xml` 中找到。如有需要，開發人員可採用專案專用的設定進行覆蓋。

有關其他安全性資訊，請參閱[適用於AEM as a Cloud Service 安裝](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/home.html)及[適用於內部部署安裝的 AEM 開發人員文件](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/security.html)。

>[!NOTE]
>
>雖然 AntiSamy 清理框架規則可透過覆蓋 `/libs/cq/xssprotection/config.xml` 來設定，但這些變更會影響到所有 HTL 和 JSP 行為，而不只是嵌入核心元件。

### 樣式索引標籤 {#styles-tab-edit}

![嵌入元件編輯對話框的樣式索引標籤](/help/assets/embed-styles.png)

嵌入元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取想要套用至元件的樣式。在編輯對話框中所做的選取，與從元件工具列中選擇具有相同效果。

元件樣式必須在[設計對話框](#design-dialog)中設定，才能使用該下拉式清單。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可為使用嵌入元件的內容作者定義可用選項，以及在放置嵌入元件時所設定的預設值。

### 嵌入式項目類型索引標籤 {#embeddable-types-tab}

![嵌入元件的設計對話框](/help/assets/embed-design.png)

* **停用 URL** - 選取後，停用內容作者的 **URL** 選項
* **停用嵌入式項目** - 選取後，停用內容作者的&#x200B;**嵌入式項目**&#x200B;選項，無論允許哪些嵌入式項目處理器。
* **停用 HTML** - 選取後，停用內容作者的 **HTML** 選項。
* **允許的嵌入式項目** - 多重選取，只要&#x200B;**嵌入式項目**&#x200B;選項為作用中，即可定義哪些嵌入式項目處理器可供內容作者使用。

### YouTube 索引標籤 {#youtube-tab}

![嵌入元件設計對話框的 YouTube 索引標籤](/help/assets/embed-design-youtube.png)

* **允許設定靜音行為** - 允許內容作者在選取 YouTube 嵌入類型時，在元件中設定&#x200B;**啟用靜音**&#x200B;選項
   * **靜音的預設值** - 當選取 YouTube 嵌入類型時，自動設定&#x200B;**啟用靜音**&#x200B;選項
* **允許設定自動播放行為** - 允許內容作者在選取 YouTube 嵌入類型時，在元件中設定&#x200B;**啟用自動播放**&#x200B;選項
   * **自動播放的預設值** - 當選取 YouTube 嵌入類型時，自動設定&#x200B;**啟用自動播放**&#x200B;選項
* **允許設定循環播放行為** - 允許內容作者在選取 YouTube 嵌入類型時，在元件中設定&#x200B;**啟用循環播放**&#x200B;選項
   * **循環播放的預設值** - 當選取 YouTube 嵌入類型時，自動設定&#x200B;**啟用循環播放**&#x200B;選項
* **允許設定內嵌播放 (iOS)** - 允許內容作者在選取 YouTube 嵌入類型時，在元件中設定&#x200B;**啟用內嵌播放 (iOS)** 選項
   * **內嵌播放 (iOS) 的預設值** - 在選取 YouTube 嵌入類型時，自動設定&#x200B;**啟用內嵌播放 (iOS)** 選項
* **允許設定內嵌影片** - 允許內容作者在選取 YouTube 嵌入類型時，在元件中設定&#x200B;**不受限制的相關影片**&#x200B;選項
   * **不受限制的相關影片的預設值** - 在選取 YouTube 嵌入類型時，自動設定&#x200B;**不受限制的相關影片**&#x200B;選項
