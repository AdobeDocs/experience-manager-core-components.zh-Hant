---
title: 開發核心元件
description: 核心元件提供強大且可擴充的基本元件，提供豐富的功能、持續傳遞、元件版本設定、現代化實作、精益標籤，以及內容的JSON匯出。
role: Architect, Developer, Admin
exl-id: 0f79cac1-a3b0-487e-90be-0bd8263d3912
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '1583'
ht-degree: 12%

---

# 開發核心元件 {#developing-core-components}

## 何時該使用核心元件？ {#when-to-use-the-core-components}

核心元件不僅是全新功能，並且有多項優點，因此建議用於新的 AEM 專案。對於既有專案來說，移轉應該是品牌重塑或整體重構等較大專案工作的一部分。

因此，Adobe提供下列建議：

* **新專**
案新專案應一律嘗試使用核心元件。如果核心元件無法直接使用或[extended](customizing.md)以符合專案需求，請依照核心元件中設定的元件架構建立自訂元件。 除非另有可能，否則請避免使用[foundation元件](/help/versions.md#foundation-component-support)。
* **除非**
已規劃網站或元件重 [構，否則現有專案建議會繼續使用基礎元件](/help/versions.md#foundation-component-support)。\
   由於大多數現有項目都廣泛使用這些元件，因此將繼續支援基礎元件[。](/help/versions.md#foundation-component-support)
* **新的自訂**
元件評估是否可 [自訂現有的核心元件](customizing.md)。\
   否則，建議依照[元件准則](guidelines.md)建立新的自訂元件。
* **現有自訂**
元件如果元件如預期般運作，請依原樣保留元件。
\
   如果沒有，請參閱上述「新自訂元件」。

## 如何使用核心元件成功 {#how-to-succeed}

核心元件功能強大、靈活，易於使用和定制。 [遵循幾項重](success.md) 要指南，即可確保您使用核心元件的專案成功。

## 移轉至核心元件

任何新專案都應使用核心元件來實作。 但現有專案通常會大量實施基礎元件。

### 從Foundation元件遷移 {#from-foundation}

對現有專案付出更大努力（例如品牌重塑或整體重構）通常可讓您移轉至核心元件。 為方便移轉，Adobe提供了許多移轉工具，以鼓勵採用核心元件和最新的AEM技術。

[AEM現代化工](http://opensource.adobe.com/aem-modernize-tools/) 具可輕鬆轉換：

* 從靜態範本轉換為可編輯的範本
* 根據原則設計設定
* 從基礎元件轉換為核心元件
* 從傳統 UI 轉換為觸控式 UI

有關這些工具使用的詳細資訊，請[參閱其文檔](http://opensource.adobe.com/aem-modernize-tools/)。

>[!NOTE]
>
>AEM現代化工具是社群的努力成果，Adobe不支援或保固。

## 透過移轉至AEM作為Cloud Service {#via-aemaacs}

由於AEM as aCloud Service會自動隨附最新版核心元件，當您從內部部署AEM安裝移轉時，將需要移除專案`pom.xml`檔案中對核心元件的任何相依性。

您的代理元件仍可如往常運作，因為   proxy會指向必要的supertype，且supertype路徑包含版本。 如此一來，只要移除相依性，核心元件就能像在內部部署一樣，在AEMaCS中運作。

如同任何其他AEMaaCS專案，您也需要將相依性新增至AEM SDK jar中。 這並非核心元件專屬，而是必要項目。

```xml
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-sdk-api</artifactId>
</dependency>
```

如需AEMaaCS專案的詳細資訊，請參閱檔案[AEM專案結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)。

## 核心元件支援 {#core-component-support}

核心元件是 AEM 不可或缺的一部分，並依照與 Quickstart 所提供相同的條款與條件給予支援。

如同其他AEM產品功能，一般規則為：元件會先宣佈淘汰，並在下列AEM版本中盡早移除。 這可讓客戶在停止支援前，至少有一個發行週期可移至新版本的元件。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

如需支援自訂元件的詳細資訊，請參閱[自訂核心元件](customizing.md)頁面。


## 技術功能 {#technical-capabilities}

下表概述核心元件與基礎元件之間的差異。

有關其創作功能和可預先配置的選項的詳細資訊，請[參閱有關它們的創作頁](/help/get-started/authoring.md)。

| **功能** | **核心元件** | **基礎元件** |
|-----|---|---|
| 邏輯實作 | 具有[Sling模型](https://sling.apache.org/documentation/bundles/models.html)注釋的Java POJO | JSP代碼 |
| 標籤定義 | [HTML範本語言](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=zh-Hant) (HTL)語法 | JSP代碼 |
| XSS淨化 | 由HTL自動化 | 多為手動 |
| CSS類命名 | 基於[區塊元素修飾詞](https://getbem.com/)(BEM)標籤法的標準化命名慣例（自2.0.0版起） | 自訂配置 |
| 對話框定義 | [珊瑚3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 +傳統UI |
| JSON輸出 | [Jackson序列化的Sling模型匯出工具](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 預設Sling Servlet |
| 版本設定 | [針對模型和HTL](guidelines.md) | 無 |
| 測試 | 單元測試+整合測試 | 整合測試 |
| 傳送 | [透過公開GitHub](https://github.com/adobe/aem-core-wcm-components) | 通過快速入門 |
| 授權 | [Apache授權](https://www.apache.org/licenses/LICENSE-2.0) | Adobe專有 |
| 貢獻 | 透過提取請求 | 不可能 |
| 協助工具 | 完全符合[WCAG 2.0 AA標準](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) | 僅部分符合[WCAG 2.0 AA標準](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## 元件清單 {#component-list}

下表列出可用的核心元件（連結至其API），並指出其所取代的基礎元件。

| 核心元件 | 說明 | 已更換基礎元件 |
|---|---|---|
| [頁面](https://adobe.com/go/aem_cmp_tech_page_v2) | 使用範本編輯器的回應式頁面 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [階層連結](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2) | 頁面階層導覽 | `/libs/foundation/components/breadcrumb` |
| [標題](https://adobe.com/go/aem_cmp_tech_title_v2) | H1-H6標題 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文字](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | RTF文字 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [影像](https://adobe.com/go/aem_cmp_tech_image_v2) | 智慧和延遲載入最佳轉譯大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [清單](https://adobe.com/go/aem_cmp_tech_list_v2) | 頁面清單 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒體分享](https://adobe.com/go/aem_cmp_tech_sharing_v1) | Facebook與Pinterest共用widget | `-` |
| [來自容器](https://adobe.com/go/aem_cmp_tech_form_container_v2) | 回應式表單段落系統 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表單文字](https://adobe.com/go/aem_cmp_tech_form_text_v2) | 文字輸入欄位 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表單選項](https://adobe.com/go/aem_cmp_tech_form_options_v2) | 多選項輸入欄位 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [已隱藏的表單](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | 隱藏輸入欄位 | `/libs/foundation/components/form/hidden` |
| [表單按鈕](https://adobe.com/go/aem_cmp_tech_form_button_v2) | 提交或自訂按鈕 | `/libs/foundation/components/form/submit` |
| [導覽](https://adobe.com/go/aem_cmp_tech_navigation_v1) | 列出巢狀頁面階層的網站導覽元件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [語言導覽](https://adobe.com/go/aem_cmp_tech_langnav_v1) | 列出全球語言結構的語言和國家切換器 | `-` |
| [快速搜尋](https://adobe.com/go/aem_cmp_tech_search_v1) | 在下拉式功能表中將結果顯示為就地建議的搜尋元件 | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1) | 可讓內容作者輕鬆建立預告，以使用影像、標題或RTF來進一步內容，並連結至更多內容或其他動作 | `-` |
| [索引標籤](https://adobe.com/go/aem_cmp_tech_tabs_v1) | 可讓內容作者在多個索引標籤內組織頁面內容 | `-` |
| [傳送](https://adobe.com/go/aem_cmp_tech_carousel_v1) | 允許內容作者在旋轉的投影片輪播中組織內容 | `/libs/foundation/components/carousel` |
| [內容片段](https://adobe.com/go/aem_cmp_tech_cf_v1) | 允許顯示內容片段 | `-` |
| [內容片段清單](https://adobe.com/go/aem_cmp_tech_cflist_v1) | 允許顯示內容片段清單 | `-` |
| [分隔符號](https://adobe.com/go/aem_cmp_tech_separator_v1) | 分隔頁面上的內容 | `-` |
| [折疊式面板](https://adobe.com/go/aem_cmp_tech_accordion_v1) | 在可折疊的折疊式折疊式功能表中組織內容面板 | `-` |
| [容器](https://adobe.com/go/aem_cmp_tech_container_v1) | 在容器內組織元件 | `-` |
| [按鈕](https://adobe.com/go/aem_cmp_tech_button_v1) | 在頁面上建立按鈕 | `-` |
| [下載](https://adobe.com/go/aem_cmp_tech_download_v1) | 新增可下載的資產至頁面 | `-` |
| [體驗片段](https://adobe.com/go/aem_cmp_tech_xf_v1) | 新增體驗片段至頁面 | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [內嵌](https://adobe.com/go/aem_cmp_tech_embed_v1) | 將外部資源內嵌在頁面中 | - |
| [進度列](https://adobe.com/go/aem_cmp_tech_progress_v1) | 提供目標進展的直觀表示 | - |
| [PDF 檢視器](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1) | 在頁面上顯示PDF文檔 | - |

### 近期元件 {#upcoming-components}

如需近期核心元件路線圖的概觀，請參閱GitHub上的[專案Wiki](https://github.com/adobe/aem-core-wcm-components/wiki/home)。

## 升級核心元件 {#upgrade-of-core-components}

版本控制元件的其中一項優點，是可將移轉至新AEM版本與移轉至新元件版本分開。 此外，如果有新元件版本可用，則可將每個元件個別移轉至新版本。

移轉至新AEM版本不會影響核心元件的運作方式，但條件是其版本也支援要移轉至的新AEM版本。 只要核心元件的自訂內容未使用[已遭取代或已移除的API](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)，則兩者皆不受影響。

移轉至新版本的核心元件也不會影響元件的運作方式，但頁面作者可能會受到新功能的影響，這可能需要透過範本編輯器進行一些設定，以防不需要預設行為。 不過，您可能需要調整自訂項目，如需詳細資訊，請參閱[自訂核心元件](customizing.md#upgrade-compatibility-of-customizations)頁面。
