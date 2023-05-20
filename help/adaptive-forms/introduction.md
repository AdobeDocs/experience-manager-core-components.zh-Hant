---
title: 適AEM用Forms核心元件簡介
description: 利用自適應Forms核心元件的靈活性，創造引人注目的註冊體驗（表格），並借助Adobe Experience Manager的力量提供。
role: Architect, Developer, Admin, User
exl-id: 6d0f2845-bbb8-4488-a254-b69d7a6290b1
source-git-commit: 1ac6ed00c19a8ae00e6a53d18419890a88235158
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 3%

---

# 自適應Forms核心元件簡介 {#adaptive-forms-core-components-introduction}

使用Adobe Experience Manager的自適應Forms核心元件，您可以利用現有的靈活性和定制選項來創造引人注目的註冊體驗。

## 核心元件  {#overview}

在Adobe Experience Manager(AEM)中，元件是用於建立頁面和表單的構件。 它們為作者建立和管理內容提供了簡單而強大的方法，同時也為開發人員提供了建立自定義元件所需的靈活性和可擴充性。 這些功能旨在加快開發時間並降低網站和表單的維護成本，靈活且可輕鬆定制以滿足網站和表單的特定需求。

核心元件還設計為能夠響應並支援多種設備，包括台式機、平板電腦和智慧手機。 它們還遵循最新的Web標準和最佳做法，使其成為用於建立Web內容的強健而可靠的解決方案。

總的來說，核心元件是建立和管理網站內容的重要工具AEM，它提供了功能強大且靈活的解決方案，可幫助減少開發時間和維護成本，同時為網站訪問者提供極好的用戶體驗。

## 自適應Forms核心元件

自適應Forms核心元件是一組24個開源、符合BEM的元件，它們構建在Adobe Experience ManagerWCM核心元件的基礎上。 它們專門設計用於建立適應性Forms，後者是適應用戶的設備、瀏覽器和螢幕大小的表單。

這些元件可通過提供多種表單域選項（包括文本域、複選框、下拉菜單等）來建立卓越的資料捕獲和註冊體驗。 它們還包括驗證、條件邏輯和響應設計等功能，這些功能可用於建立方便用戶且易於使用的表單。

此外，由於這些元件是開源的，因此開發人員能夠輕鬆定制和擴展元件以滿足其組織的特定需求。 並且，這些元件都建立在BEM方法上，確保它們具有可擴充性和可維護性。

