---
title: 最適化Forms核心元件 — 重設按鈕
description: 使用或自訂最適化Forms重設按鈕核心元件。
role: Architect, Developer, Admin, User
exl-id: e5aa9d89-aece-491e-80a1-7fb9ea6c4b60
source-git-commit: 0bebc248ee2b708f7677950d90356abd5bc70a98
workflow-type: tm+mt
source-wordcount: '1266'
ht-degree: 2%

---

# 重設 {#reset-button}

最適化表單中的重設按鈕是允許使用者清除所有表單欄位或將其重設為預設值的按鈕。 按一下重設按鈕時，已輸入表單欄位的任何資料都會被刪除，且欄位會恢復其原始狀態。 重設按鈕通常作為提交按鈕的替代方法，為使用者提供一種在表單中輸入不正確或不需要的資料時重新開始的方法。


## 使用狀況 {#reasons-to-use-reset-button}

在最適化表單中使用重設按鈕的原因是：

* **方便使用者**：重設按鈕讓使用者能夠快速輕鬆地清除表單並重新開始，而無需手動刪除每個欄位。

* **改善可用性**：重設按鈕可讓使用者輕鬆更正錯誤或變更其輸入，進而改善使用者體驗。

* **錯誤預防**：使用重設按鈕，使用者可以避免意外提交不正確的資料，進而導致錯誤或處理問題。

* **一致性**：在表單中包含重設按鈕可提供一致的使用者體驗，因為重設按鈕是表單的常見功能。

* **更好的資料管理**：使用重設按鈕，可以保持表單資料有條理且準確，因為使用者不太可能會提交不一致或不正確的資料。

## 版本和相容性 {#version-and-compatibility}

最適化Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 及更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和較新版本，但小於2.0.0。 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在的技術檔案中取得最適化Forms重設按鈕核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的「重設」按鈕體驗。 您也可以輕鬆定義「重設」按鈕選項，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本標籤](/help/adaptive-forms/assets/button_basictab.png)

* **名稱**  — 在表單和規則編輯器中，您可以使用表單元件的唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **標題**  — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。

* **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入到表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。

* **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。
* **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。
* **唯讀**  — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 說明內容標籤 {#help-content}

![說明內容標籤](/help/adaptive-forms/assets/button_helptab.png)

* **簡短說明**  — 簡短說明是簡短文字說明，提供有關特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入哪種資料型別，並可提供指引或範例，以協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明會維持隱藏狀態。 啟用 **一律顯示簡短說明** 選項來在元件下方顯示它。

* **一律顯示簡短說明**  — 啟用選項以在元件下方顯示簡短說明。

* **說明文字**  — 說明文字是指為協助使用者正確填寫表單欄位而提供的其他資訊或指引。 當使用者按一下放置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供的資訊比表單欄位的標籤或預留位置文字更詳細，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，讓填寫表單更容易、更準確。

### 協助工具 {#accessibility}

![協助工具標籤](/help/adaptive-forms/assets/button_accessibilitytab.png)


**熒幕助讀程式的文字**  — 熒幕助讀程式文字是指視力受損者使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取，包括視覺障礙的使用者，並提供他們對表單欄位及其要求的完整瞭解。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理「重設」按鈕元件的CSS樣式。


### 樣式索引標籤 {#styles-tab}

索引標籤可用來定義和管理元件的CSS樣式。 最適化Forms重設按鈕核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/reset_designdialog.png)

* **預設CSS類別**：您可以為最適化Forms重設按鈕核心元件提供預設的CSS類別。

* **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

## 相關文章 {#related-article}

* [在AEM Sites頁面或體驗片段中建立最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [建立獨立的最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)


>[!MORELIKETHIS]
>
>* [折疊式面板](/help/adaptive-forms/components/accordion.md)
>* [按鈕](/help/adaptive-forms/components/button.md)
>* [核取方塊群組](/help/adaptive-forms/components/checkbox-group.md)
>* [日期挑選器](/help/adaptive-forms/components/date-picker.md)
>* [下拉式清單](/help/adaptive-forms/components/drop-down.md)
>* [電子郵件輸入](/help/adaptive-forms/components/email-input.md)
>* [來自容器](/help/adaptive-forms/components/form-container.md)
>* [檔案附件](/help/adaptive-forms/components/file-attachment.md)
>* [頁尾](/help/adaptive-forms/components/footer.md)
>* [頁首](/help/adaptive-forms/components/header.md)
>* [水準索引標籤](/help/adaptive-forms/components/horizontal-tabs.md)
>* [影像](/help/adaptive-forms/components/image.md)
>* [數字輸入](/help/adaptive-forms/components/number-input.md)
>* [面板容器](/help/adaptive-forms/components/panel-container.md)
>* [選項按鈕](/help/adaptive-forms/components/radio-button.md)
>* [提交按鈕](/help/adaptive-forms/components/submit-button.md)
>* [電話輸入](/help/adaptive-forms/components/telephone-input.md)
>* [文字輸入](/help/adaptive-forms/components/text-input.md)
>* [文字](/help/adaptive-forms/components/text.md)
>* [標題](/help/adaptive-forms/components/title.md)
>* [精靈](/help/adaptive-forms/components/wizard.md)

## 另請參閱 {#see-also}

{{see-also}}