---
title: 自適應表單核心元件 - 檔案附件
description: 使用或自訂自適應表單檔案附件核心元件。
role: Architect, Developer, Admin, User
exl-id: 64a54fc6-db52-481f-bf5a-60c05122004d
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '2061'
ht-degree: 100%

---


# 檔案附件元件 {#file-attachment-adaptive-forms-core-component}

<span class="preview">早期採用者計劃參與者可使用&#x200B;**提交值的資料類型**&#x200B;功能。您可以使用官方電子郵件 ID 寫信至 aem-forms-ea@adobe.com，以加入早期採用者計劃並要求存取該功能。</span>

自適應表單中的檔案附件元件可讓使用者從本機電腦或裝置選取和上傳檔案。檔案附件元件可以設定為允許特定檔案類型、大小限制和多個附件。

{{traditional-aem}}

**範例**

![範例](/help/adaptive-forms/assets/upload-image.png)


## 用途 {#reasons-to-use-file-attachment}

在自適應表單中加入檔案附件元件有多項好處，包括：

- **收集額外資訊**：檔案附件元件可讓使用者上傳文件、影像、影片或其他類型的檔案，以作為表單提交的一部分。這對於收集履歷、專案組合或支援文件等額外資訊非常實用。

- **輕鬆共用大型檔案**：檔案附件元件可讓使用者輕鬆共用大型檔案，而不需依賴外部檔案共用服務。

- **便利性**：檔案附件元件可讓使用者從本機電腦上傳檔案，不必離開表單或使用其他工具。

- **資料分析**：檔案附件元件可用於收集各種來源的資料，並加以分析，或用來作為進一步處理的輸入。

- **使用者體驗**：透過檔案附加元件，可讓使用者以清晰直觀的方式上傳檔案，使表單更加易於使用。

## 版本和相容性 {#version-and-compatibility}

自適應表單檔案附件核心元件於 2023 年 2 月發行，屬於 Cloud Service 核心元件 2.0.4 和 AEM 6.5.16.0 Forms 或更新版本的核心元件 1.1.12 的一部分。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更新版本 |
|---|---|---|
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 與<br>[ 1.1.12 版](/help/adaptive-forms/version.md)及更新版本相容，但低於 2.0.0 版。 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_tw). -->

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/fileinput/v1/fileinput) 的技術文件中可找到自適應表單檔案附件核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的檔案附件體驗。同樣能夠輕鬆定義檔案附件選項，以提供順暢無礙的使用者體驗。

### 基本索引標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/fileattachement_basictab1.png)

- **名稱** - 在表單和規則編輯器中，您可以使用其唯一名稱輕鬆識別表單元件，但該名稱不得包含空格或特殊字元。

- **標題** - 您可以使用其標題輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。若未新增標題，則會顯示該元件的名稱而非標題文字。
- **允許標題使用 RTF 文字** - 此功能可讓使用者格式化純文字標題，整合粗體、斜體、底線文字、各種字型、字體大小、顏色等功能，以及可增強視覺呈現和自訂的其他選項。提供更大的靈活性和創意控制，讓標題在文件、網站或應用程式中脫穎而出。\
  選取&#x200B;**允許標題使用 RTF 文字**&#x200B;核取方塊後，即可看到格式選項，以設定元件標題的樣式。若要存取所有可用的格式選項，您可以按一下 ![全螢幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png) 索引標籤。

  ![RTF 文字支援](/help/adaptive-forms/assets/richtext-support-title.png)

- **隱藏標題** - 選取該選項，以隱藏元件「標題」。

- **按鈕標題** - 此選項用於設定自適應表單上顯示的按鈕的標籤。
- **繫結參考** - 繫結參考是指儲存在外部資料來源，並在表單中使用的資料元素的參考。繫結參考可讓您將資料動態繫結至表單欄位，讓表單可以顯示資料來源的最新資料。例如，繫結參考可用於根據輸入至表單的客戶 ID，在表單中顯示客戶的姓名和地址。繫結參考也可用於使用已輸入至表單中的資料更新資料來源。透過此方式，AEM Forms 可讓您建立與外部資料來源互動的表單，提供順暢無礙的使用者體驗，以收集和管理資料。
- **標示為未繫結的表單元素**：選取該選項，以設定未連結至任何結構描述的表單欄位。此選項可讓您儲存資料，且無需更新資料來源。還可讓您以自訂方式處理資料，不同於標準資料庫整合。
- **提交值的資料類型**：選取該選項以決定如何將附加檔案提交至伺服器。若要以二進位資料傳送附件，請選擇 `File` 選項。若要以 Base64 編碼字串形式傳送附件，請選擇 `String` 選項。如果選取 `String` ，則會將二進位格式的檔案作為資料 URL 提交至伺服器。伺服器會自動將資料 URL 轉換回二進位格式，確保與現有動作 (例如傳送電子郵件和產生記錄文件) 相容，而不需要使用者進行任何變更。根據預設，已選取 `File` 選項。
- **隱藏元件** - 選取該選項，以隱藏表單中的元件。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。這在您需要儲存使用者不需看到或直接變更的資訊時十分有用。
- **停用元件** - 選取該選項以停用元件。一般使用者無法啟動或編輯已停用的元件。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀** - 選取該選項，使元件無法編輯。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。
- **允許多個附件** - 選擇此選項可使用&#x200B;**檔案附件**&#x200B;按鈕上傳多個附件。
- **拖放文字** - 這是顯示在&#x200B;**附加**&#x200B;按鈕頂端的文字，可提示使用者附加或拖放檔案。您可以選擇自訂顯示在&#x200B;**附加**&#x200B;按鈕頂端的文字。此外，您可以使用 RTF 文字選單格式化文字。

