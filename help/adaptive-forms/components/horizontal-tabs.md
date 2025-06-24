---
title: 最適化Forms核心元件 — 水準索引標籤
description: 使用或自訂最適化Forms水準索引標籤核心元件。
role: Architect, Developer, Admin, User
exl-id: fbdf330b-3b85-4f94-9dab-eea8465fba67
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '2153'
ht-degree: 0%

---


# 水準索引標籤元件（頂端索引標籤）元件{#horizontal-tabs-adaptive-forms-core-component}

最適化表單中的水準索引標籤是指一個設計模式，其中表單的多個區段分組在一起，並以水準對齊的單獨索引標籤顯示。 使用者可在標籤之間切換以存取表單的不同區段。 每個標籤都會當作顯示和隱藏相關表單內容的觸發器。 水準標籤有助於將長表格組織成易於管理的部分，並改善使用者體驗。 索引標籤可協助殘障使用者更輕鬆地存取表單，因為他們可以使用鍵盤導覽在區段之間切換。

標籤通常以一系列連結或按鈕的形式建立，每個連結或按鈕都會與表單的某個區段相對應。 當使用者按一下索引標籤，表單內容會動態更新以顯示對應的區段。

![範例](/help/adaptive-forms/assets/horizontal-example-new.png)

{{traditional-aem}}

## 使用情況 {#reasons-to-use-horizontal-tabs}

在最適化表單中使用水準索引標籤的常見原因包括：

- **改善可用性**：水準標籤讓使用者更容易瀏覽表單，尤其是表單有多個區段或大量欄位時。

- **空間管理**：水準索引標籤可將相關的表單區段分組為索引標籤，一次只顯示一個區段，有助於節省熒幕空間。

- **更好的組織**：標籤為表單提供清晰且有條理的結構，讓使用者更容易理解並完成表單。

- **增加使用者參與度**：水準索引標籤可以讓表單更吸引目光，並讓使用者更容易使用，進而提高表單完成率。

## 版本和相容性 {#version-and-compatibility}

最適化Forms水準標籤核心元件於2023年2月發行，是核心元件2.0.4的一部分。下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service |
| — | — |
| v1 | 與<br>[版本2.0.4](/help/adaptive-forms/version.md)和更新版本相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)檔案。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Horizontal-tabs  Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_Horizontal-tabs ). -->


## 技術細節 {#technical-details}

在[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageHorizontaltabs/v1/pageHorizontaltabs)的技術檔案中取得最適化Forms水準標籤核心元件的最新資訊。 如需開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的水準索引標籤體驗。 您也可以輕鬆定義「水準」標籤選項，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/tabs-on-top-basic.png)

- **名稱** — 您可以在表單和規則編輯器中輕鬆識別具有唯一名稱的表單元件，但名稱不得包含空格或特殊字元。

- **標題** — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。
- **允許標題使用RTF格式** — 此功能可讓使用者格式化純文字標題，並整合如粗體、斜體、底線文字、各種字型、字型大小、顏色等功能以及可增強視覺呈現和自訂的其他選項。 它提供更大的彈性和創意控制，讓標題在檔案、網站或應用程式中脫穎而出。\
  選取&#x200B;**允許標題為RTF格式**&#x200B;的核取方塊後，即可看到格式化選項，以設定元件標題的樣式。 若要存取所有可用的格式選項，您可以按一下![全熒幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png)標籤。

  ![RTF支援](/help/adaptive-forms/assets/richtext-support-title.png)

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

<!-- **Layout** - You can have either a fixed layout (Simple) or a flexible layout (Responsive Grid) for your wizard. The Simple layout keeps everything fixed in the place, while the Responsive Grid allows you to adjust the position of components to suit your needs. For example, use Responsive Grid to align "First Name", "Middle Name" and "Last Name" in a form in a single row. -->

