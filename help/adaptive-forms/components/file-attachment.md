---
title: 最適化Forms核心元件 — 檔案附件
description: 使用或自訂Adaptive Forms檔案附件核心元件。
role: Architect, Developer, Admin, User
exl-id: 64a54fc6-db52-481f-bf5a-60c05122004d
source-git-commit: 79b99d4f6b5a2b186ff3dbf570a58dc86bf24d4a
workflow-type: tm+mt
source-wordcount: '1851'
ht-degree: 0%

---

# 檔案附件 {#file-attachment-adaptive-forms-core-component}

<span class="preview"> 本文包含有關以下專案的內容： **允許標題使用RTF文字** 功能，搶鮮版功能。 搶鮮版功能只能透過我們的 [發行前通道](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html#new-features).</span>

最適化表單中的檔案附件元件可讓使用者從本機電腦或裝置選取及上傳檔案。 檔案附件元件可設定為允許特定檔案型別、大小限制和多個附件。

**範例**

![範例](/help/adaptive-forms/assets/upload-image.png)


## 使用情況 {#reasons-to-use-file-attachment}

在最適化表單中加入檔案附件元件有幾個好處，包括：

- **收集其他資訊**：檔案附件元件可讓使用者在表單提交時上傳檔案、影像、影片或其他型別的檔案。 這對於收集其他資訊，例如履歷、產品組合或支援檔案非常有用。

- **輕鬆共用大型檔案**：檔案附件元件可讓使用者輕鬆共用大型檔案，而不需依賴外部檔案共用服務。

- **便利性**：檔案附件元件可讓使用者從其本機電腦上傳檔案，無需導覽離開表單或使用其他工具。

- **資料分析**：檔案附件元件可用來從各種來源收集資料並加以分析，或用來作為進一步處理的輸入。

- **使用者體驗**：檔案附件元件可讓使用者以清楚直覺的方式上傳檔案，好讓表單更人性化。

## 版本和相容性 {#version-and-compatibility}

最適化Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 及更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和較新版本，但小於2.0.0。 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在的技術檔案中取得最適化Forms檔案附件核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/fileinput/v1/fileinput). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的檔案附件體驗。 您也可以輕鬆定義檔案附件選項，提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/fileattachement_basictab.png)

- **名稱**  — 在表單和規則編輯器中，您可以使用表單元件的唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

- **標題**  — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。
- **允許標題使用RTF文字**  — 此功能可讓使用者格式化純文字標題，並整合如粗體、斜體、底線文字、各種字型、字型大小、顏色，以及其他可增強視覺呈現和自訂的選項。 它提供更大的彈性和創意控制，讓標題在檔案、網站或應用程式中脫穎而出。\
  選取「 」的核取方塊時 **允許標題使用RTF文字** ，可顯示格式選項以設定元件標題的樣式。 若要存取所有可用的格式選項，您可以按一下 ![全熒幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png) 標籤。

  ![RTF支援](/help/adaptive-forms/assets/richtext-support-title.png)

- **隱藏標題**  — 選取可隱藏元件標題的選項。

- **按鈕標題**  — 此選項用於設定最適化表單上所顯示按鈕的標籤。

- **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。
- **標籤為未繫結表單元素**：選取選項以設定未連結至任何結構的表單欄位。 此選項可讓您儲存資料而不更新資料來源。 它也可讓您以自訂方式處理資料，與標準資料庫整合不同。
- **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。
- **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
- **唯讀**  — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
- **允許多個附件**  — 選取此選項以使用上傳多個附件 **檔案附件** 按鈕。
- **拖放文字**  — 這是顯示在 **附加** 按鈕以提示使用者附加或拖放檔案。 您可以選擇自訂顯示在頂端的 **附加** 按鈕。 此外，您可以使用RTF功能表來格式化文字。

### 驗證標籤 {#validation-tab}

![驗證標籤](/help/adaptive-forms/assets/fileattachment_validationtab.png)

- **必填**  — 如果您想要在最適化表單中顯示元件，請選取此選項。 選取選項後，您必須附加附件才能繼續提交表單。 您無法選取 **隱藏元件** 或 **停用元件**  在 **基本** 標籤。
- **錯誤訊息**  — 此選項可讓您輸入訊息，如果 **必填** 核取方塊，且欄位留空。

- **指令碼驗證訊息**  — 此選項可讓您輸入指令碼驗證失敗時顯示的訊息。

<!--   **Minimum files error message** - This option is used to enter an error message that is displayed if you upload files lesser than the specified minimum number of files.-->

- **檔案大小上限(MB)**  — 此選項可指定檔案大小上限。 檔案大小以MB為單位指定。
  <!--   **Maximum files error message** - This option is used to enter an error message that is displayed if you upload files greater than the specified maximum number of files.-->

- **檔案大小上限錯誤訊息**  — 此選項用於輸入當您上傳的檔案大小超過中指定的檔案大小時顯示的錯誤訊息。 **檔案大小上限(MB)** 選項。

- **允許的檔案型別**  — 可使用上傳的各種檔案型別 **檔案附件** 按鈕已新增至此處。 它也可讓您按一下 **新增** 按鈕。 支援的檔案格式包括：音訊、視訊、影像、文字或PDF。 您也可以刪除或重新排列允許的檔案型別，使用：
   - **刪除**  — 點選或按一下以移除特定檔案型別。
   - **重新排列**  — 點選或按一下並拖曳以重新排列允許的檔案型別順序。

- **檔案型別錯誤訊息**  — 此選項可讓您輸入上傳檔案格式（中列出的檔案格式除外）時顯示的錯誤訊息。 **允許的檔案型別** 選項。

### 說明內容標籤 {#help-content-tab}

![說明內容標籤](/help/adaptive-forms/assets/fileattachement_helpcontenttab.png)

- **簡短說明**  — 簡短說明是簡短文字說明，提供有關特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用 **一律顯示簡短說明** 選項來在元件下方顯示它。

- **一律顯示簡短說明**  — 啟用選項以在元件下方顯示簡短說明。

- **說明文字**  — 說明文字是指為協助使用者正確填寫表單欄位而提供的其他資訊或指引。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。

### 協助工具標籤 {#accessibility-tab}


![協助工具標籤](/help/adaptive-forms/assets/fileattachement_accessibilitytab.png)

- **熒幕助讀程式的文字**  — 熒幕助讀程式文字是指視力受損者使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理檔案附件元件的CSS樣式。

### 樣式索引標籤 {#styles-tab}

最適化Forms檔案附件核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/checkbox-style.png)

- **預設CSS類別**：您可以為最適化Forms檔案附件核心元件提供預設CSS類別。

- **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話方塊](/help/adaptive-forms/assets/checkbox-customproperties.png)

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
