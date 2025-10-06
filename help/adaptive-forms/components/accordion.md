---
title: 自適應表單摺疊面板
description: 使用摺疊面板來整理和簡化冗長或複雜的表單，方法是將其分成更小、更易於管理的區段。
role: Architect, Developer, Admin, User
exl-id: 0ed38eee-fc22-4708-82eb-3fb1839b1ff2
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '2237'
ht-degree: 100%

---


# 摺疊面板元件 {#accordion-component-adaptive-forms-core-component}

摺疊面板核心元件可讓使用者在自適應表單中建立可展開和可收合的區段。它通常用於整理和簡化冗長或複雜的表單，方法是將其分成更小、更易於管理的區段。摺疊面板的每個區段通常由標頭表示，使用者可以按一下標頭來展開或收合對應的內容。內容可以是任何核心元件。

![範例](/help/adaptive-forms/assets/example-accordion.png)

{{traditional-aem}}

## 用途 {#usage}

在自適應表單中加入摺疊面板有多項好處，包括：

- **節省空間**：摺疊面板可讓使用者展開和收合表單的區段，減少一次顯示所有表單欄位所需的空間量。

- **導覽**：摺疊面板可用來建立階層式導覽結構，讓使用者更容易找到所需的表單欄位。

- **使用者體驗**：透過摺疊面板，可讓使用者以清晰直觀的方式存取及填寫表單欄位，使表單更加易於使用。

- **冗長表單**：摺疊面板是處理冗長表單的理想元件，因為使用者可一次專注一個區段，而不是一次處理許多資訊。

您可以使用：

