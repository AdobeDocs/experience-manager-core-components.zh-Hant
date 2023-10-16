---
title: AEM Adaptive Forms核心元件簡介
description: 運用Adaptive Forms核心元件的彈性，建立吸引人的註冊體驗（表單），並運用Adobe Experience Manager的強大功能加以提供。
role: Architect, Developer, Admin, User
exl-id: 6d0f2845-bbb8-4488-a254-b69d7a6290b1
source-git-commit: 13e802c510e165d3ef3da431e1e8b0fe7b35d801
workflow-type: tm+mt
source-wordcount: '1262'
ht-degree: 7%

---

# 最適化Forms核心元件簡介 {#adaptive-forms-core-components-introduction}

使用Adobe Experience Manager中的最適化Forms核心元件，您可以運用彈性和可用的自訂選項來建立引人入勝的註冊體驗。

## 核心元件  {#overview}

在Adobe Experience Manager (AEM)中，元件是用來建立頁面和表單的建置組塊。 它們為作者提供簡單且強大的方式來建立和管理內容，同時為開發人員提供建立自訂元件所需的彈性和擴充性。 這些設定可加快開發時間並降低網站與表單的維護成本、彈性且可輕鬆自訂，以符合網站與表單的特定需求。

核心元件也設計為可快速回應，並支援各種裝置，包括桌上型電腦、平板電腦和智慧型手機。 此外，也遵循最新的網頁標準與最佳實務，使其成為建立網頁內容的健全且可靠的解決方案。

整體而言，核心元件是在AEM中建立及管理Web內容的重要工具，提供強大且彈性的解決方案，有助於減少開發時間及維護成本，同時為網站訪客提供絕佳的使用者體驗。

## 最適化Forms核心元件

最適化Forms核心元件是一組24個開放原始碼、BEM相容的元件，建立在Adobe Experience Manager WCM核心元件的基礎上。 這些表單是專為建立最適化Forms所設計，是適合使用者裝置、瀏覽器和熒幕大小的表單。

這些元件可用來建立優異的資料擷取和註冊體驗，方法是提供各式各樣的表單欄位選項，包括文字欄位、核取方塊、下拉式功能表等。 此外也包含驗證、條件式邏輯和回應式設計等功能，可用來建立簡單易用的表單。

此外，由於這些元件是開放原始碼，開發人員可輕鬆自訂和擴充元件，以符合其組織的特定需求。 此外，這些元件建置於BEM方法上，可確保它們具有可擴充性和可維護性。

