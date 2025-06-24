---
title: AEM最適化Forms核心元件簡介
description: 運用Adaptive Forms核心元件的彈性，建立吸引人的註冊體驗（表單），並運用Adobe Experience Manager的強大功能加以提供。
role: Architect, Developer, Admin, User
exl-id: 6d0f2845-bbb8-4488-a254-b69d7a6290b1
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '2123'
ht-degree: 6%

---


# 最適化Forms核心元件  {#adaptive-forms-core-components-introduction}

使用Adobe Experience Manager中的最適化Forms核心元件，您可以建立引人入勝的註冊體驗。

{{traditional-aem}}

## 核心元件 {#overview}

在Adobe Experience Manager (AEM)中，元件是用來建立頁面和表單的建置組塊。 它們為作者提供簡單且強大的方式來建立和管理內容，同時為開發人員提供建立自訂元件所需的彈性和擴充性。 這些設定可加快開發時間並降低網站與表單的維護成本、彈性且可輕鬆自訂，以符合網站與表單的特定需求。

核心元件也設計為可快速回應，並支援各種裝置，包括桌上型電腦、平板電腦和智慧型手機。 此外，也遵循最新的網頁標準與最佳實務，使其成為建立網頁內容的健全且可靠的解決方案。

整體而言，核心元件是在AEM中建立及管理Web內容的重要工具，提供強大且彈性的解決方案，有助於減少開發時間及維護成本，同時為網站訪客提供絕佳的使用者體驗。

## 最適化Forms核心元件

最適化Forms核心元件是以Adobe Experience Manager WCM核心元件為基礎所建立的30個開放原始碼且符合BEM的元件集。 這些表單是專為建立最適化Forms所設計，是適合使用者裝置、瀏覽器和熒幕大小的表單。

這些元件可用來建立優異的資料擷取和註冊體驗，方法是提供各式各樣的表單欄位選項，包括文字欄位、核取方塊、下拉式功能表等。 此外也包含驗證、條件式邏輯和回應式設計等功能，可用來建立簡單易用的表單。

此外，由於這些元件是開放原始碼，開發人員可輕鬆自訂和擴充元件，以符合其組織的特定需求。 而且，這些元件是以BEM方法建置的，可確保它們具有可擴充性和可維護性。

![最適化表單影像](assets/sample-adaptive-form.png)

## 功能 {#features}

