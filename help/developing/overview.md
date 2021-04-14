---
title: 開發核心元件
description: 核心元件提供強穩且可擴充的基本元件，提供豐富的功能、持續傳送、元件版本修訂、現代化實作、精簡的標籤和JSON內容匯出。
role: Architect, Developer, Administrator
exl-id: 0f79cac1-a3b0-487e-90be-0bd8263d3912
translation-type: tm+mt
source-git-commit: b01fdc7ab6b4d4bb4200d28aaa3706c58ccdea9f
workflow-type: tm+mt
source-wordcount: '1591'
ht-degree: 14%

---

# 開發核心元件 {#developing-core-components}

## 何時使用核心元件？{#when-to-use-the-core-components}

核心元件不僅是全新功能，並且有多項優點，因此建議用於新的 AEM 專案。對於既有專案來說，移轉應該是品牌重塑或整體重構等較大專案工作的一部分。

因此，Adobe提出以下建議：

* **新專**
案新專案應一律嘗試使用核心元件。如果核心元件無法直接使用或[extended](customizing.md)以符合專案需求，則請依照核心元件中所述的元件架構建立自訂元件。 除非其他情況不可能，否則請避免使用[foundation元件](/help/versions.md#foundation-component-support)。
* **現有**
的ProjectsRecommendation會繼續使用 [基礎元件](/help/versions.md#foundation-component-support)，除非計畫進行網站或元件重構。\
   由於它們在大多數現有項目中都非常廣泛地使用，因此將繼續支援基礎元件[。](/help/versions.md#foundation-component-support)
* **新自訂元**
件評估是否可 [自訂現有核心元件](customizing.md)。\
   如果沒有，建議是按照[元件指南](guidelines.md)建立新的自定義元件。
* **現有自訂**
元件如果您的元件如預期般運作，則可維持原狀。
\
   否則，請參閱上述「新自訂元件」。

## 如何成功使用核心元件{#how-to-succeed}

核心元件功能強大、靈活，而且易於使用和自訂。 [遵循幾項主要指](success.md) 南，可確保您使用核心元件的專案成功。

## 遷移至核心元件

任何新專案都應與核心元件一起實施。 但是，現有項目通常會廣泛實施Foundation Components。

### 從Foundation元件{#from-foundation}遷移

對現有專案（例如重新品牌化或整體重構）的投入更大，通常會提供移轉至核心元件的機會。 為促進此項移轉，Adobe提供了一些移轉工具，以鼓勵採用核心元件和最新AEM技術。

[現代化AEM工](http://opensource.adobe.com/aem-modernize-tools/) 具套件，讓您輕鬆轉換：

* 從靜態範本轉換為可編輯的範本
* 根據原則設計設定
* 從基礎元件轉換為核心元件
* 從傳統 UI 轉換為觸控式 UI

有關這些工具使用的詳細資訊，請[參見其文檔](http://opensource.adobe.com/aem-modernize-tools/)。

>[!NOTE]
>
>最新AEM化工具是社群的努力，不受Adobe支援或保證。

## 通過移至作AEM為Cloud Service{#via-aemaacs}的遷移

由AEM於Cloud Service自動附帶最新版核心元件，因此當您從內部安裝移AEM動時，將需要刪除對項目`pom.xml`檔案中核心元件的任何依賴。

您的Proxy元件仍能像以前一樣運作，因為   proxy會指向必要的超類型，而超類型路徑中包含版本。 如此，只要移除相依性，「核心元件」就可像在內部執行一樣，在AEMaCS中運作。

就像其他AEMaCS專案一樣，您也需要將相依性新增至AEMSDK jar。 這並非核心元件的特定功能，而是必要功能。

```xml
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-sdk-api</artifactId>
</dependency>
```

如需AEMaCS專案的詳細資訊，請參AEM閱檔案[專案結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)。

## 核心元件支援{#core-component-support}

核心元件是 AEM 不可或缺的一部分，並依照與 Quickstart 所提供相同的條款與條件給予支援。

與其他AEM產品功能一樣，一般規則是：元件會先宣佈不建議使用，而且最早會在下列版本中移AEM除。 這可讓客戶在放棄支援之前，至少有一個版本週期移至新版本的元件。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

有關支援元件定製的詳細資訊，請參閱[自定義核心元件](customizing.md)頁。


## 技術能力{#technical-capabilities}

下表概述核心元件與基礎元件之間的差異。

有關其編寫功能和預先配置選項的詳細資訊，請[參閱有關它們的編寫頁面](/help/get-started/authoring.md)。

| **功能** | **核心元件** | **Foundation Component** |
|-----|---|---|
| 邏輯實作 | 具有[Sling Models](https://sling.apache.org/documentation/bundles/models.html)註解的Java POJO | JSP程式碼 |
| 標籤定義 | [HTML範本語言](https://docs.adobe.com/content/help/zh-Hant/experience-manager-htl/using/overview.html) (HTL)語法 | JSP程式碼 |
| XSS淨化 | 由HTL自動化 | 主要是手動 |
| CSS類別命名 | 基於[塊元素修飾詞](https://getbem.com/)(BEM)符號的標準命名約定（自2.0.0版起） | 自訂配置 |
| 對話框定義 | [珊瑚3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 + Classic UI |
| JSON輸出 | [Sling Models Exporter與Jackson序列化](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 預設Sling servlet |
| 版本設定 | [針對模型和HTL](guidelines.md) | 無 |
| 測試 | 單元測試+整合測試 | 整合測試 |
| 傳送 | [透過公開GitHub](https://github.com/adobe/aem-core-wcm-components) | 透過快速入門 |
| 授權 | [Apache授權](https://www.apache.org/licenses/LICENSE-2.0) | Adobe專有 |
| 貢獻 | 透過提取請求 | 不可能 |
| 協助工具 | 完全符合[WCAG 2.0 AA標準](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) | 僅部分符合[WCAG 2.0 AA標準](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## 元件清單{#component-list}

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
| [PDF 檢視器](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1) | 在頁面上呈現PDF檔案 | - |

### 近期元件{#upcoming-components}

如需即將推出的核心元件路線圖的概述，請參閱[專案GitHub的Wiki](https://github.com/adobe/aem-core-wcm-components/wiki/home)。

## 升級核心元件{#upgrade-of-core-components}

版本化元件的一個優點是，它允許將遷移區隔為新版本，AEM而將遷移區隔為新元件版本。 此外，如果有新的元件版本，則允許將每個元件個別移轉至新版本。

遷移到新AEM版本不會影響核心元件的工作方式，前提是其版本還支援要遷移到AEM的新版本。 對核心元件的自訂也不應受到影響，只要它們不使用[已過時或已移除的API](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)。

遷移到新版本的核心元件也不會影響元件的工作方式，但頁面作者可能會引入新功能，這可能需要模板編輯器進行一些配置，以防不需要預設行為。 不過，可能需要調整自定義，有關詳細資訊，請參閱[自定義核心元件](customizing.md#upgrade-compatibility-of-customizations)頁。
