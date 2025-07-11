---
title: 最適化Forms核心元件 — 選項按鈕
description: 使用或自訂最適化Forms選項按鈕核心元件。
role: Architect, Developer, Admin, User
exl-id: 86b5e9ec-58ac-4cd5-9c7c-4269247ec34f
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '2135'
ht-degree: 0%

---


# 選項按鈕元件 {#radio-button-adaptive-forms-core-component}

最適化表單中的選項按鈕是一種輸入元素，可讓使用者從一組相關選項中選取一個選項。 它由一個小的圓形按鈕表示，該按鈕已填滿或空白，以指示是否選取該選項。 當使用者選取一個選項按鈕時，群組中的其他按鈕會變為取消選取。 當有多個互斥選項且一次只能選取一個選項時，通常會使用選項按鈕。

{{traditional-aem}}

**範例**

![範例](/help/adaptive-forms/assets/radio-button.png)

**屬性對話方塊**

![範例](/help/adaptive-forms/assets/radio-button-properties.png)

在此範例中，Options元素用於將選項按鈕群組在一起。 **顯示文字**&#x200B;專案是用來提供專案的標籤，而&#x200B;**資料值**&#x200B;是用來指定提交表單時傳送至伺服器的值。

每個選項按鈕選項都有唯一的「資料」值和「顯示文字」屬性。 如果使用者選取「1-10」，則表單提交時會將對應的資料值傳送到伺服器。 接著，伺服器端指令碼可處理此資料，以判斷使用者選取的選項，且可用於執行各種動作，例如更新表單中的其他欄位，或將表單資料提交至伺服器端指令碼以供進一步處理。

此外，每個選項按鈕都可設定為每個選項提供不同的處理值，並可使用最適化Forms規則編輯器進行設定

## 使用情況 {#reasons-to-use-radio-button}

在表單中使用選項按鈕有幾個理由，包括：

- **有限選擇**：選項按鈕是用來提供預先定義的選項清單，供使用者選擇，一次只能選取一個選項。 當選項的數量有限且互斥時，此選項會很有用。

- **清除表示方式**：選項按鈕清晰易懂，讓使用者可以輕鬆瞭解選取的內容。

- **一致性**：使用選項按鈕可確保向使用者呈現選項時採用一致且標準化的方式，讓他們更容易理解表單並與之互動。

- **更易於使用**：選項按鈕易於使用，尤其是不熟悉技術或行動能力有限的使用者。

## 版本和相容性 {#version-and-compatibility}

最適化Forms選項按鈕核心元件於2023年2月發行，屬於Cloud Service核心元件2.0.4以及AEM 6.5.16.0 Forms或更新版本的核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 與<br>[版本2.0.4](/help/adaptive-forms/version.md)和更新版本相容 | 與<br>[版本1.1.12](/help/adaptive-forms/version.md)及更新版本相容，但小於2.0.0。 |

如需核心元件版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_tw). -->

## 技術細節 {#technical-details}

在[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/radiobutton/v1/radiobutton)的技術檔案中取得最適化Forms選項按鈕核心元件的最新資訊。 如需開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的單選按鈕體驗。 您也可以輕鬆定義選項按鈕選項，以提供順暢的使用者體驗。

### 基本索引標籤

![基本索引標籤](/help/adaptive-forms/assets/radiobutton_basictab.png)

- **名稱** — 您可以在表單和規則編輯器中輕鬆識別具有唯一名稱的表單元件，但名稱不得包含空格或特殊字元。

- **標題** — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。
- **允許標題使用RTF格式** — 此功能可讓使用者格式化純文字標題，並整合如粗體、斜體、底線文字、各種字型、字型大小、顏色等功能以及可增強視覺呈現和自訂的其他選項。 它提供更大的彈性和創意控制，讓標題在檔案、網站或應用程式中脫穎而出。\
  選取&#x200B;**允許標題為RTF格式**&#x200B;的核取方塊後，即可看到格式化選項，以設定元件標題的樣式。 若要存取所有可用的格式選項，您可以按一下![全熒幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png)標籤。

  ![RTF支援](/help/adaptive-forms/assets/richtext-support-title.png)

- **隱藏標題** — 選取隱藏元件標題的選項。

- **選項** — 您可以使用&#x200B;**新增**&#x200B;按鈕來新增資料值並顯示文字組。\
  新增選項後，可以執行下列動作：
   - **資料值** — 此選項可讓您在選取選項時，輸入要送出的內容。
   - **顯示文字** — 此選項可讓您輸入要在最適化表單中顯示的內容。
   - **刪除** — 點選或按一下以刪除選項按鈕的選項。
   - **重新排列** — 點選或按一下並拖曳以重新排列選項。
