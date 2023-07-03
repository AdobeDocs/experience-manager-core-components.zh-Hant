---
title: 最適化Forms核心元件 — 核取方塊群組
description: 使用或自訂Adaptive Forms核取方塊群組核心元件。
role: Architect, Developer, Admin, User
exl-id: 2ced0223-e664-470b-a400-b6865d3a67c9
source-git-commit: 7888cfa0f1358ce8018fc1e3cc3b19eb66a82b9d
workflow-type: tm+mt
source-wordcount: '1664'
ht-degree: 0%

---

# 核取方塊群組 {#button-component-adaptive-forms-core-component}

最適化表單中的核取方塊群組是一組相關的核取方塊，可讓使用者從清單中選取一個或多個選項。 每個核取方塊都由資料值（用於處理核取方塊群組專案的值）和顯示值（描述其用途的每個核取方塊專案的標籤）表示

**範例**

![](/help/adaptive-forms/assets/checkbox-group.png)

**屬性對話方塊**

![](/help/adaptive-forms/assets/checkbox-group-properties.png)

在此範例中，Options元素用於將核取方塊群組在一起。 此 **顯示文字** 元素用於為專案提供標籤，並且 **資料值** 用於指定提交表單時傳送至伺服器的值。

每個核取方塊選項/專案都有唯一的「資料」值和「顯示文字」屬性。 如果使用者選取「兒子」和「女兒」核取方塊，則在提交表單時，對應的資料值會傳送到伺服器。 伺服器端指令碼可處理此資料，以判斷使用者選取的選項，且可用於執行各種動作，例如更新表單中的其他欄位，或將表單資料提交至伺服器端指令碼，以供進一步處理。

此外，核取方塊群組可設定為每個選項有不同的處理值，並可使用最適化Forms規則編輯器進行設定。

## 使用狀況 {#reasons-to-use-check-box-group}

在最適化表單中包含核取方塊群組有利有幾個原因，包括：

* **多重選擇**：核取方塊群組可讓使用者從清單中選取多個選項，這在允許或需要選取多個選項的情況下很有用。

* **使用者體驗**：核取方塊群組可讓使用者透過清晰且直覺的方式選取多個選項，讓表單更人性化。

* **資料分析**：核取方塊群組可用來從各種來源收集資料並加以分析，或作為進一步處理的輸入。

* **調查**：核取方塊群組可用於調查，以針對問題選取多個選項。

* **使用者偏好設定**：核取方塊群組可用於收集不同選項的使用者偏好設定。

* **資料值**：核取方塊群組也可用於處理核取方塊群組的專案。

## 版本和相容性 {#version-and-compatibility}

Adaptive Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 和更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和更新版本，但低於2.0.0。 |

如需核心元件版本和發行版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在以下位置的技術檔案中，取得最適化Forms核取方塊群組核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/checkboxgroup/v1/checkboxgroup). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以使用「設定」對話方塊輕鬆自訂訪客的核取方塊體驗。 您也可以輕鬆定義核取方塊選項，以提供順暢的使用者體驗。


### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/checkbox_basictab.png)

* **名稱**  — 此名稱可唯一識別規則編輯器中的元件。名稱字串中不允許特殊字元和空格。

* **標題**  — 透過其Title ，您可以輕鬆識別表單中的元件，且根據預設，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件名稱而非標題文字。

* **隱藏標題**  — 選取隱藏元件標題的選項。

* **選項**  — 您可以新增資料值並顯示文字配對，請使用 **新增** 按鈕。 在新增選項後，可以執行下列動作：

   * **資料值**  — 此選項可讓您輸入在選取選項時要提交的內容。
   * **顯示文字**  — 此選項可讓您輸入要在最適化表單中顯示的內容。
   * **刪除**  — 點選或按一下以刪除核取方塊的選項。
   * **重新排列**  — 點選或按一下並拖曳以重新排列面板。

* **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。

* **已提交值的資料型別**  — 此選項會指定在選取任何選項時傳送之值的資料型別。 如果 **提交值的資料型別** 設為 `Number` 而您將字串資料新增至 **資料值** 在&#x200B;&#x200B;上 **選項** 索引標籤上，畫面會顯示 `Value type mismatch` 錯誤訊息。

* **顯示選項**  — 此選項用於設定最適化表單中核取方塊的視覺對齊方式。 支援的兩個選項為：
   * **水準**  — 選取此選項時，核取方塊會由左至右顯示在最適化表單中。
   * **垂直**  — 選取此選項時，核取方塊會由上到下顯示在最適化表單中。

* **預設選項**  — 此選項可讓您在表單載入時新增預先選取的預設值。 使用刪除圖示可移除新增的選項。 如果 **提交值的資料型別** 設為 `Number` 而您將字串資料新增至 **預設選項**，畫面會顯示 `Value type mismatch` 錯誤訊息。
* **隱藏元件**  — 選取選項，從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存使用者不需要看到或直接變更的資訊時，這會很有用。
* **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
* **唯讀**  — 選取選項，使元件不可編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 驗證標籤 {#validation-tab}

![驗證標籤](/help/adaptive-forms/assets/checkbox_validationtab.png)

* **必填**  — 如果您想要在最適化表單中顯示元件，請選取此選項。 您無法選取 **隱藏元件** 或 **停用元件**  在 **基本** 索引標籤來標籤選取此選項。

* **錯誤訊息**  — 此選項可讓您輸入訊息，如果 **必填** 核取方塊，且表單欄位留空。

* **指令碼驗證訊息**  — 此選項可讓您輸入指令碼驗證失敗時顯示的訊息。

### 說明內容標籤 {#helpcontent-tab}

![說明內容標籤](/help/adaptive-forms/assets/checkbox_helptab.png)

* **簡短說明**  — 簡短說明是簡短文字說明，提供有關特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入什麼型別的資料，並可提供指引或範例來協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明仍會隱藏。 啟用 **一律顯示簡短說明** 選項來將它顯示在元件下方。

* **一律顯示簡短說明**  — 啟用選項以在元件下方顯示簡短說明。

* **說明文字**  — 說明文字是指為協助使用者正確填寫表單欄位，而提供給使用者的其他資訊或指引。 當使用者按一下置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供比表單欄位的標籤或預留位置文字更詳細的資訊，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，使填寫表單更容易、更準確。

### 協助工具標籤 {#accessibility-tab}

![協助工具索引標籤](/help/adaptive-forms/assets/checkbox_accessibility.png)

**熒幕助讀程式的文字**  — 熒幕助讀程式文字是指視力不佳人士使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取（包括視覺障礙使用者），並讓他們完全瞭解表單欄位及其需求。

    ##設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理核取方塊群組元件的CSS樣式。

### 樣式索引標籤 {#styles-tab}

Adaptive Forms核取方塊群組核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/checkbox_designdialog.png)

* **預設CSS類別**：您可以為Adaptive Forms核取方塊群組核心元件提供預設CSS類別。

* **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在調適型Forms編輯器中將這些樣式使用或套用至調適型表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只需返回「設計」對話方塊，更新樣式標籤中的樣式，然後儲存變更即可。

## 相關文章 {#related-article}

* [在AEM Sites頁面或體驗片段中建立最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [建立獨立的最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

