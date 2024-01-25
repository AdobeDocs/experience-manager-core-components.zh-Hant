---
title: 最適化Forms核心元件 — 切換元件
description: 使用或自訂最適化Forms交換器核心元件。
role: Architect, Developer, Admin, User
hide: true
hidefromToC: true
source-git-commit: d172e019c5621d950a94cbdd8d27e4834dbabe3b
workflow-type: tm+mt
source-wordcount: '1689'
ht-degree: 0%

---


# 切換元件{#switch-adaptive-forms-core-component}

切換元件是表單中使用的圖形使用者介面，可讓使用者在兩個選項之間進行選取。 這通常是兩種狀態切換，可讓使用者在兩種狀態之間進行選擇，啟用或停用功能、設定或功能。 開關元件設計成以視覺化方式呈現目前狀態，並顯示特定特徵是否開啟。

switch元件是布林控制元素，會將值設為true或false。 例如，它可用來開啟或關閉功能，例如將聲音設為靜音或取消靜音，或啟用或停用藍芽或WiFi。

![切換元件範例](/help/adaptive-forms/assets/switch-example.png)

## 使用狀況 {#reasons-to-use-switch}

在最適化表單中使用切換的常見原因包括：

- **使用者互動**：使用者可以按一下或點選交換器元件，與其互動。

- **狀態**：切換元件有兩種狀態：開啟和關閉。 切換元件的初始狀態取決於其控制之特徵的預設設定或目前狀態。

- **視覺化表示**：切換元件會變更顏色或位置，以視覺化方式反映其目前狀態。

- **控制功能**：切換元件是用來啟用或停用AEM表單中的特定功能。 例如，它可讓使用者開啟或關閉功能。

## 版本和相容性 {#version-and-compatibility}

最適化Forms交換器核心元件已隨核心元件2.0.64發行。下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service  |
| — | — |
| v1 | 相容於<br>[版本2.0.64](/help/adaptive-forms/version.md) 及更新版本 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

## 技術細節 {#technical-details}

在的技術檔案中取得最適化Forms交換器核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/switch/v1/switch). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的Switch元件體驗。 您也可以輕鬆定義交換器元件選項，以提供順暢的使用者體驗。

### 基本標籤

![基本索引標籤](/help/adaptive-forms/assets/switch-basic.png)

- **名稱**  — 在表單和規則編輯器中，您可以使用表單元件的唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

- **標題**  — 您可以使用其Title輕鬆識別表單中的元件，根據預設，標題會顯示在元件的旁邊。 如果您未新增標題，元件不會顯示。

- **隱藏標題**  — 選取可隱藏元件標題的選項。

- **保留取消核取狀態值**  — 選取此選項可讓您指定未選取切換元件時要傳回的值。
- **選項**  — 指定資料值，並顯示每個選項的文字。
   - **資料值**  — 指定在調適型表單中啟用切換時要提交的值。
   - **顯示文字**  — 指定在最適化表單中啟用切換時，要顯示為標籤的文字。
   - **關閉資料值**  — 指定在調適型表單中未啟用切換器時要提交的值。 只有當 **保留取消核取狀態值** 切換器已啟用。
   - **關閉顯示文字**  — 指定在調適型表單中未啟用切換鍵時，要顯示為標籤的文字。 只有當 **保留取消核取狀態值** 切換器已啟用。

- **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。
- **標籤為未繫結表單元素**：選取選項以設定未連結至任何結構的表單欄位。 此選項可讓您儲存資料而不更新資料來源。 它也可讓您以自訂方式處理資料，與標準資料庫整合不同。

- **提交值的資料型別**：此選項會指定在選取任何選項時傳送之值的資料型別。 如果 **提交值的資料型別** 設為 `Number` 而您將字串資料新增至 **資料值** 在&#x200B;&#x200B;上 **選項** 索引標籤中，畫面會顯示 `Value type mismatch` 錯誤訊息。
- **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。

- **停用元件**  — 選取選項以停用或鎖定元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

- **預設值**：此選項可讓您在表單欄位中新增預設值。 如果 **已停用的元件** 或 **唯讀元件** 選取時，預設值會顯示在畫面上。 如果使用者在表單欄位中未輸入值，此值會在表單提交時提交。

### 驗證標籤 {#validation-tab}

![驗證標籤](/help/adaptive-forms/assets/switch-validation.png)

- **必填**  — 如果您想要在最適化表單中顯示元件，請選取此選項。 選取選項後，您必須先進行選取，才能繼續提交表單。 您無法選取 **隱藏元件** 或 **停用元件**  在 **基本** 標籤。

- **錯誤訊息**  — 此選項可讓您輸入訊息，如果 **必填** 核取方塊，且表單欄位留空。

- **指令碼驗證訊息**  — 此選項可讓您輸入指令碼驗證失敗時顯示的訊息。

### 說明內容標籤 {#helpcontent-tab}

![說明內容標籤](/help/adaptive-forms/assets/switch-help.png)

- **簡短說明**  — 簡短說明是簡短文字說明，提供有關特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用 **一律顯示簡短說明** 選項來在元件下方顯示它。

- **一律顯示簡短說明**  — 啟用選項以在元件下方顯示簡短說明。

- **說明文字**  — 說明文字是指為協助使用者正確填寫表單欄位而提供的其他資訊或指引。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。

### 協助工具標籤 {#accessibility-tab}

![協助工具標籤](/help/adaptive-forms/assets/switch-accessibility.png)

**熒幕助讀程式的文字**  — 熒幕助讀程式文字是指供視障人士使用的輔助技術（例如熒幕助讀程式）閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。

### 樣式索引標籤 {#styles-tab}

![樣式索引標籤](/help/adaptive-forms/assets/switch-styles.png)

- **隱藏標籤**  — 選取此選項可隱藏切換元件的標籤。

- **顯示標籤**  — 選取此選項可顯示切換元件的標籤。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理Switch元件的CSS樣式。

### 樣式索引標籤 {#styles-design-tab}

最適化Forms交換器核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/checkbox-style.png)

- **預設CSS類別**：您可以為最適化Forms交換器群組核心元件提供預設CSS類別。

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








