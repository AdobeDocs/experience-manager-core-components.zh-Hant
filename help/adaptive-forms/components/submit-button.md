---
title: 適用性Forms核心元件 — 提交按鈕
description: 使用或自訂適用性Forms提交按鈕核心元件。
role: Architect, Developer, Admin, User
exl-id: e4b8e475-79b9-4c4d-9f11-a125a424d32b
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 1%

---

# 提交按鈕 {#submit-button}

適用性表單中的「提交」按鈕是可讓使用者將表單資料提交至伺服器進行處理的按鈕。 按一下提交按鈕時，表單資料會傳送至伺服器，以便儲存、處理或用於各種用途，例如傳送電子郵件或更新資料庫。

「提交」按鈕通常是表單填寫程式的最後一步，用於起始將表單資料傳送至伺服器的程式。

## 使用狀況 {#reasons-to-use-submit-button}

在適用性表單中使用提交按鈕的原因如下：

* **資料提交**:提交按鈕是將表單資料提交至伺服器進行處理的主要機制。

* **改善使用者體驗**:精心設計的提交按鈕可以提供關於表單提交流程的明確反饋，並指明表單何時成功提交，從而改善用戶體驗。

* **資料驗證**:提交按鈕可用於觸發資料驗證檢查，確保表單資料在傳送至伺服器之前完整且準確。


## 版本與相容性 {#version-and-compatibility}

適用性Forms折疊式功能表核心元件已於2023年2月發行，作為Cloud Service核心元件2.0.4的一部分，以及AEM 6.5.16.0 Forms或更新版本核心元件1.1.12的一部分。 下表顯示所有支援的版本、AEM相容性，以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 和 | 相容於<br>[版本1.1.12](/help/adaptive-forms/version.md) 和2.0.0以下的。 |

如需核心元件版本和版本的相關資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

取得下列技術檔案中適用性Forms提交按鈕核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 配置對話框 {#configure-dialog}

您可以透過「設定」對話方塊，輕鬆自訂訪客的「提交」按鈕體驗。 您也可以輕鬆定義「提交」按鈕選項，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本標籤](/help/adaptive-forms/assets/button_basictab.png)

* **名稱**  — 您可以在表單和規則編輯器中，以唯一的名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **標題**  — 使用其「標題」，您可以輕鬆地在表單中識別元件，預設情況下，標題會顯示在元件上方。 如果未新增標題，則會顯示元件名稱，而非標題文字。

* **系結參考**  — 綁定引用是對資料元素的引用，該資料元素儲存在外部資料源中，並用於表單中。 系結參考可讓您將資料動態系結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，系結參考可用來根據在表單中輸入的客戶ID，在表單中顯示客戶的名稱和地址。 系結參考也可用來使用輸入表單的資料更新資料來源。 如此一來，AEM Forms便能讓您建立與外部資料來源互動的表單，為收集和管理資料提供順暢的使用者體驗。

* **隱藏元件**  — 選取從表單中隱藏元件的選項。 元件仍可供其他用途存取，例如在規則編輯器中用於計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這個功能會很實用。
* **禁用元件**  — 選取要停用元件的選項。 已禁用的元件不活動或不可編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可供其他用途存取，例如在規則編輯器中用於計算。
* **唯讀**  — 選取選項，使元件不可編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可供其他用途存取，例如在規則編輯器中用於計算。

### 說明內容標籤 {#help-content}

![說明內容標籤](/help/adaptive-forms/assets/button_helptab.png)

* **簡短說明**  — 簡短說明是簡短的文本說明，提供關於特定表單欄位用途的其他資訊或說明。 它可協助使用者了解應在欄位中輸入的資料類型，並可提供指引或範例，以協助確保輸入的資訊有效且符合所需的條件。 依預設，短說明仍會隱藏。 啟用 **一律顯示簡短說明** 選項，將其顯示在元件下方。

* **一律顯示簡短說明**  — 啟用選項，在元件下方顯示簡短說明。

* **說明文字**  — 說明文字是指提供給使用者的其他資訊或指引，以協助他們正確填寫表單欄位。 當使用者按一下元件旁的說明圖示(i)時，就會顯示。 說明文字提供比表單欄位的標籤或預留位置文字更詳細的資訊，旨在協助使用者了解欄位的要求或限制。 您也可以提供建議或範例，讓填寫表單更簡單、更準確。

### 協助工具 {#accessibility}

![協助工具標籤](/help/adaptive-forms/assets/button_accessibilitytab.png)

**螢幕助讀程式的文字**  — 螢幕助讀程式的文字是指視覺障礙人士專用的輔助技術（例如螢幕助讀程式）專門用來閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息的相關資訊（自訂文字）。 螢幕助讀程式文字可協助確保所有使用者都能存取表單，包括視覺障礙者，並讓他們完全了解表單欄位及其需求。

## 設計對話方塊 {#design-dialog}

「設計對話方塊」用於定義和管理「提交」按鈕元件的CSS樣式。

### 樣式標籤 {#styles-tab}

索引標籤可用來定義及管理元件的CSS樣式。 適用性Forms提交按鈕核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/reset_designdialog.png)


* **預設CSS類**:您可以為適用性Forms提交按鈕核心元件提供預設CSS類別。

* **允許的樣式**:您可以提供代表樣式的名稱和CSS類別，以定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight:粗體」。 您可以在適用性Forms編輯器中，將這些樣式使用或套用至適用性表單。 若要套用樣式，請在適用性Forms編輯器中選取您要套用樣式的元件、導覽至屬性對話方塊，然後從 **樣式** 下拉式清單。 如果需要更新或修改樣式，只需返回「設計」對話框、更新樣式頁簽中的樣式並保存更改即可。
