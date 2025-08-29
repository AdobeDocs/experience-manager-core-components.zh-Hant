---
title: 最適化Forms核心元件 — 日期與時間
description: 使用或自訂最適化Forms日期和時間核心元件。
role: Architect, Developer, Admin, User
source-git-commit: daeabccaff39e255c111c6af2540ca4d5be0c709
workflow-type: tm+mt
source-wordcount: '1898'
ht-degree: 0%

---


# 日期與時間元件

最適化表單中的日期和時間元件是使用者介面元素，可讓使用者使用日曆和時鐘介面或透過以特定格式手動輸入值來選取&#x200B;**日期和時間**。 它可確保針對日期和時間都至關重要的使用案例進行準確、標準化的輸入。

**範例**

![範例](/help/adaptive-forms/assets/date-time-picker.png)

## 使用情況 {#reasons-to-use-date-time-picker}

在表單中加入「日期與時間」選擇器有幾個好處，包括：

- **便利性**：讓使用者能夠輕鬆挑選日期和時間，而不需要手動輸入值。
- **一致性**：在整個表單中執行日期與時間輸入的標準格式。
- **改善使用者體驗**：提供直覺式使用者介面，其中包含行事曆和時間選擇器。
- **事件排程**：適用於約會預約、面談或會議排程表單。
- **旅行和預訂**：可讓使用者選取簽到/簽出的日期和時間。
- **資料正確性**：與自由文字輸入相比，可減少輸入錯誤。

## 版本和相容性 {#version-and-compatibility}

最適化Forms日期與時間核心元件於2025年8月&#x200B;**發佈**，屬於Cloud Service適用的&#x200B;**核心元件2.24.6**&#x200B;及更新版本的一部分。

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 與<br>[版本2.24.6](/help/adaptive-forms/version.md)和更新版本相容 | |

如需版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)。

## 技術細節 {#technical-details}

在[GitHub](https://github.com/adobe/aem-core-forms-components)上取得最適化Forms日期與時間核心元件的最新技術詳細資訊。 如需開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 設定對話方塊 {#configure-dialog}

「設定」對話方塊可讓您自訂日期和時間。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/datetime_basictab.png)

- **名稱** — 此名稱可唯一識別規則編輯器中的元件。 名稱字串中不允許特殊字元和空格。

- **標題** — 標題是出現在最適化表單中元件頂端的字串。 標題可唯一識別最適化表單樹狀結構中的元件。 如果您未新增標題，則會顯示元件的名稱而非標題文字。
- **允許標題使用RTF格式** — 此功能可讓使用者格式化純文字標題，並整合如粗體、斜體、底線文字、各種字型、字型大小、顏色等功能以及可增強視覺呈現和自訂的其他選項。 它提供更大的彈性和創意控制，讓標題在檔案、網站或應用程式中脫穎而出。\
  選取&#x200B;**允許標題為RTF格式**&#x200B;的核取方塊後，即可看到格式化選項，以設定元件標題的樣式。 若要存取所有可用的格式選項，您可以按一下![全熒幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png)標籤。

  ![RTF支援](/help/adaptive-forms/assets/richtext-support-title.png)

- **隱藏標題** — 選取此選項可隱藏最適化表單中元件型別的標題。

- **預留位置文字** — 表單元件中的預留位置文字是指在輸入欄位中顯示的簡短標籤或提示，作為使用者在該欄位中預期輸入何種資訊型別的提示。 當使用者開始在欄位中輸入時，預留位置文字消失，如果欄位留空，則會重新出現。 它向使用者提供視覺提示，但不會作為欄位的永久標籤或值。
- **繫結參考** — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。

- **標籤為未繫結的表單元素**：選取選項以設定未連結至任何結構描述的表單欄位。 此選項可讓您儲存資料而不更新資料來源。 它也可讓您以自訂方式處理資料，與標準資料庫整合不同。

- **隱藏元件** — 選取選項，以隱藏表單中的元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。
- **停用元件** — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀** — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
- **預設日期和時間** — 此選項可讓您新增日期和時間到表單欄位。 依預設，輸入的日期會顯示在元件的位置。 如果使用者未輸入日期或時間，則會在提交表單時提交此值。 如果選取&#x200B;**已停用的元件**&#x200B;或&#x200B;**唯讀元件**，預設的日期和時間會顯示在熒幕上，並在表單提交時提交。

