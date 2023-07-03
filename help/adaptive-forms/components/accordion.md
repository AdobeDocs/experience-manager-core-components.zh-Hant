---
title: 自適應表單可摺疊面板
description: 使用摺疊式功能表，將表格分成更小、更易於管理的章節，以整理及簡化長或複雜的表格。
role: Architect, Developer, Admin, User
exl-id: 0ed38eee-fc22-4708-82eb-3fb1839b1ff2
source-git-commit: 7888cfa0f1358ce8018fc1e3cc3b19eb66a82b9d
workflow-type: tm+mt
source-wordcount: '1950'
ht-degree: 0%

---

# 收合式選單元件 {#accordion-component-adaptive-forms-core-component}

摺疊式功能表核心元件可讓使用者在最適化表單中建立可展開和可收合的區段。 它通常用於組織和簡化長或複雜的表單，方法是將其分成更小、更易於管理的部分。 摺疊式功能表的每個區段通常由標題表示，使用者可以按一下標題以展開或收合對應的內容。 內容可以是任何核心元件。

## 使用狀況 {#usage}

在最適化表單中加入摺疊式功能表有幾個好處，包括：

* **節省空間**：摺疊式功能表可讓使用者展開和摺疊表單的區段，減少一次顯示所有表單欄位所需的空間量。

* **導覽**：摺疊式功能表可用來建立階層式導覽結構，讓使用者更容易找到所需的表單欄位。

* **使用者體驗**：摺疊式功能表可讓使用者透過清晰且直覺的方式存取及填寫表單欄位，讓表單更人性化。

* **長Forms**：摺疊式功能表是處理長表單的理想元件，因為使用者可一次專注一個區段，而非一次嘗試處理許多資訊。

您可以使用：

