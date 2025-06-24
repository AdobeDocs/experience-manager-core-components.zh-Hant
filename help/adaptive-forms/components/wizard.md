---
title: 最適化Forms核心元件 — 精靈
description: 使用或自訂最適化Forms精靈核心元件。
role: Architect, Developer, Admin, User
exl-id: fd785cd2-5ed6-4efb-997f-ce9056ed113d
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '2186'
ht-degree: 0%

---


# 精靈元件{#wizard-adaptive-forms-core-component}

最適化表單中的精靈版面配置是指分成多個步驟或頁面，使用者一次移動一個步驟的表單。 此版面稱為「精靈」，因為它會逐步引導使用者完成表單。

精靈的每個步驟通常包含一組相關的表單欄位和導覽機制，例如「下一步」和「上一步」按鈕，以便在步驟之間移動。 完成目前步驟並填寫完所有必填欄位後，使用者才能繼續進行下一個步驟。

精靈版面對於含有大量欄位或需要收集資訊的表單非常有用，因為它會將表單劃分為更小、更易於管理的區塊。 此外，也可協助使用者一次只專注於一組欄位，減少填寫表單的麻煩。

但是，它也可能會增加表單的複雜性，因為使用者必須瀏覽幾個頁面才能完成表單。 因此，在決定使用精靈版面配置之前，必須評估表單需求和使用者需求。
您可以在調適型表單中使用精靈版面配置核心元件來建立精靈版面。

{{traditional-aem}}

**範例**

![範例](/help/adaptive-forms/assets/wizard.png)

## 使用情況 {#reasons-to-use-wizard-in-an-adaptive-form}

在最適化表單中使用精靈版面配置有幾個好處：

- **簡單性**：將表單劃分為多個步驟可以讓使用者更容易理解和完成，因為他們一次可以集中處理一組欄位。

- **組織**：精靈版面配置可協助您依主題或用途組織表單，也可以將相關欄位群組在一起，讓表單填寫程式更合乎邏輯且更有效率。

- **驗證**：精靈版面配置允許逐步驗證，這可以協助使用者識別並更正錯誤，而不是等到表單結束。

- **進度指示器**：精靈配置可以顯示表單的進度，這可以幫助使用者瞭解還有多少表單要完成。

- **長表單**：如果表單中有許多欄位，使用者可能無法一次看到所有欄位，因此將它們分成更小、更易於管理的區塊，可讓表單不那麼令人生畏。

- **避免放棄**：精靈版面配置也有助於減少表單放棄，因為使用者如果能夠看到進度並瞭解還有多少工作要做，就更有可能完成表單。

- **行動體驗**：精靈版面配置也有利於在行動裝置上存取的表單，因為它可讓較小的頁面更快載入且更容易導覽。

整體而言，精靈版面配置可讓使用者更容易管理且更有效率地填寫表單，但在決定使用此型別的版面配置之前，請務必考量表單的複雜度以及使用者的需求。

## 版本和相容性 {#version-and-compatibility}

最適化Forms精靈配置核心元件於2023年2月發行，是核心元件2.0.4的一部分。下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service |
| — | — |
| v1 | 與<br>[版本2.0.4](/help/adaptive-forms/version.md)和更新版本相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/wizard/v1/wizard)上的技術檔案中取得最適化Forms精靈核心元件的最新資訊。 如需開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的精靈體驗。 您也可以輕鬆定義精靈選項，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/wizard-basic.png)

- **名稱** — 您可以在表單和規則編輯器中輕鬆識別具有唯一名稱的表單元件，但名稱不得包含空格或特殊字元。

- **標題** — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。

- **隱藏標題** — 選取隱藏元件標題的選項。

- **在表單提交時將子元件的資料分組（將資料包裝在物件中）** — 選取選項時，其子元件的資料會巢狀內嵌在父元件的JSON物件中。 但是，如果未選取選項，則提交的JSON資料會具有平坦結構，沒有父元件的物件。 例如：

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

<!--   **Wrap data in an object** - Choose "Wrap data in an object" to put the field data from the Wizard inside a JSON object. If not chosen, the submit data JSON has a flat structure for the Wizard's fields.

-   **Layout** - You can have either a fixed layout (Simple) or a flexible layout (Responsive Grid) for your wizard. The Simple layout keeps everything fixed in the place, while the Responsive Grid allows you to adjust the position of components to suit your needs. For example, use Responsive Grid to align "First Name", "Middle Name" and "Last Name" in a form in a single row.  -->

- **繫結參考** — 繫結參考是儲存在外部資料來源中，並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。

- **隱藏元件** — 選取選項，以隱藏表單中的元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。

- **停用元件** — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