|  |  |
|---|---|
| 生產就緒 | 最適化Forms核心元件是24個強大的WCM元件。 |
| 雲端就緒 | 可用於[AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html)。 |
| 多功能 | 這些元件代表一般概念，Forms作者可透過這些概念來組合幾乎所有版面。 |
| 可設定 | 範本層級[內容原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies)定義允許使用或不允許使用的功能。 |
| 易於取得 | 這類選件提供ARIA標籤、支援鍵盤導覽，以及熒幕閱讀器等輔助技術的文字。 |
| 佈景主題表格 | 元件實作[樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)，標籤遵循[BEM CSS慣例](https://getbem.com/)。 |
| 可自訂 | 有數種模式可讓您輕鬆自訂，從調整HTML到進階功能重複使用。 |
| 版本設定 | [版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)可確保核心元件在改善可能影響您的內容時，不會中斷您的網站。 |
| 開放來源 | 如果有出錯的地方，請協助您改善。 |

<!-- comply with [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), -->


## 優點 {#benefits}

資料擷取體驗對於潛在客戶產生和註冊至關重要，Adaptive Forms核心元件為建立針對資料擷取最佳化的表單提供強大的解決方案。 使用核心元件透過基礎元件建立這些體驗的部分原因包括：

* **[在GitHub上可供使用](https://github.com/adobe/aem-core-forms-components)**： AEM最適化Forms核心元件是開放原始碼，可在GitHub上取得，以及完整的檔案。 如此一來，開發人員就能更輕鬆瞭解元件及其運作方式，且更能協助開發工作。 [aemcomponents.dev](https://www.aemcomponents.dev/)網站也是寶貴的資源，開發人員可在此檢視運作中的元件，並存取詳細檔案。

* 樣式的&#x200B;**[BEM模型](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components)**：核心元件會依循BEM （區塊元素修飾元）模型來設定樣式，這是一種建立良好且廣泛使用的CSS組織方法。 如此一來，開發人員就能更輕鬆瞭解樣式的組織方式，以及如何修改樣式，以符合其特定需求。

* **對協力廠商程式庫沒有相依性**：核心元件的優點之一，就是它們對協力廠商JavaScript程式庫（包括JQuery和Underscore）沒有相依性。 這可讓元件更快且更輕量，以及更輕鬆地整合至現有的AEM實作。

* **著重於效能與協助工具**：核心元件建置時已考慮到效能與協助工具，這反映在它們的Google Lighthouse和Web重要分數上。 這可讓開發人員更輕鬆地建立可存取且高效能的網頁，在當今的數位格局中，這越來越重要。

* **Sites 30範本和主題中的表單元件**：核心元件支援Sites 30範本和主題中的表單元件，讓開發人員更容易在AEM中建立和自訂表格。

* **[樣式更簡單](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components)**：核心元件的樣式比基礎元件的樣式更簡單。 佈景主題建立程式類似於Sites，可從父Sites頁面繼承相同佈景主題/CSS。 此外，用於樣式化的BEM模型可讓您更容易理解及修改樣式。

* **協助工具**：最適化Forms核心元件支援協助工具標準和准則，以確保殘障人士可以使用表格，包括使用輔助技術（例如熒幕閱讀器）的使用者。

* **[版本設定](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/add-comments-annotations-versioning-adaptive-form-core-components)**：您可以建立並管理多個基於核心元件的最適化Forms版本、透過註解參與合作討論，以及將註解附加至特定表單元件，藉此增強整體表單建立體驗。

## 可用元件：依元件型別的劃分

目前版本的AEM Forms有下列核心元件、[基礎元件](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/create-an-adaptive-form-on-forms-cs/introduction-forms-authoring#component-toolbar)和[表單區塊元件(Edge Delivery Services)](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/edge-delivery/build-forms/forms-references/form-components)。

| 元件 | Foundation 元件 | 核心元件 | 表單區塊元件 | 其他資訊 |
|------------|:---------------------:|:---------------:|:---------------------:|-----------------------|
| Adobe Sign 區塊 | ✔️ | | | [Adobe Sign整合](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/integrate/services/adobe-sign-integration-adaptive-forms#adobe-acrobat-sign-for-government)僅適用於Foundation元件。 |
| 折疊面板 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/accordion.md)</span> | | 對於Foundation元件，您可以在[面板元件屬性](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout)中設定收合式選單配置。 |
| 最適化表單片段 | ✔️ | ✔️ | | 對於基礎元件，您可以從Assets瀏覽器[新增片段](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/adaptive-forms-basic-authoring/adaptive-form-fragments#insert-a-fragment-in-an-adaptive-form)。 |
| 自適應表單 reCAPTCHA | ✔️ | ✔️ | ✔️ | 對於基礎元件，請使用Captcha元件將Google reCaptcha新增至表單](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms#google-reCAPTCHA)。[ |
| 按鈕 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/button.md)</span> | ✔️ | |
| 圖表 | ✔️ | | | |
| 核取方塊 | ✔️ | ✔️ | | |
| 核取方塊群組 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/checkbox-group.md)</span> | ✔️ | 對於基礎元件，使用核取方塊元件以新增多個核取方塊 |
| 資料輸入欄位 | ✔️ | | | 對於核心元件，請使用[日期選擇器](/help/adaptive-forms/components/date-picker.md)元件。 您也可以新增個別的[文字方塊](/help/adaptive-forms/components/text-box.md)或[數值方塊](/help/adaptive-forms/components/numeric-box.md)元件，以擷取日、月和年。 |
| 日期挑選器 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/date-picker.md)</span> | ✔️ | |
| 下拉式清單 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/drop-down-list.md)</span> | ✔️ | |
| 電子郵件 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/email.md)</span> | ✔️ | |
| 檔案附件 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/file-attachment.md)</span> | ✔️ | |
| 檔案附件清單 | ✔️ | | | |
| 頁尾 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/footer.md)</span> | ✔️ | |
| 註腳預留位置 | ✔️ | | | |
| 表單容器 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/form-container.md)</span> | ✔️ | 若為基礎元件，請使用[根面板元件](https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/forms/create-first-af/configure-root-panel)。 |
| 表單標題 | ✔️ | ✔️ | | 對於基礎元件，請使用標題元件。 |
| hCaptcha | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/hcaptcha.md)</span> |  | 對於Foundation元件，您可以[將最適化表單與hCaptcha](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile.html)連線，以用於Foundation元件為基礎的表單。 |
| 頁首 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/header.md)</span> | ✔️ | |
| 水準索引標籤 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/horizontal-tabs.md)</span> | | 對於基礎元件，您可以在面板元件屬性中設定頂端（水準標籤）配置[標籤](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout)。 |
| 影像 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/image.md)</span> | ✔️ | |
| 下一個按鈕 | ✔️ | ✔️ | | 使用[精靈元件](/help/adaptive-forms/components/wizard.md)，讓下一個和上一個按鈕在多個面板之間移動。 |
| 數值方塊 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/numeric-box.md)</span> | ✔️ | |
| 數值步進器 | ✔️ | | | |
| 面板 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/panel.md)</span> | ✔️ | |
| 電話/電話 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/phone.md)</span> | ✔️ | |
| 前一個按鈕 | ✔️ | ✔️ | | 使用[精靈元件](/help/adaptive-forms/components/wizard.md)，讓下一個和上一個按鈕在多個面板之間移動。 |
| 選項按鈕群組 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/radio-button.md)</span> | ✔️ | |
| 重設按鈕 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/reset-button.md)</span> | ✔️ | |
| 檢閱 |  | <span style="color:blue">[✔️](/help/adaptive-forms/components/reset-button.md)</span> |  | |
| 草寫簽名 | ✔️ | | | |
| 分隔符號 | ✔️ | | | 使用WCM [分隔符號](/help/components/separator.md)元件 |
| 提交按鈕 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/submit-button.md)</span> | ✔️ | |
| 摘要步驟 | ✔️ | | | |
| 切換 | ✔️ | <span style="color:blue"> [✔️](/help/adaptive-forms/components/adaptive-form-switch.md) | | |
| 表格 | ✔️ | | | |
| 條款與條件 | ✔️ | ✔️ | | |
| 文字 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/text.md)</span> | ✔️ | |
| 文字方塊 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/text-box.md)</span> | ✔️ | |
| Turnstile驗證碼 | ✔️ | | | [Turnstile驗證碼](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile)僅適用於Foundation元件。 |
| 垂直標籤 | ✔️ | ✔️ | | 對於基礎元件，您可以在面板元件屬性中設定左側[標籤（垂直標籤）配置](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout) |
| 精靈 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/wizard.md)</span> | ✔️ | 對於Foundation元件，您可以在面板元件屬性中設定[精靈配置](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout) |

