---
title: AEM 自適應表單核心元件簡介
description: 運用自適應表單核心元件的靈活性來創造吸引人的註冊體驗 (表單)，並結合 Adobe Experience Manager 的強大功能進行傳遞。
role: Architect, Developer, Admin, User
exl-id: 6d0f2845-bbb8-4488-a254-b69d7a6290b1
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '2123'
ht-degree: 100%

---


# 自適應表單核心元件  {#adaptive-forms-core-components-introduction}

使用 Adobe Experience Manager 中的自適應表單核心元件，您可以創造吸引人的註冊體驗。

{{traditional-aem}}

## 核心元件 {#overview}

在 Adobe Experience Manager (AEM) 中，元件是用來建立頁面和表單的建構區塊。它們為作者提供簡單且強大的方式來建立和管理內容，同時為開發人員提供建立自訂元件所需的彈性和擴充性。這些設定可加快開發時間，並降低網站與表單的維護成本、靈活性高且可輕鬆自訂，以符合網站與表單的特定需求。

核心元件也設計為可快速回應，並支援各種裝置，包括桌上型電腦、平板電腦和智慧型手機。此外，也遵循最新的網頁標準與最佳做法，使其成為建立網頁內容的強大可靠解決方案。

整體而言，核心元件是在 AEM 中建立及管理網頁內容的重要工具，提供強大且彈性的解決方案，有助於減少開發時間及維護成本，同時為網站訪客提供絕佳的使用者體驗。

## 自適應表單核心元件

自適應表單核心元件是以 Adobe Experience Manager WCM 核心元件為基礎所建立的 30 個開放原始碼且符合 BEM 的元件集。這些元件專為建立自適應表單所設計，而此類表單可根據使用者的裝置、瀏覽器和螢幕大小自動調整。

這些元件可用來創造優異的資料擷取和註冊體驗，方法是提供各式各樣的表單欄位選項，包括文字欄位、核取方塊、下拉式選單等。它們也包含驗證、條件式邏輯和回應式設計等功能，可用來建立簡單易用的表單。

此外，由於這些元件是開放原始碼，開發人員可輕鬆自訂和擴充元件，以符合其組織的特定需求。而且，這些元件是以 BEM 方法建置的，可確保它們具有可擴充性和可維護性。

