---
title: 最適化Forms核心元件 — 面板容器
description: 使用或自訂Adaptive Forms面板容器核心元件。
role: Architect, Developer, Admin, User
exl-id: 104836fe-8325-47de-978d-1ff2d6a9dd15
source-git-commit: 37ac7d3a9ae8c88d4c9be8129cfbd1eb4a7cccd1
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 3%

---

# 面板容器 {#panel-container-adaptive-forms-core-component}

在最適化表單中，面板是容器元素，可用來將相關的表單元素群組在一起。 它可讓您以邏輯和有意義的方式分組和組織不同的表單元素。 這有助於改善表單的整體結構和可讀性，讓使用者更容易理解和導覽。

面板也可用來建立可摺疊的區段，這對於隱藏複雜或不常使用的表單欄位很有用，讓表單保持簡單且易於使用。 它也可讓您包含其他元件，例如文字、核取方塊、按鈕等。

它也可用來設定不同的規則型動作，例如提交表單、開啟網站、顯示/隱藏元件，或新增面板的執行個體。

**範例**

![](/help/adaptive-forms/assets/panel-container.png)

## 使用狀況 {#reasons-to-use-panel-container}

在表單中使用面板有幾個理由，包括：

- **組織表單元素**：面板可用來將相關的表單元素分組在一起，讓使用者更容易理解和導覽表單。

- **改善表單結構**：將表單元素分組為面板，可改善表單的整體結構和可讀性，使其更易於理解。

- **建立可摺疊區段**：面板可用來建立可摺疊的區段，這對於隱藏複雜或不太常用的表單欄位很有用，讓表單保持簡單且易於使用。

- **提升可用性**：使用面板來組織表單元素，可讓表單更方便使用者使用，進而提高完成率。

## 版本和相容性 {#version-and-compatibility}

最適化Forms面板容器核心元件於2023年2月發行，是核心元件2.0.4的一部分。下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service  |
| — | --- |
| v1 | 相容於<br>[版本2.0.4](/help/versions.md) 及更新版本 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/versions.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在的技術檔案中取得最適化Forms面板容器核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的面板容器體驗。 您也可以輕鬆定義面板容器選項，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/basic-panel.png)

- **名稱**  — 在表單和規則編輯器中，您可以使用表單元件的唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

- **標題**  — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。

- **隱藏標題**  — 選取可隱藏元件標題的選項。

- **在表單提交時將子元件的資料分組（將資料包裝在物件中）**  — 選取選項時，其子元件的資料會巢狀內嵌於父元件的JSON物件中。 但是，如果未選取選項，則提交的JSON資料會具有平坦結構，沒有父元件的物件。 例如：

   - 選取選項時，子元件（例如街道、城市和郵遞區號）的資料會巢狀內嵌於父元件（位址）中，做為JSON物件。 這樣會建立階層式結構，而資料會整理在父元件下。

     提交資料的結構：

     ```JSON
     { "Address":
     
     { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     
     }
     ```

   - 未選取選項時，提交的JSON資料會具有不含父系元件（位址）物件的平面結構。 所有資料都位於相同層級，沒有任何階層式組織。


     提交資料的結構：

     ```JSON
        { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     ```

- **版面**  — 您可以為精靈設定固定版面（簡單）或彈性版面（回應式格線）。 「簡單」版面可讓一切固定在原處，而「回應式格線」則可讓您調整元件位置，以符合需求。 例如，使用回應式格線在單一列中對齊表單中的「名字」、「中間名」和「姓氏」。

