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
source-git-commit: f30a6a9f4d41c672472beb60767f3766479d9c16

---


# Developing Core Components{#developing-core-components}

## 綜覽 {#overview}

核心元件提供強穩且可擴充的基礎元件，其重點在於：

* 功能豐富的功能
   * [彈性的配置選項](authoring.md) ，可容納許多使用案例
   * [可預先設定的功能](authoring.md#pre-configuring-core-components) ，可定義哪些功能可供頁面作者使用
* 持續傳送
   * 經常遞增的功能改良功能
   * Availability of the [source code on GitHub](https://github.com/adobe/aem-core-wcm-components) to allow the developer community to give feedback and contribute
   * Installation through a [separately released content package](https://github.com/adobe/aem-core-wcm-components/releases) for component upgrades to be done independently from AEM upgrades
* [元件版本修訂](guidelines.md#component-versioning)
   * [確保版本內的相容性](#upgrade-of-core-components)，但允許元件進化
   * 允許一個元件的多個版本存在於同一個環境上
* 現代化實作
   * Markup defined in [HTML Template Language](https://helpx.adobe.com/experience-manager/htl/using/overview.html) (HTL)
   * Content model logic implemented with [Sling Models](https://sling.apache.org/documentation/bundles/models.html)
* 精簡標記
   * Following [Block Element Modifier](https://getbem.com/) (BEM) notation as of Release 2.0.0
      * Prior release follow [Bootstrap](https://getbootstrap.com/css/) naming conventions
   * Built around [accessibility guidelines](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)
   * 可用於互動式和行動網站
* 功能可將內容模型視為無前端CMS使用案例的內容模型
* 可存取
   * Compliant with the [WCAG 2.0 AA standard](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

>[!CAUTION]
>
>Core Components require AEM 6.3 or later and Java 8 and and require the use of [editable templates](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)
>
>核心元件無法使用Classic UI或靜態範本。

## Gems Session Overview {#gems-session-overview}

For an introduction to the Core Components, the features they offer, and how they are leveraged in AEM, check out the AEM Gems Session [AEM Core Components.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) 是Adobe專家提供的一系列技術深入探討。本系列補充了產品文件和所有其他技術管道，讓開發人員能夠接觸並深入探討特定主題。

## WKND Developer Tutorial {#wknd-developer-tutorial}

Get started developing AEM Sites with Core Components by following [this step-by-step tutorial.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## Delivered over GitHub {#delivered-over-github}

核心元件是透過GitHub開發並傳遞。

GUTHub的程式碼

您可以在GitHub上找到此頁面的程式碼

* [在GitHub開啓aem-core-wcm-components專案](https://github.com/adobe/aem-core-wcm-components)
* Download the project as [a ZIP file](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

See the [Using Core Components](using.md) documentation page to learn how to get started using them in your project.

GitHub的核心元件將允許經常更新，並聽取AEM開發人員社群的意見回應。此外，這應該有助於客戶和合作夥伴在建立自訂元件時遵循類似模式。

>[!NOTE]
>
>To keep up-to-date on the latest changes to the core components, you can watch the [Core Components repository](https://github.com/adobe/aem-core-wcm-components) on GitHub.

## 元件庫

Check out the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library.html), which showcases the current release of the Core Components and gives examples of their usage.

### Sample Content Run-Mode {#sample-content-run-mode}

The Core Components are visible in the Quickstart when the sample content is present, because the [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) uses them. However, when running in production (in `nosamplecontent` runmode, without sample content enabled), the core components won&#39;t be present anymore and must be installed on the AEM instances by the development and/or operations team.

>[!NOTE]
>
>In production environments, always run the Quickstart in `nosamplecontent` runmode. To use the Core Components in `nosamplecontent` runmode, follow the instructions of the [Using Core Components](using.md) documentation page.

## Technical Capabilities {#technical-capabilities}

下表概述核心元件與基礎元件之間的差異。

For details about their authoring capabilities and options to pre-configurable them, [refer to the authoring page about them](authoring.md).

| **功能** | **核心元件** | **Foundation Component** |
|-----|---|---|
| 邏輯實作 | Java POJOs with [Sling Models](https://sling.apache.org/documentation/bundles/models.html) annotations | JSP程式碼 |
| 標記定義 | [HTML範本語言](https://helpx.adobe.com/experience-manager/htl/user-guide.html) (HTL)語法 | JSP程式碼 |
| XSS淨化 | 由HTL自動化 | 大部份手冊 |
| CSS類別命名 | Standardized naming convention based on [Block Element Modifier](https://getbem.com/) (BEM) notation (as of release 2.0.0) | 自訂配置 |
| 對話框定義 | [Coral3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral2+ Classic UI |
| JSON輸出 | [Sling Models Exporter with Jackson序列化](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 預設Sling servlet |
| 版本設定 | [針對模型和HTL](guidelines.md) | 無 |
| 測試 | 單元測試+整合測試 | 整合測試 |
| 傳送 | [透過公開GitHub](https://github.com/adobe/aem-core-wcm-components) | 透過QuickStart |
| 授權 | [Apache授權](https://www.apache.org/licenses/LICENSE-2.0) | Adobe專屬 |
| 貢獻 | 透過提取請求 | 不可能 |
| 協助工具 | Fully compliant with the [WCAG 2.0 AA standard](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) | Only partially compliant with the [WCAG 2.0 AA standard](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) |

## Component List {#component-list}

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

### Upcoming Components {#upcoming-components}

For an overview of the upcoming Core Componente roadmap see the [project wiki on GitHub](https://github.com/adobe/aem-core-wcm-components/wiki/home).

## Upgrade of Core Components {#upgrade-of-core-components}

版本化元件的優點之一，就是它可將移轉至新的元件版本，將移轉至新的AEM版本。此外，如果有新的元件版本可供使用，則可讓每個元件的個別移轉至新版本。

移轉至新的AEM版本不會影響核心元件運作的方式，前提是其版本也支援正在移轉的新AEM版本。Customizations made to the Core Components should not be affected either, as long as they don&#39;t use APIs that have been [deprecated or removed](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html).

移轉至新版本的核心元件並不會影響元件運作的方式，但是新功能可能會引入頁面作者，而範本編輯器可能需要某些設定，以防預設行為不需要。Customizations however might need to be adapted, for more details see the [Customizing Core Components](customizing.md#upgrade-compatibility-of-customizations) page.

## When to Use the Core Components? {#when-to-use-the-core-components}

由於核心元件是全新的並提供多項優點，因此建議新的AEM專案使用它們。對於現有專案，移轉應該是較大型專案的一部分，例如重新品牌或整體重構。

因此，Adobe提供下列建議：

* **新專案** 新專案應一律嘗試使用核心元件。If Core Components cannot be used directly or [extended](customizing.md) to satisfy project requirements, then create a custom component following the component architecture set forth in core components. Except where not otherwise possible, avoid using the [foundation components](developing.md).
* **除非計劃網站或元件重構，否則現有的專案** 建議會持續使用 [基礎元件](developing.md)。\
   As they are very widely used by most existing projects, the foundation components [will continue to be supported.](developing.md)
* **新自訂元件** 評估現有 [核心元件是否可自訂](customizing.md)。\
   If not, recommendation is to build a new custom component following the [Component Guidelines](guidelines.md).
* **現有的自訂元件** 如果您的元件如預期般運作，則保留它們。\
   如果沒有，請參閱上述「新增自訂元件」。

## 移轉至核心元件

任何新專案都應使用核心元件實施。不過，現有專案通常會大量建置Foundation元件。

對現有專案(例如重新品牌或整體重構)投入較大的心力通常會提供移轉至核心元件的機會。為促進此項移轉，Adobe提供了許多移轉工具，以鼓勵核心元件和最新的AEM技術採用。

[AEM現代化工具](http://opensource.adobe.com/aem-modernize-tools/) 可讓您輕鬆轉換：

* 靜態範本至可編輯範本
* 設計原則的組態
* Foundation Components to Core Components
* Classic UI至觸控式UI

For further information about the usage of these tools, [see their documentation](http://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>AEM Modernize Tools是社群的工作，不受Adobe支援或顛覆。

## Core Component Support {#core-component-support}

核心元件是AEM中不可或缺的一部分，並受支援，如同使用QuickStart傳遞一樣。

如同其他AEM產品功能，一般規則為：元件首先宣佈已過時，且最早已移除至下列AEM版本。如此，客戶至少可以在放棄支援之前，至少一個版本週期移至新版本的元件。

每個元件的版本清楚表明其支援的AEM版本。當支援適用於AEM版本時，該版本的AEM支援核心元件也一樣。

For details about the support of component customizations, see the [Customizing Core Components](customizing.md) page.

## Foundation Component Support {#foundation-component-support}

由於基礎元件在許多AEM版本上都是如此多的專案開發，所以未來將繼續支援它們。

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.

**下一步閱讀：**

* [使用核心元件](using.md) -在您自己的專案中啓動並執行核心元件。
* [元件准則](guidelines.md) -瞭解核心元件的實施模式。
