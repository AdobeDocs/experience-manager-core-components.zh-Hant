---
title: 最適化Forms核心元件 — 精靈
description: 使用或自訂最適化Forms精靈核心元件。
role: Architect, Developer, Admin, User
exl-id: fd785cd2-5ed6-4efb-997f-ce9056ed113d
source-git-commit: 0026734a2e43c51c7f5af2b37492d61e8f779ac7
workflow-type: tm+mt
source-wordcount: '1866'
ht-degree: 1%

---

# 精靈 {#wizard-adaptive-forms-core-component}

最適化表單中的精靈版面配置是指分成多個步驟或頁面，使用者一次移動一個步驟的表單。 此版面稱為「精靈」，因為它會逐步引導使用者完成表單。

精靈的每個步驟通常包含一組相關的表單欄位和導覽機制，例如「下一步」和「上一步」按鈕，以便在步驟之間移動。 完成目前步驟並填寫完所有必填欄位後，使用者才能繼續進行下一個步驟。

精靈版面對於含有大量欄位或需要收集資訊的表單非常有用，因為它會將表單劃分為更小、更易於管理的區塊。 此外，也可協助使用者一次只專注於一組欄位，減少填寫表單的麻煩。

但是，它也可能會增加表單的複雜性，因為使用者必須瀏覽幾個頁面才能完成表單。 因此，在決定使用精靈版面配置之前，必須評估表單需求和使用者需求。

您可以在調適型表單中使用精靈版面配置核心元件來建立精靈版面。


**範例**

![](/help/adaptive-forms/assets/wizard.png)

## 使用狀況 {#reasons-to-use-wizard-in-an-adaptive-form}

在最適化表單中使用精靈版面配置有幾個好處：

* **簡單性**：將表單劃分為多個步驟可以讓使用者更容易理解和完成，因為他們可以一次專注在一組欄位上。

* **組織**：精靈版面配置可協助您依主題或用途組織表單，也可以將相關欄位分組在一起，讓表單填寫流程更加邏輯化和有效率。

* **驗證**：精靈版面配置可逐步驗證，這可幫助使用者隨時識別和更正錯誤，而不是等到表單結束。

* **進度指示器**：精靈版面配置可顯示表單進度，有助於使用者瞭解還有多少表單要完成。

* **長表單**：如果表單中有許多欄位，使用者一次看到這些欄位可能會感到吃力，因此將它們分成更小、更易於管理的區塊，會讓表單不那麼令人生畏。

* **避免放棄**：精靈版面配置也有助於減少表單放棄率，因為使用者如果可以檢視進度並瞭解還有多少工作要做，就更有可能完成表單。

* **行動體驗**：精靈版面配置也有利於在行動裝置上存取的表單，因為它允許更小的頁面，這些頁面載入更快，也更容易導覽。

整體而言，精靈版面配置可讓使用者更容易管理且更有效率地填寫表單，但在決定使用此型別的版面配置之前，請務必考量表單的複雜度以及使用者的需求。

## 版本和相容性 {#version-and-compatibility}

最適化Forms精靈配置核心元件於2023年2月發行，是核心元件2.0.4的一部分。下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service  |
| — | --- |
| v1 | 相容於<br>[版本2.0.4](/help/versions.md) 及更新版本 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/versions.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在的技術檔案中取得最適化Forms標題核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/wizard/v1/wizard). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的精靈體驗。 您也可以輕鬆定義精靈選項，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/wizard-basic.png)

* **名稱**  — 在表單和規則編輯器中，您可以使用表單元件的唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **標題**  — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。

* **隱藏標題**  — 選取可隱藏元件標題的選項。

* **將資料換行到物件中**  — 選擇「在物件中繞排資料」，將精靈的欄位資料放在JSON物件中。 如果未選擇，則提交資料JSON的精靈欄位會採用平面結構。

* **版面**  — 您可以為精靈設定固定版面（簡單）或彈性版面（回應式格線）。 「簡單」版面可讓一切固定在原處，而「回應式格線」則可讓您調整元件位置，以符合需求。 例如，使用回應式格線在單一列中對齊表單中的「名字」、「中間名」和「姓氏」。

* **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。

* **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。

