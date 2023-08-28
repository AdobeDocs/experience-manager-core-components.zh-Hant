---
title: 最適化Forms核心元件 — 數字輸入
description: 使用或自訂最適化Forms編號輸入核心元件。
role: Architect, Developer, Admin, User
exl-id: 75604ecf-1ec5-4e97-b934-d6ed49726147
source-git-commit: ad3e3bca5cb46f14e864e4704c90ac3b62779794
workflow-type: tm+mt
source-wordcount: '1870'
ht-degree: 1%

---

# 數字輸入 {#number-input-adaptive-forms-core-component}

最適化表單中的數字輸入元件是一種表單欄位，可讓使用者輸入數值。 元件通常以文字欄位表示，並使用向上和向下箭頭遞增和遞減數字。

也可以搭配最小值、最大值、步長、值等屬性使用。 這些屬性可用於設定欄位中允許的最小值和最大值、增加或減少數字的步驟間隔，以及欄位的預設值。

此元件可用於收集年齡、數量等數值資料。 它也可以用來執行數學運算，例如加法和減法。 此元件也可用於驗證使用者輸入的數值資料。

對於協助工具，請務必指定「label」，以說明數字輸入欄位的用途，以及預期的輸入型別。

**範例**

![](/help/adaptive-forms/assets/numeric-stepper.png)

## 使用狀況 {#reasons-to-use-number-input-numeric-stepper}

在最適化表單中加入數值輸入元件有幾個好處，包括：

* **數學運算**：數值欄位可用於執行數學運算，例如加、減、乘和除。

* **資料範圍**：數值欄位可用來使用最小、最大和步驟屬性來設定有效值的範圍。

* **動態內容**：數值元件可用來根據表單欄位顯示動態資料。


## 版本和相容性 {#version-and-compatibility}

最適化Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 及更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和較新版本，但小於2.0.0。 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在的技術檔案中取得最適化Forms編號輸入核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/numberinput/v1/numberinput). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以使用「設定」對話方塊輕鬆自訂訪客的數字輸入體驗。 您也可以輕鬆定義數字輸入選項，提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本標籤](/help/adaptive-forms/assets/numberinput_basictab.png)

* **名稱**  — 在表單和規則編輯器中，您可以使用表單元件的唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **標題**  — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。

* **隱藏標題**  — 選取可隱藏元件標題的選項。

* **預留位置文字**  — 表單元件中的預留位置文字是指在輸入欄位中顯示的簡短標籤或提示，作為使用者應在該欄位中輸入哪種資訊型別的提示。 當使用者開始在欄位中輸入時，預留位置文字消失，如果欄位留空，則會重新出現。 它向使用者提供視覺提示，但不會作為欄位的永久標籤或值。
* **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。
* **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。
* **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
* **唯讀**  — 選取讓元件不可編輯的選項使用者可以看到欄位的值但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
* **號碼型別**  — 此選項可讓您選取表單欄位中&#x200B;允許&#x200B;的數值型別。 您可以從下拉式選單中選取「小數」或「整數」型別。
* **預設值**  — 此選項可讓您在表單欄位中新增預設值。 如果 **已停用的元件** 或 **唯讀元件** 選取時，預設值會顯示在畫面上。 如果使用者在表單欄位中未輸入值，此值會在表單提交時提交

### 驗證標籤 {#validation-tab}

![驗證標籤](/help/adaptive-forms/assets/numberinput_validationtab.png)

* **必填**  — 如果您想要在最適化表單中顯示元件，請選取此選項。 您無法選取 **隱藏元件** 或 **停用元件**  在 **基本** 標籤。

* **錯誤訊息**  — 此選項可讓您輸入訊息，如果 **必填** 核取方塊，且欄位留空。

* **指令碼驗證訊息**  — 此選項可讓您輸入指令碼驗證失敗時顯示的訊息。

* **最小數字/最小數字**  — 使用此選項來選取在表單欄位中輸入的最小允許數字。 如果值小於中指定的數字 **最小數字/最小數字** 選項，則會顯示錯誤訊息。

* **最小錯誤訊息**  — 此選項可讓您輸入當使用者輸入的值小於中指定的值時顯示的錯誤訊息。 **最小數量/最小數量** 選項。

* **排除最小值**  — 如果您不想要指定的最小值 **最小數字/最小數字** 要包含在表單欄位中輸&#x200B;入的值範圍中的選項。

