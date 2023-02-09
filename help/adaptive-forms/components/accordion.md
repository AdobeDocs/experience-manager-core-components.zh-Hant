---
title: 適用性表單折疊式功能表
description: 使用折疊式功能表，將長或複雜的表單分割成更小、更方便管理的區段，以組織並簡化表單。
role: Architect, Developer, Admin, User
source-git-commit: 0e4fb8454b7ef84eb5b1b73b01c982a2f9c12381
workflow-type: tm+mt
source-wordcount: '1652'
ht-degree: 0%

---

# 折疊式面板元件 {#accordion-component-adaptive-forms-core-component}

折疊式功能表核心元件可讓使用者在適用性表單中建立可展開和可折疊的區段。 它通常用於組織和簡化長表單或複雜表單，將表單拆分為更小、更易於管理的部分。 折疊式功能表的每個區段通常會以標題表示，使用者可按一下標題來展開或折疊對應的內容。 內容可以是任何核心元件。

## 使用狀況 {#usage}

將折疊式功能表納入最適化表單有幾個好處，包括：

* **節省空間**:折疊式功能表可讓使用者展開和折疊表單的區段，減少一次顯示所有表單欄位所需的空間量。

* **導覽**:折疊式功能表可用來建立階層式導覽結構，讓使用者更容易找到所需的表單欄位。

* **使用者體驗**:折疊式功能表可讓使用者以清楚且直覺的方式存取及填寫表單欄位，讓表單更方便使用。

* **龍Forms**:折疊式功能表是處理長表單的理想元件，因為它可讓使用者一次專注在一個區段，而非一次處理大量資訊。

您可以使用：