![自適應表單影像](assets/sample-adaptive-form.png)

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 自適應表單核心元件是 24 個強大的 WCM 元件。 |
| 雲端就緒 | 適用於 [AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html)。 |
| 多功能 | 這些元件代表通用概念，表單作者可加以運用，以組合出幾乎任何版面。 |
| 可設定 | 範本層級[內容原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies) 定義可以使用或無法使用的功能。 |
| 易於存取 | 它們提供 ARIA 標籤、支援鍵盤導覽，以及輔助技術 (如螢幕助讀程式) 所使用的文字等。 |
| 可主題化 | 元件實施[樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)，標記語言也遵循 [BEM CSS 慣例](https://getbem.com/)。 |
| 可自訂 | 數個模式允許輕鬆自訂，涵蓋從調整 HTML 到進階功能重複使用。 |
| 版本設定 | [版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)可確保核心元件在改善可能影響您的內容時，不會破壞您的網站。 |
| 開放原始碼 | 如果發現錯誤，請協助我們改進。 |

<!-- comply with [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), -->


## 優點 {#benefits}

資料擷取體驗對於潛在客戶產生和註冊至關重要，而自適應表單核心元件為建立針對資料擷取最佳化的表單提供強大的解決方案。使用核心元件而非基礎元件來建立這些體驗的部分原因包括：

* **[GitHub 上的可用性](https://github.com/adobe/aem-core-forms-components)**：AEM 自適應表單核心元件是開放原始碼，可在 GitHub 上取得，並提供完整文件。如此一來，開發人員就能更輕鬆了解元件及其運作方式，且更能協助開發工作。[aemcomponents.dev](https://www.aemcomponents.dev/) 網站也是寶貴的資源，開發人員可在此檢視運作中的元件，並存取詳細文件。

* **[樣式的 BEM 模型](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components)**：核心元件遵循 BEM (區塊元素修飾元) 模型來設定樣式，這是一套建立完善且廣泛使用的 CSS 組織方法。如此一來，開發人員就能更輕鬆了解樣式的組織方式，以及如何修改樣式，以符合其特定需求。

* **對第三方程式庫沒有相依性**：核心元件的優點之一，就是它們對第三方 JavaScript 程式庫 (包括 JQuery 和 Underscore) 沒有相依性。這可讓元件更快且更輕量，以及更輕鬆地整合至現有的 AEM 實施。

* **著重於效能與協助工具**：核心元件建置時已考慮到效能與協助工具，這反映在它們的 Google Lighthouse 和網頁指標分數上。這可讓開發人員更輕鬆地建立可存取且高效能的網頁，而這在現今的數位環境中日益重要。

* **Sites 30 個範本和主題的表單元件**：核心元件支援 Sites 30 個範本和主題的表單元件，讓開發人員更容易在 AEM 中建立和自訂表格。

* **[樣式更簡單](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components)**：核心元件的樣式比基礎元件的樣式更簡單。佈景主題建立流程類似於 Sites，可從上層 Sites 頁面繼承相同主題/CSS。此外，樣式的 BEM 模型可讓您更容易理解及修改樣式。

* **協助工具**：自適應表單核心元件支援協助工具標準和指南，以確保身心障礙使用者 (包括使用輔助技術 (例如螢幕助讀程式) 的使用者) 可以使用表格。

* **[版本設定](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/add-comments-annotations-versioning-adaptive-form-core-components)**：您可以建立並管理多個以核心元件為基礎的自適應表單版本，透過留言功能參與合作討論，並可針對特定表單元件附上註解，藉此提升整體表單建置體驗。

## 可用元件：依元件類型劃分

AEM Forms 的目前版本有下列核心元件、[基礎元件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/create-an-adaptive-form-on-forms-cs/introduction-forms-authoring#component-toolbar)，和[表單區塊元件 (Edge Delivery Services)](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/edge-delivery/build-forms/forms-references/form-components)。

| 元件 | 基礎元件 | 核心元件 | 表單區塊元件 | 其他資訊 |
|------------|:---------------------:|:---------------:|:---------------------:|-----------------------|
| Adobe Sign 區塊 | ✔️ | | | [Adobe Sign 整合](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/integrate/services/adobe-sign-integration-adaptive-forms#adobe-acrobat-sign-for-government) 僅適用於基礎元件。 |
| 摺疊面板 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/accordion.md)</span> | | 對於基礎元件，您可以在[面板元件屬性](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout)中設定摺疊面板的版面。 |
| 自適應表單片段 | ✔️ | ✔️ | | 對於基礎元件，您可以從資產瀏覽器[新增片段](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-65/content/forms/adaptive-forms-basic-authoring/adaptive-form-fragments#insert-a-fragment-in-an-adaptive-form)。 |
| 自適應表單 reCAPTCHA | ✔️ | ✔️ | ✔️ | 對於基礎元件，請使用驗證碼元件將 [Google reCaptcha 新增至表單](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms#google-reCAPTCHA)。 |
| 按鈕 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/button.md)</span> | ✔️ | |
| 圖表 | ✔️ | | | |
| 核取方塊 | ✔️ | ✔️ | | |
| 核取方塊群組 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/checkbox-group.md)</span> | ✔️ | 對於基礎元件，請使用核取方塊元件以新增多個核取方塊 |
| 資料輸入欄位 | ✔️ | | | 對於核心元件，請使用[日期挑選器](/help/adaptive-forms/components/date-picker.md)元件。您也可以新增個別的[文字方塊](/help/adaptive-forms/components/text-box.md)或[數值方塊](/help/adaptive-forms/components/numeric-box.md)元件，以擷取日、月和年。 |
| 日期挑選器 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/date-picker.md)</span> | ✔️ | |
| 下拉式清單 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/drop-down-list.md)</span> | ✔️ | |
| 電子郵件 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/email.md)</span> | ✔️ | |
| 檔案附件 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/file-attachment.md)</span> | ✔️ | |
| 檔案附件清單 | ✔️ | | | |
| 頁尾 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/footer.md)</span> | ✔️ | |
| 註腳預留位置 | ✔️ | | | |
| 表單容器 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/form-container.md)</span> | ✔️ | 對於基礎元件，請使用[根面板元件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/cloud-service/forms/create-first-af/configure-root-panel)。 |
| 表單標題 | ✔️ | ✔️ | | 對於基礎元件，請使用標題元件。 |
| hCaptcha | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/hcaptcha.md)</span> |  | 對於基礎元件，您可以[將自適應表單與 hCaptcha 連接](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile.html)，以用於以基礎元件為基礎的表單。 |
| 頁首 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/header.md)</span> | ✔️ | |
| 水平索引標籤 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/horizontal-tabs.md)</span> | | 對於基礎元件，您可以在面板元件屬性中設定[頂端索引標籤 (水平索引標籤) 版面](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout)。 |
| 影像 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/image.md)</span> | ✔️ | |
| 下一個按鈕 | ✔️ | ✔️ | | 請使用[精靈元件](/help/adaptive-forms/components/wizard.md)中的下一個和上一個按鈕，以便在多個面板之間移動。 |
| 數值方塊 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/numeric-box.md)</span> | ✔️ | |
| 數值步進器 | ✔️ | | | |
| 面板 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/panel.md)</span> | ✔️ | |
| 電話/手機 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/phone.md)</span> | ✔️ | |
| 上一個按鈕 | ✔️ | ✔️ | | 請使用[精靈元件](/help/adaptive-forms/components/wizard.md)中的下一個和上一個按鈕，以便在多個面板之間移動。 |
| 選項按鈕群組 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/radio-button.md)</span> | ✔️ | |
| 重設按鈕 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/reset-button.md)</span> | ✔️ | |
| 檢閱 |  | <span style="color:blue">[✔️](/help/adaptive-forms/components/reset-button.md)</span> |  | |
| 手寫簽名 | ✔️ | | | |
| 分隔符號 | ✔️ | | | 請使用 WCM [分隔符號](/help/components/separator.md)元件 |
| 提交按鈕 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/submit-button.md)</span> | ✔️ | |
| 摘要步驟 | ✔️ | | | |
| 切換 | ✔️ | <span style="color:blue"> [✔️](/help/adaptive-forms/components/adaptive-form-switch.md) | | |
| 表格 | ✔️ | | | |
| 條款與條件 | ✔️ | ✔️ | | |
| 文字 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/text.md)</span> | ✔️ | |
| 文字方塊 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/text-box.md)</span> | ✔️ | |
| Turnstile 驗證碼 | ✔️ | | | [Turnstile 驗證碼](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile) 僅適用於基礎元件。 |
| 垂直索引標籤 | ✔️ | ✔️ | | 對於基礎元件，您可以在面板元件屬性中設定[左側索引標籤 (垂直索引標籤) 版面](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout) |
| 精靈 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/wizard.md)</span> | ✔️ | 對於基礎元件，您可以在面板元件屬性中設定[精靈版面](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout) |

