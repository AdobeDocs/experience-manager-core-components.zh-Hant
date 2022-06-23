---
title: 開發核心元件
description: 核心元件提供強大且可擴展的基本元件，這些元件提供功能豐富、連續交付、元件版本控制、現代實現、精益標籤和內容的JSON導出。
role: Architect, Developer, Admin
exl-id: 0f79cac1-a3b0-487e-90be-0bd8263d3912
source-git-commit: faf73c70a4bff387bed2f8cf6e48c39e597e51c7
workflow-type: tm+mt
source-wordcount: '1559'
ht-degree: 13%

---

# 開發核心元件 {#developing-core-components}

## 何時使用核心元件？ {#when-to-use-the-core-components}

核心元件不僅是全新功能，並且有多項優點，因此建議用於新的 AEM 專案。對於既有專案來說，移轉應該是品牌重塑或整體重構等較大專案工作的一部分。

因此，Adobe提出了以下建議：

* **新建項目**
新項目應始終嘗試使用核心元件。 如果核心元件不能直接使用或 [擴展](customizing.md) 為滿足項目要求，然後按照核心元件中規定的元件體系結構建立一個自定義元件。 除非不可能，否則請避免使用 [基礎元件](/help/versions.md#foundation-component-support)。
* **現有項目**
建議是繼續使用 [基礎元件](/help/versions.md#foundation-component-support)，除非計畫進行站點或元件重構。\
   由於它們被大多數現有項目廣泛使用，所以基礎部件 [將繼續受支援。](/help/versions.md#foundation-component-support)
* **新建自定義元件**
評估現有 [可以定制核心元件](customizing.md)。\
   否則，建議在 [元件指南](guidelines.md)。
* **現有自定義元件**
如果元件按預期工作，則按原樣保持它們。
\
   否則，請參閱上面的「新建自定義元件」。

## 如何成功使用核心元件 {#how-to-succeed}

核心元件功能強大、靈活，易於使用和定制。 [遵循幾條關鍵准則](success.md) 將確保您的核心元件項目成功。

## 遷移到核心元件

任何新項目都應與核心元件一起實施。 但是，現有項目通常會有廣泛的Foundation Components實施。

### 從Foundation元件遷移 {#from-foundation}

對現有項目（例如重新品牌塑造或整體重構）進行更大的努力通常提供了遷移到核心元件的機會。 為了促進這一遷移，Adobe提供了一些遷移工具，以鼓勵採用核心元件和最新AEM技術。

[現代AEM化工具](http://opensource.adobe.com/aem-modernize-tools/) 允許輕鬆轉換：

* 從靜態範本轉換為可編輯的範本
* 根據原則設計設定
* 從基礎元件轉換為核心元件
* 從傳統 UI 轉換為觸控式 UI

有關這些工具的使用情況的詳細資訊， [查看文檔](http://opensource.adobe.com/aem-modernize-tools/)。

>[!NOTE]
>
>現代AEM化工具是社區工作，不受Adobe支援或授權。

## 通過移動到AEMas a Cloud Service {#via-aemaacs}

由AEM於as a Cloud Service自動附帶最新版本的核心元件，因此當您從內部安裝AEM遷移時，需要刪除項目中對核心元件的任何依賴關係 `pom.xml` 的子菜單。

代理元件仍將像以前一樣工作，因為代理指向必要的超類型，且超類型路徑中包含版本。 這樣，只要刪除依賴項，核心元件就可以像在內部那樣在AEMaCS中工作。

與任何其他AEMaaCS項目一樣，您也需要向SDK jarAEM添加依賴項。 這並非特定於核心元件，而是必需的。

```xml
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-sdk-api</artifactId>
</dependency>
```

查看文檔 [項AEM目結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html) 的子菜單。

## 核心元件支援 {#core-component-support}

核心元件是 AEM 不可或缺的一部分，並依照與 Quickstart 所提供相同的條款與條件給予支援。

與其他產AEM品功能一樣，一般規則是：首先宣佈不建議使用元件，並且最早刪除以下版本的AEM元件。 這樣，客戶在放棄對元件的支援之前，至少可以在一個發佈週期內轉到新版本的元件。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

有關支援元件自定義的詳細資訊，請參見 [定制核心元件](customizing.md) 的子菜單。


## 技術能力 {#technical-capabilities}

下表概述了核心元件和基礎元件之間的差異。

有關其創作能力和預配置選項的詳細資訊， [請參閱有關它們的創作頁面](/help/get-started/authoring.md)。

| **功能** | **核心元件** | **基礎元件** |
|-----|---|---|
| 邏輯實現 | Java POJO [吊具模型](https://sling.apache.org/documentation/bundles/models.html) 注釋 | JSP代碼 |
| 標籤定義 | [HTML模板語言](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=zh-Hant) (HTL)語法 | JSP代碼 |
| XSS消毒 | 由HTL自動 | 主要是手動 |
| CSS類命名 | 基於的標準化命名約定 [塊要素修改量](https://getbem.com/) (BEM)符號(從2.0.0版開始) | 自定義方案 |
| 對話框定義 | [珊瑚3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | 珊瑚2 +經典用戶介面 |
| JSON輸出 | [Sling Models Exporter，帶Jackson系列](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 預設Sling Servlet |
| 版本設定 | [對於模型和HTL](guidelines.md) | 無 |
| 測試 | 設備Test+整合Test | 整合Test |
| 傳送 | [通過公共GitHub](https://github.com/adobe/aem-core-wcm-components) | 通過快速啟動 |
| 授權 | [Apache許可證](https://www.apache.org/licenses/LICENSE-2.0) | Adobe專有 |
| 貢獻 | 通過拉入請求 | 不可能 |
| 協助工具 | 完全符合 [WCAG 2.0 AA標準](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) | 僅與 [WCAG 2.0 AA標準](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## 元件清單 {#component-list}

下表列出了可用的核心元件，它們連結到API，並指明了它們替換的基礎元件。

| 核心元件 | 說明 | 已更換基礎元件 |
|---|---|---|
| [Page](https://adobe.com/go/aem_cmp_tech_page_v2) | 使用模板編輯器的響應頁面 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [階層連結](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2) | 頁面層次導航 | `/libs/foundation/components/breadcrumb` |
| [標題](https://adobe.com/go/aem_cmp_tech_title_v2) | H1-H6標題 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文字](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | 富文本 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [影像](https://adobe.com/go/aem_cmp_tech_image_v2) | 智慧且緩慢地載入最佳再現大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [清單](https://adobe.com/go/aem_cmp_tech_list_v2) | 頁面清單 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒體分享](https://adobe.com/go/aem_cmp_tech_sharing_v1) | Facebook和Pinterest共用小部件 | `-` |
| [來自容器](https://adobe.com/go/aem_cmp_tech_form_container_v2) | 回應式段落系統 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表單文字](https://adobe.com/go/aem_cmp_tech_form_text_v2) | 文本輸入欄位 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表單選項](https://adobe.com/go/aem_cmp_tech_form_options_v2) | 多個選項輸入欄位 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [已隱藏的表單](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | 隱藏輸入欄位 | `/libs/foundation/components/form/hidden` |
| [表單按鈕](https://adobe.com/go/aem_cmp_tech_form_button_v2) | 提交或自定義按鈕 | `/libs/foundation/components/form/submit` |
| [導覽](https://adobe.com/go/aem_cmp_tech_navigation_v1) | 列出嵌套頁層次結構的站點導航元件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [語言導覽](https://adobe.com/go/aem_cmp_tech_langnav_v1) | 列出全球語言結構的語言和國家/地區切換器 | `-` |
| [快速搜尋](https://adobe.com/go/aem_cmp_tech_search_v1) | 在下拉菜單中將結果顯示為就地建議的搜索元件 | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1) | 允許內容作者使用影像、標題或富格文本輕鬆建立預告，以進一步內容，並連結到其他內容或其他操作 | `-` |
| [索引標籤](https://adobe.com/go/aem_cmp_tech_tabs_v1) | 允許內容作者在多個頁籤內組織頁面內容 | `-` |
| [傳送](https://adobe.com/go/aem_cmp_tech_carousel_v1) | 允許內容作者將內容組織在旋轉的幻燈片旋轉盤中 | `/libs/foundation/components/carousel` |
| [內容片段](https://adobe.com/go/aem_cmp_tech_cf_v1) | 允許顯示內容片段 | `-` |
| [內容片段清單](https://adobe.com/go/aem_cmp_tech_cflist_v1) | 允許顯示內容片段清單 | `-` |
| [分隔符號](https://adobe.com/go/aem_cmp_tech_separator_v1) | 分隔頁面上的內容 | `-` |
| [折疊式面板](https://adobe.com/go/aem_cmp_tech_accordion_v1) | 在可折疊手風琴中組織內容面板 | `-` |
| [容器](https://adobe.com/go/aem_cmp_tech_container_v1) | 在容器內組織元件 | `-` |
| [按鈕](https://adobe.com/go/aem_cmp_tech_button_v1) | 在頁面上建立按鈕 | `-` |
| [下載](https://adobe.com/go/aem_cmp_tech_download_v1) | 將可下載資產添加到頁面 | `-` |
| [體驗片段](https://adobe.com/go/aem_cmp_tech_xf_v1) | 將體驗片段添加到頁面 | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [內嵌](https://adobe.com/go/aem_cmp_tech_embed_v1) | 在頁面中嵌入外部資源 | - |
| [進度列](https://adobe.com/go/aem_cmp_tech_progress_v1) | 提供目標進展的直觀表示 | - |
| [PDF 檢視器](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1) | 在頁面上顯示PDF文檔 | - |

## 升級核心元件 {#upgrade-of-core-components}

版本控制元件的一個好處是它允許將遷移到新版本AEM與遷移到新元件版本分開。 此外，如果有新的元件版本，它允許將每個元件單獨遷移到新版本。

遷移到新版AEM本不會影響核心元件的工作方式，前提是其版本還支援要遷AEM移到的新版本。 對核心元件進行的自定義也不應受到影響，只要它們不使用已使用的API [已棄用或刪除](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)。

遷移到新版本的核心元件也不會影響元件的工作方式，但可能會向頁面作者介紹新功能，這可能需要模板編輯器進行一些配置，以防不需要預設行為。 但是，可能需要調整自定義項，有關詳細資訊，請參閱 [定制核心元件](customizing.md#upgrade-compatibility-of-customizations) 的子菜單。
