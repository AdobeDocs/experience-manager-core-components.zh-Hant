---
title: 自適應表單核心元件 - 精靈
description: 使用或自訂自適應表單精靈核心元件。
role: Architect, Developer, Admin, User
exl-id: fd785cd2-5ed6-4efb-997f-ce9056ed113d
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '2186'
ht-degree: 100%

---


# 精靈元件{#wizard-adaptive-forms-core-component}

自適應表單中的精靈版面是指表單分成多個步驟或頁面，使用者按步驟逐步完成表單填寫。此版面稱為「精靈」，因為它會逐步引導使用者完成表單。

精靈的每個步驟通常包含一組相關的表單欄位和導覽機制，例如「下一步」和「上一步」按鈕，以便在步驟之間移動。完成目前步驟並填寫完所有必填欄位後，使用者才能繼續進行下一個步驟。

精靈版面對於含有大量欄位或需要收集大量資訊的表單非常有用，因為它會將表單劃分為更小、更易於管理的區塊。此外，也可協助使用者一次只專注於一組欄位，減少填寫表單的麻煩。

但是，它也可能會增加表單的複雜性，因為使用者必須逐頁填寫才能完成表單。因此，在決定使用精靈版面之前，必須評估表單要求和使用者需求。您可以在自適應表單中使用精靈版面核心元件來建立精靈版面。

{{traditional-aem}}

**範例**

![範例](/help/adaptive-forms/assets/wizard.png)

## 用途 {#reasons-to-use-wizard-in-an-adaptive-form}

在自適應表單中使用精靈版面有多項好處，包括：

- **簡單性**：將表單劃分為多個步驟可以讓使用者更容易理解和完成，因為他們每次可以集中處理一組欄位。

- **組織**：精靈版面可協助您依主題或用途整理表單，也可以將相關欄位分組，讓表單填寫流程更具邏輯性與效率。

- **驗證**：精靈版面允許逐步驗證，這可以協助使用者在過程中及時識別並更正錯誤，而不必等到完成表單後才發現。

- **進度指示器**：精靈版面可以顯示表單的進度，這可以幫助使用者瞭解表單還剩多少內容未完成。

- **冗長表單**：如果表單中有許多欄位，使用者可能無法一次看到所有欄位，因此將它們分成更小、更易於管理的區塊，可讓表單不那麼令人生畏。

- **避免放棄**：精靈版面也有助於降低放棄表單的情況，因為使用者如果能夠看到進度並瞭解剩餘待完成量時，就更有可能完成表單。

- **行動體驗**：精靈版面也有利於在行動裝置上存取表單，因為它可採用較小的頁面，可加快載入速度且更容易導覽。

整體而言，精靈版面可讓使用者更輕鬆有效率地整握表單填寫流程，但在決定使用此類型的版面之前，請務必考量表單的複雜度以及使用者的需求。

## 版本和相容性 {#version-and-compatibility}

自適應表單精靈版面核心元件於 2023 年 2 月作為核心元件 2.0.4 版的一部分發行。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 相容 | 相容 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/wizard/v1/wizard) 的技術文件中可找到自適應表單精靈核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的精靈體驗。同樣能夠輕鬆定義精靈選項，以提供順暢無礙的使用者體驗。

### 基本索引標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/wizard-basic.png)

- **名稱** - 在表單和規則編輯器中，您可以使用其唯一名稱輕鬆識別表單元件，但該名稱不得包含空格或特殊字元。

- **標題** - 您可以使用其標題輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。

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

<!--   **Wrap data in an object** - Choose "Wrap data in an object" to put the field data from the Wizard inside a JSON object. If not chosen, the submit data JSON has a flat structure for the Wizard's fields.

-   **Layout** - You can have either a fixed layout (Simple) or a flexible layout (Responsive Grid) for your wizard. The Simple layout keeps everything fixed in the place, while the Responsive Grid allows you to adjust the position of components to suit your needs. For example, use Responsive Grid to align "First Name", "Middle Name" and "Last Name" in a form in a single row.  -->

- **繫結參考** - 繫結參考是指儲存在外部資料來源，並在表單中使用的資料元素的參考。繫結參考可讓您將資料動態繫結至表單欄位，讓表單可以顯示資料來源的最新資料。例如，繫結參考可用於根據輸入至表單的客戶 ID，在表單中顯示客戶的姓名和地址。繫結參考也可用於使用已輸入至表單中的資料更新資料來源。透過此方式，AEM Forms 可讓您建立與外部資料來源互動的表單，提供順暢無礙的使用者體驗，以收集和管理資料。

- **隱藏元件** - 選取該選項，以隱藏表單中的元件。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。這在您需要儲存使用者不需看到或直接變更的資訊時十分有用。

- **停用元件** - 選取該選項以停用元件。一般使用者無法啟動或編輯已停用的元件。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。

- **唯讀** - 選取該選項，使元件無法編輯。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。

### 重複精靈索引標籤 {#repeat-wizard-tab}

![重複精靈](/help/adaptive-forms/assets/wizard-repeat.png)

您可以使用重複性選項來複製精靈及其下層元件、定義最小和最大重複計數，以及簡化表單中類似區段的複寫。與精靈元件互動並存取其設定時，會顯示下列選項：