- **繫結參考** — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。
- **隱藏元件** — 選取選項，以隱藏表單中的元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。
- **停用元件** — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀** — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 重複頂端標籤 {#repeat-tabs-on-top}

![協助工具標籤](/help/adaptive-forms/assets/repeat-tabsontop.png)

您可以使用重複性選項來複製「水平定位點」元件及其子元件、定義最小和最大重複計數，以及簡化表單中類似區段的複製。 與「水準」標籤元件互動並存取其設定時，會顯示下列選項：

- **將索引標籤設定在頂端可重複**：切換功能，可讓使用者啟用或停用重複功能。
- **最小重複次數**：建立水準標籤元件可重複的最小次數。 值為零表示「水平定位點」元件不會重複；預設值為零。
- **最大重複次數**：設定Horizontal-tab元件可重複的最大次數。 預設情況下，此值為無限制。
若要有效管理水準標籤內的可重複區段，請依照[建立包含可重複區段的表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html)文章中提供的步驟操作。

### 專案標籤 {#items-tab}

![專案索引標籤](/help/adaptive-forms/assets/items-tabs-on-top.png)

**新增**&#x200B;按鈕可讓您從元件選取視窗中選取要新增為面板的元件。 新增元件後，您會看到下列選項：

- **圖示** — 圖示可識別清單中面板的元件。 您可以將滑鼠停留在圖示上，以工具提示的形式檢視完整的元件名稱。
- **描述** — 用來作為面板文字的描述。 依預設，為面板選取的元件名稱。
- **刪除** — 點選或按一下以從水準標籤元件中刪除面板。
- **重新排列** — 點選或按一下並拖曳以重新排列面板。

### 說明內容標籤 {#help-content}

![說明內容標籤](/help/adaptive-forms/assets/helpcontent-tabs-on-top.png)

- **簡短說明** — 簡短說明是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用&#x200B;**永遠顯示簡短描述**&#x200B;選項，以在元件下方顯示它。
- **永遠顯示簡短描述** — 啟用選項以在元件下方顯示簡短描述。

- **說明文字** — 說明文字是指提供給使用者的其他資訊或指引，以協助使用者正確填寫表單欄位。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。

### 協助工具標籤 {#accessibility}

![協助工具標籤](/help/adaptive-forms/assets/accessibilty-tabs-on-top.png)

- **熒幕助讀程式文字** — 熒幕助讀程式文字是指視力不佳人士使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。
   - **自訂文字**：選取此選項即可使用ARIA協助工具標籤的自訂文字。 選取此選項會顯示「自訂文字」對話方塊。 您可以在「自訂文字」對話方塊中新增相關資訊。
   - **說明**：選取此選項即可使用ARIA協助工具標籤的說明。
   - **標題**：選取此選項即可使用ARIA協助工具標籤的標題。
   - **名稱**：選取此選項即可使用ARIA協助工具標籤的名稱。
   - **無**：如果您不想新增ARIA協助工具標籤，請選取此選項。

- **熒幕朗讀程式要宣告的HTML角色** - HTML角色是用來指定HTML元素用途的屬性，以輔助技術（例如熒幕朗讀程式）使用。 角色屬性可用來提供元素的其他上下文和語意意義，讓熒幕朗讀程式更容易向使用者解譯和宣告內容。 例如，在AEM Forms中，表單欄位的標籤可能會具有「label」角色，而其輸入欄位的角色可能會具有「textbox」。 這可協助熒幕助讀程式瞭解標籤和輸入欄位之間的關係，並向使用者正確宣告。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本建立者控制物件的預設顯示方式。 對於最適化Forms水準標籤元件，您可以設定下列專案：

- 表單建立者可以新增到最適化Forms編輯器中的水準索引標籤的核心元件
- 樣式（CSS類別）的簡單名稱，可套用至最適化Forms編輯器中「水準」索引標籤元件的「屬性」對話方塊中。

這有助於讓建立和自訂表單的流程更直接有效。

### 允許的元件標籤 {#allowed-components-tab}

![允許的元件索引標籤](/help/adaptive-forms/assets/tabs-allowed-component.png)

**允許的元件**&#x200B;索引標籤可讓範本編輯器設定元件，這些元件可在最適化Forms編輯器的「水準索引標籤」元件中新增為面板的專案。

### 樣式索引標籤 {#styles-tab}

「設計」對話方塊可用來定義和管理元件的CSS樣式。 最適化Forms水準標籤核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![樣式索引標籤](/help/adaptive-forms/assets/tabs-styles-tab.png)

- **預設CSS類別**：您可以為最適化Forms水準索引標籤核心元件提供預設CSS類別。

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