- [設定對話框](#configure-dialog)以指定摺疊面板元件的屬性。

- [選取面板彈出視窗](#select-panel-popover)以定義摺疊面板的面板順序。這可讓作者依照面板應出現的順序來排列面板。

- 表單作者在[設計對話框](#design-dialog)中啟用或停用某些功能的選項。例如，作者可以選擇停用表單的特定欄位或區段。這些選項可讓作者更能掌控表單的設計和功能，有利於更輕鬆地建立符合組織特定需求的表單。

設定對話框、選取面板彈出視窗和設計對話框都是核心元件的一部分，其建置可讓表單的製作更容易，並提供高效率建立複雜表單的方法。

## 版本和相容性 {#version-and-compatibility}


自適應表單摺疊面板核心元件於 2023 年 2 月作為核心元件 2.0.4 版的一部分發行。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 相容 | 相容 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_tw). -->

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion)上的技術文件中可取得摺疊面板元件的最新相關資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的摺疊面板體驗。同樣能夠輕鬆定義摺疊面板項目、面板、行為和外觀，以提供順暢無礙的使用者體驗。

### 基本索引標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/acc-basic.png)

- **名稱** - 在表單和規則編輯器中，您可以使用其唯一名稱輕鬆識別表單元件，但該名稱不得包含空格或特殊字元。

- **標題** - 您可以使用其標題輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。若未新增標題，則會顯示該元件的名稱而非標題文字。

- **允許標題使用 RTF 文字** - 此功能可讓使用者格式化純文字標題，整合粗體、斜體、底線文字、各種字型、字體大小、顏色等功能，以及可增強視覺呈現和自訂的其他選項。提供更大的靈活性和創意控制，讓標題在文件、網站或應用程式中脫穎而出。\
  選取&#x200B;**允許標題使用 RTF 文字**&#x200B;核取方塊後，即可看到格式選項，以設定元件標題的樣式。若要存取所有可用的格式選項，您可以按一下 ![全螢幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png) 索引標籤。

  ![RTF 文字支援](/help/adaptive-forms/assets/richtext-support-title.png)

- **隱藏標題** - 選取該選項，以隱藏元件標題。
- **在表單提交時將下層元件的資料分組 (將資料包裝在物件中)** - 選取該選項時，其下層元件的資料會巢狀內嵌在上層元件的 JSON 物件中。但是，如果未選取此選項，則提交的 JSON 資料具有單層結構，不含用於上層元件的物件。例如：

   - 選取此選項時，下層元件 (例如街道、城市和郵遞區號) 的資料會以 JSON 物件的形式巢狀內嵌於上層元件 (地址) 中。這樣會建立階層式結構，而資料會整理在上層元件下。

     提交資料的結構：

     ```JSON
     { "Address":
     
     { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     
     }
     ```

   - 未選取此選項時，提交的 JSON 資料具有單層結構，不含用於上層元件 (地址) 的物件。所有資料都位於相同層級，沒有任何階層式組織。


     提交資料的結構：

     ```JSON
        { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     ```

<!--  **Layout** - You can have either a fixed layout (Simple) or a flexible layout (Responsive Grid) for your wizard. The Simple layout keeps everything fixed in the place, while the Responsive Grid allows you to adjust the position of components to suit your needs. For example, use Responsive Grid to align "First Name", "Middle Name" and "Last Name" in a form in a single row. -->

- **繫結參考** - 繫結參考是指儲存在外部資料來源，並在表單中使用的資料元素的參考。繫結參考可讓您將資料動態繫結至表單欄位，讓表單可以顯示資料來源的最新資料。例如，繫結參考可用於根據輸入至表單的客戶 ID，在表單中顯示客戶的姓名和地址。繫結參考也可用於使用已輸入至表單中的資料更新資料來源。透過此方式，AEM Forms 可讓您建立與外部資料來源互動的表單，提供順暢無礙的使用者體驗，以收集和管理資料。

- **隱藏元件** - 選取該選項，以隱藏表單中的元件。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。這在您需要儲存使用者不需看到或直接變更的資訊時十分有用。

- **停用元件** - 選取該選項以停用元件。一般使用者無法啟動或編輯已停用的元件。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。

- **唯讀** - 選取該選項，使元件無法編輯。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。

### 重複可摺疊面板 {#repeat-accordion}

![重複摺疊面板](/help/adaptive-forms/assets/repeat-accordion.png)

您可以使用重複性選項來複製摺疊面板及其下層元件、定義最小和最大重複計數，以及簡化表單中類似區段的複寫。與摺疊面板元件互動並存取其設定時，會顯示下列選項：

- **設定摺疊面板可重複**：切換功能，可讓使用者啟用或停用重複功能。
- **最小重複次數**：建立摺疊面板可重複的最小次數。值為零表示摺疊面板元件不會重複；預設值為零。
- **最大重複次數**：設定摺疊面板可重複的最大次數。預設情況下，此值為無限制。

若要有效管理摺疊面板內的可重複區段，請依照[建立具有可重複區段的表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html?lang=zh-Hant)文章中提供的步驟操作。

### 項目索引標籤 {#items-tab}

![項目索引標籤](/help/adaptive-forms/assets/acc-items.png)

新增按鈕可讓您從元件選取視窗中選取要新增為面板的元件。新增元件後，您會看到下列選項：

- **圖示** - 圖示可識別清單中的面板元件。您可以將滑鼠停留在圖示上，以工具提示的形式檢視完整的元件名稱。
- **說明** - 用來作為面板文字的說明。預設情況下，為面板選取的元件名稱。
- **刪除** - 點選或按一下，以從摺疊面板元件刪除該面板。
- **重新排列** - 點選或按一下並拖曳，以重新排列面板的順序。

### 說明內容索引標籤 {#help-content}

![說明內容索引標籤](/help/adaptive-forms/assets/acc-helpcontent.png)

- **簡短說明** - 簡短說明指的是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。這有助於使用者了解應在該欄位中輸入的資料類型，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。預設情況下，簡短說明會保持隱藏。啟用&#x200B;**永遠顯示簡短說明**&#x200B;選項，使其顯示於元件下方。

- **永遠顯示簡短說明** - 啟用該選項，使簡短說明顯示於元件下方。

- **說明文字** - 說明文字指的是為使用者提供的其他資訊或指引，協助其正確填寫表單欄位。當使用者按一下放置於元件旁的說明圖示 (i) 時，就會出現此選項。說明文字提供的資訊比表單欄位的標籤或預留位置文字更加詳細，旨在協助使用者了解該欄位的要求或限制。還能夠提供建議或範例，使表單填寫更輕鬆、更準確。

### 協助工具索引標籤 {#accessibility}

![協助工具索引標籤](/help/adaptive-forms/assets/acc-accessisbilty.png)

在&#x200B;**協助工具**&#x200B;索引標籤上，可以設定元件的 [ARIA 協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤值。螢幕助讀程式的文字有多種可用選項：

- **螢幕助讀程式文字** - 螢幕助讀程式文字指的是專門供視障人士所使用的輔助技術 (如螢幕助讀程式) 朗讀的額外文字。此文字提供表單欄位用途的音訊說明，並可包含有關欄位標題、說明、名稱和任何相關訊息 (自訂文字) 的資訊。螢幕助讀程式文字協助確保表單可供所有使用者存取，包括視障人士，使他們能夠充分理解表單欄位及其要求。

   - **自訂文字**：選取此選項，以使用 ARIA 協助工具標籤的自訂文字。選取此選項會顯示自訂文字對話框。您可以在自訂文字對話框中新增相關資訊。
   - **說明**：選取此選項，以使用 ARIA 協助工具標籤的說明。
   - **標題**：選取此選項，以使用 ARIA 協助工具標籤的標題。
   - **名稱**：選取此選項，以使用 ARIA 協助工具標籤的名稱。
   - **無**：如果您不想新增 ARIA 協助工具標籤，請選取此選項。

<!--

### Properties Tab {#properties-tab}

![Properties tab of the edit dialog of the Accordion Component](/help/assets/accordion-edit-properties.png)

*   **Single item expansion** - When selected, this option forces a single accordion item to be expanded at a time. Expanding one item will then collapse all others.
*   **Expanded items** - This option defines the items that are expanded by default when the page is loaded.
    * When **Single item expansion** is selected, one panel must be selected. By default the first panel is selected.
    * When **Single item expansion** is not selected, this option is a multi-select and is optional.
*   **ID** - This option allows to control the unique identifier of the component in the HTML and in the [Data Layer](/help/developing/data-layer/overview.md).
    * If left blank, a unique ID is automatically generated for you and can be found by inspecting the resulting page.
    * If an ID is specified, it is the responsibility of the author to make sure that it is unique.
    * Changing the ID can have an impact on CSS, JS and Data Layer tracking.

## Select Panel Popover {#select-panel-popover}

The **Select Panel** option (![Select panel icon](/help/assets/select-panel-icon.png)) on the component toolbar enables content authors to modify the panels in an accordion with ease. By selecting this option, the author can switch to a different panel for editing and rearrange the order of the panels in the accordion. The configured panels will be displayed in a drop-down menu for the author to choose from. This feature optimizes the editing process and makes it user-friendly for content authors.

![Select panel popover](/help/assets/select-panel-popover.png)


* The panels are displayed in a numbered list, reflecting the assigned arrangement.
* Each panel is listed with its component type in bold, followed by a brief description in lighter font.
* By clicking or tapping on a panel in the drop-down, you can easily switch the view in the editor to that specific panel.
* To rearrange the panels, simply use the drag handles to move them into the desired order. -->

## 設計對話框 {#design-dialog}

設計對話框可讓範本建立者控制物件的預設顯示方式。針對自適應表單摺疊面板元件，您可以設定下列項目：

- 允許並設為預設的 HTML 標題元素類型 (例如 H1、H2、H3 等)
- 表單建立者可以在自適應表單編輯器中新增至摺疊面板的核心元件
- 樣式 (CSS 類別) 的簡易名稱，可在自適應表單編輯器中摺疊面板元件的屬性對話框中套用。

這有助於讓建立和自訂表單的流程更直接且有效率。

### 屬性索引標籤 {#properties-tab-design}

屬性索引標籤可讓範本作者為表單作者設定預設和允許的 HTML 標題元素：

![設計對話框屬性索引標籤](/help//adaptive-forms/assets/accordion-design-properties.png)

- **允許的標題元素**：包含多個選項的下拉式清單，可讓範本作者選擇哪些標題元素可供表單作者用於摺疊面板。

- **預設標題元素**：為摺疊面板元件設定預設標題元素的下拉式清單。

### 允許的元件索引標籤 {#allowed-components-tab}

![設定對話框允許的元件索引標籤](/help//adaptive-forms/assets/accordion-allowed-components.png)

透過&#x200B;**允許的元件**&#x200B;索引標籤，範本編輯者可設定作為項目新增至自適應表單編輯器中摺疊面板元件內面板的元件。

### 樣式索引標籤 {#styles-tab}

![設計對話框樣式索引標籤](/help/adaptive-forms/assets/accordion-styles-tab.png)

設計對話框可用於定義和管理元件的 CSS 樣式。自適應表單摺疊面板核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

- **預設 CSS 類別**：您可以為摺疊面板元件提供預設 CSS 類別。

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![摺疊面板自訂屬性索引標籤](/help/adaptive-forms/assets/accordion-custom-properties-tab.png)
自訂屬性可讓您使用表單範本，將自訂屬性 (鍵值對) 與自適應表單核心元件建立關聯。自訂屬性會反映在元件的無周邊轉譯屬性區段中。可讓您建立根據自訂屬性值調整的動態表單行為。例如，開發人員可以為行動裝置、桌上型電腦或網頁平台設計各種無周邊表單元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱，以識別自訂屬性群組。還可以新增、刪除或重新排列多個自訂屬性群組。新增自訂屬性群組後，您可以看到下列選項：

   - **鍵值對**：按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，即可新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳，以重新排列自訂屬性名稱和自訂屬性值的順序。

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}