<!--| Password Box | ✔️ | ✔️| ✔️ | |
| Image Choice | ✔️ | | | |
-->


>[!NOTE]
>
>
> * 除了上述元件之外，表單區塊還支援所有有效的 [HTML5 輸入類型](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#input_types)和[文字區域](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)作為元件。
> * 需要上方未列出的元件嗎？請從您的官方地址傳送電子郵件至 aem-forms-ea@adobe.com 以提出請求。


<!-- >
* [Accordion](/help/adaptive-forms/components/accordion.md)
* [Adaptive Form Fragment](/help/adaptive-forms/components/adaptive-form-fragment.md)
* [Adaptive Form Switch](/help/adaptive-forms/components/adaptive-form-switch.md)
* [Button](/help/adaptive-forms/components/button.md)
* [Check Box Group](/help/adaptive-forms/components/checkbox-group.md)
* [Date Picker](/help/adaptive-forms/components/date-picker.md)
* [Drop-down list](/help/adaptive-forms/components/drop-down-list.md)
* [Email](/help/adaptive-forms/components/email.md)
* [Form Container](/help/adaptive-forms/components/form-container.md)
* [File Attachment](/help/adaptive-forms/components/file-attachment.md)
* [Footer](/help/adaptive-forms/components/footer.md)
* [Header](/help/adaptive-forms/components/header.md)
* [Horizontal Tabs](/help/adaptive-forms/components/horizontal-tabs.md)
* [Image](/help/adaptive-forms/components/image.md)
* [Numeric Box](/help/adaptive-forms/components/numeric-box.md)
* [Panel](/help/adaptive-forms/components/panel.md)
* [Phone](/help/adaptive-forms/components/phone.md)
* [Radio Button](/help/adaptive-forms/components/radio-button.md)
* [Adaptive Form reCAPTCHA](/help/adaptive-forms/components/adaptive-form-recaptcha.md)
* [Reset Button](/help/adaptive-forms/components/reset-button.md)
* [Submit Button](/help/adaptive-forms/components/submit-button.md)
* [Text Box](/help/adaptive-forms/components/text-box.md)
* [Text](/help/adaptive-forms/components/text.md)
* [Form Title](/help/adaptive-forms/components/form-title.md)
* [Wizard](/help/adaptive-forms/components/wizard.md)

-->

## 簡單易用的表單編輯器

以核心元件為基礎的自適應表單編輯器類似於您已用於建立 AEM Sites 頁面的編輯器。以下是您獲得的內容：


* **熟悉的 UI 元素和設定**：設定表單元件的屬性時，您會看到屬性對話框，外觀和您在 WCM 核心元件上所使用的對話框非常相似。這可讓您更快找到所需的選項。如同 WCM 核心元件，表單元件的屬性對話框會顯示在編輯器的中央，以清楚的索引標籤分隔基本和進階選項、說明文字及協助工具資訊，所有內容都以索引標籤格式顯示，以方便瀏覽。

* **[規則編輯器](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/rule-editor-core-components)**：您可以新增邏輯和動態功能至表單，而不需要撰寫程式碼。您可以使用內建規則編輯器進行下列：
   * 根據使用者選擇以顯示或隱藏欄位
   * 啟用或停用物件
   * 設定物件的值
   * 執行計算
   * 設定物件的屬性
   * 驗證資料輸入
   * 叫用服務 (呼叫外部功能)
   * 使用內建函數 (常見任務的預先定義函數)
   * 使用自訂函數 (自己為特定需求撰寫的程式碼)
   * 驗證欄位和面板 (確保資料符合要求)
   * 驗證物件的值
   * 執行函數以運算物件的值
   * 叫用表單資料模型 (FDM) 服務並執行作業
   * 動態新增樣式 (根據條件變更外觀)
   * 建立其他規則 (串接動作和邏輯)
   * 及更多內容！

  規則編輯器沒有程式碼編輯器。您可以使用[自訂函數](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-and-use-custom-functions)，將自己為特定需求撰寫的程式碼新增至規則編輯器。



* **預填表單**：當使用者開啟表單時，會自動將現有資料填入表單中的特定欄位。如此一來，使用者就無需手動輸入可能已存在的資訊，進而節省時間與精力。核心元件編輯器提供 OOTB 預填服務，可在表單資料模型的協助下填入表單欄位。您也可以為更複雜的情境建立自訂預填服務。

* **[記錄文件 (DoR)](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components)**：記錄文件 (DoR) 是指透過表單提交的資料的正式、可列印版本。它用作使用者輸入資訊的永久記錄，以方便使用的格式 (通常是 PDF 文件) 提供提交資料的快照。您可以使用編輯器輕鬆設定自訂範本，或使用 OOTB 範本產生 DoR。

* **[表單資料模型](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/using-form-data-model)**：自適應表單資料模型 (FDM) 可作為自適應表單和資料來源之間的橋樑。它基本上定義您的表單收集和互動之資料的結構和組織。您可以使用編輯器輕鬆地將表單與表單資料模型 (FDM) 連接。

* **[表單提交](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Adaptive%20Form%20Submit%20Action&text=Adobe%20recommends%20using%20Core%20Components,to%20create%20standalone%20Adaptive%20Forms.&text=A%20Submit%20Action%20lets%20you,button%20on%20an%20Adaptive%20Form)**：表單提交是指使用者填寫並傳送已填妥的表單的過程。這會觸發在表單設定中定義的一系列動作，最終將提交的資料進行儲存或處理。自適應表單編輯器提供多種設定表單提交的選項。常見的提交動作包括：

   * [傳送電子郵件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Adaptive%20Form%20Submit%20Action&text=Adobe%20recommends%20using%20Core%20Components,to%20create%20standalone%20Adaptive%20Forms.&text=A%20Submit%20Action%20lets%20you,button%20on%20an%20Adaptive%20Form)
   * [叫用 Power Automate 流程](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/integrate/services/forms-microsoft-power-automate-integration)
   * [提交至 SharePoint](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-action-sharepoint)
   * [叫用 Workfront Fusion](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Invoke%20a%20Workfront%20Fusion)
   * [使用表單資料模型 (FDM) 提交](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/using-form-data-model)
   * [提交至 Azure Blob Storage](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Submit%20to%20Azure%20Blob%20Storage)
   * [提交至 REST 端點](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-action-restpoint)
   * [提交至 OneDrive](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=to%20REST%20endpoint-,Submit%20to%20OneDrive,-Invoke%20an%20AEM)
   * [叫用 AEM 工作流程](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Invoke%20an%20AEM%20Workflow)


* [Sites 頁面編輯器中的自適應表單核心元件](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page)：您可以在 AEM 頁面編輯器和 AEM 體驗片段中啟用並使用自適應表單核心元件，以便在建置 Sites 頁面的同時直接建立資料擷取體驗。

  >[!VIDEO](https://video.tv.adobe.com/v/3419284?quality=12&learn=on)


<!-- 
* **Preview Forms**: You can use the editor to  simulates how the form would appear on various devices like desktops, tablets, and smartphones.
-->



## 啟用自適應表單核心元件

在 AEM Forms as a Cloud Service 上啟用自適應表單核心元件，可讓您使用 AEM Forms as a Cloud Service 執行個體開始建立、發佈和傳遞以核心元件為主的自適應表單和無周邊表單至多個管道。如需啟用自適應表單核心元件的詳細指示，請參閱[在 AEM Forms as a Cloud Service 和本機開發環境中啟用自適應表單核心元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html)。

自適應表單核心元件有下列要求。

| AEM 版本 | AEM Forms 附加元件 | 自適應表單核心元件 |
|---|---|---|
| AEM as a Cloud Service | Forms - 數位註冊 | [版本 2.0.10](version.md)+ |
| AEM 6.5 | Forms 附加元件 | [版本 1.1.12](version.md)+ |

如果您的 AEM Cloud Service SDK 版本比 2023.02.0 更舊，[請確定已`prerelease`在您的環境中啟用標幟](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=zh-hant#new-features)，因為自適應表單核心元件是 2023.02.0 版本之前搶鮮版的一部分。


## 建立以核心元件為主的自適應表單

您可以在 AEM Forms as a Cloud Service 或 AEM 6.5 Forms 環境中執行下列動作：

| 動作 | AEM Forms 版本 |
|--------|------------------|
| 建立獨立的自適應表單 | [AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html) |
| 在 AEM Sites 頁面建立自適應表單 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=zh-hant#create-an-adaptive-form-in-sites-editor-or-experience-fragment)、 [AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#create-an-adaptive-form-in-sites-editor-or-experience-fragment) |
| 在 AEM 體驗片段中建立自適應表單 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=zh-hant#create-an-adaptive-form-in-experience-fragment)、 [AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#create-an-adaptive-form-in-experience-fragment) |
| 將自適應表單轉換為體驗片段 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=zh-hant#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment)、 [AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment) |





<!-- >, such as  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), to ensure that forms can be used by people with disabilities, including those using assistive technologies such as screen readers.

*   **Alignment with AEM Sites**: The Core Components are designed to be more aligned with AEM Sites, making it easier for Sites users to adopt and use them without having to learn anything new. The components use the same front-end pipeline as Sites, making it easier to style and modify their appearance. 

<!-- Additionally, the following points further illustrate this alignment:

    *   **Authoring experience inline with Page editor**: The Core Components have an authoring experience that is inline with the Sites editor, with dialogs and other experiences similar to the Page editor. This makes it easier for Sites users to create and manage forms within the familiar context of the Sites editor.

    *   **Inline form editing in Sites editor**: The Core Components allow  inline form editing within the Sites editor, avoiding the need to switch back and forth between editors. This streamlines the authoring experience and makes it easier to create and manage forms.

    *   **Inheriting Sites features in Forms**: Forms authored within a Sites page inherit the same features as Sites. This provides a seamless and integrated experience for creating and managing forms within the context of AEM Sites 
    
    <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->

## 另請參閱 {#see-also}

{{see-also}}
