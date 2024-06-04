---
title: 最適化表單片段
description: 使用表單片段建立表單片段或欄位群組，並在最適化Forms中重複使用，以提高效率和可重複使用性。
role: Architect, Developer, Admin, User
exl-id: bde4a416-1d6b-4e9e-ac74-70fccef473cb
source-git-commit: 4c510b8fe59f4be6e1b329ee4257ab1b780fbf22
workflow-type: tm+mt
source-wordcount: '1954'
ht-degree: 1%

---

# 最適化表單片段元件 {#form-fragment-component-adaptive-forms-core-component}

最適化Forms提供建立表單區段（例如面板或欄位群組）的便利方式，以便這些區段能在不同的最適化Forms中重複使用。 這些可重複使用的獨立區段稱為 [最適化表單片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/adaptive-form-fragments-core-components.html).

您可以 [將片段新增至檔案多次](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/adaptive-form-fragments-core-components.html#insert-a-fragment-in-an-adaptive-form) 並使用其元件的資料繫結屬性將其繫結至不同的資料來源或結構描述。 例如，您可以將相同的地址片段用於永久、通訊和帳單地址，並將其連線到資料來源或結構的不同欄位。

![範例](/help/adaptive-forms/assets/using-multiple-fragment-af.gif)


您也可以使用 [重複選項](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html) 若要複製表單片段元件及其子元件，請定義最小和最大重複計數，並促進表單中類似區段的複製。

>[!NOTE]
>
> 您可以 [建立自適應表單片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/adaptive-form-fragments-core-components.html#create-a-fragment) 從頭開始或將現有Adaptive Form中的面板另存為片段。

## 使用情況 {#usage}

- **可重複使用**：在多個最適化Forms中重複使用表單片段的能力是使用表單片段的主要優點。 它有助於保持設計和功能的一致性，因為對片段所做的變更會反映在使用片段的所有例項中。

- **一致的使用者體驗**：將表單片段用於常見元素，例如頁首或頁尾，可確保一致和連貫的使用者體驗。

- **輕鬆維護**：對表單片段進行的變更或修改會反映在使用它的所有執行個體中。 它可簡化維護作業，並降低錯誤發生率。

- **效率**：設計人員和開發人員只需建置和測試表單片段一次，即可節省時間。 然後，這些表單片段就可以輕鬆整合到多個最適化Forms中，而無需進行多餘的工作。

## 版本和相容性 {#version-and-compatibility}

Adaptive Forms片段核心元件已發行為Cloud Service核心元件2.0.50的一部分，以及AEM 6.5.16.0 Forms或更新版本的核心元件1.1.26。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[發行版本2.0.50](/help/adaptive-forms/version.md) 及更新版本 | 相容於<br>[第1.1.26發行版本](/help/adaptive-forms/version.md) 和較新版本，但小於2.0.0。 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

## 技術細節 {#technical-details}

在的技術檔案中取得最適化Forms片段核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/fragment). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的片段體驗。 您也可以輕鬆定義片段屬性，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/fragment-basictab.png)

- **名稱**  — 在表單和規則編輯器中，您可以使用表單元件的唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

- **標題**  — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。
- **允許標題使用RTF文字**  — 此功能可讓使用者格式化純文字標題，並整合如粗體、斜體、底線文字、各種字型、字型大小、顏色，以及其他可增強視覺呈現和自訂的選項。 它提供更大的彈性和創意控制，讓標題在檔案、網站或應用程式中脫穎而出。\
  選取「 」的核取方塊時 **允許標題使用RTF文字** ，可顯示格式選項以設定元件標題的樣式。 若要存取所有可用的格式選項，您可以按一下 ![全熒幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png) 標籤。

  ![RTF支援](/help/adaptive-forms/assets/richtext-support-title.png)

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

- **片段引用**  — 片段參考是儲存在外部資料來源中並在表單中使用的表單片段的參考。 片段參考可讓您動態地將表單片段繫結至表單。

- **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。

- **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。
- **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀**  — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 重複片段標籤 {#repeat-tab}

![重複片段標籤](/help/adaptive-forms/assets/fragment-repeattab.png)

- **讓片段可重複**：一種切換功能，可讓使用者啟用或停用重複測量功能。
- **最小重複次數**：建立片段元件可重複的最小次數。 零值表示不重複片段元件；預設值為零。
- **最大重複次數**：設定片段元件可重複的最大次數。 預設情況下，此值為無限制。

### 說明內容標籤 {#help-content}

![說明內容標籤](/help/adaptive-forms/assets/fragment-helptab.png)

- **簡短說明**  — 簡短說明是簡短文字說明，提供有關特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用 **一律顯示簡短說明** 選項來在元件下方顯示它。

- **一律顯示簡短說明**  — 啟用選項以在元件下方顯示簡短說明。

- **說明文字**  — 說明文字是指為協助使用者正確填寫表單欄位而提供的其他資訊或指引。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。

### 親和力 {#accessibility}

![協助工具標籤](/help/adaptive-forms/assets/fragment-accessibilitytab.png)

- **熒幕助讀程式的文字**  — 熒幕助讀程式文字是指視力受損者使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。
   - **自訂文字**：選取此選項以使用自訂文字做為ARIA協助工具標籤。 選取此選項會顯示「自訂文字」對話方塊。 您可以在「自訂文字」對話方塊中新增相關資訊。
   - **說明**：選取此選項即可使用ARIA協助工具標籤的說明。
   - **標題**：選取此選項以使用ARIA協助工具標籤的標題。
   - **名稱**：選取此選項即可使用ARIA協助工具標籤的名稱。
   - **無**：如果您不想要新增ARIA協助工具標籤，請選取此選項。

- **熒幕助讀程式宣告的HTML角色** -HTML角色是一種屬性，用來指定HTML元素對輔助技術（例如熒幕閱讀程式）的用途。 角色屬性可用來提供元素的其他上下文和語意意義，讓熒幕朗讀程式更容易向使用者解譯和宣告內容。 例如，在AEM Forms中，表單欄位的標籤可能會具有「label」角色，而其輸入欄位的角色可能會具有「textbox」。 這可協助熒幕助讀程式瞭解標籤和輸入欄位之間的關係，並向使用者正確宣告。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理表單片段元件的CSS樣式。

### 樣式索引標籤 {#styles-tab}

最適化表單片段核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/checkbox-style.png)

- **預設CSS類別**：您可以為最適化表單片段核心元件提供預設CSS類別。

- **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話方塊](/help/adaptive-forms/assets/checkbox-customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性（索引鍵/值組）與最適化表單核心元件建立關聯。 自訂屬性會反映在元件Headless轉譯的properties區段中。 它可讓您建立根據自訂屬性值調整的動態表單行為。 例如，開發人員可以為行動、桌上型電腦或Web平台設計各種無頭Forms元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱來識別自訂屬性群組。 您可以新增、刪除或重新排列多個自訂屬性群組。 新增自訂屬性群組後，您可以看到下列選項：

   - **索引鍵值配對**：您可以按一下「 」，新增多個自訂屬性名稱和自訂屬性值 **新增** 按鈕來設定每個自訂屬性群組。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳以重新排列自訂屬性名稱和自訂屬性值。


## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