- **唯讀** — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 重複精靈索引標籤 {#repeat-wizard-tab}

![重複精靈](/help/adaptive-forms/assets/wizard-repeat.png)

您可以使用重複性選項來複製精靈及其子元件、定義最小和最大重複計數，以及簡化表單中類似區段的複製。 與精靈元件互動並存取其設定時，會顯示下列選項：

- **讓精靈可重複**：讓使用者啟用或停用重複功能切換功能。
- **最小重複次數**：建立精靈面板可重複的最小次數。 值為零表示「精靈」面板不會重複；預設值為零。
- **最大重複次數**：設定精靈面板可重複的最大次數。 預設情況下，此值為無限制。

若要有效管理精靈中的可重複區段，請依照[建立包含可重複區段的表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html)文章中提供的步驟操作。

### 專案標籤 {#items-tab}

![專案索引標籤](/help/adaptive-forms/assets/wizard_itemstab.png)

此選項可讓您按一下「新增」按鈕來新增最適化表單元件，當精靈以編輯模式新增時，預設會顯示「新增」按鈕。

### 說明標籤 {#help-tab}

![說明標籤](/help/adaptive-forms/assets/wizard_helptab.png)

- **簡短說明** — 簡短說明是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用&#x200B;**永遠顯示簡短描述**&#x200B;選項，以在元件下方顯示它。

- **永遠顯示簡短描述** — 啟用選項以在元件下方顯示簡短描述。

- **說明文字** — 說明文字是指提供給使用者的其他資訊或指引，以協助使用者正確填寫表單欄位。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。


### 協助工具標籤 {#accessibility}

![協助工具標籤](/help/adaptive-forms/assets/wizard_accessibiltytab.png)

- **熒幕助讀程式文字** — 熒幕助讀程式文字是指視力不佳人士使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。
   - **自訂文字**：選取此選項即可使用ARIA協助工具標籤的自訂文字。 選取此選項會顯示「自訂文字」對話方塊。 您可以在「自訂文字」對話方塊中新增相關資訊。
   - **說明**：選取此選項即可使用ARIA協助工具標籤的說明。
   - **標題**：選取此選項即可使用ARIA協助工具標籤的標題。
   - **名稱**：選取此選項即可使用ARIA協助工具標籤的名稱。
   - **無**：如果您不想新增ARIA協助工具標籤，請選取此選項。

- **熒幕朗讀程式要宣告的HTML角色** - HTML角色是用來指定HTML元素用途的屬性，以輔助技術（例如熒幕朗讀程式）使用。 角色屬性可用來提供元素的其他上下文和語意意義，讓熒幕朗讀程式更容易向使用者解譯和宣告內容。 例如，在AEM Forms中，表單欄位的標籤可能會具有「label」角色，而其輸入欄位的角色可能會具有「textbox」。 這可協助熒幕助讀程式瞭解標籤和輸入欄位之間的關係，並向使用者正確宣告。


## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本建立者控制物件的預設顯示方式。 針對最適化Forms精靈元件，您可以設定下列專案：

- 表單建立者可以在Adaptive Forms編輯器中新增到精靈的核心元件
- 樣式（CSS類別）的簡單名稱，可在最適化Forms編輯器中的精靈元件屬性對話方塊中套用。

這有助於讓建立和自訂表單的流程更直接有效。

### 允許的元件標籤 {#allowed-components-tab}

![允許的元件索引標籤](/help/adaptive-forms/assets/tabs-allowed-component.png)

**允許的元件**&#x200B;索引標籤允許範本編輯器設定元件，這些元件可以在最適化Forms編輯器的精靈元件中新增為面板。

### 樣式索引標籤 {#styles-tab}

「設計」對話方塊可用來定義和管理元件的CSS樣式。 最適化Forms精靈核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![樣式索引標籤](/help/adaptive-forms/assets/tabs-styles-tab.png)

- **預設CSS類別**：您可以為最適化Forms精靈核心元件提供預設CSS類別。

- **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至屬性對話方塊，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性索引標籤

![自訂屬性索引標籤](/help/adaptive-forms/assets/tabs-custom-properties.png)

自訂屬性可讓您使用表單範本，將自訂屬性（索引鍵/值組）與最適化表單核心元件建立關聯。 自訂屬性會反映在元件Headless轉譯的properties區段中。 它可讓您建立根據自訂屬性值調整的動態表單行為。 例如，開發人員可以為行動、桌上型電腦或Web平台設計各種無頭Forms元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供一個名稱來識別自訂屬性群組。 您可以新增、刪除或重新排列多個自訂屬性群組。 新增自訂屬性群組後，您可以看到下列選項：

   - **索引鍵 — 值配對**：您可以按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，以新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳以重新排列自訂屬性名稱和自訂屬性值。

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}