<!--| Password Box | ✔️ | ✔️| ✔️ | |
| Image Choice | ✔️ | | | |
-->


>[!NOTE]
>
>
> * 除了上述元件之外，Forms區塊還支援所有有效的[HTML5輸入型別](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#input_types)和[文字區域](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)作為元件。
> * 需要上方未列出的元件嗎？ 請從您的官方地址寄送電子郵件至aem-forms-ea@adobe.com以提出要求。


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

基於核心元件的最適化Forms的編輯器類似於您已用於建立AEM Sites頁面的編輯器。 以下是您獲得的內容：


* **熟悉的UI元素和設定**：設定表單元件的屬性時，您會看到屬性對話方塊，就像您對WCM核心元件使用的對話方塊一樣。 這可讓您更快找到所需的選項。 如同WCM核心元件，對於表單元件，「屬性」對話方塊會顯示在編輯器的中央，以清楚的索引標籤分隔基本和進階選項、說明文字及協助工具資訊 — 所有內容都以索引標籤格式顯示，以方便瀏覽。

* **[規則編輯器](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/rule-editor-core-components)**：您可以新增邏輯和動態功能至表單，而不需要撰寫程式碼。 您可以使用內建規則編輯器來：
   * 根據使用者選擇顯示或隱藏欄位
   * 啟用或停用物件
   * 設定物件的值
   * 執行計算
   * 設定物件的屬性
   * 驗證資料輸入
   * 叫用服務（呼叫外部功能）
   * 使用內建函式（常見工作的預先定義函式）
   * 使用自訂函式（您針對特定需求自己的程式碼）
   * 驗證欄位和面板（確保資料符合要求）
   * 驗證物件的值
   * 執行函式以計算物件的值
   * 啟動表單資料模型(FDM)服務並執行作業
   * 動態新增樣式（根據條件變更外觀）
   * 建立其他規則（鏈結動作和邏輯）
   * 及更多內容！

  規則編輯器沒有程式碼編輯器。 您可以使用[自訂函式](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-and-use-custom-functions)，針對特定需求將您自己的程式碼新增至規則編輯器。



* **預先填寫表單**：您可以在使用者開啟表單時，自動將現有資料填入表單中的特定欄位。 如此一來，使用者就無需手動輸入可能已有可用的資訊，進而節省時間與精力。 核心元件編輯器提供OOTB預填服務，可在表單資料模型的協助下填入表單欄位。 您也可以為更複雜的案例建立自訂預填服務。

* **[記錄檔案(DoR)](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components)**：記錄檔案(DoR)是指透過表單提交的資料的正式、可列印表示法。 它可做為使用者輸入資訊的永久記錄，以使用者友善的格式(通常是PDF檔案)提供提交資料的快照。 您可以使用編輯器輕鬆設定自訂範本，或使用OOTB範本產生DoR。

* **[表單資料模型](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/using-form-data-model)**：最適化Forms資料模型(FDM)可作為最適化Forms與資料來源之間的橋樑。 它基本上定義您的表單收集和互動之資料的結構和組織。 您可以使用編輯器輕鬆地將表單與Forms資料模型(FDM)連線。

* **[表單提交](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Adaptive%20Form%20Submit%20Action&text=Adobe%20recommends%20using%20Core%20Components,to%20create%20standalone%20Adaptive%20Forms.&text=A%20Submit%20Action%20lets%20you，button%20on%20an%20Adaptive%20Form)**：表單提交是指使用者填寫並傳送表單的程式。 這會觸發在表單設定中定義的一系列動作，最終導致儲存或處理提交的資料。 最適化Forms編輯器提供多種設定表單提交的選項。 常見的提交動作包括：

   * [傳送電子郵件](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Adaptive%20Form%20Submit%20Action&text=Adobe%20recommends%20using%20Core%20Components,to%20create%20standalone%20Adaptive%20Forms.&text=A%20Submit%20Action%20lets%20you，button%20on%20an%20Adaptive%20Form。)
   * [叫用Power Automate流程](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/integrate/services/forms-microsoft-power-automate-integration)
   * [提交至SharePoint](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-action-sharepoint)
   * [叫用Workfront Fusion](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Invoke%20a%20Workfront%20Fusion)
   * [使用表單資料模型(FDM)提交](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/using-form-data-model)
   * [提交至Azure Blob儲存體](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Submit%20to%20Azure%20Blob%20Storage)
   * [提交至 REST 端點](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-action-restpoint)
   * [送出至OneDrive](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=to%20REST%20endpoint-,Submit%20to%20OneDrive,-Invoke%20an%20AEM)
   * [叫用AEM工作流程](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Invoke%20an%20AEM%20Workflow)


* [Sites頁面編輯器中的自適應Forms核心元件](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page)：您可以在AEM頁面編輯器和AEM體驗片段中啟用並使用自適應Forms核心元件，以便在建置Sites頁面的同時直接建立資料擷取體驗。

  >[!VIDEO](https://video.tv.adobe.com/v/3419284?quality=12&learn=on)


<!-- 
* **Preview Forms**: You can use the editor to  simulates how the form would appear on various devices like desktops, tablets, and smartphones.
-->



## 啟用最適化Forms核心元件

在 AEM Forms as a Cloud Service 上啟用調適型表單心元件，可讓您使用 AEM Forms as a Cloud Service 實例開始建立、發佈和提供以核心元件為主的調適型表單和 Headless 表單至多個管道。 如需啟用最適化表單核心元件的詳細指示，請參閱[在AEM Forms as a Cloud Service和本機開發環境中啟用最適化Forms核心元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html)。

最適化Forms核心元件具有下列需求。

| AEM 版本 | AEM Forms附加元件 | 最適化Forms核心元件 |
|---|---|---|
| AEM as a Cloud Service | Forms - 數位註冊 | [版本2.0.10](version.md)+ |
| AEM 6.5 | Forms附加元件 | [版本1.1.12](version.md)+ |

如果您的AEM Cloud Service SDK版本比2023.02.0舊，[請確定已在您的環境中啟用`prerelease`標幟](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=zh-Hant#new-features)，因為Adaptive Forms核心元件是2023.02.0版之前預先租用的組成部分。


## 建立以核心元件為基礎的最適化表單

您可以在AEM Forms as a Cloud Service或AEM 6.5 Forms環境中執行下列動作：

| 動作 | AEM Forms版本 |
|--------|------------------|
| 建立獨立的最適化表單 | [AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html) |
| 在AEM Sites頁面中建立最適化表單 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=en#create-an-adaptive-form-in-sites-editor-or-experience-fragment)，[AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#create-an-adaptive-form-in-sites-editor-or-experience-fragment) |
| 在AEM體驗片段中建立最適化表單 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=en#create-an-adaptive-form-in-experience-fragment)，[AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#create-an-adaptive-form-in-experience-fragment) |
| 將最適化表單轉換為體驗片段 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=en#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment)，[AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment) |





<!-- >, such as  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), to ensure that forms can be used by people with disabilities, including those using assistive technologies such as screen readers.

*   **Alignment with AEM Sites**: The Core Components are designed to be more aligned with AEM Sites, making it easier for Sites users to adopt and use them without having to learn anything new. The components use the same front-end pipeline as Sites, making it easier to style and modify their appearance. 

<!-- Additionally, the following points further illustrate this alignment:

    *   **Authoring experience inline with Page editor**: The Core Components have an authoring experience that is inline with the Sites editor, with dialogs and other experiences similar to the Page editor. This makes it easier for Sites users to create and manage forms within the familiar context of the Sites editor.

    *   **Inline form editing in Sites editor**: The Core Components allow  inline form editing within the Sites editor, avoiding the need to switch back and forth between editors. This streamlines the authoring experience and makes it easier to create and manage forms.

    *   **Inheriting Sites features in Forms**: Forms authored within a Sites page inherit the same features as Sites. This provides a seamless and integrated experience for creating and managing forms within the context of AEM Sites 
    
    <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->

## 另請參閱 {#see-also}

{{see-also}}
