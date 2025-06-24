---
title: 開發核心元件
description: 核心元件提供強大且可擴充的基本元件，具備豐富的功能、持續傳送、元件版本設定、現代化實施、精簡標籤以及內容的JSON匯出。
role: Architect, Developer, Admin
exl-id: 0f79cac1-a3b0-487e-90be-0bd8263d3912
source-git-commit: 5994133947ff697f7c866fe61598c58e37e77008
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 12%

---

# 開發核心元件 {#developing-core-components}

核心元件提供強大且可擴充的基本元件，具備豐富的功能、持續傳送、元件版本設定、現代化實施、精簡標籤以及內容的JSON匯出。

{{traditional-aem}}

## 如何使用核心元件獲得成功 {#how-to-succeed}

核心元件功能強大、彈性好用，且易於自訂。 [遵循幾項重要准則](success.md)將確保您使用核心元件的專案成功進行。

## 移轉至核心元件

任何新專案都應使用核心元件實作。 不過，現有專案通常具有基礎元件的廣泛實作。

### 從基礎元件移轉 {#from-foundation}

對現有專案進行較大的變動（例如品牌重塑或整體重構）通常會提供移轉至核心元件的機會。 為了協助此移轉，Adobe提供了許多移轉工具，以鼓勵採用核心元件和最新的AEM技術。

