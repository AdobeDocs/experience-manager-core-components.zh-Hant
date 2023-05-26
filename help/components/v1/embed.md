---
title: 內嵌元件(v1)
description: 內嵌元件可在AEM內容頁面中內嵌外部內容。
role: Architect, Developer, Admin, User
exl-id: 28a2d196-cc1f-4e29-a8e4-c2e0acba3bfc
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 0%

---

# 內嵌元件(v1) {#embed-component}

核心元件內嵌元件允許在AEM內容頁面中內嵌外部內容。

## 使用狀況 {#usage}

核心元件內嵌元件可讓內容作者定義要內嵌於AEM內容頁面中的選定外部內容。 此外，您也可以選擇定義要內嵌的自由格式HTML。

* 元件的屬性可在 [設定對話方塊](#configure-dialog).
* 將元件新增至頁面時的元件預設值可在下列位置定義： [設計對話方塊](#design-dialog).

## 版本和相容性 {#version-and-compatibility}

本檔案說明內嵌元件v1，此版本隨2019年9月的核心元件發行版本2.7.0的發佈引入。

>[!CAUTION]
>
>本檔案說明內嵌元件v1。
>
>如需目前版本的內嵌元件的詳細資訊，請參閱 [內嵌元件](/help/components/embed.md) 檔案。

## 範例元件輸出 {#sample-component-output}

若要體驗內嵌元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_embed).

## 技術細節 {#technical-details}

有關內嵌元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_embed_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義要內嵌在頁面上的外部資源。 首先，選擇應該內嵌的資源型別：

* [URL](#url)
* [內嵌項目](#embeddable)
* [HTML](#html)

對於每種可內嵌的型別，您可以定義 **ID**. 此選項可讓您控制HTML和中的元件的唯一識別碼 [資料層](/help/developing/data-layer/overview.md).

* 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
* 若指定ID，作者應負責確認該ID是唯一的。
* 變更ID會對CSS、JS和資料層追蹤造成影響。

### URL {#url}

最簡單的內嵌專案是URL。 只要貼上您想要內嵌在中的資源URL即可 **URL** 欄位。 元件將嘗試存取資源，如果可由其中一個處理器轉譯，它將在下方顯示確認訊息 **URL** 欄位。 如果沒有，該欄位將會標示為錯誤。

內嵌元件隨附下列資源型別的處理器：

* 符合「 」的資源 [內嵌標準](https://oembed.com/) 包括Facebook Post、Instagram、SoundCloud、Twitter和YouTube
* Pinterest

開發人員可透過以下方式新增其他URL處理器 [請依照內嵌元件的開發人員檔案操作。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![內嵌元件的URL編輯對話方塊](/help/assets/embed-url.png)

### 內嵌項目 {#embeddable}

內嵌專案允許內嵌資源進行更多自訂，這些可以引數化並包含其他資訊。 作者能從預先設定的信任內嵌專案中進行選取，而且元件出廠時隨附YouTube內嵌專案。

此 **內嵌專案** 欄位定義您要使用的處理器型別。 若是YouTube內嵌專案，您可以定義：

* **視訊ID**  — 來自您要內嵌之資源的YouTube的唯一影片ID
* **寬度**  — 內嵌視訊的寬度
* **高度**  — 內嵌視訊的高度
* **啟用靜音**  — 此引數會指定視訊在預設情況下是否將靜音播放。 啟用此項會增加自動播放在現代瀏覽器中運作的機會。
* **啟用自動播放**  — 此引數會指定在播放器載入時，初始視訊是否將自動開始播放。 這僅在發佈執行個體上或使用 **檢視已發佈** 編寫執行個體上的選項。
* **啟用回圈**  — 若是單一影片，此引數會指定播放器是否應重複播放初始影片。 若是播放清單，播放器會播放整個播放清單，然後從第一個影片重新開始。
* **啟用內嵌播放(iOS)**  — 此引數會控制在iOS上的HTML5播放器中，影片會內嵌播放（開啟）還是全熒幕播放（關閉）。
* **不受限制的相關影片**  — 如果停用此選項，則相關影片將來自與剛播放的影片相同的頻道，否則將來自任何頻道。

請注意，「啟用」選項必須透過 [設計對話方塊](#design-dialog) 和可以設定為預設值。

其他內嵌專案會提供類似的欄位，並可由開發人員透過以下方式定義 [請依照內嵌元件的開發人員檔案操作。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![內嵌元件的可內嵌專案的「編輯」對話方塊](/help/assets/embed-embeddable.png)

>[!NOTE]
>內嵌專案必須透過在範本層級啟用 [設計對話方塊](#design-dialog) 可供頁面作者使用。

### HTML {#html}

您可以使用內嵌元件將自由格式的HTML新增至頁面。

![內嵌元件的HTML編輯對話方塊](/help/assets/embed-html.png)

>[!NOTE]
>系統會從輸入的HTML中篩選任何不安全的標籤（例如指令碼），且不會在產生的頁面上轉譯。

#### 安全性 {#security}

作者可以輸入的HTML標籤會基於安全目的進行篩選，以避免跨網站指令碼攻擊，例如允許作者取得管理許可權。

*一般而言，* 所有指令碼和 `style` 元素及全部 `on*` 和 `style` 將從輸出中移除屬性。

不過，規則比較複雜，因為內嵌元件會遵循AEM全域HTMLAntiSamy淨化架構篩選規則集，此規則集可在以下網址找到： `/libs/cq/xssprotection/config.xml`. 如有需要，這可以由開發人員針對專案特定的設定進行覆蓋。

如需其他安全性資訊，請參閱 [適用於內部部署安裝的AEM開發人員檔案](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/security.html) 以及 [AEMas a Cloud Service安裝。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>雖然AntiSamy淨化架構規則可以透過覆蓋來設定 `/libs/cq/xssprotection/config.xml`，這些變更會影響到所有HTL和JSP行為，而不只是內嵌核心元件。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些選項可供使用內嵌元件的內容作者使用，以及在放置內嵌元件時的預設值。

### 內嵌專案型別標籤 {#embeddable-types-tab}

![內嵌元件的設計對話方塊](/help/assets/embed-design.png)

* **停用URL**  — 停用 **URL** 內容作者的選項（在選取時）
* **停用內嵌專案**  — 停用 **內嵌專案** 內容作者的選項（無論允許內嵌式處理常式）。
* **停用HTML**  — 停用 **HTML** 內容作者的選項（在選取時）。
* **允許的內嵌專案**  — 多項選取，定義哪些內嵌專案處理者可供內容作者使用，但前提是 **內嵌專案** 選項為作用中。

### YouTube索引標籤 {#youtube-tab}

![內嵌元件之「設計」對話方塊的「YouTube」標籤](/help/assets/embed-design-youtube.png)

* **允許設定靜音行為**  — 允許內容作者設定 **啟用靜音** 選取YouTube內嵌型別時元件中的選項
   * **靜音的預設值**  — 自動設定 **啟用靜音** 選項(當選取YouTube內嵌型別時)
* **允許設定自動播放行為**  — 允許內容作者設定 **啟用自動播放** 選取YouTube內嵌型別時元件中的選項
   * **自動播放的預設值**  — 自動設定 **啟用自動播放** 選項(當選取YouTube內嵌型別時)
* **允許設定回圈行為**  — 允許內容作者設定 **啟用回圈** 選取YouTube內嵌型別時元件中的選項
   * **回圈的預設值**  — 自動設定 **啟用回圈** 選項(當選取YouTube內嵌型別時)
* **允許設定內嵌播放(iOS)**  — 允許內容作者設定 **啟用內嵌播放(iOS)** 選取YouTube內嵌型別時元件中的選項
   * **內嵌播放的預設值(iOS)**  — 自動設定 **啟用內嵌播放(iOS)** 選項(當選取YouTube內嵌型別時)
* **允許設定內嵌視訊**  — 允許內容作者設定 **不受限制的相關影片** 選取YouTube內嵌型別時元件中的選項
   * **不受限制的相關影片的預設值**  — 自動設定 **不受限制的相關影片** 選項(當選取YouTube內嵌型別時)
