---
title: 自適應表單核心元件 - 日期和時間
description: 使用或自訂自適應表單日期和時間核心元件。
role: Architect, Developer, Admin, User
exl-id: 74140dca-d831-487c-8e78-e13769f63922
source-git-commit: 006f6c844ab9e7a784dabea026867939445479e9
workflow-type: ht
source-wordcount: '1898'
ht-degree: 100%

---

# 日期和時間元件

自適應表單中的日期和時間元件是一種使用者介面元素，讓使用者可以利用日曆和時鐘介面來選取&#x200B;**日期和時間**，或依照特定格式手動輸入值。對於日期和時間兩者均極為重要的使用案例，此元素可確保準確輸入標準化的值。

**範例**

![範例](/help/adaptive-forms/assets/date-time-picker.png)

## 用途 {#reasons-to-use-date-time-picker}

在表單中加入日期和時間挑選器會很有幫助，其中包括幾個原因：

- **便利性**：讓使用者輕鬆地挑選日期和時間，無需手動輸入值。
- **一致性**：對整個表單中的日期和時間輸入採用標準格式。
- **改善使用者體驗**：使用日曆和時間選擇器，讓使用者介面變得簡單易用。
- **事件排程**：在預約、面談或會議排程表單中很實用。
- **旅行和預訂**：讓使用者可以選取入住/退房的日期和時間。
- **資料準確性**：減少輸入錯誤，優於自由文字輸入。

## 版本和相容性 {#version-and-compatibility}

自適應表單日期和時間核心元件已於 **2025 年 8 月**&#x200B;發佈，作為 Cloud Service **核心元件 2.24.6**&#x200B;及以上版本的一部分。

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更新版本 |
|---|---|---|
| v1 | 與 <br>[2.24.6 ](/help/adaptive-forms/version.md)及以上版本相容 | |

如需版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)。

## 技術詳細資訊 {#technical-details}