[AEM現代化工具](https://opensource.adobe.com/aem-modernize-tools/)可讓您輕鬆轉換：

* 從靜態範本轉換為可編輯的範本
* 根據原則設計設定
* 從基礎元件轉換為核心元件
* 從傳統 UI 轉換為觸控式 UI

如需這些工具使用方式的詳細資訊，[請參閱其檔案](https://opensource.adobe.com/aem-modernize-tools/)。

>[!NOTE]
>
>AEM現代化工具是社群共同努力的成果，Adobe不提供支援或保固。

## 透過移轉至AEM as a Cloud Service進行移轉 {#via-aemaacs}

由於AEM as a Cloud Service自動隨最新版本的核心元件提供，當您從內部部署AEM安裝移轉時，您必須在專案`pom.xml`檔案中移除與核心元件的任何相依性。

您的Proxy元件仍會如往常般運作，原因如下   代理指向必要的超型別，而超型別路徑中有版本。 如此一來，只要移除相依性，核心元件就能像內部部署一樣在AEMaaCS中運作。

就像任何其他AEMaaCS專案一樣，您也需要將相依性新增到AEM SDK jar。 這並非核心元件所特有，但為必要專案。

```xml
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-sdk-api</artifactId>
</dependency>
```

如需AEMaaCS專案的詳細資訊，請參閱檔案[AEM專案結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)。

## 核心元件支援 {#core-component-support}

核心元件是 AEM 不可或缺的一部分，並依照與 Quickstart 所提供相同的條款與條件給予支援。

就像其他AEM產品功能一樣，一般規則是：首先宣佈元件將過時，並且最早從下列AEM版本中移除。 這可讓客戶在停止支援之前，至少有一個版本的週期可移至新版本的元件。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

如需支援自訂元件的詳細資訊，請參閱[自訂核心元件](customizing.md)頁面。


## 技術功能 {#technical-capabilities}

下表概述核心元件與基礎元件之間的差異。

如需有關其撰寫功能的詳細資訊以及可預先設定它們的選項，[請參閱有關它們的撰寫頁面](/help/get-started/authoring.md)。

| **功能** | **核心元件** | **基礎元件** |
|-----|---|---|
| 邏輯實施 | 具有[Sling模型](https://sling.apache.org/documentation/bundles/models.html)註解的Java POJO | JSP程式碼 |
| 標籤定義 | [HTML範本語言](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html) (HTL)語法 | JSP程式碼 |
| XSS淨化 | 由HTL自動化 | 多為手動 |
| CSS類別命名 | 標準化命名慣例是以[區塊元素修飾元](https://getbem.com/) (BEM)標籤法（截至發行版本2.0.0）為基礎 | 自訂配置 |
| 對話方塊定義 | [珊瑚色3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 + Classic UI |
| JSON 輸出 | [Sling模型匯出工具與Jackson序列化](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 預設Sling servlet |
| 版本設定 | 模型和HTL的[&#128279;](guidelines.md) | 無 |
| 測試 | 單元測試+整合測試 | 整合測試 |
| 傳遞 | [透過公開GitHub](https://github.com/adobe/aem-core-wcm-components) | 透過Quickstart |
| 授權 | [Apache授權](https://www.apache.org/licenses/LICENSE-2.0) | Adobe專屬 |
| 貢獻 | 透過提取請求 | 不可能 |
| 協助工具 | 完全符合[WCAG 2.0 AA Standard](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) | 僅部分符合[WCAG 2.0 AA標準](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## 元件清單 {#component-list}

下表列出可用的核心元件、其API的連結，並指出其取代的基礎元件。

| 核心元件 | 說明 | 取代的基礎元件 |
|---|---|---|
| [Page](https://adobe.com/go/aem_cmp_tech_page_v2) | 使用範本編輯器的回應式頁面 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [階層連結](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2) | 頁面階層導覽 | `/libs/foundation/components/breadcrumb` |
| [標題](https://adobe.com/go/aem_cmp_tech_title_v2) | H1-H6標題 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文字](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | RTF 文字 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [影像](https://adobe.com/go/aem_cmp_tech_image_v2) | 以智慧和延遲的方式載入最佳轉譯大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [清單](https://adobe.com/go/aem_cmp_tech_list_v2) | 頁面清單 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒體分享](https://adobe.com/go/aem_cmp_tech_sharing_v1) | Facebook和Pinterest共用Widget | `-` |
| [來自容器](https://adobe.com/go/aem_cmp_tech_form_container_v2) | 回應式表單段落系統 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表單文字](https://adobe.com/go/aem_cmp_tech_form_text_v2) | 文字輸入欄位 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表單選項](https://adobe.com/go/aem_cmp_tech_form_options_v2) | 多選項輸入欄位 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [已隱藏的表單](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | 隱藏輸入欄位 | `/libs/foundation/components/form/hidden` |
| [表單按鈕](https://adobe.com/go/aem_cmp_tech_form_button_v2) | 提交或自訂按鈕 | `/libs/foundation/components/form/submit` |
| [導覽](https://adobe.com/go/aem_cmp_tech_navigation_v1) | 列出巢狀頁面階層的網站導覽元件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [語言導覽](https://adobe.com/go/aem_cmp_tech_langnav_v1) | 列出全球語言結構的語言和國家/地區切換器 | `-` |
| [快速搜尋](https://adobe.com/go/aem_cmp_tech_search_v1) | 在下拉式選單中將結果顯示為就地建議的搜尋元件 | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1) | 允許內容作者輕鬆建立Teaser，以使用影像、標題或RTF文字進一步內容並連結至進一步內容或其他動作 | `-` |
| [索引標籤](https://adobe.com/go/aem_cmp_tech_tabs_v1) | 允許內容作者將頁面內容整理在多個索引標籤中 | `-` |
| [傳送](https://adobe.com/go/aem_cmp_tech_carousel_v1) | 允許內容作者將內容整理在旋轉的幻燈片輪播中 | `/libs/foundation/components/carousel` |
| [內容片段](https://adobe.com/go/aem_cmp_tech_cf_v1) | 允許顯示內容片段 | `-` |
| [內容片段清單](https://adobe.com/go/aem_cmp_tech_cflist_v1) | 允許顯示內容片段清單 | `-` |
| [分隔符號](https://adobe.com/go/aem_cmp_tech_separator_v1) | 分隔頁面上的內容 | `-` |
| [折疊式面板](https://adobe.com/go/aem_cmp_tech_accordion_v1) | 在可摺疊的摺疊式功能表中整理內容面板 | `-` |
| [容器](https://adobe.com/go/aem_cmp_tech_container_v1) | 在容器中組織元件 | `-` |
| [按鈕](https://adobe.com/go/aem_cmp_tech_button_v1) | 在頁面上建立按鈕 | `-` |
| [下載](https://adobe.com/go/aem_cmp_tech_download_v1) | 將可下載的資產新增至頁面 | `-` |
| [體驗片段](https://adobe.com/go/aem_cmp_tech_xf_v1) | 新增體驗片段至頁面 | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [內嵌](https://adobe.com/go/aem_cmp_tech_embed_v1) | 在頁面中內嵌外部資源 | - |
| [進度列](https://adobe.com/go/aem_cmp_tech_progress_v1) | 提供目標進度的視覺化表示 | - |
| [PDF檢視器](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1) | 在頁面上顯示PDF檔案 | - |

## 核心元件的升級 {#upgrade-of-core-components}

版本化元件的一個優點是，它允許將移轉至新AEM版本與移轉至新元件版本分開。 此外，如果有新的元件版本，可讓個別元件移轉至新版本。

移轉至新AEM版本不會影響核心元件的運作方式，前提是其版本也支援正在移轉至的新AEM版本。 對核心元件進行的自訂作業也不應受影響，只要這些自訂作業未使用已[棄用或移除的API](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)。

移轉至核心元件的新版本也不會影響元件的運作方式，但可能會為頁面作者引入新功能，這可能需要範本編輯器進行一些設定，以備不想要的預設行為時使用。 不過，可能需要調整自訂，如需詳細資訊，請參閱[自訂核心元件](customizing.md#upgrade-compatibility-of-customizations)頁面。