* 此 [配置對話框](#configure-dialog) 指定折疊式功能表元件的屬性。

* 此 [選取面板彈出視窗](#select-panel-popover)  來定義折疊式功能表面板的順序。 這可讓作者依照面板的顯示順序排列面板。

* 表單作者啟用或停用 [設計對話](#design-dialog). 例如，作者可以選擇停用表單的特定欄位或區段。 這些選項可讓作者進一步掌控表單的設計和功能，更輕鬆建立符合組織特定需求的表單。

「設定」對話方塊、選取面板彈出視窗和設計對話方塊都是核心元件的一部分，這些元件旨在讓表單的編寫過程變得簡單輕鬆，並提供建立複雜表單的有效方式。

## 版本與相容性 {#version-and-compatibility}


適用性Forms折疊式功能表核心元件已於2023年2月發行，作為核心元件2.0.4的一部分。下表顯示所有支援的版本、AEM相容性，以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容於<br>[版本2.0.4](/help/versions.md) 和 | 相容 | 相容 |

如需核心元件版本和版本的相關資訊，請參閱 [核心元件版本](/help/versions.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

取得相關技術檔案中折疊式功能表元件的最新資訊，位於 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 配置對話框 {#configure-dialog}

您可以使用「設定」對話方塊，輕鬆自訂訪客的折疊式功能表體驗。 您也可以輕鬆定義折疊式功能表項目、面板、行為和外觀，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本標籤](/help/adaptive-forms/assets/accordion_basictab.png)

* **名稱**  — 您可以在表單和規則編輯器中，以唯一的名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **標題**  — 使用其「標題」，您可以輕鬆地在表單中識別元件，預設情況下，標題會顯示在元件上方。 如果未新增標題，則會顯示元件名稱，而非標題文字。

* **隱藏標題**  — 選取要隱藏元件標題的選項。

* **將資料包裝在物件中**  — 選擇「將資料包裝在物件中」，將精靈的欄位資料放入JSON物件中。 如果未選取，提交資料JSON的精靈欄位結構會很平坦。

* **版面**  — 您可以為精靈提供固定版面（簡單）或彈性版面（回應式格線）。 「簡單」版面可讓所有內容固定在原處，而「回應式格線」可讓您調整元件的位置，以符合您的需求。 例如，使用回應式格線來對齊單一列中表單中的「名字」、「中間名稱」和「姓氏」。

* **系結參考**  — 綁定引用是對資料元素的引用，該資料元素儲存在外部資料源中，並用於表單中。 系結參考可讓您將資料動態系結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，系結參考可用來根據在表單中輸入的客戶ID，在表單中顯示客戶的名稱和地址。 系結參考也可用來使用輸入表單的資料更新資料來源。 如此一來，AEM Forms便能讓您建立與外部資料來源互動的表單，為收集和管理資料提供順暢的使用者體驗。
* **隱藏元件**  — 選取從表單中隱藏元件的選項。 元件仍可供其他用途存取，例如在規則編輯器中用於計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這個功能會很實用。
* **禁用元件**  — 選取要停用元件的選項。 已禁用的元件不活動或不可編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可供其他用途存取，例如在規則編輯器中用於計算。

### 項目標籤 {#items-tab}

![項目索引標籤](/help/adaptive-forms/assets/accordion_itemstab.png)

「添加」按鈕允許您從元件選擇窗口中選擇要添加為面板的元件。 新增元件後，您會看到下列選項：

* **圖示**  — 此圖示會識別清單中面板的元件。 您可以將滑鼠移至圖示上，以工具提示的形式查看完整元件名稱。
* **說明**  — 用作面板文字的說明。 預設情況下，會為面板選取元件名稱。
* **刪除**  — 點選或按一下，從折疊式功能表元件中刪除面板。
* **重新排列**  — 點選或按一下並拖曳，重新排列面板的順序。

### 說明內容標籤 {#help-content}

![說明內容標籤](/help/adaptive-forms/assets/accordion_helpcontent.png)

* **簡短說明**  — 簡短說明是簡短的文本說明，提供關於特定表單欄位用途的其他資訊或說明。 它可協助使用者了解應在欄位中輸入的資料類型，並可提供指引或範例，以協助確保輸入的資訊有效且符合所需的條件。 依預設，短說明仍會隱藏。 啟用 **一律顯示簡短說明** 選項，將其顯示在元件下方。

* **一律顯示簡短說明**  — 啟用選項，在元件下方顯示簡短說明。

* **說明文字**  — 說明文字是指提供給使用者的其他資訊或指引，以協助他們正確填寫表單欄位。 當使用者按一下元件旁的說明圖示(i)時，就會顯示。 說明文字提供比表單欄位的標籤或預留位置文字更詳細的資訊，旨在協助使用者了解欄位的要求或限制。 您也可以提供建議或範例，讓填寫表單更簡單、更準確。

### 協助工具標籤 {#accessibility}

![協助工具標籤](/help/adaptive-forms/assets/accordion_accessibility.png)

* **螢幕助讀程式的文字**  — 螢幕助讀程式的文字是指視覺障礙人士專用的輔助技術（例如螢幕助讀程式）專門用來閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息的相關資訊（自訂文字）。 螢幕助讀程式文字可協助確保所有使用者都能存取表單，包括視覺障礙者，並讓他們完全了解表單欄位及其需求。

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

「設計對話框」允許模板建立者控制預設顯示內容的方式。 對於適用性Forms折疊式功能表元件，您可以設定下列項目：

* 允許的HTML標題元素類型，並設為預設元素（例如H1、H2、H3等）
* 表單建立者可新增至適用性Forms編輯器中折疊式功能表的核心元件
* 樣式的簡單名稱（CSS類別），可套用至適用性Forms編輯器中折疊式功能表元件的屬性對話方塊中。

這有助於讓建立和自訂表單的程式更簡單且有效。

### 屬性標籤 {#properties-tab-design}

「屬性」索引標籤可讓範本作者為表單作者設定預設和允許的HTML標題元素：

![「設計」對話框屬性頁簽](/help/assets/accordion-design-properties.png)

* **允許的標題元素**:一個下拉式清單，內含多個選項，可讓範本作者選擇哪些標題元素可讓表單作者用於折疊式功能表。

* **預設標題元素**:下拉式清單會設定折疊式功能表元件的預設「標題」元素。

### 「允許的元件」頁簽 {#allowed-components-tab}

此 **允許的元件** 標籤可讓範本編輯器將可新增為項目的元件，設定至適用性Forms編輯器中折疊式功能表元件的面板。

### 樣式標籤 {#styles-tab}

「設計對話方塊」可用來定義及管理元件的CSS樣式。 適用性Forms折疊式功能表核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

**預設CSS類**:您可以為折疊式功能表元件提供預設的CSS類別。

**允許的樣式**:您可以提供代表樣式的名稱和CSS類別，以定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight:粗體」。 您可以在適用性Forms編輯器中，將這些樣式使用或套用至適用性表單。 若要套用樣式，請在適用性Forms編輯器中選取您要套用樣式的元件、導覽至屬性對話方塊，然後從 **樣式** 下拉式清單。 如果需要更新或修改樣式，只需返回「設計」對話框、更新樣式頁簽中的樣式並保存更改即可。


<!-- 

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