* 此 [設定對話方塊](#configure-dialog) 以指定摺疊式功能表元件的屬性。

* 此 [「選取面板」彈出視窗](#select-panel-popover)  以定義摺疊式功能表的面板順序。 這可讓作者以面板出現的順序來排列面板。

* 表單作者可啟用或停用中某些功能的選項 [設計對話方塊](#design-dialog). 例如，作者可以選擇停用表單的某些欄位或區段。 這些選項可讓作者更能掌控表單的設計和功能，讓您更輕鬆地建立符合組織特定需求的表單。

「設定」對話方塊、選取面板彈出視窗和「設計」對話方塊都是核心元件的一部分，這些元件的建置可讓表單的製作更容易，並提供建立複雜表單的有效方式。

## 版本和相容性 {#version-and-compatibility}


最適化Forms摺疊式功能表核心元件於2023年2月發行，屬於核心元件2.0.4的一部分。下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service  |
| — | --- |
| v1 | 相容於<br>[版本2.0.4](/help/versions.md) 和更新版本 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱 [核心元件版本](/help/versions.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在以下位置的技術檔案中取得摺疊式功能表元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的收合式選單體驗。 您也可以輕鬆定義摺疊式功能表專案、面板、行為和外觀，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/acc-basic.png)

* **名稱**  — 您可以在表單和規則編輯器中以唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **標題**  — 透過其Title ，您可以輕鬆識別表單中的元件，且根據預設，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件名稱而非標題文字。

* **隱藏標題**  — 選取隱藏元件標題的選項。

* **將資料換行至物件**  — 選擇「在物件中繞排資料」，將精靈的欄位資料放在JSON物件內。 如果未選擇，則提交資料JSON的精靈欄位會具有平面結構。

* **版面**  — 您可以為精靈使用固定版面（簡單）或彈性版面（回應式格線）。 「簡單」版面可讓一切固定在原處，而「回應式格線」則可讓您調整元件位置，以符合您的需求。 例如，使用回應式格線將「名字」、「中間名」和「姓氏」在表單中以單列對齊。

* **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。
* **隱藏元件**  — 選取選項，從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存使用者不需要看到或直接變更的資訊時，這會很有用。
* **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 重複可摺疊面板 {#repeat-accordion}

![repeat-accordion](/help/adaptive-forms/assets/repeat-accordion.png)

您可以使用重複性選項來複製摺疊面板及其子元件、定義最小和最大重複計數，以及簡化表單中類似區段的複製。 與摺疊式功能表元件互動並存取其設定時，會顯示下列選項：

* **將摺疊面板設為可重複**：可讓使用者啟用或停用重複測量功能的切換功能。
* **最小重複次數**：建立摺疊面板可重複的最小次數。 值為零表示不重複摺疊面板；預設值為零。
* **最大重複次數**：設定摺疊面板可重複的最大次數。 預設情況下，此值為無限制。

若要有效管理摺疊式功能表內的可重複區段，請依照以下提供的步驟操作： [建立具有可重複區段的表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html) 文章。

### 專案標籤 {#items-tab}

![專案索引標籤](/help/adaptive-forms/assets/acc-items.png)

「新增」按鈕可讓您從元件選取視窗中選取要新增為面板的元件。 新增元件後，您會看到下列選項：

* **圖示**  — 圖示可識別清單中面板的元件。 您可以將滑鼠停留在圖示上，以工具提示的形式檢視完整的元件名稱。
* **說明**  — 用作面板文字的說明。 依預設，會為面板選取元件名稱。
* **刪除**  — 點選或按一下以從摺疊式功能表元件中刪除面板。
* **重新排列**  — 點選或按一下並拖曳以重新排列面板。

### 說明內容標籤 {#help-content}

![說明內容標籤](/help/adaptive-forms/assets/acc-helpcontent.png)

* **簡短說明**  — 簡短說明是簡短文字說明，提供有關特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入什麼型別的資料，並可提供指引或範例來協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明仍會隱藏。 啟用 **一律顯示簡短說明** 選項來將它顯示在元件下方。

* **一律顯示簡短說明**  — 啟用選項以在元件下方顯示簡短說明。

* **說明文字**  — 說明文字是指為協助使用者正確填寫表單欄位，而提供給使用者的其他資訊或指引。 當使用者按一下置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供比表單欄位的標籤或預留位置文字更詳細的資訊，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，使填寫表單更容易、更準確。

### 協助工具標籤 {#accessibility}

![協助工具索引標籤](/help/adaptive-forms/assets/acc-accessisbilty.png)

於 **協助工具** 標籤，值設定為 [ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。 熒幕助讀程式的文字使用方式有多種選項：

* **熒幕助讀程式的文字**  — 熒幕助讀程式文字是指視力不佳人士使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取（包括視覺障礙使用者），並讓他們完全瞭解表單欄位及其需求。


   * **自訂文字**：選取此選項以使用自訂文字作為ARIA協助工具標籤。 選取此選項會顯示「自訂文字」對話方塊。 您可以在「自訂文字」對話方塊中新增相關資訊。
   * **說明**：選取此選項可使用ARIA協助工具標籤的說明。
   * **標題**：選取此選項可使用ARIA協助工具標籤的標題。
   * **名稱**：選取此選項，即可使用ARIA協助工具標籤的名稱。
   * **無**：如果您不想要新增ARIA協助工具標籤，請選取此選項。

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

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本建立者控制物件的預設顯示方式。 針對最適化Forms摺疊式功能表元件，您可以設定下列專案：

* 允許並設為預設的HTML標題元素型別（例如H1、H2、H3等）
* 表單建立者可以新增至最適化Forms編輯器中摺疊式功能表的核心元件
* 樣式（CSS類別）的簡單名稱，可套用至最適化Forms編輯器中accordion元件的「屬性」對話方塊。

這有助於讓建立和自訂表單的程式更直接更有效率。

### 屬性標籤 {#properties-tab-design}

「屬性」標籤可讓範本作者為表單作者設定預設和允許的HTML標題元素：

![設計對話方塊屬性索引標籤](/help/assets/accordion-design-properties.png)

* **允許的標題元素**：含有多個選項的下拉式清單，可讓範本作者選擇哪些標題元素可以形成作者以用於摺疊式功能表。

* **預設標題元素**：下拉式清單會為摺疊式功能表元件設定預設的「標題」元素。

### 允許的元件索引標籤 {#allowed-components-tab}

此 **允許的元件** 索引標籤可讓範本編輯器設定元件，這些元件可在最適化Forms編輯器的摺疊式功能表元件中新增為面板的專案。

### 樣式索引標籤 {#styles-tab}

「設計」對話方塊可用來定義和管理元件的CSS樣式。 最適化Forms摺疊式功能表核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

**預設CSS類別**：您可以為摺疊式功能表元件提供預設的CSS類別。

**允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在調適型Forms編輯器中將這些樣式使用或套用至調適型表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只需返回「設計」對話方塊，更新樣式標籤中的樣式，然後儲存變更即可。


<!--- 

The design dialog allows the template author to define the options available to the content author who uses the Accordion Component and the defaults set when placing the Accordion Component.


### Properties Tab {#properties-tab-design}

![Design dialog properties tab](/help/assets/accordion-design-properties.png)

* **Allowed Heading Elements** - This multi-select drop-down defines the accordion item heading HTML elements that are allowed to be selected by an author.
* **Default Heading Element** - This drop-down defines the default accordion item heading HTML element.

### Allowed Components Tab {#allowed-components-tab}

The **Allowed Components** tab is used to define which components can be added as items to panels in the Accordion Component by the content author.

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### Styles Tab {#styles-tab}

The Accordion Component supports the AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

The Accordion Component supports the [Adobe Client Data Layer.](/help/developing/data-layer/overview.md) 


-->

## 相關文章 {#related-article}

* [在AEM Sites頁面或體驗片段中建立最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [建立獨立的最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