在 [GitHub](https://github.com/adobe/aem-core-forms-components) 上取得關於自適應表單日期和時間核心元件的最新技術詳細資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

您可以使用「設定」對話框來自訂日期和時間。

### 基本索引標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/datetime_basictab.png)

- **名稱** - 此名稱可唯一識別規則編輯器中的元件。名稱字串中不允許特殊字元和空格。

- **標題** - 標題是出現在自適應表單中元件頂端的字串。標題可唯一識別自適應表單樹狀結構中的元件。若未新增標題，則會顯示該元件的名稱而非標題文字。
- **允許標題使用 RTF 文字** - 此功能可讓使用者格式化純文字標題，整合粗體、斜體、底線文字、各種字型、字體大小、顏色等功能，以及可增強視覺呈現和自訂的其他選項。提供更大的靈活性和創意控制，讓標題在文件、網站或應用程式中脫穎而出。\
  選取&#x200B;**允許標題使用 RTF 文字**&#x200B;核取方塊後，即可看到格式選項，以設定元件標題的樣式。若要存取所有可用的格式選項，您可以按一下 ![全螢幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png) 索引標籤。

  ![RTF 文字支援](/help/adaptive-forms/assets/richtext-support-title.png)

- **隱藏標題** - 選取此選項可隱藏自適應表單中元件類型的標題。

- **預留位置文字** - 表單元件中的預留位置文字是指在輸入欄位中顯示的簡短標籤或提示，用於提示使用者在該欄位中預期輸入的資訊類型。當使用者開始在該欄位中輸入時，預留位置文字會消失，如果欄位留空，則會重新出現。這為使用者提供視覺提示，但不會作為該欄位的永久標籤或值。
- **繫結參考** - 繫結參考是指儲存在外部資料來源，並在表單中使用的資料元素的參考。繫結參考可讓您將資料動態繫結至表單欄位，讓表單可以顯示資料來源的最新資料。例如，繫結參考可用於根據輸入至表單的客戶 ID，在表單中顯示客戶的姓名和地址。繫結參考也可用於使用已輸入至表單中的資料更新資料來源。透過此方式，AEM Forms 可讓您建立與外部資料來源互動的表單，提供順暢無礙的使用者體驗，以收集和管理資料。

- **標示為未繫結的表單元素**：選取該選項，以設定未連結至任何結構描述的表單欄位。此選項可讓您儲存資料，且無需更新資料來源。還可讓您以自訂方式處理資料，不同於標準資料庫整合。

- **隱藏元件** - 選取該選項，以隱藏表單中的元件。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。這在您需要儲存使用者不需看到或直接變更的資訊時十分有用。
- **停用元件** - 選取該選項以停用元件。一般使用者無法啟動或編輯已停用的元件。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀** - 選取該選項，使元件無法編輯。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。
- **預設日期和時間** - 您可以使用此選項對表單欄位新增日期和時間。根據預設，輸入的日期會顯示在元件位置。若使用者未輸入日期或時間，則在提交表單時會提交這個值。如果選取「**停用元件**」或「**唯讀元件**」，則預設日期和時間會顯示在畫面上，並在表單提交時提交。

### 驗證索引標籤 {#validation-tab}

![驗證索引標籤](/help/adaptive-forms/assets/datetime_validation.png)

- **必要** - 若要在自適應表單中顯示該元件，請選取此選項。選取該選項後，必須先進行選取，才能繼續提交表單。選取此選項後，您無法在&#x200B;**基本**&#x200B;索引標籤中選取&#x200B;**隱藏元件**&#x200B;或&#x200B;**停用元件**。

- **錯誤訊息** - 此選項可讓您輸入訊息，在已勾選&#x200B;**必要**&#x200B;核取方塊且表單欄位留空時顯示。

- **指令碼驗證訊息** - 此選項可讓您輸入訊息，以在指令碼驗證失敗時顯示。

- **最小日期** - 此選項可讓您輸入所要求的最早日期。如果您輸入的日期早於「最早日期和時間」中的指定日期，畫面上便會顯示錯誤訊息。您可以透過「**最早日期錯誤訊息**」對話框來新增自訂錯誤訊息。

- **最早日期錯誤訊息** - 「**最早日期錯誤訊息**」對話框讓您新增自訂錯誤訊息，若您輸入的日期或時間早於「**最早日期**」選項中指定的日期或時間，便會顯示此自訂錯誤訊息。

- **最晚日期** - 您可以透過此選項輸入所要求的最晚日期和時間。如果您輸入的日期或時間晚於「最晚日期」中指定的日期或時間，畫面上便會顯示錯誤訊息。您可以透過「**最晚日期錯誤訊息**」對話框新增自訂錯誤訊息。

- **最晚日期錯誤訊息** -「**最晚日期錯誤訊息**」對話框讓您新增自訂錯誤訊息，若您輸入的日期或時間晚於「**最晚日期**」選項中指定的日期或時間，便會顯示此自訂錯誤訊息。

### 說明內容索引標籤 {#help-content-tab}

![說明內容索引標籤](/help/adaptive-forms/assets/datetime_helptab.png)

- **簡短說明** - 簡短說明指的是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。這有助於使用者了解應在該欄位中輸入的資料類型，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。預設情況下，簡短說明會保持隱藏。啟用&#x200B;**永遠顯示簡短說明**&#x200B;選項，使其顯示於元件下方。

- **永遠顯示簡短說明** - 啟用該選項，使簡短說明顯示於元件下方。

- **說明文字** - 說明文字指的是為使用者提供的其他資訊或指引，協助其正確填寫表單欄位。當使用者按一下放置於元件旁的說明圖示 (i) 時，就會出現此選項。說明文字提供的資訊比表單欄位的標籤或預留位置文字更加詳細，旨在協助使用者了解該欄位的要求或限制。還能夠提供建議或範例，使表單填寫更輕鬆、更準確。


### 協助工具索引標籤 {#accessibility-tab}

![協助工具索引標籤](/help/adaptive-forms/assets/datetime_accessibilitytab.png)

- **螢幕助讀程式文字** - 螢幕助讀程式文字指的是專門供視障人士所使用的輔助技術 (如螢幕助讀程式) 朗讀的額外文字。此文字提供表單欄位用途的音訊說明，並可包含有關欄位標題、說明、名稱和任何相關訊息 (自訂文字) 的資訊。螢幕助讀程式文字協助確保表單可供所有使用者存取，包括視障人士，使他們能夠充分理解表單欄位及其要求。
   - **自訂文字**：選取此選項，以使用 ARIA 協助工具標籤的自訂文字。選取此選項會顯示自訂文字對話框。您可以在自訂文字對話框中新增相關資訊。
   - **說明**：選取此選項，以使用 ARIA 協助工具標籤的說明。
   - **標題**：選取此選項，以使用 ARIA 協助工具標籤的標題。
   - **名稱**：選取此選項，以使用 ARIA 協助工具標籤的名稱。
   - **無**：如果您不想新增 ARIA 協助工具標籤，請選取此選項。

<!--
### Formats Tab {#format-tab}

![Formats tab](/help/adaptive-forms/assets/datepicker_formattab.png)

-   **Display Format** - It represents the date format that is displayed to the user. The **Type** option allows the user to select the date format. You can also customize the date format using the **Custom** option in the **Type** dropdown menu.

-   **Edit Format** - It represents a date format in which the user can edit the date. The **Type** option allows the user to select the date format. You can also customize the date format using the **Custom** option in the **Type** dropdown menu.
-  **Format error message** - This option allows you to enter the message displayed on the screen when the entered date is not in the correct format.
- **Language** - This feature is used for formatting the specific field. When a user selects any language option from the **Type** drop-down menu, the **IETF BCP 47 language tag** option appears in the panel. You can choose the language for field formatting when translating an Adaptive Form into a specific language.
  
The set of languages is not visible by default, but users can input a custom **IETF BCP 47 language tag** by updating the template policy:

  1. Open the corresponding template associated with an Adaptive Form in the template editor.
  2. Select the existing policy as `datepicker-default-policy` from the drop-down menu.
   
        ![Date Picker template Policy](/help/adaptive-forms/assets/date-picker-template-policy.png)

  3. Click **Done**.

        >[!NOTE]
        >
        > For further information on how to translate an Adaptive Form to a specific locale, [click here](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components).
-->

## 設計對話框 {#design-dialog}

您可以使用「設計」對話框來定義及管理日期和時間元件的 CSS 樣式。

### 樣式索引標籤 {#styles-tab}

此索引標籤可用於定義和管理元件的 CSS 樣式。自適應表單日期和時間核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![樣式索引標籤](/help/adaptive-forms/assets/datepicker_styletab.png)

- **預設 CSS 類別**：您可以為自適應表單日期和時間核心元件提供預設 CSS 類別。

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話框](/help/adaptive-forms/assets/datepicker_customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性 (鍵值對) 與自適應表單核心元件建立關聯。自訂屬性會反映在元件的無周邊轉譯屬性區段中。可讓您建立根據自訂屬性值調整的動態表單行為。例如，開發人員可以為行動裝置、桌上型電腦或網頁平台設計各種無周邊表單元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱，以識別自訂屬性群組。還可以新增、刪除或重新排列多個自訂屬性群組。新增自訂屬性群組後，您可以看到下列選項：

   - **鍵值對**：按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，即可新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳，以重新排列自訂屬性名稱和自訂屬性值的順序。

<!--
### Formats Tab {#formats-tab}

The formats tab allows you to specify default and custom date formats.

![Formattab](/help/adaptive-forms/assets/datepicker_formatpolicy.png)



## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
