---
title: 開發核心元件
seo-title: 開發核心元件
description: 核心元件提供強穩且可擴充的基本元件，提供豐富的功能、持續傳送、元件版本修訂、現代化實作、精簡的標籤和JSON內容匯出。
seo-description: 核心元件提供強穩且可擴充的基本元件，提供豐富的功能、持續傳送、元件版本修訂、現代化實作、精簡的標籤和JSON內容匯出。
uuid: 68569da2-9bc8-4e20-9a71-e5816ace51ce
contentOwner: 使用者
content-type: 引用
topic-tags: 開發
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新功能
discoiquuid: 157a2ec3-9fca-4fad-977a-d93013eeb218
translation-type: tm+mt
source-git-commit: 63e75079e41d3091ca57bfc3129e700675bf4939

---


# 開發核心元件{#developing-core-components}

## 綜覽 {#overview}

核心元件提供強穩且可擴充的基本元件，其亮點為：

* 功能豐富的功能
   * [靈活的配置選項](authoring.md) ，可容納許多使用案例
   * [預先設定的功能](authoring.md#pre-configuring-core-components) ，以定義頁面作者可使用的功能
* 持續傳送
   * 頻繁的增量功能改進
   * GitHub上的 [原始碼已推出](https://github.com/adobe/aem-core-wcm-components) ，讓開發人員社群提供意見回饋並貢獻
   * 透過個別發 [行的內容套件安裝](https://github.com/adobe/aem-core-wcm-components/releases) ，以獨立於AEM升級完成元件升級
* [元件版本控制](guidelines.md#component-versioning)
   * [確保版本的相容性](#upgrade-of-core-components)，同時允許元件改進
   * 允許一個元件的多個版本共存於同一環境中
* 現代實作
   * 在 [HTML範本語言](https://helpx.adobe.com/experience-manager/htl/using/overview.html) (HTL)中定義的標籤
   * 使用 [Sling Models實作的內容模型邏輯](https://sling.apache.org/documentation/bundles/models.html)
* 精益標籤
   * 自2. [0.0版起，遵循塊元素修飾詞](https://getbem.com/) (BEM)注釋
      * 舊版遵循 [Bootstrap](https://getbootstrap.com/css/) 命名慣例
   * 以協助工具指 [南為基礎](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)
   * 可用於互動式和行動網站
* 可序列化為JSON的無頭CMS使用案例內容模型
* 可存取
   * 符合 [WCAG 2.0 AA標準](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

>[!CAUTION]
>
>核心元件需要AEM 6.3或更新版本和Java 8，而且需要使用可編輯 [的範本](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)
>
>核心元件不適用於Classic UI，也不適用於靜態範本。

## Gems會話概述 {#gems-session-overview}

如需核心元件、其提供的功能以及如何在AEM中運用這些元件的簡介，請參閱AEM Gems Session [AEM核心元件。](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) ，是Adobe專家提供的一系列技術深入探討。 本系列補充了產品說明檔案和所有其他技術通道，讓開發人員可以深入瞭解特定主題。

## WKND開發人員教學課程 {#wknd-developer-tutorial}

依照本逐步教學課程，開始開 [發具核心元件的AEM Sites。](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## 透過GitHub提供 {#delivered-over-github}

核心元件是在GitHub中開發並傳遞的。

GITHUB代碼

您可以在GitHub上找到此頁面的程式碼

* [在GitHub上開啟aem-core-wcm-components專案](https://github.com/adobe/aem-core-wcm-components)
* 將專案下載為 [ZIP檔案](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

請參 [閱使用核心元件](using.md) 檔案頁面，瞭解如何在專案中開始使用這些元件。

在GitHub上安裝核心元件可讓您頻繁進行更新，並聽取AEM開發人員社群的意見回應。 此外，這應有助於客戶和合作夥伴在建立自訂元件時遵循類似的模式。

>[!NOTE]
>
>若要隨時掌握核心元件的最新變更，您可以在GitHub上檢視核 [心元件存放庫](https://github.com/adobe/aem-core-wcm-components) 。

## 元件庫

查看元 [件庫](http://opensource.adobe.com/aem-core-wcm-components/library.html)，其中顯示核心元件的最新版本，並提供其使用範例。

### 範例內容執行模式 {#sample-content-run-mode}

當範例內容出現時，Quickstart中會顯示核心元件，因為 [We.Retail參考網站會使用它們](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) 。 不過，當在生產環境中執行(在 `nosamplecontent` runmode中，未啟用範例內容)時，核心元件將不再存在，而且必須由開發和／或營運團隊安裝在AEM例項上。

>[!NOTE]
>
>在生產環境中，請始終以運行模式運行快速 `nosamplecontent` 入門。 若要在執行模式中使 `nosamplecontent` 用核心元件，請依照「使用核 [心元件](using.md) 」檔案頁面的指示進行。

## 技術功能 {#technical-capabilities}

下表概述核心元件與基礎元件之間的差異。

如需其製作功能和預先設定選項的詳細資訊，請 [參閱相關的製作頁面](authoring.md)。

| **功能** | **核心元件** | **Foundation Component** |
|-----|---|---|
| 邏輯實作 | Java POJOs with [Sling Models](https://sling.apache.org/documentation/bundles/models.html) annotations | JSP程式碼 |
| 標籤定義 | [HTML範本語言](https://helpx.adobe.com/experience-manager/htl/user-guide.html) (HTL)語法 | JSP程式碼 |
| XSS淨化 | 由HTL自動化 | 主要是手動 |
| CSS類別命名 | 基於塊元素修 [飾詞](https://getbem.com/) (BEM)符號的標準命名慣例（自2.0.0版起） | 自訂配置 |
| 對話框定義 | [珊瑚3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 + Classic UI |
| JSON輸出 | [Sling Models Exporter與Jackson序列化](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 預設Sling servlet |
| 版本設定 | [針對模型和HTL](guidelines.md) | 無 |
| 測試 | 單元測試+整合測試 | 整合測試 |
| 傳送 | [透過公開GitHub](https://github.com/adobe/aem-core-wcm-components) | 透過快速入門 |
| 授權 | [Apache授權](https://www.apache.org/licenses/LICENSE-2.0) | Adobe專屬 |
| 貢獻 | 透過提取請求 | 不可能 |
| 協助工具 | 完全符合 [WCAG 2.0 AA標準](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) | 僅部分符合 [WCAG 2.0 AA標準](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) |

## 元件清單 {#component-list}

下表列出可用的核心元件、連結至其API，並指出其所取代的基礎元件。

| 核心元件 | 說明 | 已更換基礎元件 |
|---|---|---|
| [頁面](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page) | 使用範本編輯器的互動式頁面 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [階層連結](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb) | 頁面階層導覽 | `/libs/foundation/components/breadcrumb` |
| [標題](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title) | H1-H6標題 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文字](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | 豐富式文字 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [影像](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image) | 智慧和延遲載入最佳轉譯大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [清單](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list) | 頁面清單 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒體分享](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/sharing/v1/sharing) | Facebook和Pinterest共用介面工具集 | `-` |
| [來自容器](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container) | 自適應表單段落系統 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表單文字](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text) | 文字輸入欄位 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表單選項](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options) | 多選項輸入欄位 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [已隱藏的表單](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden) | 隱藏輸入欄位 | `/libs/foundation/components/form/hidden` |
| [表單按鈕](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button) | 提交或自訂按鈕 | `/libs/foundation/components/form/submit` |
| [導覽](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation) | 列出巢狀頁面階層的網站導覽元件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [語言導覽](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation) | 列出全球語言結構的語言和國家切換器 | `-` |
| [快速搜尋](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/search/v1/search) | 在下拉式選單中將結果顯示為就地建議的搜尋元件 | `/libs/foundation/components/search` |
| [Teaser](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser) | 可讓內容作者使用影像、標題或豐富式文字輕鬆建立摘要，並連結至其他內容或其他動作 | `-` |
| [索引標籤](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs) | 允許內容作者在多個標籤中組織頁面內容 | `-` |
| [傳送](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel) | 可讓內容作者在旋轉的投影片轉盤中組織內容 | `/libs/foundation/components/carousel` |
| [內容片段化](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment) | 允許顯示內容片段 | `-` |
| [內容片段清單](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragmentlist/v1/contentfragmentlist) | 允許顯示內容片段的清單 | `-` |
| [分隔符號](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/separator/v1/separator) | 分隔頁面上的內容 | `-` |
| [折疊面板](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/accordion/v1/accordion) | 將內容面板組織成可折疊的收合式收合面板 | `-` |
| [容器](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container) | 在容器中組織元件 | `-` |
| [按鈕](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/button/v1/button) | 在頁面上建立按鈕 | `-` |
| [下載](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download) | 新增可下載的資產至頁面 | `-` |
| [體驗片段](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/experience-fragment/v1/experience-fragment) | 新增體驗片段至頁面 | `/libs/cq/experience-fragments/editor/components/experiencefragment` |

### 近期元件 {#upcoming-components}

如需即將推出的核心元件路線圖的概述，請參 [閱GitHub專案Wiki](https://github.com/adobe/aem-core-wcm-components/wiki/home)。

## 升級核心元件 {#upgrade-of-core-components}

版本化元件的一個優點是，它可將移轉至新AEM版本與移轉至新元件版本分開。 此外，如果有新的元件版本，則允許將每個元件個別移轉至新版本。

移轉至新AEM版本不會影響核心元件的運作方式，但是其版本也支援要移轉至的新AEM版本。 對核心元件的自訂也不應受到影響，只要它們不使用已過時或移除 [的API](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html)。

遷移到新版本的核心元件也不會影響元件的工作方式，但頁面作者可能會引入新功能，這可能需要模板編輯器進行一些配置，以防不需要預設行為。 不過，自訂可能需要調整，如需詳細資訊，請參閱自 [訂核心元件頁面](customizing.md#upgrade-compatibility-of-customizations) 。

## 何時使用核心元件？ {#when-to-use-the-core-components}

由於核心元件是全新的，並提供多項優點，因此建議新的AEM專案使用它們。 對於現有專案，移轉應是大型專案工作的一部分，例如品牌再造或整體重構。

因此，Adobe提供下列建議：

* **新專案**&#x200B;新專案應一律嘗試使用核心元件。 如果核心元件無法直接使用或 [擴充](customizing.md) ，以符合專案需求，請依照核心元件中所述的元件架構建立自訂元件。 除非其他情況不可能，否則請避免使 [用基礎元件](developing.md)。
* **現有的專案**&#x200B;建議會繼續使用 [基礎元件](developing.md)，除非計畫進行網站或元件重構。\
   由於它們在大多數現有項目中都非常廣泛地使用，因此將繼 [續支援基礎元件。](developing.md)
* **新自訂元件**&#x200B;評估是否可自 [訂現有的核心元件](customizing.md)。\
   如果不是，建議是依照「元件准則」建立新的自 [訂元件](guidelines.md)。
* **現有自訂元**&#x200B;件：如果您的元件如預期般運作，請依原樣維持元件。\
   否則，請參閱上述「新自訂元件」。

## 遷移至核心元件

任何新專案都應與核心元件一起實施。 但是，現有項目通常會廣泛實施Foundation Components。

對現有專案（例如重新品牌化或整體重構）的投入更大，通常會提供移轉至核心元件的機會。 為協助此項移轉，Adobe提供了許多移轉工具，以鼓勵採用核心元件和最新的AEM技術。

[AEM Meduration Tools](http://opensource.adobe.com/aem-modernize-tools/) 可讓您輕鬆轉換：

* 靜態範本至可編輯的範本
* 為策略設計配置
* Foundation Components to Core Components
* 傳統UI至觸控式UI

如需這些工具使用的詳細資訊，請參 [閱其檔案](http://opensource.adobe.com/aem-modernize-tools/)。

>[!NOTE]
>
>AEM最新工具是社群的努力，Adobe不支援或授權。

## 核心元件支援 {#core-component-support}

核心元件是AEM不可或缺的一部分，並依照與Quickstart一樣的條款與條件提供。

和其他AEM產品功能一樣，一般規則是：元件會先宣佈不建議使用，並且是下列AEM版本最早移除的元件。 這可讓客戶在放棄支援之前，至少有一個版本週期移至新版本的元件。

每個元件的版本都清楚說明其支援的AEM版本。 當AEM版本的支援停止時，該AEM版本的核心元件支援也停止。

有關支援元件定製的詳細資訊，請參閱自 [定義核心元件頁](customizing.md) 。

## Foundation元件支援 {#foundation-component-support}

由於基礎元件是許多AEM版本專案開發的基礎，因此在可預見的未來，它們仍將受到支援。

不過，Adobe的開發重點已轉移到核心元件，並會新增新功能，而幾乎所有的 [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) Foundation元件都已在AEM 6.5中過時，而且未來Foundation元件只會修正錯誤。

**閱讀下一頁：**

* [使用核心元件](using.md) -在您自己的專案中使用核心元件進行啟動和執行。
* [元件准則](guidelines.md) -瞭解核心元件的實作模式。
