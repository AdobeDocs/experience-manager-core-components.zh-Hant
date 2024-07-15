---
title: 內嵌元件
description: 內嵌元件可在AEM內容頁面中內嵌外部內容。
role: Architect, Developer, Admin, User
exl-id: 985fa304-70a3-4329-957e-76d1832a06f1
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '1339'
ht-degree: 1%

---

# 內嵌元件 {#embed-component}

核心元件內嵌元件允許將外部內容內嵌於AEM內容頁面。

## 使用情況 {#usage}

核心元件內嵌元件可讓內容作者定義要內嵌於AEM內容頁面中的選定外部內容。 此外，您也可以選擇定義要內嵌的自由格式HTML。

* 可以在[設定對話方塊](#configure-dialog)中定義元件的屬性。
* 將元件新增至頁面時的預設值可以在[設計對話方塊](#design-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

內嵌元件的目前版本是v2，此版本隨2022年2月的核心元件發行版本2.18.0的發佈引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v2 | - | 相容 | 相容 |
| [v1](v1/embed.md) | 相容 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗內嵌元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_embed)。

## 技術細節 {#technical-details}

在GitHub](https://adobe.com/go/aem_cmp_tech_embed_v2)上可找到有關內嵌元件[的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義要嵌入頁面上的外部資源。

### 屬性標籤 {#properties-tab}

首先選擇應該嵌入的資源型別：

* [URL](#url)
* [內嵌項目](#embeddable)
* [HTML](#html)

對於每種可內嵌的型別，您可以定義&#x200B;**ID**。 此選項允許控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。

* 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
* 若指定ID，作者應負責確認該ID為唯一ID。
* 變更ID會對CSS、JS和資料層追蹤造成影響。

#### URL {#url}

最簡單的內嵌專案是URL。 只要將您要內嵌之資源的URL貼到&#x200B;**URL**&#x200B;欄位中即可。 元件將嘗試存取資源，如果可由其中一個處理器轉譯，則會在&#x200B;**URL**&#x200B;欄位下方顯示確認訊息。 如果不會，該欄位將會標示為錯誤。

內嵌元件隨附下列資源型別的處理器：

* 符合[oEmbed標準](https://oembed.com/)的資源，包括Facebook Post、Instagram、SoundCloud、Twitter和YouTube
* Pinterest

開發人員可以依照內嵌元件的開發人員檔案[新增其他URL處理器。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![內嵌元件的URL](/help/assets/embed-url.png)編輯對話方塊

#### 內嵌項目 {#embeddable}

內嵌專案允許內嵌資源的更多自訂，這些自訂專案可以引數化並包含其他資訊。 作者能從預先設定的信任內嵌專案中進行選取，元件也隨附立即可用的YouTube內嵌專案。

**可內嵌專案**&#x200B;欄位定義您要使用的處理器型別。 在使用YouTube內嵌專案的情況下，您可以定義：

* **視訊ID** — 您要內嵌之資源來自YouTube的唯一視訊識別碼
* **寬度** — 內嵌視訊的寬度
* **高度** — 內嵌視訊的高度
* **啟用靜音** — 此引數會指定視訊在預設情況下是否將靜音播放。 啟用此項會增加自動播放在新型瀏覽器中運作的機會。
* **啟用自動播放** — 此引數會指定在播放器載入時，是否自動開始播放初始視訊。 這只有在發佈執行個體上或在編寫執行個體上使用&#x200B;**以發佈的形式檢視**&#x200B;選項時有效。
* **啟用回圈** — 在單一視訊的情況下，此引數會指定播放器是否應重複播放初始視訊。 若是播放清單，播放器會播放整個播放清單，然後從第一個視訊重新開始。
* **啟用內嵌播放(iOS)** — 此引數控制在iOS上的HTML5播放器中，是內嵌播放（開）還是全熒幕播放（關）。
* **不受限制的相關影片** — 如果停用此選項，則相關影片將來自與剛剛播放的影片相同的頻道，否則將來自任何頻道。

其他內嵌專案將提供類似的欄位，並可由開發人員[根據內嵌元件的開發人員檔案定義。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![內嵌元件的可內嵌專案的編輯對話方塊](/help/assets/embed-embeddable.png)

>[!NOTE]
>
>內嵌專案必須透過[設計對話方塊](#design-dialog)在範本層級啟用，頁面作者才能使用。

#### HTML {#html}

您可以使用內嵌元件將自由格式HTML新增至頁面。

![內嵌元件的HTML](/help/assets/embed-html.png)編輯對話方塊

>[!NOTE]
>任何不安全的標籤（例如指令碼）將會從輸入的HTML中篩選，且不會在產生的頁面上轉譯。

##### 安全性 {#security}

作者可以輸入的HTML標示會基於安全性目的進行篩選，以避免跨網站指令碼攻擊，例如允許作者取得管理許可權。

一般來說，所有指令碼和`style`元素以及所有`on*`和`style`屬性都將從輸出中移除。

不過，規則比較複雜，因為內嵌元件會遵循AEM的全域HTMLAntiSamy淨化架構篩選規則集（可在`/libs/cq/xssprotection/config.xml`找到）。 如有需要，開發人員可為專案特定的設定覆蓋此專案。

其他安全性資訊可在適用於內部部署安裝的[AEM開發人員檔案](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/security.html)以及[AEM as a Cloud Service安裝](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/home.html)中找到。

>[!NOTE]
>
>雖然AntiSamy淨化架構規則可透過覆蓋`/libs/cq/xssprotection/config.xml`來設定，但這些變更會影響到所有HTL和JSP行為，而不只是內嵌核心元件。

### 樣式索引標籤 {#styles-tab-edit}

內嵌元件](/help/assets/embed-styles.png)之編輯對話方塊的![樣式索引標籤

內嵌元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的選取具有相同的效果。

必須在[設計對話方塊](#design-dialog)中為此元件設定樣式，以便下拉式功能表可用。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些選項可供使用內嵌元件的內容作者使用，以及在放置內嵌元件時的預設值。

### 內嵌專案型別索引標籤 {#embeddable-types-tab}

![內嵌元件的設計對話方塊](/help/assets/embed-design.png)

* **停用URL** — 在選取時，停用內容作者的&#x200B;**URL**&#x200B;選項
* **停用內嵌專案** — 在選取時，對內容作者停用&#x200B;**內嵌專案**&#x200B;選項，無論允許內嵌專案處理者為何。
* **停用HTML** — 在選取時，停用內容作者的&#x200B;**HTML**&#x200B;選項。
* **允許的內嵌專案** — 多重選取，定義哪些內嵌專案處理者可供內容作者使用，前提是&#x200B;**內嵌專案**&#x200B;選項是作用中的。

### YouTube索引標籤 {#youtube-tab}

內嵌元件設計對話方塊的![YouTube標籤](/help/assets/embed-design-youtube.png)

* **允許設定靜音行為** — 允許內容作者在選取YouTube內嵌型別時，在元件中設定&#x200B;**啟用靜音**&#x200B;選項
   * **靜音的預設值** — 在選取YouTube內嵌型別時，自動設定&#x200B;**啟用靜音**&#x200B;選項
* **允許設定自動播放行為** — 允許內容作者在選取YouTube內嵌型別時，在元件中設定&#x200B;**啟用自動播放**&#x200B;選項
   * **自動播放的預設值** — 在選取YouTube內嵌型別時，自動設定&#x200B;**啟用自動播放**&#x200B;選項
* **允許設定回圈行為** — 允許內容作者在選取YouTube內嵌型別時，在元件中設定&#x200B;**啟用回圈**&#x200B;選項
   * **回圈的預設值** — 在選取YouTube內嵌型別時，自動設定&#x200B;**啟用回圈**&#x200B;選項
* **允許內嵌播放設定(iOS)** — 允許內容作者在選取YouTube內嵌型別時，在元件中設定&#x200B;**啟用內嵌播放(iOS)**&#x200B;選項
   * **內嵌播放的預設值(iOS)** — 在選取YouTube內嵌型別時，自動設定&#x200B;**啟用內嵌播放(iOS)**&#x200B;選項
* **允許內嵌影片的設定** — 允許內容作者在選取YouTube內嵌型別時，在元件中設定&#x200B;**不受限制的相關影片**&#x200B;選項
   * **不受限相關影片的預設值** — 在選取YouTube內嵌型別時，自動設定&#x200B;**不受限相關影片**&#x200B;選項