### 驗證索引標籤 {#validation-tab}

![驗證索引標籤](/help/adaptive-forms/assets/fileattachment_validationtab.png)

- **必要** - 若要在自適應表單中顯示該元件，請選取此選項。選取選項後，您必須附加附件才能繼續提交表單。選取此選項後，您無法在&#x200B;**基本**&#x200B;索引標籤中選取&#x200B;**隱藏元件**&#x200B;或&#x200B;**停用元件**。
- **錯誤訊息** - 此選項可讓您輸入訊息，在已勾選&#x200B;**必要**&#x200B;核取方塊且欄位留空時顯示。

- **指令碼驗證訊息** - 此選項可讓您輸入訊息，以在指令碼驗證失敗時顯示。

<!--   **Minimum files error message** - This option is used to enter an error message that is displayed if you upload files lesser than the specified minimum number of files.-->

- **檔案大小上限 (MB)** - 此選項可指定檔案大小上限。檔案大小以 MB 為單位指定。
  <!--   **Maximum files error message** - This option is used to enter an error message that is displayed if you upload files greater than the specified maximum number of files.-->

- **檔案大小上限錯誤訊息** - 此選項用於輸入錯誤訊息，當您上傳的檔案大小超過&#x200B;**檔案大小上限 (MB)** 選項中指定的檔案大小時，則會顯示該訊息。

- **允許的檔案類型** - 此處新增了可使用&#x200B;**檔案附件**&#x200B;按鈕上傳的各種檔案類型。也可以按一下&#x200B;**新增**&#x200B;按鈕，以新增檔案格式。支援的檔案格式包括：音訊、影片、影像、文字或 PDF。您也可以刪除或重新排列允許的檔案類型，方式如下：
   - **刪除** - 點選或按一下以移除特定檔案類型。
   - **重新排列** - 點選或按一下並拖曳，以重新排列允許的檔案類型的順序。

  透過將檔案類型變更為允許的檔案類型格式來提交檔案，會在表單提交期間擲回錯誤。
- **檔案類型錯誤訊息** - 此選項可讓您輸入上傳檔案格式時 (非&#x200B;**允許的檔案類型**&#x200B;選項中所列的格式) 所顯示的錯誤訊息。

### 說明內容索引標籤 {#help-content-tab}

![說明內容索引標籤](/help/adaptive-forms/assets/fileattachement_helpcontenttab.png)

- **簡短說明** - 簡短說明指的是簡短文字說明，提供特定表單欄位用途的其他資訊或說明。這有助於使用者了解應在該欄位中輸入的資料類型，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。預設情況下，簡短說明會保持隱藏。啟用&#x200B;**永遠顯示簡短說明**&#x200B;選項，使其顯示於元件下方。

- **永遠顯示簡短說明** - 啟用該選項，使簡短說明顯示於元件下方。

- **說明文字** - 說明文字指的是為使用者提供的其他資訊或指引，協助其正確填寫表單欄位。當使用者按一下放置於元件旁的說明圖示 (i) 時，就會出現此選項。說明文字提供的資訊比表單欄位的標籤或預留位置文字更加詳細，旨在協助使用者了解該欄位的要求或限制。還能夠提供建議或範例，使表單填寫更輕鬆、更準確。

### 協助工具索引標籤 {#accessibility-tab}


![協助工具索引標籤](/help/adaptive-forms/assets/fileattachement_accessibilitytab.png)

- **螢幕助讀程式文字** - 螢幕助讀程式文字指的是專門供視障人士所使用的輔助技術 (如螢幕助讀程式) 朗讀的額外文字。此文字提供表單欄位用途的音訊說明，並可包含有關欄位標題、說明、名稱和任何相關訊息 (自訂文字) 的資訊。螢幕助讀程式文字協助確保表單可供所有使用者存取，包括視障人士，使他們能夠充分理解表單欄位及其要求。

   - **自訂文字**：選取此選項，以使用 ARIA 協助工具標籤的自訂文字。選取此選項會顯示自訂文字對話框。您可以在自訂文字對話框中新增相關資訊。
   - **說明**：選取此選項，以使用 ARIA 協助工具標籤的說明。
   - **標題**：選取此選項，以使用 ARIA 協助工具標籤的標題。
   - **名稱**：選取此選項，以使用 ARIA 協助工具標籤的名稱。
   - **無**：如果您不想新增 ARIA 協助工具標籤，請選取此選項。

## 設計對話框 {#design-dialog}

設計對話框可用於定義和管理檔案附件元件的 CSS 樣式。

### 樣式索引標籤 {#styles-tab}

自適應表單檔案附件核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話框](/help/adaptive-forms/assets/checkbox-style.png)

- **預設 CSS 類別**：您可以為自適應表單檔案附件核心元件提供預設 CSS 類別。

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話框](/help/adaptive-forms/assets/checkbox-customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性 (鍵值對) 與自適應表單核心元件建立關聯。自訂屬性會反映在元件的無周邊轉譯屬性區段中。可讓您建立根據自訂屬性值調整的動態表單行為。例如，開發人員可以為行動裝置、桌上型電腦或網頁平台設計各種無周邊表單元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱，以識別自訂屬性群組。還可以新增、刪除或重新排列多個自訂屬性群組。新增自訂屬性群組後，您可以看到下列選項：

   - **鍵值對**：按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，即可新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳，以重新排列自訂屬性名稱和自訂屬性值的順序。
<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=zh-Hant)

-->

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
