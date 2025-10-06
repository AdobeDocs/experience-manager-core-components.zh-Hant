---
title: 自適應表單核心元件 - 數值輸入
description: 使用或自訂自適應表單數值輸入核心元件。
role: Architect, Developer, Admin, User
exl-id: 75604ecf-1ec5-4e97-b934-d6ed49726147
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '2282'
ht-degree: 100%

---


# 數值方塊元件{#number-input-adaptive-forms-core-component}

自適應表單中的數值方塊元件是一種表單欄位，可讓使用者輸入數值。元件通常以文字欄位表示，並使用向上和向下箭頭遞增和遞減數字。

同樣可以搭配最小值、最大值、步驟、值等屬性使用。這些屬性可用於設定欄位中允許的最小值和最大值、遞增或遞減數字的步驟間隔，以及欄位的預設值。

此元件可用於收集年齡、數量等數值資料。它也可以用來執行數學運算，例如加法和減法。此元件也可用於驗證使用者輸入的數值資料。

對於協助工具，請務必指定「標籤」，以說明數值輸入欄位的用途，以及預期的輸入類型。

{{traditional-aem}}

**範例**

![範例](/help/adaptive-forms/assets/numeric-stepper.png)

## 用途 {#reasons-to-use-number-input-numeric-stepper}

在自適應表單中加入數值輸入元件有多項好處，包括：

- **數學運算**：數值欄位可用來執行數學運算，例如加、減、乘、除。

- **資料範圍**：數值欄位可使用最小值、最大值和步驟屬性來設定有效值的範圍。

- **動態內容**：數值元件可用來根據表單欄位顯示動態資料。

## 版本和相容性 {#version-and-compatibility}

自適應表單數值方塊核心元件於 2023 年 2 月發行，屬於 Cloud Service 核心元件 2.0.4 和 AEM 6.5.16.0 Forms 或更新版本的核心元件 1.1.12 的一部分。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更新版本 |
|---|---|---|
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 與<br>[ 1.1.12 版](/help/adaptive-forms/version.md)及更新版本相容，但低於 2.0.0 版。 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/numberinput/v1/numberinput) 的技術文件中可找到自適應表單數值輸入核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的數值輸入體驗。同樣能夠輕鬆定義數值輸入選項，以提供順暢無礙的使用者體驗。

### 基本索引標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/numberinput_basictab.png)

- **名稱** - 在表單和規則編輯器中，您可以使用其唯一名稱輕鬆識別表單元件，但該名稱不得包含空格或特殊字元。

- **標題** - 您可以使用其標題輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。若未新增標題，則會顯示該元件的名稱而非標題文字。
- **允許標題使用 RTF 文字** - 此功能可讓使用者格式化純文字標題，整合粗體、斜體、底線文字、各種字型、字體大小、顏色等功能，以及可增強視覺呈現和自訂的其他選項。提供更大的靈活性和創意控制，讓標題在文件、網站或應用程式中脫穎而出。\
  選取&#x200B;**允許標題使用 RTF 文字**&#x200B;核取方塊後，即可看到格式選項，以設定元件標題的樣式。若要存取所有可用的格式選項，您可以按一下 ![全螢幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png) 索引標籤。

  ![RTF 文字支援](/help/adaptive-forms/assets/richtext-support-title.png)

