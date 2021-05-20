---
title: 內嵌元件
description: 「內嵌元件」可讓您將外部內容內嵌至AEM內容頁面。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 985fa304-70a3-4329-957e-76d1832a06f1
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '1341'
ht-degree: 1%

---

# 內嵌元件{#embed-component}

核心元件內嵌元件可將外部內容內嵌至AEM內容頁面。

## 使用狀況 {#usage}

核心元件內嵌元件可讓內容作者定義要內嵌於AEM內容頁面中的選取外部內容。 此外，也有可定義要內嵌的自由格式HTML的選項。

* 可在[configure dialog](#configure-dialog)中定義元件的屬性。
* 將元件新增至頁面時的預設值，可在[設計對話方塊](#design-dialog)中定義。

## 版本和相容性{#version-and-compatibility}

目前的內嵌元件版本為v1，已於2019年9月隨核心元件2.7.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗內嵌元件以及查看其設定選項的範例以及HTML和JSON輸出，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_embed)。

## 技術詳細資訊{#technical-details}

如需內嵌元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_embed_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

設定對話方塊可讓內容作者定義要內嵌在頁面上的外部資源。 首先，選擇應嵌入的資源類型：

* [URL](#url)
* [內嵌項目](#embeddable)
* [HTML](#html)

對於每種類型的可內嵌，您可以定義廣告&#x200B;**ID**。 此選項可控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一標識符。

* 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
* 若已指定ID，則作者應負責確認其唯一。
* 變更ID可能會影響CSS、JS和資料層追蹤。

### URL {#url}

最簡單的內嵌方式是URL。 只需將您要內嵌的資源的URL貼到&#x200B;**URL**&#x200B;欄位中即可。 該元件將嘗試訪問該資源，如果該資源可由其中一個處理器呈現，它將在&#x200B;**URL**&#x200B;欄位下顯示確認消息。 否則，欄位會標示為錯誤。

嵌入元件隨處理器一起提供以下資源類型：

* 符合[oEmbed standard](https://oembed.com/)的資源，包括Facebook Post、Instagram、SoundCloud、Twitter和YouTube
* Pinterest

開發人員可在內嵌元件的開發人員檔案後面，依照[新增其他URL處理器。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![URL的內嵌元件編輯對話方塊](/help/assets/embed-url.png)

### 內嵌項目 {#embeddable}

嵌入式資源允許對嵌入式資源進行更多定制，這些資源可以參數化並包含附加資訊。 作者可從預先設定的受信任內嵌項目中選取，而元件隨YouTube內嵌即可使用。

**Embeddable**&#x200B;欄位定義您要使用的處理器類型。 若是YouTube內嵌項目，您可以定義：

* **影片ID**  — 您要內嵌之資源之YouTube的唯一影片ID
* **寬度**  — 內嵌視訊的寬度
* **高度**  — 內嵌視訊的高度
* **啟用靜音**  — 此參數會指定視訊是否預設會播放靜音。若啟用此功能，Autoplay在現代瀏覽器中運作的機會就會增加。
* **啟用自動播放**  — 此參數會指定當播放器載入時，初始視訊是否會自動開始播放。這隻對發佈例項有效，或在製作例項上使用&#x200B;**以已發佈的形式檢視選項時有效。**
* **啟用回圈**  — 若是單一視訊，此參數會指定播放器是否應重複播放初始視訊。若是播放清單，播放器會播放整個播放清單，然後在第一個視訊重新開始。
* **啟用內嵌播放(iOS)**  — 此參數可控制iOS上HTML5播放器中的內嵌（開啟）或全螢幕（關閉）播放視訊。
* **非限制相關影片**  — 如果此選項已停用，則相關影片將來自與剛播放的影片相同的頻道，否則將來自任何頻道。

請注意，必須透過[設計對話方塊](#design-dialog)啟動「啟用」選項，並可設為預設值。

其他內嵌項目會提供類似欄位，且可由開發人員在內嵌元件的開發人員檔案後面[定義。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![內嵌元件的編輯對話方塊](/help/assets/embed-embeddable.png)

>[!NOTE]
>必須透過[Design Dialog](#design-dialog)在範本層級啟用Embeddables，才能供頁面作者使用。

### HTML {#html}

您可以使用內嵌元件將自由格式的HTML新增至頁面。

![HTML的內嵌元件編輯對話方塊](/help/assets/embed-html.png)

>[!NOTE]
>系統會從輸入的HTML中篩選任何不安全的標籤（例如指令碼），且不會在產生的頁面上轉譯。

#### 安全性 {#security}

為了安全起見，系統會篩選作者可輸入的HTML標籤，以避免跨網站指令碼攻擊，例如允許作者取得管理權限。

*一般而言，* 所有指令 `style` 碼和元素，以及 `on*` 所有 `style` 和屬性都將從輸出中移除。

但是，這些規則更複雜，因為「內嵌元件」遵循AEM全域HTML AntiSamy衛生框架篩選規則集，可在`/libs/cq/xssprotection/config.xml`找到。 如有需要，開發人員可重疊以進行專案專屬設定。

如需內部部署安裝](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/security.html)以及[AEM as a Cloud Service安裝，請參閱[AEM開發人員檔案，了解其他安全資訊。](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>雖然AntiSamy衛生框架規則可以通過覆蓋`/libs/cq/xssprotection/config.xml`來配置，但這些更改會影響所有HTL和JSP行為，而不僅影響內嵌核心元件。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義內容作者可使用的選項，內容作者使用內嵌元件，並在放置內嵌元件時設定預設值。

### 可嵌入類型頁簽{#embeddable-types-tab}

![內嵌元件的設計對話方塊](/help/assets/embed-design.png)

* **停用URL**  — 在選取時停 **** 用內容作者的URL選項
* **禁用Embeddables**  — 選擇該 **** 內容作者時禁用Embedable選項，而不管允許哪些可嵌入處理器。
* **停用HTML**  — 選取時停 **** 用內容作者的HTML選項。
* **允許的Embeddables**  — 多選，定義內容作者可使用哪些可嵌入的處理器，前提是Embeddable **** 選項處於活動狀態。

### YouTube標籤{#youtube-tab}

![內嵌元件設計對話方塊的YouTube標籤](/help/assets/embed-design-youtube.png)

* **允許設定靜音行為**  — 選取YouTube內嵌類型時，允許 **內** 容作者在元件中設定「啟用靜音」選項
   * **靜音的預設值**  — 選取YouTube **內嵌** 類型時，自動設定啟用靜音選項
* **允許設定自動播放行為**  — 允許內容作者在選取YouTube **內嵌** 類型時，在元件中設定「啟用自動播放」選項
   * **autoplay的預設值**  — 選取YouTube **內嵌** 類型時，自動設定啟用自動播放選項
* **允許設定回圈行為**  — 允許內容作者在選取YouTube **內** 嵌類型時，在元件中設定「啟用登入」
   * **循環的預設值**  — 選取YouTube **內嵌** 類型時，自動設定啟用選項
* **允許設定內嵌播放(iOS)**  — 允許內容作者在選取YouTube內 **嵌類型時，在元件中設定「啟用內嵌播放(iOS)** 」選項
   * **預設值內嵌播放(iOS)**  — 選取YouTube **內嵌類型時，自動設定「啟用內嵌播放(iOS)** 」選項
* **允許設定內嵌影片**  — 選取YouTube內嵌類型時，允許內 **容作者** 在元件中設定「不受限制的相關影片」選項
   * **非限制相關視訊的預設值**  — 選取YouTube內 **嵌類型時** 自動設定非限制相關視訊選項
