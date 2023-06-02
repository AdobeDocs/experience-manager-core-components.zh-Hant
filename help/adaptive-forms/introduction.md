---
title: AEM Adaptive Forms核心元件簡介
description: 運用Adaptive Forms核心元件的彈性，建立引人入勝的註冊體驗（表單），並運用Adobe Experience Manager的強大功能加以提供。
role: Architect, Developer, Admin, User
exl-id: 6d0f2845-bbb8-4488-a254-b69d7a6290b1
source-git-commit: 8648a8dabd1999c9d3bbb76bb4f04f16eafda650
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 3%

---

# Adaptive Forms核心元件簡介 {#adaptive-forms-core-components-introduction}

使用Adobe Experience Manager中的最適化Forms核心元件，您可以利用可用的彈性和自訂選項來建立引人入勝的註冊體驗。

## 核心元件  {#overview}

在Adobe Experience Manager (AEM)中，元件是用來建立頁面和表單的建置組塊。 它們為作者提供簡單且強大的方式來建立和管理內容，同時為開發人員提供建立自訂元件所需的彈性和擴充性。 這些設定旨在加快開發時間並降低網站和表單的維護成本，具有彈性，並可輕鬆自訂以符合網站和表單的特定需求。

核心元件也設計為可迅速回應，並支援各種裝置，包括桌上型電腦、平板電腦和智慧型手機。 此外，這些規則也遵循最新的網頁標準和最佳實務，使其成為建立網頁內容的健全且可靠的解決方案。

整體而言，核心元件是在AEM中建立和管理Web內容的重要工具，提供強大且彈性的解決方案，有助於減少開發時間和維護成本，同時為網站訪客提供最佳的使用者體驗。

## 最適化Forms核心元件

最適化Forms核心元件是一組24個開放原始碼、BEM相容的元件，建立在Adobe Experience Manager WCM核心元件的基礎上。 這些表單專為建立最適化Forms而設計，這些表單可適應使用者的裝置、瀏覽器和熒幕大小。

這些元件可用來建立優異的資料擷取和註冊體驗，方法是提供廣泛的表單欄位選項，包括文字欄位、核取方塊、下拉式功能表等。 此外也包含驗證、條件式邏輯和回應式設計等功能，這些功能可用來建立方便使用者且易於使用的表單。

此外，由於這些元件是開放原始碼，開發人員能夠輕鬆自訂和擴充元件，以符合其組織的特定需求。 此外，這些元件是建構在BEM方法上，可確保它們可擴充且可維護。

