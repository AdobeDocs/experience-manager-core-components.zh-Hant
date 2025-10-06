---
title: 自適應表單核心元件 - 面板容器
description: 使用或自訂自適應表單面板容器核心元件。
role: Architect, Developer, Admin, User
exl-id: 104836fe-8325-47de-978d-1ff2d6a9dd15
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '2225'
ht-degree: 100%

---


# 面板元件{#panel-container-adaptive-forms-core-component}

在自適應表單中，面板是容器元素，可用來將相關的表單元素分組。它可讓您以邏輯和有意義的方式，將不同的表單元素進行分組和整理。這有助於改善表單的整體結構和可讀性，讓使用者更容易理解和導覽。

面板也可用來建立可收合的區段，這對於隱藏複雜或不常使用的表單欄位很有用，讓表單保持簡單且易於使用。它也可讓您包含其他元件，例如文字、核取方塊、按鈕等。

它也可用來設定不同的規則型動作，例如提交表單、開啟網站、顯示/隱藏元件，或新增面板的執行個體。

{{traditional-aem}}

**範例**

![範例](/help/adaptive-forms/assets/panel-container.png)

## 用途 {#reasons-to-use-panel-container}

在表單中使用面板有許多原因，包括：

- **整理表單元素**: 面板可用來將相關的表單元素分組，讓使用者更容易理解和瀏覽表單。

- **改善表單結構**: 將表單元素分組為面板，可以改善表單的整體結構和可讀性，使其更易於理解。

- **建立可收合區段**：面板也可用來建立可收合的區段，這對於隱藏複雜或不常使用的表單欄位很有用，讓表單保持簡單且易於使用。

- **加強可用性**: 使用面板來整理表單元素，可讓表單更方便使用，進而提高完成率。

## 版本和相容性 {#version-and-compatibility}

自適應表單面板容器核心元件於 2023 年 2 月作為核心元件 2.0.4 版的一部分發行。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 相容 | 相容 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer) 的技術文件中可找到自適應表單面板容器核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的面板容器體驗。同樣能夠輕鬆定義面板容器選項，以提供順暢無礙的使用者體驗。

### 基本索引標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/basic-panel.png)

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

- **繫結參考** - 繫結參考是指儲存在外部資料來源，並在表單中使用的資料元素的參考。繫結參考可讓您將資料動態繫結至表單欄位，讓表單可以顯示資料來源的最新資料。例如，繫結參考可用於根據輸入至表單的客戶 ID，在表單中顯示客戶的姓名和地址。繫結參考也可用於使用已輸入至表單中的資料更新資料來源。透過此方式，AEM Forms 可讓您建立與外部資料來源互動的表單，提供順暢無礙的使用者體驗，以收集和管理資料。
- **隱藏元件** - 選取該選項，以隱藏表單中的元件。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。這在您需要儲存使用者不需看到或直接變更的資訊時十分有用。
- **停用元件** - 選取該選項以停用元件。一般使用者無法啟動或編輯已停用的元件。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀** - 選取該選項，使元件無法編輯。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。

### 重複面板索引標籤 {#repeat-panel}

![重複索引標籤](/help/adaptive-forms/assets/repeat-panel.png)

您可以使用重複性選項來複製面板容器及其下層元件、定義最小和最大重複計數，以及簡化表單中類似區段的複寫。與面板容器元件互動並存取其設定時，會顯示下列選項：

- **設定面板可重複**：切換功能，可讓使用者啟用或停用重複功能。
- **最小重複次數**：建立面板容器可重複的最小次數。值為零表示精靈面板不會重複；預設值為零。
- **最大重複次數**：設定面板容器可重複的最大次數。預設情況下，此值為無限制。

若要有效管理面板容器內的可重複區段，請依照[建立具有可重複區段的表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html)文章中提供的步驟操作。

### 說明內容索引標籤 {#help-content}

![說明內容索引標籤](/help/adaptive-forms/assets/helpcontent-panel.png)

- **簡短說明** - 簡短說明指的是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。這有助於使用者了解應在該欄位中輸入的資料類型，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。預設情況下，簡短說明會保持隱藏。啟用&#x200B;**永遠顯示簡短說明**&#x200B;選項，使其顯示於元件下方。

- **永遠顯示簡短說明** - 啟用該選項，使簡短說明顯示於元件下方。

- **說明文字** - 說明文字指的是為使用者提供的其他資訊或指引，協助其正確填寫表單欄位。當使用者按一下放置於元件旁的說明圖示 (i) 時，就會出現此選項。說明文字提供的資訊比表單欄位的標籤或預留位置文字更加詳細，旨在協助使用者了解該欄位的要求或限制。還能夠提供建議或範例，使表單填寫更輕鬆、更準確。

### 協助工具索引標籤 {#accessibility}

![協助工具索引標籤](/help/adaptive-forms/assets/accessibilty-panel.png)


