---
title: 開發核心元件
description: 核心元件提供強穩且可擴充的基本元件，提供豐富的功能、持續傳送、元件版本修訂、現代化實作、精簡的標籤和JSON內容匯出。
translation-type: tm+mt
source-git-commit: 6f7166c46940ed451721e0760d565d58efe412ab
workflow-type: tm+mt
source-wordcount: '1425'
ht-degree: 11%

---


# 開發核心元件 {#developing-core-components}

## When to Use the Core Components? {#when-to-use-the-core-components}

核心元件不僅是全新功能，並且有多項優點，因此建議用於新的 AEM 專案。對於既有專案來說，移轉應該是品牌重塑或整體重構等較大專案工作的一部分。

因此，Adobe提供下列建議：

* **新專案**&#x200B;新專案應一律嘗試使用核心元件。 如果核心元件無法直接使用或 [擴充](customizing.md) ，以符合專案需求，請依照核心元件中所述的元件架構建立自訂元件。 除非其他情況不可能，否則請避免使 [用基礎元件](/help/versions.md#foundation-component-support)。
* **現有的專案**&#x200B;建議會繼續使用 [基礎元件](/help/versions.md#foundation-component-support)，除非計畫進行網站或元件重構。\
   由於它們在大多數現有項目中都非常廣泛地使用，因此將繼 [續支援基礎元件。](/help/versions.md#foundation-component-support)
* **新自訂元件**&#x200B;評估是否可自 [訂現有的核心元件](customizing.md)。\
   如果不是，建議是依照「元件准則」建立新的自 [訂元件](guidelines.md)。
* **現有自訂元**&#x200B;件：如果您的元件如預期般運作，請依原樣維持元件。\
   否則，請參閱上述「新自訂元件」。

## 如何使用核心元件獲得成功 {#how-to-succeed}

核心元件功能強大、靈活，而且易於使用和自訂。 [遵循幾項主要准則](success.md) ，可確保您的核心元件專案成功。

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

核心元件是 AEM 不可或缺的一部分，並依照與 Quickstart 所提供相同的條款與條件給予支援。

和其他AEM產品功能一樣，一般規則是： 元件會先宣佈不建議使用，並且是下列AEM版本最早移除的元件。 這可讓客戶在放棄支援之前，至少有一個版本週期移至新版本的元件。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

有關支援元件定製的詳細資訊，請參閱自 [定義核心元件頁](customizing.md) 。


## 技術功能 {#technical-capabilities}

下表概述核心元件與基礎元件之間的差異。

如需其製作功能和預先設定選項的詳細資訊，請 [參閱相關的製作頁面](/help/get-started/authoring.md)。

| **功能** | **核心元件** | **Foundation Component** |
|-----|---|---|
| 邏輯實作 | Java POJOs with [Sling Models](https://sling.apache.org/documentation/bundles/models.html) annotations | JSP程式碼 |
| 標籤定義 | [HTML範本語言](https://docs.adobe.com/content/help/zh-Hant/experience-manager-htl/using/overview.html) (HTL)語法 | JSP程式碼 |
| XSS淨化 | 由HTL自動化 | 主要是手動 |
| CSS類別命名 | 基於塊元素修 [飾詞](https://getbem.com/) (BEM)符號的標準命名慣例（自2.0.0版起） | 自訂配置 |
| 對話框定義 | [珊瑚3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 + Classic UI |
| JSON輸出 | [Sling Models Exporter與Jackson序列化](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 預設Sling servlet |
| 版本設定 | [針對模型和HTL](guidelines.md) | 無 |
| 測試 | 單元測試+整合測試 | 整合測試 |
| 傳送 | [透過公開GitHub](https://github.com/adobe/aem-core-wcm-components) | 透過快速入門 |
| 授權 | [Apache授權](https://www.apache.org/licenses/LICENSE-2.0) | Adobe專屬 |
| 貢獻 | 透過提取請求 | 不可能 |
| 協助工具 | 完全符合 [WCAG 2.0 AA標準](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html | 僅部分符合 [WCAG 2.0 AA標準](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## 元件清單 {#component-list}

下表列出可用的核心元件、連結至其API，並指出其所取代的基礎元件。

| 核心元件 | 說明 | 已更換基礎元件 |
|---|---|---|
| [頁面](https://adobe.com/go/aem_cmp_tech_page_v2) | 使用範本編輯器的互動式頁面 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [階層連結](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2) | 頁面階層導覽 | `/libs/foundation/components/breadcrumb` |
| [標題](https://adobe.com/go/aem_cmp_tech_title_v2) | H1-H6標題 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文字](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | 豐富式文字 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [影像](https://adobe.com/go/aem_cmp_tech_image_v2) | 智慧和延遲載入最佳轉譯大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [清單](https://adobe.com/go/aem_cmp_tech_list_v2) | 頁面清單 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒體分享](https://adobe.com/go/aem_cmp_tech_sharing_v1) | Facebook和Pinterest共用介面工具集 | `-` |
| [來自容器](https://adobe.com/go/aem_cmp_tech_form_container_v2) | 自適應表單段落系統 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表單文字](https://adobe.com/go/aem_cmp_tech_form_text_v2) | 文字輸入欄位 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表單選項](https://adobe.com/go/aem_cmp_tech_form_options_v2) | 多選項輸入欄位 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [已隱藏的表單](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | 隱藏輸入欄位 | `/libs/foundation/components/form/hidden` |
| [表單按鈕](https://adobe.com/go/aem_cmp_tech_form_button_v2) | 提交或自訂按鈕 | `/libs/foundation/components/form/submit` |
| [導覽](https://adobe.com/go/aem_cmp_tech_navigation_v1) | 列出巢狀頁面階層的網站導覽元件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [語言導覽](https://adobe.com/go/aem_cmp_tech_langnav_v1) | 列出全球語言結構的語言和國家切換器 | `-` |
| [快速搜尋](https://adobe.com/go/aem_cmp_tech_search_v1) | 在下拉式選單中將結果顯示為就地建議的搜尋元件 | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1) | 可讓內容作者使用影像、標題或豐富式文字輕鬆建立摘要，並連結至其他內容或其他動作 | `-` |
| [索引標籤](https://adobe.com/go/aem_cmp_tech_tabs_v1) | 允許內容作者在多個標籤中組織頁面內容 | `-` |
| [傳送](https://adobe.com/go/aem_cmp_tech_carousel_v1) | 可讓內容作者在旋轉的投影片轉盤中組織內容 | `/libs/foundation/components/carousel` |
| [內容片段](https://adobe.com/go/aem_cmp_tech_cf_v1) | 允許顯示內容片段 | `-` |
| [內容片段清單](https://adobe.com/go/aem_cmp_tech_cflist_v1) | 允許顯示內容片段的清單 | `-` |
| [分隔符號](https://adobe.com/go/aem_cmp_tech_separator_v1) | 分隔頁面上的內容 | `-` |
| [折疊式面板](https://adobe.com/go/aem_cmp_tech_accordion_v1) | 將內容面板組織成可折疊的收合式收合面板 | `-` |
| [容器](https://adobe.com/go/aem_cmp_tech_container_v1) | 在容器中組織元件 | `-` |
| [按鈕](https://adobe.com/go/aem_cmp_tech_button_v1) | 在頁面上建立按鈕 | `-` |
| [下載](https://adobe.com/go/aem_cmp_tech_download_v1) | 新增可下載的資產至頁面 | `-` |
| [體驗片段](https://adobe.com/go/aem_cmp_tech_xf_v1) | 新增體驗片段至頁面 | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [內嵌](https://adobe.com/go/aem_cmp_tech_embed_v1) | 將外部資源內嵌在頁面中 | - |
| [進度列](https://adobe.com/go/aem_cmp_tech_progress_v1) | 以視覺化方式呈現實現目標的進展 | - |

### 近期元件 {#upcoming-components}

如需即將推出的核心元件路線圖的概述，請參 [閱GitHub專案Wiki](https://github.com/adobe/aem-core-wcm-components/wiki/home)。

## 升級核心元件 {#upgrade-of-core-components}

版本化元件的一個優點是，它可將移轉至新AEM版本與移轉至新元件版本分開。 此外，如果有新的元件版本，則允許將每個元件個別移轉至新版本。

移轉至新AEM版本不會影響核心元件的運作方式，但是其版本也支援要移轉至的新AEM版本。 對核心元件的自訂也不應受到影響，只要它們不使用已過時或移除 [的API](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)。

遷移到新版本的核心元件也不會影響元件的工作方式，但頁面作者可能會引入新功能，這可能需要模板編輯器進行一些配置，以防不需要預設行為。 不過，自訂可能需要調整，如需詳細資訊，請參閱自 [訂核心元件頁面](customizing.md#upgrade-compatibility-of-customizations) 。