* **最高數字/最大數字**  — 使用此選項可選取在表單欄位中允許輸入的最大數字。 如果數字大於中指定的數字 **最高數字/最大數字** 選項，則會顯示錯誤訊息。

* **錯誤訊息上限**  — 此選項可讓您輸入當使用者輸入的值大於中指定的值時顯示的錯誤訊息。 **最高數字/最大數字** 選項。

* **排除最大值**  — 如果您不想要指定的最大值，請選取此核取方塊 **最高數字/最大數字** 要包含在表單欄位中輸入之值範圍的選項。

### 說明內容標籤 {#help-content}

![說明內容標籤](/help/adaptive-forms/assets/numberinput_helptab.png)

* **簡短說明**  — 簡短說明是簡短文字說明，提供有關特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用 **一律顯示簡短說明** 選項來在元件下方顯示它。

* **一律顯示簡短說明**  — 啟用選項以在元件下方顯示簡短說明。

* **說明文字**  — 說明文字是指為協助使用者正確填寫表單欄位而提供的其他資訊或指引。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。

### 協助工具標籤 {#accessibility}

![協助工具標籤](/help/adaptive-forms/assets/numberinput_accessibility.png)

**熒幕助讀程式的文字**  — 熒幕助讀程式文字是指供視障人士使用的輔助技術（例如熒幕助讀程式）閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。

### 格式標籤 {#formats-tab}

![協助工具標籤](/help/adaptive-forms/assets/numberinput_formattab.png)

* **顯示格式**  — 此選項可讓您從不同的整數 — 數字型別格式中選取選項以供顯示。 當使用者選擇任何選項 **型別** 下拉式功能表、 **格式** 選項即會顯示在面板中。 您可以選擇向使用者顯示數字的特定格式。

* **小數點分隔符號前的位數(1234.000)**  — 使用此選項指定小數點前顯示的位數。

* **小數點分隔符號後的位數(1234.000)**  — 使用此選項可指定小數點後要顯示的位數。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理Number輸入元件的CSS樣式。

### 樣式索引標籤 {#styles-tab}

索引標籤可用來定義和管理元件的CSS樣式。 最適化Forms編號輸入核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![Styletab](/help/adaptive-forms/assets/datepicker_styletab.png)

**預設CSS類別**：您可以為最適化Forms編號輸入核心元件提供預設CSS類別。

**允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms中使用這些樣式或將其套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的編輯器元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 格式標籤 {#format-tab}

「格式」標籤可讓您指定預設和自訂數字格式。
![設計索引標籤](/help/adaptive-forms/assets/emailinput_designformattab.png)

## 相關文章 {#related-article}

* [在AEM Sites頁面或體驗片段中建立最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [建立獨立的最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)


## 另請參閱 {#see-also}

* [折疊式面板](/help/adaptive-forms/components/accordion.md)
* [按鈕](/help/adaptive-forms/components/button.md)
* [核取方塊群組](/help/adaptive-forms/components/checkbox-group.md)
* [日期挑選器](/help/adaptive-forms/components/date-picker.md)
* [下拉式清單](/help/adaptive-forms/components/drop-down.md)
* [電子郵件輸入](/help/adaptive-forms/components/email-input.md)
* [來自容器](/help/adaptive-forms/components/form-container.md)
* [檔案附件](/help/adaptive-forms/components/file-attachment.md)
* [頁尾](/help/adaptive-forms/components/footer.md)
* [頁首](/help/adaptive-forms/components/header.md)
* [水準索引標籤](/help/adaptive-forms/components/horizontal-tabs.md)
* [影像](/help/adaptive-forms/components/image.md)
* [面板容器](/help/adaptive-forms/components/panel-container.md)
* [選項按鈕](/help/adaptive-forms/components/radio-button.md)
* [重設按鈕](/help/adaptive-forms/components/reset-button.md)
* [提交按鈕](/help/adaptive-forms/components/submit-button.md)
* [電話輸入](/help/adaptive-forms/components/telephone-input.md)
* [文字輸入](/help/adaptive-forms/components/text-input.md)
* [文字](/help/adaptive-forms/components/text.md)
* [標題](/help/adaptive-forms/components/title.md)
* [精靈](/help/adaptive-forms/components/wizard.md)