- **螢幕助讀程式文字** - 螢幕助讀程式文字指的是專門供視障人士所使用的輔助技術 (如螢幕助讀程式) 朗讀的額外文字。此文字提供表單欄位用途的音訊說明，並可包含有關欄位標題、說明、名稱和任何相關訊息 (自訂文字) 的資訊。螢幕助讀程式文字協助確保表單可供所有使用者存取，包括視障人士，使他們能夠充分理解表單欄位及其要求。
   - **自訂文字**：選取此選項，以使用 ARIA 協助工具標籤的自訂文字。選取此選項會顯示自訂文字對話框。您可以在自訂文字對話框中新增相關資訊。
   - **說明**：選取此選項，以使用 ARIA 協助工具標籤的說明。
   - **標題**：選取此選項，以使用 ARIA 協助工具標籤的標題。
   - **名稱**：選取此選項，以使用 ARIA 協助工具標籤的名稱。
   - **無**：如果您不想新增 ARIA 協助工具標籤，請選取此選項。

- **螢幕助讀程式播報的 HTML 角色** - HTML 角色是用於向輔助技術 (例如螢幕助讀程式) 指定 HTML 元素用途的屬性。角色屬性可用來提供元素的其他內容脈絡和語義上的涵義，讓螢幕助讀程式更容易向使用者解譯和播報內容。例如，在 AEM Forms 中，表單欄位的標籤可能會具有「標籤」角色，其輸入欄位則可能會具有「文字方塊」的角色。這可協助螢幕助讀程式瞭解標籤和輸入欄位之間的關係，並向使用者正確播報。

## 設計對話框 {#design-dialog}

設計對話框可用於定義和管理面板元件的 CSS 樣式。

### 允許的元件索引標籤 {#allowed-components-tab}

![設定對話框允許的元件索引標籤](/help/adaptive-forms/assets/panel-container-allowed-component.png)

透過&#x200B;**允許的元件**&#x200B;索引標籤，範本編輯器可設定作為項目新增至自適應表單編輯器中元件內面板的元件。

### 預設元件索引標籤 {#default-components-tab}

![設計對話框預設元件索引標籤](/help/adaptive-forms/assets/panel-container-default-component.png)

**預設元件** 索引標籤可讓範本編輯器指定在自適應表單編輯器中，預設顯示為表單容器元件項目的元件。

### 回應式設定索引標籤 {#responsive-tab}

![設計對話框回應式設定索引標籤](/help/adaptive-forms/assets/panel-container-responsive-style-tab.png)

**回應式設定**&#x200B;索引標籤可讓範本編輯器在自適應表單編輯器的表單容器元件中，指定格線中的欄數。

### 容器設定索引標籤

![容器設定索引標籤](/help/adaptive-forms/assets/panel-container-container-settings.png)

- **版面** - 您可以為精靈使用固定版面 (簡單) 或彈性版面 (回應式格線)。「簡單」版面可讓一切固定在原處，而「回應式格線」則可讓您調整元件位置，以符合需求。例如，使用回應式格線在單一列中對齊表單中的「名字」、「中間名」和「姓氏」。

- **停用版面**：選取此選項可停用元件的編輯對話框中的版面選取。

- **啟用背景影像**：此選項可讓使用者設定面板的設定，以包含視覺背景，增強視覺吸引力。

- **啟用背景顏色**：此選項可讓您設定或變更面板的背景顏色。此功能通常用於使用者介面設計，以自訂較大介面內的面板外觀。當您選取&#x200B;**啟用背景顏色**&#x200B;選項時，就會顯示&#x200B;**僅色票**&#x200B;選項。**僅色票**&#x200B;選項可讓您使用&#x200B;**新增**&#x200B;按鈕，為面板中的背景、文字或其他視覺元素指定或選擇色彩

### 樣式索引標籤 {#styles-tab}

自適應表單檔案附件核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話框](/help/adaptive-forms/assets/panel-container-styles-tab.png)

- **預設 CSS 類別**：您可以為自適應表單面板容器核心元件提供預設 CSS 類別。

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性索引標籤

![自訂屬性對話框](/help/adaptive-forms/assets/panel-container-custom-properties.png)

自訂屬性可讓您使用表單範本，將自訂屬性 (鍵值對) 與自適應表單核心元件建立關聯。自訂屬性會反映在元件的無周邊轉譯屬性區段中。可讓您建立根據自訂屬性值調整的動態表單行為。例如，開發人員可以為行動裝置、桌上型電腦或網頁平台設計各種無周邊表單元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱，以識別自訂屬性群組。還可以新增、刪除或重新排列多個自訂屬性群組。新增自訂屬性群組後，您可以看到下列選項：

   - **鍵值對**：按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，即可新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳，以重新排列自訂屬性名稱和自訂屬性值的順序。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}