![](assets/sample-adaptive-form.png)

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 最適化Forms核心元件是24個強大的WCM元件。 |
| 雲端就緒 | 可用於  [AEM Formsas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html). |
| 多功能 | 這些元件代表了一般概念，Forms作者可透過這些概念來組合幾乎所有版面。 |
| 可設定 | 範本層級 [內容原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies) 定義允許使用或不使用哪些特徵。 |
| 易於取得 | 它們提供ARIA標籤，支援鍵盤導覽([已知問題](✓ https://github.com/adobe/aem-core-wcm-components/issues?utf8=&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle))，以及熒幕閱讀器等輔助技術的文字。 |
| 佈景主題表格 | 元件會實作 [樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)，標籤如下 [BEM CSS慣例](https://getbem.com/). |
| 可自訂 | 有幾種模式可讓您輕鬆自訂，從調整HTML到進階功能重複使用。 |
| 版本設定 | 此 [版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) 確保核心元件在改善可能影響您的內容時，不會破壞您的網站。 |
| 開放來源 | 如果有出錯的地方，請協助改進。 |

<!-- comply with [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), -->


## 優點 {#benefits}

資料擷取體驗對於銷售機會產生和註冊至關重要，Adaptive Forms核心元件為建立針對資料擷取最佳化的表單提供強大的解決方案。 使用核心元件透過基礎元件建立這些體驗的部分原因包括：

* **提供GitHub和完整檔案**： AEM Adaptive Forms核心元件是開放原始碼，可在GitHub上取得，並提供完整檔案。 如此一來，開發人員就能更輕鬆瞭解元件及其運作方式，並協助進行開發。 此 [aemcomponents.dev](https://www.aemcomponents.dev/) 網站也是寶貴資源，開發人員可透過網站檢視運作中的元件及存取詳細檔案。

* **樣式的BEM模型**：核心元件會遵循BEM （區塊元素修飾元）模型來設定樣式，這是用於組織CSS的成熟且廣泛使用的方法。 如此一來，開發人員就能更輕鬆瞭解樣式的組織方式，以及如何修改樣式，以符合其特定需求。

* **對協力廠商程式庫沒有相依性**：核心元件的優點之一，就是其不依存於協力廠商JavaScript程式庫，包括JQuery和Underscore。 這可讓元件更快、更輕量，以及更易於整合至現有AEM實作。

* **著重於效能與協助工具**：核心元件建置時已考慮到效能和無障礙功能，這反映在其高的Google Lighthouse和Web重要分數中。 如此一來，開發人員就能更輕鬆地建立無障礙且高效能的網頁，而這在當今的數位環境中變得愈加重要。

* **Sites 30範本和主題中的表單元件**：核心元件支援Sites 30範本和主題中的表單元件，讓開發人員更容易在AEM中建立和自訂表單。

* **樣式更簡單**：核心元件的樣式比對應的基礎元件更容易設定。 佈景主題建立程式類似於Sites，能夠從父Sites頁面繼承相同佈景主題/CSS。 此外，用於樣式的BEM模型使樣式更容易理解和修改。

* **協助工具**：最適化Forms核心元件支援無障礙標準和准則，以確保殘障人士可以使用表單，包括使用熒幕閱讀器等輔助技術的殘障人士

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
* [水準標籤](/help/adaptive-forms/components/horizontal-tabs.md)
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

在AEM Formsas a Cloud Service上啟用最適化Forms核心元件，可讓您使用AEM FormsCloud Service例項在多個管道中開始建立、發佈和提供核心元件型最適化Forms和Headless Forms。 如需啟用最適化表單核心元件的詳細指示，請參閱 [在AEM Formsas a Cloud Service和本機開發環境中啟用最適化Forms核心元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html).

最適化Forms核心元件具有下列需求。

| AEM | AEM Forms附加元件 | 最適化Forms核心元件 |
|---|---|---|
| AEM as a Cloud Service  | Forms — 數位註冊 | [版本2.0.10](version.md)+ |
| AEM 6.5 | Forms附加元件 | [發行版本1.1.12](version.md)+ |

如果您的AEM Cloud Service SDK版本比2023.02.0舊， [確定您擁有 `prerelease` 在您的環境中啟用的標幟](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=en#new-features) as Adaptive Forms核心元件屬於2023.02.0版之前的預先租賃。


### 根據核心元件建立最適化表單

若要在AEM Formsas a Cloud Service上建立最適化表單，請參閱 [建立最適化表單（核心元件）](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?).





<!-- >, such as  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), to ensure that forms can be used by people with disabilities, including those using assistive technologies such as screen readers.

*   **Alignment with AEM Sites**: The Core Components are designed to be more aligned with AEM Sites, making it easier for Sites users to adopt and use them without having to learn anything new. The components use the same front-end pipeline as Sites, making it easier to style and modify their appearance. 

<!-- Additionally, the following points further illustrate this alignment:

    *   **Authoring experience inline with Page editor**: The Core Components have an authoring experience that is inline with the Sites editor, with dialogs and other experiences similar to the Page editor. This makes it easier for Sites users to create and manage forms within the familiar context of the Sites editor.

    *   **Inline form editing in Sites editor**: The Core Components allow  inline form editing within the Sites editor, avoiding the need to switch back and forth between editors. This streamlines the authoring experience and makes it easier to create and manage forms.

    *   **Inheriting Sites features in Forms**: Forms authored within a Sites page inherit the same features as Sites. This provides a seamless and integrated experience for creating and managing forms within the context of AEM Sites 
    
    <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->
