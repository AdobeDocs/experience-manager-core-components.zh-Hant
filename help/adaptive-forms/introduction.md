---
title: AEM適用性Forms核心元件簡介
description: 利用適用性Forms核心元件的彈性，建立引人入勝的註冊體驗（表單），並運用Adobe Experience Manager的強大功能提供。
role: Architect, Developer, Admin, User
source-git-commit: 86fa434d884b24b8d4b231c6108f5e6151a89813
workflow-type: tm+mt
source-wordcount: '1231'
ht-degree: 3%

---


# 適用性Forms核心元件簡介 {#adaptive-forms-core-components-introduction}

使用Adobe Experience Manager中的適用性Forms核心元件，您可以利用可用的彈性和自訂選項，建立引人入勝的註冊體驗。

## 核心元件  {#overview}

在Adobe Experience Manager(AEM)中，元件是用來建立頁面和表單的基礎元件。 它們為作者提供簡單而強大的方式來建立和管理內容，同時為開發人員提供建立自訂元件所需的彈性和擴充性。 這些功能可縮短開發時間並降低網站和表單的維護成本、靈活靈活，並可輕鬆定制以符合網站和表單的特定需求。

核心元件的設計回應速度也快，可支援多種裝置，包括桌上型電腦、平板電腦和智慧手機。 他們也遵守最新的網頁標準和最佳實務，成為建立網頁內容的強大且可靠的解決方案。

總的來說，核心元件是在AEM中建立和管理網頁內容的必要工具，提供強大而有彈性的解決方案，可協助減少開發時間和維護成本，同時為網站訪客提供絕佳的使用者體驗。

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
| 主題 | 元件會實作 [樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)，標籤如下 [BEM CSS慣例](https://getbem.com/). |
| 可自訂 | 從調整HTML到高級功能重複使用，多種模式都允許輕鬆定制。 |
| 版本設定 | 此 [版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) 確保核心元件在改善可能影響您的項目時不會破壞您的網站。 |
| 開放來源 | 如果有事不如預期，請協助您改善。 |

## 優點 {#benefits}

資料擷取體驗對於銷售機會的產生和註冊至關重要，而適用性Forms核心元件為建立針對資料擷取而最佳化的表單提供功能強大的解決方案。 使用核心元件建立基礎元件體驗的部分原因如下：

* **GitHub上市情況及完整檔案**:AEM適用性Forms核心元件為開放原始碼，可在GitHub上取得，並提供完整說明檔案。 這可讓開發人員更輕鬆了解元件及其運作方式，並協助開發人員進行開發。 此 [aemcomponents.dev](https://www.aemcomponents.dev/) 網站也是一項寶貴資源，開發人員可在其中查看實際運作中的元件，並存取詳細檔案。

* **用於樣式的BEM模型**:核心元件遵循BEM(Block Element Modifier)模型來進行樣式設計，這是一種建立良好且廣泛使用的CSS組織方法。 這可讓開發人員更輕鬆了解樣式的組織方式，以及如何修改樣式以符合其特定需求。

* **不相依於第三方程式庫**:核心元件的優點之一，就是不相依於協力廠商JavaScript程式庫，包括JQuery和底線。 這可讓元件更快速、更輕量，也更輕鬆整合至現有的AEM實作。

* **著重於效能和協助工具**:核心元件以效能和協助工具為基礎打造，其高Google燈塔和網路生命線分數便反映在此。 這可讓開發人員更輕鬆建立無障礙且高效能的網頁，這在現今的數位環境中日益重要。

* **Sites 30範本和主題中的表單元件**:核心元件支援Sites 30範本和主題中的表單元件，讓開發人員更容易在AEM中建立和自訂表單。

* **更輕鬆設定樣式**:核心元件的樣式比基礎元件相對應項目更輕鬆。 主題建立程式與Sites類似，可從上層Sites頁面繼承相同的主題/CSS。 此外，樣式的BEM模型可讓您更輕鬆了解和修改樣式。

* **協助工具**:適用性Forms核心元件支援協助工具標準和准則，例如  [WCAG 2.1標準](https://www.w3.org/TR/WCAG21/)，確保殘疾人（包括使用輔助技術的人，例如螢幕閱讀器）能使用表單。

* **與AEM Sites對齊**:核心元件的設計目的是更符合AEM Sites，讓Sites使用者更容易採用和使用，而不需學習任何新功能。 元件使用與Sites相同的前端管道，可更輕鬆地設定樣式和修改外觀。 此外，以下幾點進一步說明了此對齊方式：

   * **內嵌於頁面編輯器中的製作體驗**:核心元件的製作體驗內嵌於Sites編輯器中，具有與頁面編輯器類似的對話方塊和其他體驗。 這可讓Sites使用者更輕鬆地在熟悉的Sites編輯器內容中建立和管理表單。

   * **在Sites編輯器中編輯內嵌表單**:核心元件可讓Sites編輯器內嵌表單編輯作業，避免編輯器之間往返切換。 這可簡化製作體驗，並更輕鬆建立和管理表單。

   * **繼承Forms中的Sites功能**:在Sites頁面中撰寫的Forms會繼承與Sites相同的功能。 這可提供順暢且整合的體驗，讓您在AEM Sites中建立和管理表單

   <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->



## 要求 {#requirements}

適用性Forms核心元件有下列需求。

| AEM | AEM Forms附加元件 | 核心元件 |
|---|---|---|
| AEM as a Cloud Service  | Forms — 數位註冊 | [版本2.20.8](/help/versions.md)+ |


## 適用性Forms核心元件 {#components}

您可以使用 [適用性Forms編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html) 以建立以核心元件為基礎的適用性Forms。 最新版的適用性Forms核心元件提供下列元件。

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