![](assets/sample-adaptive-form.png)

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 最適化Forms核心元件是24個強大的WCM元件。 |
| 雲端就緒 | 可用於  [AEM Formsas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html). |
| 多功能 | 這些元件代表一般概念，Forms作者可透過這些概念來組合幾乎所有版面。 |
| 可設定 | 範本層級 [內容原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies) 定義允許使用或不使用哪些特徵。 |
| 易於取得 | 這類選件提供ARIA標籤、支援鍵盤導覽，以及熒幕閱讀器等輔助技術的文字。 |
| 佈景主題表格 | 元件實作 [樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)，標籤如下 [BEM CSS慣例](https://getbem.com/). |
| 可自訂 | 有幾種模式可讓您輕鬆自訂，從調整HTML到進階功能重複使用。 |
| 版本設定 | 此 [版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) 確保核心元件在改善可能影響您的內容時，不會中斷您的網站。 |
| 開放來源 | 如果有出錯的地方，請協助您改善。 |

<!-- comply with [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), -->


## 優點 {#benefits}

資料擷取體驗對於潛在客戶產生和註冊至關重要，Adaptive Forms核心元件為建立針對資料擷取最佳化的表單提供強大的解決方案。 使用核心元件透過基礎元件建立這些體驗的部分原因包括：

* **GitHub和完整檔案可供使用**： AEM最適化Forms核心元件是開放原始碼，可在GitHub上取得，以及完整的檔案。 如此一來，開發人員就能更輕鬆瞭解元件及其運作方式，且更能協助開發工作。 此 [aemcomponents.dev](https://www.aemcomponents.dev/) 網站也是寶貴的資源，開發人員可在此檢視運作中的元件，並存取詳細檔案。

* **樣式的BEM模型**：核心元件在樣式設定上會遵循BEM （區塊元素修飾元）模型，這是一項建立良好且廣泛使用的方法來組織CSS。 如此一來，開發人員就能更輕鬆瞭解樣式的組織方式，以及如何修改樣式，以符合其特定需求。

* **對協力廠商程式庫沒有相依性**：核心元件的優點之一，就是其不依存於協力廠商JavaScript程式庫，包括JQuery和Underscore。 這可讓元件更快且更輕量，以及更輕鬆地整合至現有的AEM實作。

* **著重於效能與協助工具**：核心元件的建置考量了效能和協助工具，這反映在其高的Google Lighthouse和Web重要分數中。 這可讓開發人員更輕鬆地建立可存取且高效能的網頁，在當今的數位格局中，這越來越重要。

* **Sites 30範本和主題中的表單元件**：核心元件支援Sites 30範本和主題中的表單元件，讓開發人員更容易在AEM中建立和自訂表單。

* **樣式更簡單**：核心元件的樣式比對應的基礎元件更容易設定。 佈景主題建立程式類似於Sites，可從父Sites頁面繼承相同佈景主題/CSS。 此外，用於樣式化的BEM模型可讓您更容易理解及修改樣式。

* **協助工具**：最適化Forms核心元件支援協助工具標準和准則，以確保殘障人士可以使用表單，包括使用熒幕閱讀器等輔助技術的殘障人士

## 最適化Forms核心元件 {#components}

目前版本的Adaptive Forms核心元件包含下列元件。

* [折疊式面板](/help/adaptive-forms/components/accordion.md)
* [按鈕](/help/adaptive-forms/components/button.md)
* [核取方塊群組](/help/adaptive-forms/components/checkbox-group.md)
* [日期挑選器](/help/adaptive-forms/components/date-picker.md)
* [下拉式清單](/help/adaptive-forms/components/drop-down.md)
* [電子郵件輸入](/help/adaptive-forms/components/email-input.md)
* [來自容器](/help/adaptive-forms/components/form-container.md)
* [檔案附件](/help/adaptive-forms/components/file-attachment.md)
* [頁尾](/help/adaptive-forms/components/footer.md)
* [頁首](/help/adaptive-forms/components/header.md)
* [水準索引標籤](/help/adaptive-forms/components/horizontal-tabs.md)
* [影像](/help/adaptive-forms/components/image.md)
* [數字輸入](/help/adaptive-forms/components/number-input.md)
* [面板容器](/help/adaptive-forms/components/panel-container.md)
* [選項按鈕](/help/adaptive-forms/components/radio-button.md)
* [重設按鈕](/help/adaptive-forms/components/reset-button.md)
* [提交按鈕](/help/adaptive-forms/components/submit-button.md)
* [電話輸入](/help/adaptive-forms/components/telephone-input.md)
* [文字輸入](/help/adaptive-forms/components/text-input.md)
* [文字](/help/adaptive-forms/components/text.md)
* [標題](/help/adaptive-forms/components/title.md)
* [精靈](/help/adaptive-forms/components/wizard.md)

## 設定最適化Forms核心元件

在 AEM Forms as a Cloud Service 上啟用調適型表單心元件，可讓您使用 AEM Forms as a Cloud Service 實例開始建立、發佈和提供以核心元件為主的調適型表單和 Headless 表單至多個管道。 如需啟用最適化表單核心元件的詳細指示，請參閱 [在AEM Formsas a Cloud Service和本機開發環境中啟用最適化Forms核心元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html).

最適化Forms核心元件具有下列需求。

| AEM版本 | AEM Forms附加元件 | 最適化Forms核心元件 |
|---|---|---|
| AEM as a Cloud Service  | Forms — 數位註冊 | [發行版本2.0.10](version.md)+ |
| AEM 6.5 | Forms附加元件 | [發行版本1.1.12](version.md)+ |

如果您的AEM Cloud Service SDK版本早於2023.02.0， [確定您已 `prerelease` 在您的環境中啟用的標幟](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=zh-Hant#new-features) as Adaptive Forms核心元件屬於2023.02.0版之前的預先租賃。


## 建立以核心元件為基礎的最適化表單

您可以在AEM Formsas a Cloud Service或AEM 6.5 Forms環境中執行下列動作：

| 動作 | AEM Forms版本 |
|--------|------------------|
| 建立獨立的最適化表單 | [AEM Forms作為Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html) |
| 在AEM Sites頁面中建立最適化表單 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=en#create-an-adaptive-form-in-sites-editor-or-experience-fragment)， [AEM Forms作為Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#create-an-adaptive-form-in-sites-editor-or-experience-fragment) |
| 在AEM體驗片段中建立最適化表單 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=en#create-an-adaptive-form-in-experience-fragment)， [AEM Forms作為Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#create-an-adaptive-form-in-experience-fragment) |
| 將最適化表單轉換為體驗片段 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=en#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment)， [AEM Forms作為Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment) |





<!-- >, such as  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), to ensure that forms can be used by people with disabilities, including those using assistive technologies such as screen readers.

*   **Alignment with AEM Sites**: The Core Components are designed to be more aligned with AEM Sites, making it easier for Sites users to adopt and use them without having to learn anything new. The components use the same front-end pipeline as Sites, making it easier to style and modify their appearance. 

<!-- Additionally, the following points further illustrate this alignment:

    *   **Authoring experience inline with Page editor**: The Core Components have an authoring experience that is inline with the Sites editor, with dialogs and other experiences similar to the Page editor. This makes it easier for Sites users to create and manage forms within the familiar context of the Sites editor.

    *   **Inline form editing in Sites editor**: The Core Components allow  inline form editing within the Sites editor, avoiding the need to switch back and forth between editors. This streamlines the authoring experience and makes it easier to create and manage forms.

    *   **Inheriting Sites features in Forms**: Forms authored within a Sites page inherit the same features as Sites. This provides a seamless and integrated experience for creating and managing forms within the context of AEM Sites 
    
    <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->

{{see-also}}
