---
title: AEM適用性Forms核心元件簡介
description: 利用適用性Forms核心元件的彈性，建立引人入勝的註冊體驗（表單），並運用Adobe Experience Manager的強大功能提供。
role: Architect, Developer, Admin, User
source-git-commit: 781cf351ef52cbb56ff33c2674c8af591c81a30e
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 4%

---


# 適用性Forms核心元件簡介 {#adaptive-forms-core-components-introduction}

使用Adobe Experience Manager中的適用性Forms核心元件，您可以利用可用的彈性和自訂選項，建立引人入勝的註冊體驗。

## 核心元件  {#overview}

在Adobe Experience Manager(AEM)中，元件是用來建立頁面和表單的基礎元件。 它們為作者提供簡單而強大的方式來建立和管理內容，同時為開發人員提供建立自訂元件所需的彈性和擴充性。

核心元件是一組預先建置、標準化的WCM元件，旨在加快網站開發時間並降低網站維護成本。 這些元件包括文字欄位、影像、視訊等。 這些功能的設計靈活，可輕鬆自訂以符合網站的特定需求。

核心元件的設計回應速度也快，可支援多種裝置，包括桌上型電腦、平板電腦和智慧手機。 他們也遵守最新的網頁標準和最佳實務，成為建立網頁內容的強大且可靠的解決方案。

此外，核心元件的建置可順暢地與AEM的其他部分搭配運作，讓作者和開發人員能以更少的工作量和更少的時間建立更吸引人的互動式表單。

總的來說，核心元件是在AEM中建立和管理網頁內容的必要工具，提供強大而有彈性的解決方案，可協助減少開發時間和維護成本，同時為網站訪客提供絕佳的使用者體驗。

在Adobe Experience Manager中，元件是構成所編寫頁面和表單內容的結構元素。 元件向來是AEM體驗的基本元素，讓作者可輕鬆建立頁面和表單，但功能強大，而開發人員可靈活擴充元件。 核心元件是一組標準化的Web內容管理(WCM)元件，可加快開發時間並降低網站的維護成本。

## 適用性Forms核心元件

適用性Forms核心元件是一組24個開放原始碼、符合BEM規範的元件，建置於Adobe Experience Manager WCM核心元件的基礎之上。 這些表單經過專門設計，可用來建立最適化Forms，這些表單可適應使用者的裝置、瀏覽器和螢幕大小。

這些元件可用於通過提供多種表單欄位選項（包括文本欄位、複選框、下拉菜單等）來建立卓越的資料捕獲和註冊體驗。 這些功能也包含驗證、條件式邏輯和回應式設計等功能，可用來建立方便使用且易於使用的表單。

此外，由於這些元件是開放原始碼，開發人員可輕鬆自訂和擴充元件，以符合其組織的特定需求。 此外，這些元件均以BEM方法為基礎，可確保可擴充且可維護。

![](assets/sample-adaptive-form.png)

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 適用性Forms核心元件是24個強大的WCM元件。 |
| 雲就緒 | 適用於  [AEM Formsas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html). |
| 多功能 | 元件代表一般概念，Forms作者可用這些概念組合幾乎任何版面。 |
| 可設定 | 範本層級 [內容原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies) 定義允許或不允許使用的功能。 |
| 易於取得 | 他們遵守 [WCAG 2.1標準](https://www.w3.org/TR/WCAG21/)，提供ARIA標籤，支援鍵盤導覽([已知問題](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle))和文字，以取得輔助技術，例如螢幕閱讀器。 |
| 表 | 元件會實作 [樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)，標籤如下 [BEM CSS慣例](http://getbem.com/). |
| 可自訂 | 從調整HTML到高級功能重複使用，多種模式都允許輕鬆定制。 |
| 版本設定 | 此 [版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) 確保核心元件在改善可能影響您的項目時不會破壞您的網站。 |
| 開放來源 | 如果有事不如預期，請協助您改善。 |

## 優點 {#benefits}

資料擷取體驗對於銷售機會的產生和註冊至關重要，而適用性Forms核心元件為建立針對資料擷取而最佳化的表單提供功能強大的解決方案。 使用核心元件來建立這些體驗的部分原因如下：

* **自訂**:適用性Forms核心元件可讓開發人員輕鬆自訂表單元件（例如文字欄位、核取方塊和下拉式選單）的外觀和行為，以符合特定需求。

* **協助工具**:適用性Forms核心元件支援協助工具標準和准則，例如  [WCAG 2.1標準](https://www.w3.org/TR/WCAG21/)，確保殘疾人（包括使用輔助技術的人，例如螢幕閱讀器）能使用表單。

* **一致的表單**:透過使用適用性Forms核心元件，開發人員可建立外觀和風格一致的表單，讓使用者更容易了解及填寫表單，進而提升參與度並改善使用者體驗。

* **WYSIWYG編輯器**:AEM Forms提供易於使用的介面，易於使用WYSIWYG編輯器來使用這些元件來建立最適化表單。 它可讓表單作者建立和編輯表單，而不需知道如何編寫程式碼。 此外，還包含視覺化規則編輯器，可協助您輕鬆建立規則型動作並實作複雜邏輯，以自動化表單行為，而無須編寫程式碼。

* **條件式邏輯**:適用性Forms核心元件支援使用條件式邏輯，這表示表單元件的外觀或行為可根據使用者輸入的值進行變更。 例如，某些欄位可以隱藏，或根據在其他欄位中所做的選取而設為必填。

* **資料驗證**:適用性Forms核心元件提供內建資料驗證功能，讓開發人員可確保使用者輸入的資料符合特定條件，例如最小和最大長度、必要值和特定格式。

## 要求 {#requirements}

適用性Forms核心元件有下列需求。

| AEM | AEM Forms附加元件 | 核心元件 |
|---|---|---|
| AEM as a Cloud Service  | Forms — 數位註冊 | [版本2.20.8](/help/versions.md)+ |


## 適用性Forms核心元件 {#components}

最新版本的適用性Forms核心元件具備下列元件。

* 折疊式面板
* 按鈕
* 核取方塊群組
* 日期挑選器
* 下拉式清單
* 電子郵件輸入
* 來自容器
* 檔案附件
* 頁尾
* 頁首
* 水準標籤
* 影像
* 數字輸入
* 面板容器
* 選項按鈕
* 重設按鈕
* 提交按鈕
* 電話輸入
* 文字輸入
* 文字
* 標題
* 精靈