- **設定精靈可重複**：切換功能，可讓使用者啟用或停用重複功能。
- **最小重複次數**：建立精靈面板可重複的最小次數。值為零表示精靈面板不會重複；預設值為零。
- **最大重複次數**：設定精靈面板可重複的最大次數。預設情況下，此值為無限制。

若要有效管理精靈內的可重複區段，請依照[建立具有可重複區段的表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html)文章中提供的步驟操作。

### 項目索引標籤 {#items-tab}

![項目索引標籤](/help/adaptive-forms/assets/wizard_itemstab.png)

此選項可讓您按一下「新增」按鈕來新增自適應表單元件，該按鈕在編輯模式下新增精靈時預設會顯示。

### 說明索引標籤 {#help-tab}

![說明索引標籤](/help/adaptive-forms/assets/wizard_helptab.png)

- **簡短說明** - 簡短說明指的是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。這有助於使用者了解應在該欄位中輸入的資料類型，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。預設情況下，簡短說明會保持隱藏。啟用&#x200B;**永遠顯示簡短說明**&#x200B;選項，使其顯示於元件下方。

- **永遠顯示簡短說明** - 啟用該選項，使簡短說明顯示於元件下方。

- **說明文字** - 說明文字指的是為使用者提供的其他資訊或指引，協助其正確填寫表單欄位。當使用者按一下放置於元件旁的說明圖示 (i) 時，就會出現此選項。說明文字提供的資訊比表單欄位的標籤或預留位置文字更加詳細，旨在協助使用者了解該欄位的要求或限制。還能夠提供建議或範例，使表單填寫更輕鬆、更準確。


### 協助工具索引標籤 {#accessibility}

![協助工具索引標籤](/help/adaptive-forms/assets/wizard_accessibiltytab.png)

- **螢幕助讀程式文字** - 螢幕助讀程式文字指的是專門供視障人士所使用的輔助技術 (如螢幕助讀程式) 朗讀的額外文字。此文字提供表單欄位用途的音訊說明，並可包含有關欄位標題、說明、名稱和任何相關訊息 (自訂文字) 的資訊。螢幕助讀程式文字協助確保表單可供所有使用者存取，包括視障人士，使他們能夠充分理解表單欄位及其要求。
   - **自訂文字**：選取此選項，以使用 ARIA 協助工具標籤的自訂文字。選取此選項會顯示自訂文字對話框。您可以在自訂文字對話框中新增相關資訊。
   - **說明**：選取此選項，以使用 ARIA 協助工具標籤的說明。
   - **標題**：選取此選項，以使用 ARIA 協助工具標籤的標題。
   - **名稱**：選取此選項，以使用 ARIA 協助工具標籤的名稱。
   - **無**：如果您不想新增 ARIA 協助工具標籤，請選取此選項。

- **螢幕助讀程式播報的 HTML 角色** - HTML 角色是用於向輔助技術 (例如螢幕助讀程式) 指定 HTML 元素用途的屬性。角色屬性可用來提供元素的其他內容脈絡和語義上的涵義，讓螢幕助讀程式更容易向使用者解譯和播報內容。例如，在 AEM Forms 中，表單欄位的標籤可能會具有「標籤」角色，其輸入欄位則可能會具有「文字方塊」的角色。這可協助螢幕助讀程式瞭解標籤和輸入欄位之間的關係，並向使用者正確播報。


## 設計對話框 {#design-dialog}

設計對話框可讓範本建立者控制物件的預設顯示方式。針對自適應表單精靈元件，您可以設定下列項目：

- 表單建立者可以在自適應表單編輯器中新增至精靈的核心元件
- 樣式 (CSS 類別) 的簡易名稱，可在自適應表單編輯器中精靈元件的屬性對話框中套用。

這有助於讓建立和自訂表單的流程更直接且有效率。

### 允許的元件索引標籤 {#allowed-components-tab}

![允許的元件索引標籤](/help/adaptive-forms/assets/tabs-allowed-component.png)

透過&#x200B;**允許的元件**&#x200B;索引標籤，範本編輯器可設定作為項目新增至自適應表單編輯器中精靈元件內面板的元件。

### 樣式索引標籤 {#styles-tab}

設計對話框可用於定義和管理元件的 CSS 樣式。自適應表單精靈核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![樣式索引標籤](/help/adaptive-forms/assets/tabs-styles-tab.png)

- **預設 CSS 類別**：您可以為自適應表單精靈核心元件提供預設 CSS 類別。

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性索引標籤

![自訂屬性索引標籤](/help/adaptive-forms/assets/tabs-custom-properties.png)

自訂屬性可讓您使用表單範本，將自訂屬性 (鍵值對) 與自適應表單核心元件建立關聯。自訂屬性會反映在元件的無周邊轉譯屬性區段中。可讓您建立根據自訂屬性值調整的動態表單行為。例如，開發人員可以為行動裝置、桌上型電腦或網頁平台設計各種無周邊表單元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱，以識別自訂屬性群組。還可以新增、刪除或重新排列多個自訂屬性群組。新增自訂屬性群組後，您可以看到下列選項：

   - **鍵值對**：按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，即可新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳，以重新排列自訂屬性名稱和自訂屬性值的順序。

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}