- **隱藏標題** - 選取該選項，以隱藏元件標題。
- **預留位置文字** - 表單元件中的預留位置文字是指在輸入欄位中顯示的簡短標籤或提示，用於提示使用者在該欄位中預期輸入的資訊類型。當使用者開始在該欄位中輸入時，預留位置文字會消失，如果欄位留空，則會重新出現。這為使用者提供視覺提示，但不會作為該欄位的永久標籤或值。
- **繫結參考** - 繫結參考是指儲存在外部資料來源，並在表單中使用的資料元素的參考。繫結參考可讓您將資料動態繫結至表單欄位，讓表單可以顯示資料來源的最新資料。例如，繫結參考可用於根據輸入至表單的客戶 ID，在表單中顯示客戶的姓名和地址。繫結參考也可用於使用已輸入至表單中的資料更新資料來源。透過此方式，AEM Forms 可讓您建立與外部資料來源互動的表單，提供順暢無礙的使用者體驗，以收集和管理資料。
- **標示為未繫結的表單元素**：選取該選項，以設定未連結至任何結構描述的表單欄位。此選項可讓您儲存資料，且無需更新資料來源。還可讓您以自訂方式處理資料，不同於標準資料庫整合。
- **隱藏元件** - 選取該選項，以隱藏表單中的元件。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。這在您需要儲存使用者不需看到或直接變更的資訊時十分有用。
- **停用元件** - 選取該選項以停用元件。一般使用者無法啟動或編輯已停用的元件。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀** - 選取讓元件不可編輯的選項使用者可以看到欄位的值，但無法修改它。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。
- **數值類型** - 此選項可讓您選取表單欄位中允許的數值類型。您可以從下拉式選單中選取「小數」或「整數」類型。
- **預設值** - 此選項可讓您在表單欄位中新增預設值。如果選取&#x200B;**已停用的元件**&#x200B;或&#x200B;**唯讀元件**，則畫面會顯示預設值。如果使用者在表單欄位中未輸入值，此值會在表單提交時提交

### 驗證索引標籤 {#validation-tab}

![驗證索引標籤](/help/adaptive-forms/assets/numberinput_validationtab.png)

- **必要** - 若要在自適應表單中顯示該元件，請選取此選項。選取選項後，您必須輸入值才能繼續提交表單。選取此選項後，您無法在&#x200B;**基本**&#x200B;索引標籤中選取&#x200B;**隱藏元件**&#x200B;或&#x200B;**停用元件**。

- **錯誤訊息** - 此選項可讓您輸入訊息，在已勾選&#x200B;**必要**&#x200B;核取方塊且欄位留空時顯示。

- **指令碼驗證訊息** - 此選項可讓您輸入訊息，以在指令碼驗證失敗時顯示。

- **最低數字/最小數字** - 使用此選項可選取在表單欄位中輸入的最小允許數字。如果在表單欄位中輸入小於在&#x200B;**最低數字/最小數字**&#x200B;選項中指定的數字的值，則會出現錯誤訊息。

- **最小錯誤訊息** - 此選項可讓您輸入錯誤訊息，當使用者輸入的值小於&#x200B;**最低數字/最小數字**&#x200B;選項中指定的值時，就會顯示該訊息。

- **排除最小值** - 如果您不希望在表單欄位中輸入值的範圍中包含&#x200B;**最低數字/最小數字**&#x200B;選項中指定的最小值，請選取此核取方塊。

- **最高數字/最大數字** - 使用此選項可選取在表單欄位中輸入的最大允許數字。如果在表單欄位中輸入大於&#x200B;**最高數字/最大數字**&#x200B;選項中指定的數字，則會出現錯誤訊息。

- **最大錯誤訊息** - 此選項可讓您輸入錯誤訊息，當使用者輸入的值高於&#x200B;**最高數字/最大數字**&#x200B;選項中指定的值時，就會顯示該訊息。

- **排除最大值** - 如果您不希望在表單欄位中輸入值的範圍中包含&#x200B;**最高數字/最大數字**&#x200B;選項中指定的最大值，請選取此核取方塊。

### 說明內容索引標籤 {#help-content}

![說明內容索引標籤](/help/adaptive-forms/assets/numberinput_helptab.png)

- **簡短說明** - 簡短說明指的是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。這有助於使用者了解應在該欄位中輸入的資料類型，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。預設情況下，簡短說明會保持隱藏。啟用&#x200B;**永遠顯示簡短說明**&#x200B;選項，使其顯示於元件下方。

- **永遠顯示簡短說明** - 啟用該選項，使簡短說明顯示於元件下方。