- **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。
- **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。
- **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 重複面板標籤 {#repeat-panel}

![重複標籤](/help/adaptive-forms/assets/repeat-panel.png)

您可以使用重複性選項來複製面板容器及其子元件、定義最小和最大重複計數，以及簡化表單中類似區段的複製。 與面板容器元件互動並存取其設定時，會顯示下列選項：

- **讓精靈可重複**：一種切換功能，可讓使用者啟用或停用重複測量功能。
- **最小重複次數**：建立面板容器可重複的最小次數。 值為零表示「精靈」面板不會重複；預設值為零。
- **最大重複次數**：設定面板容器可重複的最大次數。 預設情況下，此值為無限制。

若要有效管理面板容器內的可重複區段，請依照 [建立具有可重複區段的表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html) 文章。

### 說明內容標籤 {#help-content}

![說明內容標籤](/help/adaptive-forms/assets/helpcontent-panel.png)


- **簡短說明**  — 簡短說明是簡短文字說明，提供有關特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用 **一律顯示簡短說明** 選項來在元件下方顯示它。

- **一律顯示簡短說明**  — 啟用選項以在元件下方顯示簡短說明。

- **說明文字**  — 說明文字是指為協助使用者正確填寫表單欄位而提供的其他資訊或指引。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。

### 協助工具標籤 {#accessibility}

![協助工具標籤](/help/adaptive-forms/assets/accessibilty-panel.png)


- **熒幕助讀程式的文字**  — 熒幕助讀程式文字是指視力受損者使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。

- **熒幕助讀程式宣告的HTML角色** -HTML角色是一種屬性，用來指定HTML元素對輔助技術（例如熒幕閱讀程式）的用途。 角色屬性可用來提供元素的其他上下文和語意意義，讓熒幕朗讀程式更容易向使用者解譯和宣告內容。 例如，在AEM Forms中，表單欄位的標籤可能會具有「label」角色，而其輸入欄位的角色可能會具有「textbox」。 這可協助熒幕助讀程式瞭解標籤和輸入欄位之間的關係，並向使用者正確宣告。

## 相關文章 {#related-articles}

- [折疊式面板](/help/adaptive-forms/components/accordion.md)
- [按鈕](/help/adaptive-forms/components/button.md)
- [核取方塊群組](/help/adaptive-forms/components/checkbox-group.md)
- [日期挑選器](/help/adaptive-forms/components/date-picker.md)
- [下拉式清單](/help/adaptive-forms/components/drop-down.md)
- [電子郵件輸入](/help/adaptive-forms/components/email-input.md)
- [來自容器](/help/adaptive-forms/components/form-container.md)
- [檔案附件](/help/adaptive-forms/components/file-attachment.md)
- [頁尾](/help/adaptive-forms/components/footer.md)
- [頁首](/help/adaptive-forms/components/header.md)
- [水準索引標籤](/help/adaptive-forms/components/horizontal-tabs.md)
- [影像](/help/adaptive-forms/components/image.md)
- [數字輸入](/help/adaptive-forms/components/number-input.md)
- [選項按鈕](/help/adaptive-forms/components/radio-button.md)
- [重設按鈕](/help/adaptive-forms/components/reset-button.md)
- [提交按鈕](/help/adaptive-forms/components/submit-button.md)
- [電話輸入](/help/adaptive-forms/components/telephone-input.md)
- [文字輸入](/help/adaptive-forms/components/text-input.md)
- [文字](/help/adaptive-forms/components/text.md)
- [標題](/help/adaptive-forms/components/title.md)
- [精靈](/help/adaptive-forms/components/wizard.md)


## 另請參閱 {#see-also}

- [建立AEM最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)
- [將AEM最適化表單新增至AEM Sites頁面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)
- [將主題套用至AEM最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html)
- [將元件新增至AEM最適化表單](/help/adaptive-forms/introduction.md#adaptive-forms-core-components-components)
- [在AEM最適化表單中使用reCAPTCHA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms.html)
- [產生AEM最適化表單的PDF版本(DoR)](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components.html)
- [翻譯AEM最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-aem-translation-workflow-to-localize-adaptive-forms-core-components.html)
- [為最適化表單啟用Adobe Analytics以追蹤表單使用情況](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/services/enable-adobe-analytics-adaptive-form-using-experience-cloud-setup-automation.html)
- [將最適化表單連線至Microsoft SharePoint](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#create-sharepoint-configuration)
- [將最適化表單連線至Microsoft Power Automate](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#microsoft-power-automate)
- [將最適化表單連線至Microsoft OneDrive](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-onedrive)
- [將最適化表單連線至Microsoft Azure Blob儲存體](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-azure-blob-storage)
- [將最適化表單連線至Salesforce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/oauth2-client-credentials-flow-for-server-to-server-integration.html)
- [在AEM最適化表單中使用Adobe Sign](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/use-adobe-sign/working-with-adobe-sign.html)
- [為最適化表單新增地區設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components.html)
- [傳送最適化表單資料至資料庫](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/data-integration.html)
- [傳送最適化表單資料至REST端點](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-rest-endpoint)
- [傳送最適化表單資料至AEM Workflow](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#invoke-an-aem-workflow)
- [使用Forms入口網站列出AEM網站上的AEM Adaptive Forms](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-forms-portal.html)