### 驗證標籤 {#validation-tab}

![驗證標籤](/help/adaptive-forms/assets/datetime_validation.png)

- **必要** — 如果您想要在最適化表單中顯示元件，請選取此選項。 選取選項後，您必須先進行選取，才能繼續提交表單。 選取此選項時，您無法在&#x200B;**基本**&#x200B;索引標籤中選取&#x200B;**隱藏元件**&#x200B;或&#x200B;**停用元件**。

- **錯誤訊息** — 此選項可讓您輸入在勾選「**必要**」核取方塊並將表單欄位保留空白時顯示的訊息。

- **指令碼驗證訊息** — 此選項可讓您輸入指令碼驗證失敗時顯示的訊息。

- **最小日期** — 此選項可讓您輸入所需的最小日期。 如果您輸入的日期早於在「最小日期與時間」中指定的日期，畫面會顯示錯誤訊息。 **最小錯誤訊息**&#x200B;對話方塊可讓您新增自訂錯誤訊息。

- **最小錯誤訊息** — 如果您輸入的日期或時間早於&#x200B;**最小日期**&#x200B;選項中指定的日期或時間，則&#x200B;**最小錯誤訊息**&#x200B;對話方塊可讓您新增要顯示的自訂錯誤訊息。

- **最大日期** — 此選項可讓您輸入所需的最長日期和時間。 如果您輸入的日期或時間晚於「最大日期」中指定的日期或時間，畫面會顯示錯誤訊息。 **最大錯誤訊息**&#x200B;對話方塊可讓您新增自訂錯誤訊息。

- **錯誤訊息上限** — 如果您輸入的日期或時間晚於&#x200B;**最大日期**&#x200B;選項中指定的日期或時間，則&#x200B;**錯誤訊息上限**&#x200B;對話方塊可讓您新增要顯示的自訂錯誤訊息。

### 說明內容標籤 {#help-content-tab}

![說明內容標籤](/help/adaptive-forms/assets/datetime_helptab.png)

- **簡短說明** — 簡短說明是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用&#x200B;**永遠顯示簡短描述**&#x200B;選項，以在元件下方顯示它。

- **永遠顯示簡短描述** — 啟用選項以在元件下方顯示簡短描述。

- **說明文字** — 說明文字是指提供給使用者的其他資訊或指引，以協助使用者正確填寫表單欄位。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。


### 協助工具標籤 {#accessibility-tab}

![協助工具標籤](/help/adaptive-forms/assets/datetime_accessibilitytab.png)

- **熒幕助讀程式文字** — 熒幕助讀程式文字是指視力不佳人士使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。
   - **自訂文字**：選取此選項即可使用ARIA協助工具標籤的自訂文字。 選取此選項會顯示「自訂文字」對話方塊。 您可以在「自訂文字」對話方塊中新增相關資訊。
   - **說明**：選取此選項即可使用ARIA協助工具標籤的說明。
   - **標題**：選取此選項即可使用ARIA協助工具標籤的標題。
   - **名稱**：選取此選項即可使用ARIA協助工具標籤的名稱。
   - **無**：如果您不想新增ARIA協助工具標籤，請選取此選項。

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

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理日期和時間元件的CSS樣式。

### 樣式索引標籤 {#styles-tab}

索引標籤可用來定義和管理元件的CSS樣式。 最適化Forms日期和時間核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![樣式標籤](/help/adaptive-forms/assets/datepicker_styletab.png)

- **預設CSS類別**：您可以為最適化Forms日期和時間核心元件提供預設CSS類別。

- **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至屬性對話方塊，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話方塊](/help/adaptive-forms/assets/datepicker_customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性（索引鍵/值組）與最適化表單核心元件建立關聯。 自訂屬性會反映在元件Headless轉譯的properties區段中。 它可讓您建立根據自訂屬性值調整的動態表單行為。 例如，開發人員可以為行動、桌上型電腦或Web平台設計各種無頭Forms元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供一個名稱來識別自訂屬性群組。 您可以新增、刪除或重新排列多個自訂屬性群組。 新增自訂屬性群組後，您可以看到下列選項：

   - **索引鍵 — 值配對**：您可以按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，以新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳以重新排列自訂屬性名稱和自訂屬性值。

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


