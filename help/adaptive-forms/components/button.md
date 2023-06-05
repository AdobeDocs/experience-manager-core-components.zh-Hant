---
title: 最適化Forms核心元件 — 按鈕
description: 使用或自訂Adaptive Forms按鈕核心元件。
role: Architect, Developer, Admin, User
exl-id: cb75929b-8c86-49d1-b51a-368f5b80b1a9
source-git-commit: 90a48e6203ce611679c2a7269ffb5d48912e3d71
workflow-type: tm+mt
source-wordcount: '1406'
ht-degree: 0%

---

# 按鈕元件 {#button-component-adaptive-forms-core-component}

最適化表單中的按鈕是UI元素，可讓使用者在按一下時啟動動作。 按鈕元素可用於提交表單、重設表單或執行其他動作，例如導覽至其他頁面或觸發自訂程式碼。 可以使用按鈕核心元件來建立按鈕。

最適化Forms規則編輯器可讓使用者為按鈕元件設定各種動作。 這些動作包括開啟網站、顯示或隱藏表單元件、新增面板或元件的例項、提交或重設表單等等。

最適化Forms功能下列專案的個別元件 [提交按鈕](/help/adaptive-forms/components/submit-button.md) 和 [重設按鈕](/help/adaptive-forms/components/reset-button.md)，方便使用者提交或重設表格。 Button元件可靈活地設定為根據特定需求執行這些動作。

使用者可以使用最適化Forms規則編輯器來存取按鈕元件支援的動作完整清單。 規則編輯器可讓使用者建立由各種事件觸發的規則，例如當按一下按鈕時、當載入表單時，或當欄位值變更時。 然後，這些規則可用於執行各種動作，例如顯示或隱藏元件、設定欄位值或提交表單。

## 使用狀況 {#reasons-to-use-button}

在最適化表單中加入按鈕有幾個好處，包括：

* **表單提交**：按鈕通常用於提交表單，允許使用者將已輸入的資料傳送至伺服器以供處理。

* **表單重設**：按鈕也可用來重設表單，清除使用者輸入的所有資料。

* **導覽**：按鈕可用於在表單的不同區段或網站上的不同頁面之間導覽。

* **事件處理**：按鈕可用來觸發不同事件，例如開啟網站、顯示/隱藏元件、將面板或元件的例項新增至按鈕。

* **互動**：按鈕可用來建立互動式表單。 例如，按鈕可用於開啟強制回應對話方塊或切換表單的區段。

## 版本和相容性 {#version-and-compatibility}

Adaptive Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 和更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和更新版本，但低於2.0.0。 |

如需核心元件版本和發行版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在以下位置的技術檔案中取得最適化Forms按鈕核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以使用「設定」對話方塊輕鬆自訂訪客的按鈕體驗。 您也可以輕鬆定義按鈕屬性，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本標籤](/help/adaptive-forms/assets/button_basictab.png)

* **名稱**  — 您可以在表單和規則編輯器中以唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **標題**  — 透過其Title ，您可以輕鬆識別表單中的元件，且根據預設，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件名稱而非標題文字。

* **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。

* **記錄檔案繫結參考**  — 此選項可讓您將最適化表單欄位與記錄檔案欄位建立關聯。 當使用者在最適化表單的連結欄位中輸入任何值時，該值也會出現在相應記錄檔案的連結欄位中。 例如，記錄檔案繫結參考可用於根據在表單中輸入的客戶ID在記錄檔案中顯示客戶名稱和地址。 透過這種方式，AEM Forms可讓您產生記錄檔案，並提供順暢的使用者體驗來收集和管理資料。

* **隱藏元件**  — 選取選項，從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存使用者不需要看到或直接變更的資訊時，這會很有用。
* **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
* **唯讀**  — 選取選項，使元件不可編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 說明內容標籤 {#help-content}

![說明內容標籤](/help/adaptive-forms/assets/button_helptab.png)

* **簡短說明**  — 簡短說明是簡短文字說明，提供有關特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入什麼型別的資料，並可提供指引或範例來協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明仍會隱藏。 啟用 **一律顯示簡短說明** 選項來將它顯示在元件下方。

* **一律顯示簡短說明**  — 啟用選項以在元件下方顯示簡短說明。

* **說明文字**  — 說明文字是指為協助使用者正確填寫表單欄位，而提供給使用者的其他資訊或指引。 當使用者按一下置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供比表單欄位的標籤或預留位置文字更詳細的資訊，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，使填寫表單更容易、更準確。

### 協助工具 {#accessibility}

![協助工具索引標籤](/help/adaptive-forms/assets/button_accessibilitytab.png)


* **熒幕助讀程式的文字**  — 熒幕助讀程式文字是指視力不佳人士使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取（包括視覺障礙使用者），並讓他們完全瞭解表單欄位及其需求。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理按鈕元件的CSS樣式。

### 樣式索引標籤 {#styles-tab}

最適化Forms按鈕核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/button_designdialog.png)

* **預設CSS類別**：您可以為最適化Forms按鈕核心元件提供預設CSS類別。

* **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在調適型Forms編輯器中將這些樣式使用或套用至調適型表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只需返回「設計」對話方塊，更新樣式標籤中的樣式，然後儲存變更即可。