您也可以使用&#x200B;**允許選項的RTF格式**&#x200B;來格式化選項群組選項。

  選項的![RTF支援](/help/adaptive-forms/assets/richtext-for-options.png)

  選取&#x200B;**允許RTF格式選項**&#x200B;的核取方塊後，元件選項的樣式就會顯示出來。 若要存取所有可用的格式選項，您可以按一下`Fullscreen` ![全熒幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png)標籤。

  選項的![RTF支援](/help/adaptive-forms/assets/richtextoptions-support.png)

- **繫結參考** — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。

- **標籤為未繫結的表單元素**：選取選項以設定未連結至任何結構描述的表單欄位。 此選項可讓您儲存資料而不更新資料來源。 它也可讓您以自訂方式處理資料，與標準資料庫整合不同。

- **提交值的資料型別** — 此選項會指定選取任何選項時傳送值的資料型別。 如果提交值&#x200B;**的**&#x200B;資料型別設定為`Number`，而您在&#x200B;**選項**&#x200B;索引標籤&#x200B;上新增字串資料至&#x200B;**資料值**&#x200B;，畫面會顯示`Value type mismatch`錯誤訊息。

- **預設選項** — 此選項可讓您在表單載入時新增預先選取的預設值。 如果提交值&#x200B;**的**&#x200B;資料型別設定為`Number`，而您新增字串資料至&#x200B;**預設選項**，畫面會顯示`Value type mismatch`錯誤訊息。

- **顯示選項** — 此選項是用來設定最適化表單中選項按鈕的視覺對齊方式。 支援的兩個選項為：
   - **Horizontal** — 選取此選項時，選項按鈕會在最適化表單中由左至右顯示。
   - **Vertical** — 選取此選項時，選項按鈕會在最適化表單中由上到下顯示。
- **隱藏元件** — 選取選項，以隱藏表單中的元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。
- **停用元件** — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀** — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 驗證標籤 {#validation-tab}

![驗證標籤](/help/adaptive-forms/assets/radiobutton_validationtab.png)

- **必要** — 如果您想要在最適化表單中顯示元件，請選取此選項。 選取選項後，您必須先進行選取，才能繼續提交表單。 選取此選項時，您無法在&#x200B;**基本**&#x200B;索引標籤中選取&#x200B;**隱藏元件**&#x200B;或&#x200B;**停用元件**。
- **錯誤訊息** — 此選項可讓您輸入在勾選「**必要**」核取方塊並將表單欄位保留空白時顯示的訊息。

- **指令碼驗證訊息** — 此選項可讓您輸入指令碼驗證失敗時顯示的訊息。

### 說明內容標籤 {#helpcontent-tab}

![說明內容標籤](/help/adaptive-forms/assets/radiobutton_helptab.png)

- **簡短說明** — 簡短說明是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用&#x200B;**永遠顯示簡短描述**&#x200B;選項，以在元件下方顯示它。

- **永遠顯示簡短描述** — 啟用選項以在元件下方顯示簡短描述。

- **說明文字** — 說明文字是指提供給使用者的其他資訊或指引，以協助使用者正確填寫表單欄位。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。

### 協助工具標籤 {#accessibility-tab}

![協助工具標籤](/help/adaptive-forms/assets/radiobutton_accessibilitytab.png)

- **熒幕助讀程式文字** — 熒幕助讀程式文字是指視力不佳人士使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。
   - **自訂文字**：選取此選項即可使用ARIA協助工具標籤的自訂文字。 選取此選項會顯示「自訂文字」對話方塊。 您可以在「自訂文字」對話方塊中新增相關資訊。
   - **說明**：選取此選項即可使用ARIA協助工具標籤的說明。
   - **標題**：選取此選項即可使用ARIA協助工具標籤的標題。
   - **名稱**：選取此選項即可使用ARIA協助工具標籤的名稱。
   - **無**：如果您不想新增ARIA協助工具標籤，請選取此選項。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理選項按鈕元件的CSS樣式。


### 樣式索引標籤 {#styles-tab}

索引標籤可用來定義和管理元件的CSS樣式。 最適化Forms選項按鈕核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話方塊](/help/adaptive-forms/assets/checkbox-style.png)

- **預設CSS類別**：您可以為最適化Forms選項按鈕核心元件提供預設CSS類別。

- **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至屬性對話方塊，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話方塊](/help/adaptive-forms/assets/checkbox-customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性（索引鍵/值組）與最適化表單核心元件建立關聯。 自訂屬性會反映在元件Headless轉譯的properties區段中。 它可讓您建立根據自訂屬性值調整的動態表單行為。 例如，開發人員可以為行動、桌上型電腦或Web平台設計各種無頭Forms元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供一個名稱來識別自訂屬性群組。 您可以新增、刪除或重新排列多個自訂屬性群組。 新增自訂屬性群組後，您可以看到下列選項：

   - **索引鍵 — 值配對**：您可以按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，以新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳以重新排列自訂屬性名稱和自訂屬性值。

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