- **說明文字** - 說明文字指的是為使用者提供的其他資訊或指引，協助其正確填寫表單欄位。當使用者按一下放置於元件旁的說明圖示 (i) 時，就會出現此選項。說明文字提供的資訊比表單欄位的標籤或預留位置文字更加詳細，旨在協助使用者了解該欄位的要求或限制。還能夠提供建議或範例，使表單填寫更輕鬆、更準確。

### 協助工具索引標籤 {#accessibility}

![協助工具索引標籤](/help/adaptive-forms/assets/numberinput_accessibility.png)

- **螢幕助讀程式文字** - 螢幕助讀程式文字指的是供視障人士所使用的輔助技術 (如螢幕助讀程式) 朗讀的額外文字。此文字提供表單欄位用途的音訊說明，並可包含有關欄位標題、說明、名稱和任何相關訊息 (自訂文字) 的資訊。螢幕助讀程式文字協助確保表單可供所有使用者存取，包括視障人士，使他們能夠充分理解表單欄位及其要求。
   - **自訂文字**：選取此選項，以使用 ARIA 協助工具標籤的自訂文字。選取此選項會顯示自訂文字對話框。您可以在自訂文字對話框中新增相關資訊。
   - **說明**：選取此選項，以使用 ARIA 協助工具標籤的說明。
   - **標題**：選取此選項，以使用 ARIA 協助工具標籤的標題。
   - **名稱**：選取此選項，以使用 ARIA 協助工具標籤的名稱。
   - **無**：如果您不想新增 ARIA 協助工具標籤，請選取此選項。

### 格式索引標籤 {#formats-configure-tab}

![協助工具索引標籤](/help/adaptive-forms/assets/numberinput_formattab.png)

- **顯示格式** - 此選項可讓您從不同的整數數值類型格式中選取選項以供顯示。當使用者從&#x200B;**類型**&#x200B;下拉式選單中選取任何選項時，即可在面板中看到&#x200B;**格式**&#x200B;選項。您可以選擇向使用者顯示數字的特定格式。
- **語言** - 此功能用於格式化特定欄位。當使用者從&#x200B;**類型**&#x200B;下拉式選單選取任何語言選項時，面板中會出現 **IETF BCP 47 語言標記**&#x200B;選項。將自適應表單翻譯成特定語言時，您可以選擇欄位格式化的語言。

預設不會顯示語言集，但使用者可以更新範本原則來輸入自訂 **IETF BCP 47 語言標記**：

1. 在範本編輯器中開啟與自適應表單相關的對應範本。
2. 從下拉式選單中選取現有原則為 `numberinput-default-policy` 。

   ![日期挑選器範本原則](/help/adaptive-forms/assets/numberinput-template-policy.png)

3. 按一下&#x200B;**完成**。

   >[!NOTE]
   >
   > 如需有關如何將自適應表單翻譯為特定地區設定的詳細資訊，[請按一下這裡](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components)。


## 設計對話框 {#design-dialog}

設計對話框可用於定義和管理數值方塊元件的 CSS 樣式。

### 樣式索引標籤 {#styles-tab}

此索引標籤可用於定義和管理元件的 CSS 樣式。自適應表單數值輸入核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![樣式索引標籤](/help/adaptive-forms/assets/datepicker_styletab.png)

- **預設 CSS 類別**：您可以為自適應表單數值方塊核心元件提供預設 CSS 類別。

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話框](/help/adaptive-forms/assets/datepicker_customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性 (鍵值對) 與自適應表單核心元件建立關聯。自訂屬性會反映在元件的無周邊轉譯屬性區段中。可讓您建立根據自訂屬性值調整的動態表單行為。例如，開發人員可以為行動裝置、桌上型電腦或網頁平台設計各種無周邊表單元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱，以識別自訂屬性群組。還可以新增、刪除或重新排列多個自訂屬性群組。新增自訂屬性群組後，您可以看到下列選項：

   - **鍵值對**：按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，即可新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳，以重新排列自訂屬性名稱和自訂屬性值的順序。

### 格式索引標籤 {#formats-tab}

格式索引標籤可讓您指定預設和自訂日期格式。

![格式索引標籤](/help/adaptive-forms/assets/emailinput_formattab.png)

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
