---
title: 開發核心元件
description: 核心元件提供強大且可擴充的基本元件，具備豐富的功能、持續傳遞、元件版本設定、現代化實施、精簡標籤以及內容的JSON匯出。
role: Architect, Developer, Admin
exl-id: 0f79cac1-a3b0-487e-90be-0bd8263d3912
source-git-commit: 614bc5fd01a76a6888606faa4576e1695b77ba58
workflow-type: tm+mt
source-wordcount: '1559'
ht-degree: 13%

---

# 開發核心元件 {#developing-core-components}

## 何時該使用核心元件？ {#when-to-use-the-core-components}

核心元件不僅是全新功能，並且有多項優點，因此建議用於新的 AEM 專案。對於既有專案來說，移轉應該是品牌重塑或整體重構等較大專案工作的一部分。

因此，Adobe提供下列建議：

* **新專案**
新專案應一律嘗試使用核心元件。 如果核心元件無法直接使用或 [延伸](customizing.md) 若要滿足專案需求，請依照核心元件中所述的元件架構建立自訂元件。 除非沒有其他方法，否則請避免使用 [基礎元件](/help/versions.md#foundation-component-support).
* **現有專案**
建議持續使用 [基礎元件](/help/versions.md#foundation-component-support)，除非有計畫進行網站或元件重構。\
   由於大部分的現有專案已廣泛使用基礎元件，因此基礎元件 [將繼續獲得支援。](/help/versions.md#foundation-component-support)
* **新自訂元件**
評估是否存在 [可自訂核心元件](customizing.md).\
   如果沒有，建議您在下列步驟之後建置新的自訂元件 [元件指導方針](guidelines.md).
* **現有自訂元件**
如果您的元件如預期般運作，則請原樣保留。
\
   如果沒有，請參閱上述「新自訂元件」。

## 如何使用核心元件獲得成功 {#how-to-succeed}

核心元件功能強大、彈性好用，且易於使用與自訂。 [遵循幾項重要准則](success.md) 將確保您使用核心元件的專案成功進行。

## 移轉至核心元件

任何新專案都應使用核心元件實作。 不過，現有專案通常具有基礎元件的廣泛實作。

### 從基礎元件移轉 {#from-foundation}

對現有專案進行較大努力（例如品牌重塑或整體重構）通常可讓您移轉至核心元件。 為了加速此移轉，Adobe提供了許多移轉工具，以鼓勵採用核心元件和最新的AEM技術。

[AEM現代化工具](https://opensource.adobe.com/aem-modernize-tools/) 可輕鬆轉換：

* 從靜態範本轉換為可編輯的範本
* 根據原則設計設定
* 從基礎元件轉換為核心元件
* 從傳統 UI 轉換為觸控式 UI

如需這些工具使用方式的詳細資訊， [請參閱他們的檔案](https://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>AEM現代化工具是社群共同努力的成果，Adobe不提供支援或保證。

## 透過移轉至AEMas a Cloud Service進行移轉 {#via-aemaacs}

由於AEMas a Cloud Service會自動隨最新版核心元件提供，當您從內部部署AEM安裝遷移時，您必須在專案中移除任何與核心元件的相依性 `pom.xml` 檔案。

您的Proxy元件仍會像之前一樣運作，因為Proxy指向必要的超型別，而超型別路徑中有版本。 如此一來，只要移除相依性，核心元件就能像內部部署一樣在AEMaaCS中運作。

就像任何其他AEMaaCS專案一樣，您也需要將相依性新增到AEM SDK jar。 這並非核心元件所特有，但為必要專案。

```xml
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-sdk-api</artifactId>
</dependency>
```

檢視檔案 [AEM專案結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html) 以取得AEMaaCS專案的詳細資訊。

## 核心元件支援 {#core-component-support}

核心元件是 AEM 不可或缺的一部分，並依照與 Quickstart 所提供相同的條款與條件給予支援。

如同其他AEM產品功能，一般規則是：首先宣佈元件將過時，並且最早從下列AEM版本中移除。 這可讓客戶在停止支援之前，至少有一個發行週期可移至元件的新版本。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

如需支援元件自訂功能的詳細資訊，請參閱 [自訂核心元件](customizing.md) 頁面。


## 技術功能 {#technical-capabilities}

下表概述核心元件與基礎元件之間的差異。

如需有關其製作功能的詳細資訊以及可預先設定它們的選項， [請參閱其相關撰寫頁面](/help/get-started/authoring.md).

| **功能** | **核心元件** | **基礎元件** |
|-----|---|---|
| 邏輯實施 | Java POJOs搭配 [Sling模型](https://sling.apache.org/documentation/bundles/models.html) 註解 | JSP程式碼 |
| 標籤定義 | [HTML範本語言](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=zh-Hant) (HTL)語法 | JSP程式碼 |
| XSS淨化 | 由HTL自動化 | 大部分手動 |
| CSS類別命名 | 標準化命名慣例依據 [區塊元素修飾元](https://getbem.com/) (BEM)標籤法（截至發行版本2.0.0） | 自訂配置 |
| 對話方塊定義 | [珊瑚色3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 + Classic UI |
| JSON 輸出 | [具有Jackson序列化的Sling模型匯出工具](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 預設Sling servlet |
| 版本設定 | [用於模型和HTL](guidelines.md) | 無 |
| 測試 | 單元測試+整合測試 | 整合測試 |
| 傳送 | [透過公開GitHub](https://github.com/adobe/aem-core-wcm-components) | 透過Quickstart |
| 授權 | [Apache授權](https://www.apache.org/licenses/LICENSE-2.0) | 專屬Adobe |
| 貢獻 | 透過提取請求 | 不可能 |
| 協助工具 | 完全符合 [WCAG 2.0 AA標準](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) | 僅與部分相容 [WCAG 2.0 AA標準](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## 元件清單 {#component-list}

下表列出可用的核心元件、其API的連結，並指出其取代的基礎元件。

| 核心元件 | 說明 | 已取代的基礎元件 |
|---|---|---|
| [Page](https://adobe.com/go/aem_cmp_tech_page_v2) | 使用範本編輯器的回應式頁面 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [階層連結](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2) | 頁面階層導覽 | `/libs/foundation/components/breadcrumb` |
| [標題](https://adobe.com/go/aem_cmp_tech_title_v2) | H1-H6標題 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文字](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | RTF文字 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [影像](https://adobe.com/go/aem_cmp_tech_image_v2) | 智慧型和延遲載入最佳轉譯大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [清單](https://adobe.com/go/aem_cmp_tech_list_v2) | 頁面清單 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒體分享](https://adobe.com/go/aem_cmp_tech_sharing_v1) | facebook和Pinterest共用Widget | `-` |
| [來自容器](https://adobe.com/go/aem_cmp_tech_form_container_v2) | 回應式表單段落系統 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表單文字](https://adobe.com/go/aem_cmp_tech_form_text_v2) | 文字輸入欄位 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表單選項](https://adobe.com/go/aem_cmp_tech_form_options_v2) | 多選項輸入欄位 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [已隱藏的表單](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | 隱藏的輸入欄位 | `/libs/foundation/components/form/hidden` |
| [表單按鈕](https://adobe.com/go/aem_cmp_tech_form_button_v2) | 提交或自訂按鈕 | `/libs/foundation/components/form/submit` |
| [導覽](https://adobe.com/go/aem_cmp_tech_navigation_v1) | 列出巢狀頁面階層的網站導覽元件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [語言導覽](https://adobe.com/go/aem_cmp_tech_langnav_v1) | 列出全球語言結構的語言和國家/地區切換器 | `-` |
| [快速搜尋](https://adobe.com/go/aem_cmp_tech_search_v1) | 在下拉式選單中將結果顯示為就地建議的搜尋元件 | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1) | 允許內容作者輕鬆建立Teaser，以使用影像、標題或RTF文字進一步內容並連結至進一步內容或其他動作 | `-` |
| [索引標籤](https://adobe.com/go/aem_cmp_tech_tabs_v1) | 允許內容作者將頁面內容整理在多個標籤中 | `-` |
| [傳送](https://adobe.com/go/aem_cmp_tech_carousel_v1) | 允許內容作者將內容整理在旋轉的幻燈片輪播中 | `/libs/foundation/components/carousel` |
| [內容片段](https://adobe.com/go/aem_cmp_tech_cf_v1) | 允許顯示內容片段 | `-` |
| [內容片段清單](https://adobe.com/go/aem_cmp_tech_cflist_v1) | 允許顯示內容片段清單 | `-` |
| [分隔符號](https://adobe.com/go/aem_cmp_tech_separator_v1) | 分隔頁面上的內容 | `-` |
| [折疊式面板](https://adobe.com/go/aem_cmp_tech_accordion_v1) | 在可摺疊的摺疊式功能表中整理內容面板 | `-` |
| [容器](https://adobe.com/go/aem_cmp_tech_container_v1) | 在容器中組織元件 | `-` |
| [按鈕](https://adobe.com/go/aem_cmp_tech_button_v1) | 在頁面上建立按鈕 | `-` |
| [下載](https://adobe.com/go/aem_cmp_tech_download_v1) | 新增可下載的資產至頁面 | `-` |
| [體驗片段](https://adobe.com/go/aem_cmp_tech_xf_v1) | 新增體驗片段至頁面 | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [內嵌](https://adobe.com/go/aem_cmp_tech_embed_v1) | 在頁面中內嵌外部資源 | - |
| [進度列](https://adobe.com/go/aem_cmp_tech_progress_v1) | 提供向目標進度的視覺化表示 | - |
| [PDF 檢視器](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1) | 在頁面上顯示PDF檔案 | - |

## 核心元件的升級 {#upgrade-of-core-components}

版本化元件的一個優點是，它允許將移轉至新AEM版本與移轉至新元件版本分開。 此外，如果有新的元件版本可用，它允許個別地將每個元件移轉至新版本。

移轉至新AEM版本不會影響核心元件的運作方式，前提是其版本也支援移轉至的新AEM版本。 對核心元件進行的自訂也不應受影響，只要這些自訂不使用 [已棄用或已移除](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html).

移轉至新版本的核心元件也不會影響元件的運作方式，但可能會為頁面作者引入新功能，這可能需要範本編輯器進行一些設定，以免出現預設行為。 不過，自訂功能可能需要調整，如需詳細資訊，請參閱 [自訂核心元件](customizing.md#upgrade-compatibility-of-customizations) 頁面。
