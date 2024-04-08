---
title: 最適化Forms核心元件 — 面板容器
description: 使用或自訂Adaptive Forms面板容器核心元件。
role: Architect, Developer, Admin, User
exl-id: 104836fe-8325-47de-978d-1ff2d6a9dd15
source-git-commit: f1fce5f661bc7581f7c6c6905f34e9954d1d4f70
workflow-type: tm+mt
source-wordcount: '2052'
ht-degree: 0%

---

# 面板容器 {#panel-container-adaptive-forms-core-component}

在最適化表單中，面板是容器元素，可用來將相關的表單元素群組在一起。 它可讓您以邏輯和有意義的方式分組和組織不同的表單元素。 這有助於改善表單的整體結構和可讀性，讓使用者更容易理解和導覽。

面板也可用來建立可摺疊的區段，這對於隱藏複雜或不常使用的表單欄位很有用，讓表單保持簡單且易於使用。 它也可讓您包含其他元件，例如文字、核取方塊、按鈕等。

它也可用來設定不同的規則型動作，例如提交表單、開啟網站、顯示/隱藏元件，或新增面板的執行個體。

**範例**

![範例](/help/adaptive-forms/assets/panel-container.png)

## 使用情況 {#reasons-to-use-panel-container}

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
| — | — |
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 及更新版本 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

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
<!-- **Allow Rich Text for Title** - This features enables users to format plain text titles, incorporating features like bold, italic, underlined text, various fonts, font sizes, colors, and additional option to enhance visual presentation and customization. It offers greater flexibility and creative control in making titles stand out within documents, websites, or applications.  
    Upon selecting the checkbox for **Allow Rich Text for Title** , formatting options become visible to style the component's title. To access all available formatting options, you can click on the ![Fullscreen icon](/help/adaptive-forms/assets/fullscreen-icon.png) tab.
     
     ![Rich text support](/help/adaptive-forms/assets/richtext-support-title.png) -->

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

- **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。
- **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。
- **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀**  — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 重複面板標籤 {#repeat-panel}

![重複標籤](/help/adaptive-forms/assets/repeat-panel.png)

您可以使用重複性選項來複製面板容器及其子元件、定義最小和最大重複計數，以及簡化表單中類似區段的複製。 與面板容器元件互動並存取其設定時，會顯示下列選項：

- **讓面板可重複**：一種切換功能，可讓使用者啟用或停用重複測量功能。
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

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理表單容器元件的CSS樣式。

### 允許的元件標籤 {#allowed-components-tab}

![設計對話方塊允許的元件索引標籤](/help/adaptive-forms/assets/panel-container-allowed-component.png)

此 **允許的元件** 索引標籤可讓範本編輯器設定元件，這些元件可在最適化Forms編輯器中作為面板的專案新增。

### 預設元件標籤 {#default-components-tab}

![「設計」對話方塊預設元件索引標籤](/help/adaptive-forms/assets/panel-container-default-component.png)

此 **預設元件** 索引標籤可讓範本編輯器指定在調適型Forms編輯器中，預設顯示為表單容器元件專案的元件。

### 回應式設定標籤 {#responsive-tab}

![設計對話方塊回應式設定索引標籤](/help/adaptive-forms/assets/panel-container-responsive-style-tab.png)

此 **回應式設定** 索引標籤可讓範本編輯器在調適型Forms編輯器中指定表單容器元件內格線的欄數。

### 容器設定索引標籤

![容器設定索引標籤](/help/adaptive-forms/assets/panel-container-container-settings.png)

- **版面**  — 您可以為精靈設定固定版面（簡單）或彈性版面（回應式格線）。 「簡單」版面可讓一切固定在原處，而「回應式格線」則可讓您調整元件位置，以符合需求。 例如，使用回應式格線在單一列中對齊表單中的「名字」、「中間名」和「姓氏」。

- **停用配置**：選取此選項可停用元件的「編輯」對話方塊中的版面選擇。

- **啟用背景影像**：此選項可讓使用者設定面板設定，加入視覺背景以增強視覺吸引力。

- **啟用背景顏色**：此選項可讓您設定或變更面板的背景顏色。 此功能通常用於使用者介面設計，以自訂較大介面中面板的外觀。 當您選取 **啟用背景顏色** 選項， **僅限色票** 選項隨即顯示。 此 **僅限色票** 選項可讓您指定或選擇面板中背景、文字或其他視覺元素的顏色，使用 **新增** 按鈕

### 樣式索引標籤 {#styles-tab}

最適化Forms檔案附件核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/panel-container-styles-tab.png)

- **預設CSS類別**：您可以為最適化Forms面板容器核心元件提供預設CSS類別。

- **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性標籤

![自訂屬性對話方塊](/help/adaptive-forms/assets/panel-container-custom-properties.png)

自訂屬性可讓您使用表單範本，將自訂屬性（索引鍵/值組）與最適化表單核心元件建立關聯。 自訂屬性會反映在元件Headless轉譯的properties區段中。 它可讓您建立根據自訂屬性值調整的動態表單行為。 例如，開發人員可以為行動、桌上型電腦或Web平台設計各種無頭Forms元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱來識別自訂屬性群組。 您可以新增、刪除或重新排列多個自訂屬性群組。 新增自訂屬性群組後，您可以看到下列選項：

   - **索引鍵值配對**：您可以按一下「 」，新增多個自訂屬性名稱和自訂屬性值 **新增** 按鈕來設定每個自訂屬性群組。

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