![](assets/sample-adaptive-form.png)

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 自適應Forms核心元件是24個強健的WCM元件。 |
| 雲就緒 | 可用於  [AEM Formsas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html)。 |
| 多功能 | 這些元件代表通用概念，Forms作者可以用這些概念裝配幾乎任何佈局。 |
| 可配置 | 模板級 [內容策略](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies) 定義允許使用或不使用哪些特徵。 |
| 易於取得 | 它們提供ARIA標籤，支援鍵盤導航([已知問題](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+輔助功能+in%3Atitle))，以及螢幕閱讀器等輔助技術的文本。 |
| 主題 | 元件實現 [樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)的 [BEM CSS約定](https://getbem.com/)。 |
| 可定製 | 幾種模式允許輕鬆自定義，從調整HTML到高級功能重用。 |
| 版本設定 | 的 [版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) 確保核心元件在改進可能影響您的內容時不會中斷您的站點。 |
| 開源 | 如果事情不是它應該做的，那就幫助你改進。 |

<!-- comply with [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), -->


## 優點 {#benefits}

資料捕獲體驗對於潛在客戶的生成和註冊至關重要，而自適應Forms核心元件為建立針對資料捕獲而優化的表單提供了強大的解決方案。 使用核心元件建立基礎元件的這些體驗的一些原因包括：

* **GitHub上的可用性和全面的文檔**:自適AEM應Forms核心元件是開源的，可在GitHub上使用，並提供全面的文檔。 這使開發人員更容易瞭解元件及其工作方式，並有助於開發。 的 [aemcomponents.dev](https://www.aemcomponents.dev/) 網站也是一個有價值的資源，開發人員可以在這裡查看操作中的元件，並訪問詳細的文檔。

* **造型的BEM模型**:「核心元件」遵循BEM（塊元素修飾符）模型進行造型，這是一種建立良好且廣泛使用的組織CSS的方法。 這樣，開發人員就更容易瞭解樣式的組織方式以及如何根據其特定需求修改它們。

* **不依賴第三方圖書館**:核心元件的一個優點是它們不依賴於第三方JavaScript庫，包括JQuery和下划線。 這使元件更快、更輕，而且更容易整合到現有實AEM施中。

* **注重效能和可訪問性**:核心元件的構建以效能和可訪問性為核心，這一點反映在它們的Google燈塔和網路生命體評分高中。 這使開發人員能夠更輕鬆地建立可訪問且高效能的網頁，而在當今的數字環境中，這一點越來越重要。

* **網站30模板和主題中的表單元件**:核心元件支援站點30模板和主題中的表單元件，使開發人員能夠更輕鬆地在中建立和自定義表AEM單。

* **更易於設計樣式**:核心元件比其基礎元件對應元件更易於設計樣式。 主題建立過程與「站點」類似，能夠從父「站點」頁繼承相同的主題/CSS。 此外，造型的BEM模型使得更容易理解和修改樣式。

* **輔助功能**:適應性Forms核心部分支援無障礙標準和准則，以確保殘疾人，包括使用輔助技術的殘疾人，如螢幕閱讀器，可以使用表格

## 自適應Forms核心元件 {#components}

當前版本的自適應Forms核心元件具有以下所列元件。

* [折疊式面板](/help/adaptive-forms/components/accordion.md)
* [按鈕](/help/adaptive-forms/components/button.md)
* [複選框組](/help/adaptive-forms/components/checkbox-group.md)
* [日期挑選器](/help/adaptive-forms/components/date-picker.md)
* [下拉清單](/help/adaptive-forms/components/drop-down.md)
* [電子郵件輸入](/help/adaptive-forms/components/email-input.md)
* [來自容器](/help/adaptive-forms/components/form-container.md)
* [檔案附件](/help/adaptive-forms/components/file-attachment.md)
* [頁尾](/help/adaptive-forms/components/footer.md)
* [頁首](/help/adaptive-forms/components/header.md)
* [水準制表符](/help/adaptive-forms/components/horizontal-tabs.md)
* [影像](/help/adaptive-forms/components/image.md)
* [數字輸入](/help/adaptive-forms/components/number-input.md)
* [面板容器](/help/adaptive-forms/components/panel-container.md)
* [選項按鈕](/help/adaptive-forms/components/radio-button.md)
* [重設按鈕](/help/adaptive-forms/components/reset-button.md)
* [提交按鈕](/help/adaptive-forms/components/submit-button.md)
* [電話輸入](/help/adaptive-forms/components/telephone-input.md)
* [文本輸入](/help/adaptive-forms/components/text-input.md)
* [文字](/help/adaptive-forms/components/text.md)
* [標題](/help/adaptive-forms/components/title.md)
* [精靈](/help/adaptive-forms/components/wizard.md)

## 設定核心元件


自適應Forms核心元件具有以下要求。

| AEM | AEM Forms附加 | 核心元件 |
|---|---|---|
| AEM as a Cloud Service  | Forms — 數字註冊 | [2.20.8版](version.md)+ |
| AEM 6.5 | Forms附加 | [1.1.12版](version.md)+ |

### 基於核心元件建立自適應表單

**AEM Formsas a Cloud Service:** 建立新的AEM Formsas a Cloud Service程式時，已為您的環境啟用了自適應Forms核心元件。 如果你有一個基於原型39或更早的Formsas a Cloud Service環境， [為您的環境啟用自適應Forms核心元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html?#enable-adaptive-forms-core-components-for-an-existing-aem-archetype-based-project)。

在為您的環境啟用核心元件時， **自適應Forms（核心元件）** 模板和畫布主題將添加到您的環境中。 如果AEMSDK版本早於2023.02.0, [確保 `prerelease` 在您的環境中啟用的標誌](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=en#new-features) 因為自適應Forms核心元件是發佈前預租2023.02.0的一部分。

要使用自適應Forms嚮導和自適應表單編輯器建立自適應表單，請參見建立自適應表單([核心元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?))。





<!-- >, such as  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), to ensure that forms can be used by people with disabilities, including those using assistive technologies such as screen readers.

*   **Alignment with AEM Sites**: The Core Components are designed to be more aligned with AEM Sites, making it easier for Sites users to adopt and use them without having to learn anything new. The components use the same front-end pipeline as Sites, making it easier to style and modify their appearance. 

<!-- Additionally, the following points further illustrate this alignment:

    *   **Authoring experience inline with Page editor**: The Core Components have an authoring experience that is inline with the Sites editor, with dialogs and other experiences similar to the Page editor. This makes it easier for Sites users to create and manage forms within the familiar context of the Sites editor.

    *   **Inline form editing in Sites editor**: The Core Components allow  inline form editing within the Sites editor, avoiding the need to switch back and forth between editors. This streamlines the authoring experience and makes it easier to create and manage forms.

    *   **Inheriting Sites features in Forms**: Forms authored within a Sites page inherit the same features as Sites. This provides a seamless and integrated experience for creating and managing forms within the context of AEM Sites 
    
    <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->
