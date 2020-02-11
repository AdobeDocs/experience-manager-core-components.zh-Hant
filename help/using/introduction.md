---
title: 核心元件簡介
description: '以最新技術和最佳實務為基礎，核心元件的引入提供了既強大又可擴充的基本元件。 '
translation-type: tm+mt
source-git-commit: 5439f90faef28c72367419bb7429a3a880b65229

---


# 核心元件簡介{#core-components-introduction}

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。元件向來是 AEM 體驗的基本元素，讓作者可輕鬆建立頁面、功能又強大，而開發人員在開發元件時，也可保有靈活性與擴充空間。

以最新技術和最佳實務為基礎，核心元件的引入提供了既強大又可擴充的基本元件，並遵循無障礙指南方針，且符合 WCAG 2.0 AA 標準。核心元件讓頁面的編寫方式更加靈活且提供客製化，開發人員可以輕鬆將元件擴展並加上客製化的功能。

## 嘗試使用核心元件

如果您想要立即開始試用核心元件，請前往[元件資料庫](https://adobe.com/go/aem_cmp_library)。「元件資料庫」是多數核心元件目前版本的線上展示，可讓您與各種元件互動，並檢視 HTML 和 JSON 的輸出範例。

WKND教 [學課程](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html) ，也說明如何使用核心元件。

## 核心元件 - 核心功能 {#core-components-core-features}

核心元件包括:

|  |  |
|--- |--- |
| 可預先設定 | 範本可以定義頁面作者的使用方式。 |
| 多功能 | 可供作者用來建立大多數的內容。 |
| 簡單好上手 | 可供作者有效率地建立和管理內容。 |
| 生產就緒 | 立即可用! 功能強大可靠、經過完善測試，而且效能優異。 |
| 易於取得 | 元件符合 WCAG 2.0 標準，提供 ARIA 標籤，並支援鍵盤導覽。 |
| 易於設計樣式 | 作者可使用 Style System 設計元件，標記語言也遵循 BEM CSS 命名規範。 |
| 搜尋引擎最佳化 (SEO) 友善 | HTML 可輸出語意，並提供 schema.org 結構化資料標記。 |
| PWA/SPA/應用程式就緒 | 用戶端演算亦可使用精簡的 JSON 輸出。 |
| 可擴充 | 既滿足客製化需求，又不需從頭做起，所有元件皆可擴充。 |
| 開放原始碼 | 如果發現錯誤，可前往 GitHub 提供改善 (Apache 授權)。 |
| 建立版本 | 核心元件改善可能影響您的內容時，不會使您的網站故障。 |
| [本地化](localization.md) | 智慧型參考解析度可讓特定元件自動尋找並轉換對應的本地化內容 |

## 可用元件 {#available-components}

目前版本的核心元件主打下列元件。

* [折疊式面板](accordion.md)
* [階層連結](breadcrumb.md)
* [按鈕](button.md)
* [容器](container.md)
* [傳送](carousel.md)
* [內容片段](content-fragment-component.md)
* [內容片段清單](content-fragment-list.md)
* [下載](download.md)
* [內嵌](embed.md)
* [體驗片段](experience-fragment.md)
* [表單按鈕](form-button.md)
* [來自容器](form-container.md)
* [已隱藏的表單](form-hidden.md)
* [表單選項](form-options.md)
* [表單文字](form-text.md)
* [影像](image.md)
* [語言導覽](language-navigation.md)
* [清單](list.md)
* [導覽](navigation.md)
* [頁面](page.md)
* [快速搜尋](quick-search.md)
* [分隔符號](separator.md)
* [社交媒體分享](sharing.md)
* [索引標籤](tabs.md)
* [文字](text.md)
* [標題](title.md)

>[!NOTE]
>
>[開發團隊必須先依照作者的環境整合核心元件](using.md)，才能將其提供給您。整合後，可透過範本編輯器提供並預先 [設定](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。

>[!CAUTION]
>
>某些版本的個別核心元件可能只相容於特定版本的 AEM。
>
>如需特定元件的相容性資訊，請參閱說明頁面 (連結至上一份清單)，或參考[核心元件版本](versions.md)文件以取得詳細資訊。

## 何時該使用核心元件 {#when-to-use-core-components}

核心元件不僅是全新功能，並且有多項優點，因此建議用於新的 AEM 專案。對於既有專案來說，移轉應該是品牌重塑或整體重構等較大專案工作的一部分。

如需特定使用建議，請參閱[何時該使用核心元件? ](developing.md)位於[開發核心元件](developing.md)文件中。

## Gem 課程概覽 {#gems-session-overview}

如需瞭解核心元件的簡介、其所提供的功能、以及在 AEM 中的運用方式，請參閱 AEM Gem 課程 [AEM 核心元件。](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) ，是Adobe專家提供的一系列技術深入探討。 這個系列補充了產品說明文件和所有其他的技術管道，讓開發人員可以接觸並深入瞭解特定的主題。

## 使用核心元件進行開發 {#developing-core-components}

核心元件提供強穩且可擴充的基本元件，可建置數種可輕鬆自訂的模式，從簡單樣式到進階功能可重複使用。 如需詳細 [資訊，請參閱核心元件開發檔案](developing.md) 。

依照WKND教學課程，開始使用核心元件開 [發AEM Sites。](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

別忘了開始使用 [AEM Project Archetype](overview.md) with the latest Core Components builted in!

## 核心元件支援 {#core-components-support}

核心元件是 AEM 不可或缺的一部分，並依照與 Quickstart 所提供相同的條款與條件給予支援。

就如同其他產品的功能，其生命週期結束的通則是:

* 移除元件前，將先公告該元件已被取代
* 最快將於公告後釋出的 AEM 版本中移除這些項目。

這可讓客戶在支援結束前，至少有一個版本的週期可移至新版本的元件。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

如需支援自訂元件的詳細資訊，請參閱[自訂核心元件](customizing.md)頁面瞭解相關的核心元件版本。

## 基礎元件支援 {#foundation-component-support}

由於基礎元件是過去許多版本中專案開發的基礎，因此在可預見的未來中，這些元件仍將繼續受到支援。

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.
