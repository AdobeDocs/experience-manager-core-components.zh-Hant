---
title: 自適應表單片段
description: 使用表單片段建立表單區段或欄位群組，並在自適應表單中重複使用，從而提高效率和可重複使用性。
role: Architect, Developer, Admin, User
exl-id: bde4a416-1d6b-4e9e-ac74-70fccef473cb
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '1952'
ht-degree: 100%

---


# 自適應表單片段元件 {#form-fragment-component-adaptive-forms-core-component}

自適應表單提供建立表單區段 (例如面板或欄位群組) 的便利方式，以便這些區段能在不同的自適應表單中重複使用。這些可重複使用的獨立區段即稱為[自適應表單片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/adaptive-form-fragments-core-components.html)。

您可以[多次將片段新增至文件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/adaptive-form-fragments-core-components.html#insert-a-fragment-in-an-adaptive-form)，並使用其元件的資料繫結屬性將其繫結到不同的資料來源或結構描述。例如，您可以將相同的地址片段用於永久、通訊和帳單地址，並將其連接到資料來源或結構描述的不同欄位。

![範例](/help/adaptive-forms/assets/using-multiple-fragment-af.gif)


您也可以使用[重複性選項](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html)來複製表單片段元件及其下層元件、定義最小和最大重複計數，以及簡化表單中類似區段的複寫。

>[!NOTE]
>
> 您可以從頭開始[建立自適應表單片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/adaptive-form-fragments-core-components.html#create-a-fragment)，或將現有自適應表單中的面板儲存為片段。

{{traditional-aem}}

## 用途 {#usage}

- **可重複使用**：能夠跨多個自適應表單重複使用表單片段是使用表單片段的主要優點。它有助於保持設計和功能的一致性，因為對片段所做的變更會反映在使用片段的所有執行個體中。

- **一致的使用者體驗**：將表單片段用於一般元素 (例如頁首或頁尾)，可確保一致且連貫的使用者體驗。

- **輕鬆維護**：對表單片段所做的變更或修改會反映在使用它的所有執行個體中。它可簡化維護作業，並降低錯誤發生率。

- **效率**：設計人員和開發人員只須建置和測試表單片段一次，因此能節省時間。然後，這些表單片段就可以輕鬆整合到多個自適應表單中，而無需進行多餘的工作。

## 版本和相容性 {#version-and-compatibility}

自適應表單檔案片段核心元件作為 Cloud Service 核心元件 2.0.50 和 AEM 6.5.16.0 Forms 或更新版本核心元件 1.1.26 的一部分發行。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更新版本 |
|---|---|---|
| v1 | 與<br>[ 2.0.50 版](/help/adaptive-forms/version.md)及更新版本相容 | 與<br>[ 1.1.26 版](/help/adaptive-forms/version.md)及更新版本相容，但低於 2.0.0 版。 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/fragment) 的技術文件中可找到自適應表單片段核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的片段體驗。同樣能夠輕鬆定義片段屬性，以提供順暢無礙的使用者體驗。

### 基本索引標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/fragment-basictab.png)

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

- **片段參考** - 片段參考是儲存在外部資料來源中，並在表單中使用的表單片段的參考。片段參考可讓您將表單片段動態繫結至表單。

- **繫結參考** - 繫結參考是指儲存在外部資料來源，並在表單中使用的資料元素的參考。繫結參考可讓您將資料動態繫結至表單欄位，讓表單可以顯示資料來源的最新資料。例如，繫結參考可用於根據輸入至表單的客戶 ID，在表單中顯示客戶的姓名和地址。繫結參考也可用於使用已輸入至表單中的資料更新資料來源。透過此方式，AEM Forms 可讓您建立與外部資料來源互動的表單，提供順暢無礙的使用者體驗，以收集和管理資料。

- **隱藏元件** - 選取該選項，以隱藏表單中的元件。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。這在您需要儲存使用者不需看到或直接變更的資訊時十分有用。
- **停用元件** - 選取該選項以停用元件。一般使用者無法啟動或編輯已停用的元件。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀** - 選取該選項，使元件無法編輯。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。

### 重複片段索引標籤 {#repeat-tab}

![重複片段索引標籤](/help/adaptive-forms/assets/fragment-repeattab.png)

- **設定片段可重複**：切換功能，可讓使用者啟用或停用重複功能。
- **最小重複次數**：建立片段元件可重複的最小次數。值為零表示片段元件不會重複；預設值為零。
- **最大重複次數**：設定片段元件可重複的最大次數。預設情況下，此值為無限制。

### 說明內容索引標籤 {#help-content}

![說明內容索引標籤](/help/adaptive-forms/assets/fragment-helptab.png)

- **簡短說明** - 簡短說明指的是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。這有助於使用者了解應在該欄位中輸入的資料類型，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。預設情況下，簡短說明會保持隱藏。啟用&#x200B;**永遠顯示簡短說明**&#x200B;選項，使其顯示於元件下方。

- **永遠顯示簡短說明** - 啟用該選項，使簡短說明顯示於元件下方。

- **說明文字** - 說明文字指的是為使用者提供的其他資訊或指引，協助其正確填寫表單欄位。當使用者按一下放置於元件旁的說明圖示 (i) 時，就會出現此選項。說明文字提供的資訊比表單欄位的標籤或預留位置文字更加詳細，旨在協助使用者了解該欄位的要求或限制。還能夠提供建議或範例，使表單填寫更輕鬆、更準確。

### 協助工具 {#accessibility}

![協助工具索引標籤](/help/adaptive-forms/assets/fragment-accessibilitytab.png)

- **螢幕助讀程式文字** - 螢幕助讀程式文字指的是專門供視障人士所使用的輔助技術 (如螢幕助讀程式) 朗讀的額外文字。此文字提供表單欄位用途的音訊說明，並可包含有關欄位標題、說明、名稱和任何相關訊息 (自訂文字) 的資訊。螢幕助讀程式文字協助確保表單可供所有使用者存取，包括視障人士，使他們能夠充分理解表單欄位及其要求。
   - **自訂文字**：選取此選項，以使用 ARIA 協助工具標籤的自訂文字。選取此選項會顯示自訂文字對話框。您可以在自訂文字對話框中新增相關資訊。
   - **說明**：選取此選項，以使用 ARIA 協助工具標籤的說明。
   - **標題**：選取此選項，以使用 ARIA 協助工具標籤的標題。
   - **名稱**：選取此選項，以使用 ARIA 協助工具標籤的名稱。
   - **無**：如果您不想新增 ARIA 協助工具標籤，請選取此選項。

- **螢幕助讀程式播報的 HTML 角色** - HTML 角色是用於向輔助技術 (例如螢幕助讀程式) 指定 HTML 元素用途的屬性。角色屬性可用來提供元素的其他內容脈絡和語義上的涵義，讓螢幕助讀程式更容易向使用者解譯和播報內容。例如，在 AEM Forms 中，表單欄位的標籤可能會具有「標籤」角色，其輸入欄位則可能會具有「文字方塊」的角色。這可協助螢幕助讀程式瞭解標籤和輸入欄位之間的關係，並向使用者正確播報。

## 設計對話框 {#design-dialog}

設計對話框可用於定義和管理表單片段元件的 CSS 樣式。

### 樣式索引標籤 {#styles-tab}

自適應表單片段核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話框](/help/adaptive-forms/assets/checkbox-style.png)

- **預設 CSS 類別**：您可以為自適應表單表單片段核心元件提供預設 CSS 類別。

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話框](/help/adaptive-forms/assets/checkbox-customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性 (鍵值對) 與自適應表單核心元件建立關聯。自訂屬性會反映在元件的無周邊轉譯屬性區段中。可讓您建立根據自訂屬性值調整的動態表單行為。例如，開發人員可以為行動裝置、桌上型電腦或網頁平台設計各種無周邊表單元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱，以識別自訂屬性群組。還可以新增、刪除或重新排列多個自訂屬性群組。新增自訂屬性群組後，您可以看到下列選項：

   - **鍵值對**：按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，即可新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳以重新排列自訂屬性名稱和自訂屬性值。


## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
