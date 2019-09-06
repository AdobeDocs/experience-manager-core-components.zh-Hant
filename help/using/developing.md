---
title: 開發核心元件
seo-title: 開發核心元件
description: 核心元件提供強穩且可擴充的基底元件，其中提供功能豐富的功能、持續傳送、元件版本修訂、現代化實作、精簡標記和JSON匯出內容。
seo-description: 核心元件提供強穩且可擴充的基底元件，其中提供功能豐富的功能、持續傳送、元件版本修訂、現代化實作、精簡標記和JSON匯出內容。
uuid: 68569da2-9bc8-4e20-9a71-e5816 ce51 ce
contentOwner: 使用者
content-type: 引用
topic-tags: 開發
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 157a2ec3-9fca-4fad-977a-d93013 eeb218
translation-type: tm+mt
source-git-commit: 63e75079e41d3091ca57bfc3129e700675bf4939

---


# 開發核心元件{#developing-core-components}

## 綜覽 {#overview}

核心元件提供強穩且可擴充的基礎元件，其重點在於：

* 功能豐富的功能
   * [彈性的配置選項](authoring.md) ，可容納許多使用案例
   * [可預先設定的功能](authoring.md#pre-configuring-core-components) ，可定義哪些功能可供頁面作者使用
* 持續傳送
   * 經常遞增的功能改良功能
   * GitHub [原始碼的可用性可](https://github.com/adobe/aem-core-wcm-components) 讓開發人員社群提供意見回饋和貢獻
   * 安裝透過 [個別發行的內容套件，](https://github.com/adobe/aem-core-wcm-components/releases) 讓元件升級獨立於AEM升級
* [元件版本修訂](guidelines.md#component-versioning)
   * [確保版本內的相容性](#upgrade-of-core-components)，但允許元件進化
   * 允許一個元件的多個版本存在於同一個環境上
* 現代化實作
   * 以 [HTML範本語言](https://helpx.adobe.com/experience-manager/htl/using/overview.html) (HTL)定義的標記
   * 使用 [Sling模型建置的內容模型邏輯](https://sling.apache.org/documentation/bundles/models.html)
* 精簡標記
   * After [block元素修飾元(](https://getbem.com/) BEM)注釋as of Release2.0.0
      * 舊版遵循 [Bootstrap](https://getbootstrap.com/css/) 命名慣例
   * 圍繞 [協助工具方針建立](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)
   * 可用於互動式和行動網站
* 功能可將內容模型視為無前端CMS使用案例的內容模型
* 可存取
   * 符合 [WCAG2.0AA標準標準](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

>[!CAUTION]
>
>核心元件需要AEM6.3或更新版本和Java8，並需要使用 [可編輯範本](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)
>
>核心元件無法使用Classic UI或靜態範本。

## Gems作業概觀 {#gems-session-overview}

如需核心元件的簡介、他們提供的功能以及如何在AEM中運用它們，請參閱AEM Gems工作階段 [AEM核心元件。](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) 是Adobe專家提供的一系列技術深入探討。本系列補充了產品文件和所有其他技術管道，讓開發人員能夠接觸並深入探討特定主題。

## WKND開發人員教學課程 {#wknd-developer-tutorial}

透過 [這個逐步教學課程，開始使用核心元件來開發AEM Sites。](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## 透過GitHub傳遞 {#delivered-over-github}

核心元件是透過GitHub開發並傳遞。

GUTHub的程式碼

您可以在GitHub上找到此頁面的程式碼

* [在GitHub開啓aem-core-wcm-components專案](https://github.com/adobe/aem-core-wcm-components)
* 將專案下載為 [ZIP檔案](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

請參閱 [「使用核心元件](using.md) 文件」頁面，瞭解如何在專案中開始使用它們。

GitHub的核心元件將允許經常更新，並聽取AEM開發人員社群的意見回應。此外，這應該有助於客戶和合作夥伴在建立自訂元件時遵循類似模式。

>[!NOTE]
>
>若要隨時掌握核心元件的最新變更，您可以在GitHub上觀看 [核心元件存放庫](https://github.com/adobe/aem-core-wcm-components) 。

## 元件庫

請參閱 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library.html)，以展示目前版本的核心元件，並提供其使用範例。

### 範例內容執行模式 {#sample-content-run-mode}

當範例內容出現時，「核心元件」會顯示在QuickStart中，因為「零售 [」參考網站](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) 會使用它們。不過，在生產中執行時(在 `nosamplecontent` 執行模式中，未啓用範例內容)，核心元件不會再存在，而且必須由開發和/或營運團隊在AEM實例上安裝。

>[!NOTE]
>
>在生產環境中，一律在 `nosamplecontent` 執行模式中執行QuickStart。若要在 `nosamplecontent` 執行模式中使用核心元件，請遵循 [「使用核心元件](using.md) 」文件頁面的指示。

## 技術能力 {#technical-capabilities}

下表概述核心元件與基礎元件之間的差異。

如需其編寫功能和可預先設定之選項的詳細資訊，請 [參閱有關它們](authoring.md)的製作頁面。

| **功能** | **核心元件** | **Foundation Component** |
|-----|---|---|
| 邏輯實作 | 使用 [Sling模型](https://sling.apache.org/documentation/bundles/models.html) 註解的Java POJO | JSP程式碼 |
| 標記定義 | [HTML範本語言](https://helpx.adobe.com/experience-manager/htl/user-guide.html) (HTL)語法 | JSP程式碼 |
| XSS淨化 | 由HTL自動化 | 大部份手冊 |
| CSS類別命名 | 根據 [區塊元素修飾元](https://getbem.com/) (BEM)注釋的標準化命名慣例(從2.0.0版起) | 自訂配置 |
| 對話框定義 | [Coral3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral2+ Classic UI |
| JSON輸出 | [Sling Models Exporter with Jackson序列化](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 預設Sling servlet |
| 版本設定 | [針對模型和HTL](guidelines.md) | 無 |
| 測試 | 單元測試+整合測試 | 整合測試 |
| 傳送 | [透過公開GitHub](https://github.com/adobe/aem-core-wcm-components) | 透過QuickStart |
| 授權 | [Apache授權](https://www.apache.org/licenses/LICENSE-2.0) | Adobe專屬 |
| 貢獻 | 透過提取請求 | 不可能 |
| 協助工具 | 完全符合 [WCAG2.0AA標準標準](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) | 僅部分符合 [WCAG2.0AA標準](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) |

## 元件清單 {#component-list}

下表列出可用的核心元件，連結至其API，並指出他們所取代的基礎元件。

| 核心元件 | 說明 | 取代基礎元件 |
|---|---|---|
| [頁面](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page) | 使用範本編輯器的互動式頁面 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [階層連結](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb) | 頁面階層導覽 | `/libs/foundation/components/breadcrumb` |
| [標題](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title) | H1-H標題 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文字](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | 豐富文字 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [影像](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image) | 智慧和逐步載入最佳轉譯大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [清單](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list) | 頁面清單 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒體分享](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/sharing/v1/sharing) | Facebook和Pinterest共用介面工具集 | `-` |
| [來自容器](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container) | 多方互動表單段落系統 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表單文字](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text) | 文字輸入欄位 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表單選項](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options) | 多個選項輸入欄位 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [已隱藏的表單](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden) | 隱藏輸入欄位 | `/libs/foundation/components/form/hidden` |
| [表單按鈕](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button) | 提交或自訂按鈕 | `/libs/foundation/components/form/submit` |
| [導覽](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation) | 列出巢狀頁面階層的網站導覽元件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [語言導覽](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation) | 列出全域語言結構的語言和國家切換器 | `-` |
| [快速搜尋](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/search/v1/search) | 搜尋元件會在下拉式選單中顯示結果作為就地建議 | `/libs/foundation/components/search` |
| [Teaser](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser) | 內容作者可讓內容作者使用影像、標題或豐富文字，並連結至更進一步的內容或其他動作，輕鬆建立內容 | `-` |
| [索引標籤](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs) | 允許內容作者組織多個標籤中的頁面內容 | `-` |
| [傳送](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel) | 允許內容作者組織投影片旋轉轉盤中的內容 | `/libs/foundation/components/carousel` |
| [內容片段](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment) | 允許顯示內容片段 | `-` |
| [內容片段清單](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragmentlist/v1/contentfragmentlist) | 允許顯示內容片段清單 | `-` |
| [分隔符號](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/separator/v1/separator) | 區隔頁面上的內容 | `-` |
| [折疊面板](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/accordion/v1/accordion) | 在可收合的Accordion中組織內容面板 | `-` |
| [容器](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container) | 組織容器內的元件 | `-` |
| [按鈕](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/button/v1/button) | 在頁面上建立按鈕 | `-` |
| [下載](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download) | 將可下載的資產新增至頁面 | `-` |
| [體驗片段](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/experience-fragment/v1/experience-fragment) | 新增體驗片段至頁面 | `/libs/cq/experience-fragments/editor/components/experiencefragment` |

### 即將推出的元件 {#upcoming-components}

如需即將到來的核心元件規劃藍圖的概觀，請參閱GitHub上的 [專案維基](https://github.com/adobe/aem-core-wcm-components/wiki/home)。

## 核心元件升級 {#upgrade-of-core-components}

版本化元件的優點之一，就是它可將移轉至新的元件版本，將移轉至新的AEM版本。此外，如果有新的元件版本可供使用，則可讓每個元件的個別移轉至新版本。

移轉至新的AEM版本不會影響核心元件運作的方式，前提是其版本也支援正在移轉的新AEM版本。對於核心元件所做的自訂不應受到影響，只要他們不使用 [已過時或已移除](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html)的API。

移轉至新版本的核心元件並不會影響元件運作的方式，但是新功能可能會引入頁面作者，而範本編輯器可能需要某些設定，以防預設行為不需要。但可能需要調整自訂，如需詳細資訊，請參閱 [「自訂核心元件](customizing.md#upgrade-compatibility-of-customizations) 」頁面。

## 何時使用核心元件？ {#when-to-use-the-core-components}

由於核心元件是全新的並提供多項優點，因此建議新的AEM專案使用它們。對於現有專案，移轉應該是較大型專案的一部分，例如重新品牌或整體重構。

因此，Adobe提供下列建議：

* **新專案**&#x200B;新專案應一律嘗試使用核心元件。如果不能直接或 [延伸](customizing.md) 核心元件以滿足專案需求，則可依照核心元件中所設定的元件架構來建立自訂元件。除非有其他可能，否則請避免使用 [基礎元件](developing.md)。
* **除非計劃網站或元件重構，否則現有的專案**&#x200B;建議會持續使用 [基礎元件](developing.md)。\
   由於它們廣獲大部分現有專案採用，所以仍將繼續支援基礎元件 [。](developing.md)
* **新自訂元件**&#x200B;評估現有 [核心元件是否可自訂](customizing.md)。\
   如果沒有，建議建議使用 [「元件准則](guidelines.md)」建立新的自訂元件。
* **現有的自訂元件**&#x200B;如果您的元件如預期般運作，則保留它們。\
   如果沒有，請參閱上述「新增自訂元件」。

## 移轉至核心元件

任何新專案都應使用核心元件實施。不過，現有專案通常會大量建置Foundation元件。

對現有專案(例如重新品牌或整體重構)投入較大的心力通常會提供移轉至核心元件的機會。為促進此項移轉，Adobe提供了許多移轉工具，以鼓勵核心元件和最新的AEM技術採用。

[AEM現代化工具](http://opensource.adobe.com/aem-modernize-tools/) 可讓您輕鬆轉換：

* 靜態範本至可編輯範本
* 設計原則的組態
* Foundation Components to Core Components
* Classic UI至觸控式UI

有關使用這些工具的詳細資訊，請 [參閱文件](http://opensource.adobe.com/aem-modernize-tools/)。

>[!NOTE]
>
>AEM Modernize Tools是社群的工作，不受Adobe支援或顛覆。

## 核心元件支援 {#core-component-support}

核心元件是AEM中不可或缺的一部分，並受支援，如同使用QuickStart傳遞一樣。

如同其他AEM產品功能，一般規則為：元件首先宣佈已過時，且最早已移除至下列AEM版本。如此，客戶至少可以在放棄支援之前，至少一個版本週期移至新版本的元件。

每個元件的版本清楚表明其支援的AEM版本。當支援適用於AEM版本時，該版本的AEM支援核心元件也一樣。

如需元件自訂支援的詳細資訊，請參閱 [「自訂核心元件](customizing.md) 」頁面。

## Foundation Component支援 {#foundation-component-support}

由於基礎元件在許多AEM版本上都是如此多的專案開發，所以未來將繼續支援它們。

但是，Adobe的開發重點已移轉至核心元件和新功能，而 [幾乎所有的Foundation元件都已停用AEM6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) ，而Foundation元件後續只會修正錯誤。

**下一步閱讀：**

* [使用核心元件](using.md) -在您自己的專案中啓動並執行核心元件。
* [元件准則](guidelines.md) -瞭解核心元件的實施模式。