* **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 重複精靈索引標籤 {#repeat-wizard-tab}

![重複精靈](/help/adaptive-forms/assets/wizard-repeat.png)

您可以使用重複性選項來複製精靈及其子元件、定義最小和最大重複計數，以及簡化表單中類似區段的複製。 與精靈元件互動並存取其設定時，會顯示下列選項：

* **讓精靈可重複**：一種切換功能，可讓使用者啟用或停用重複測量功能。
* **最小重複次數**：建立精靈面板可重複的最小次數。 值為零表示「精靈」面板不會重複；預設值為零。
* **最大重複次數**：設定精靈面板可重複的最大次數。 預設情況下，此值為無限制。

若要有效管理精靈中的可重複區段，請依照以下提供的步驟操作： [建立具有可重複區段的表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html) 文章。

### 說明標籤 {#help-tab}

![說明標籤](/help/adaptive-forms/assets/wizard-helpcontent.png)

* **簡短說明**  — 簡短說明是簡短文字說明，提供有關特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用 **一律顯示簡短說明** 選項來在元件下方顯示它。

* **一律顯示簡短說明**  — 啟用選項以在元件下方顯示簡短說明。

* **說明文字**  — 說明文字是指為協助使用者正確填寫表單欄位而提供的其他資訊或指引。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。


### 協助工具標籤 {#accessibility}

![協助工具索引標籤](/help/adaptive-forms/assets/wizard-accessibility.png)

* **熒幕助讀程式的文字**  — 熒幕助讀程式文字是指視力受損者使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。

* **熒幕助讀程式宣告的HTML角色** -HTML角色是一種屬性，用來指定HTML元素對輔助技術（例如熒幕閱讀程式）的用途。 角色屬性可用來提供元素的其他上下文和語意意義，讓熒幕朗讀程式更容易向使用者解譯和宣告內容。 例如，在AEM Forms中，表單欄位的標籤可能會具有「label」角色，而其輸入欄位的角色可能會具有「textbox」。 這可協助熒幕助讀程式瞭解標籤和輸入欄位之間的關係，並向使用者正確宣告。


## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本建立者控制物件的預設顯示方式。 針對最適化Forms精靈元件，您可以設定下列專案：

* 表單建立者可以在Adaptive Forms編輯器中新增到精靈的核心元件
* 樣式（CSS類別）的簡單名稱，可在最適化Forms編輯器中的精靈元件屬性對話方塊中套用。

這有助於讓建立和自訂表單的流程更直接有效。

### 允許的元件標籤 {#allowed-components-tab}

此 **允許的元件** 索引標籤可讓範本編輯器設定元件，這些元件可在最適化Forms編輯器的精靈元件中新增為面板的專案。

### 樣式索引標籤 {#styles-tab}

「設計」對話方塊可用來定義和管理元件的CSS樣式。 最適化Forms精靈核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

**預設CSS類別**：您可以為精靈元件提供預設的CSS類別。

**允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

>[!MORELIKETHIS]
>
>* [折疊式面板](/help/adaptive-forms/components/accordion.md)
>* [按鈕](/help/adaptive-forms/components/button.md)
>* [核取方塊群組](/help/adaptive-forms/components/checkbox-group.md)
>* [日期挑選器](/help/adaptive-forms/components/date-picker.md)
>* [下拉式清單](/help/adaptive-forms/components/drop-down.md)
>* [電子郵件輸入](/help/adaptive-forms/components/email-input.md)
>* [來自容器](/help/adaptive-forms/components/form-container.md)
>* [檔案附件](/help/adaptive-forms/components/file-attachment.md)
>* [頁尾](/help/adaptive-forms/components/footer.md)
>* [頁首](/help/adaptive-forms/components/header.md)
>* [水準索引標籤](/help/adaptive-forms/components/horizontal-tabs.md)
>* [影像](/help/adaptive-forms/components/image.md)
>* [數字輸入](/help/adaptive-forms/components/number-input.md)
>* [面板容器](/help/adaptive-forms/components/panel-container.md)
>* [選項按鈕](/help/adaptive-forms/components/radio-button.md)
>* [重設按鈕](/help/adaptive-forms/components/reset-button.md)
>* [提交按鈕](/help/adaptive-forms/components/submit-button.md)
>* [電話輸入](/help/adaptive-forms/components/telephone-input.md)
>* [文字輸入](/help/adaptive-forms/components/text-input.md)
>* [文字](/help/adaptive-forms/components/text.md)
>* [標題](/help/adaptive-forms/components/title.md)

## 另請參閱 {#see-also}

{{see-also}}
