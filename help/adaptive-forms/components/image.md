---
title: 最適化Forms核心元件 — 影像
description: 使用或自訂最適化Forms影像核心元件。
role: Architect, Developer, Admin, User
exl-id: 9ee42d5d-16e3-4973-8364-5bc512ebe72e
source-git-commit: 0bebc248ee2b708f7677950d90356abd5bc70a98
workflow-type: tm+mt
source-wordcount: '1051'
ht-degree: 3%

---

# 影像 {#image-adaptive-forms-core-component}

最適化表單中的影像元件是一種在表單中包含影像的方式。 這些影像可用來增強表單的整體設計、提供其他資訊，或作為視覺輔助以幫助使用者瞭解表單的用途。 影像元件可用來在表單中新增標誌、像片或圖形。

若想取得協助工具，請務必指定 **替代文字** 影像的替代文字，為影像提供簡短描述性文字，向看不見影像的使用者提供說明。


**範例**

![](/help/adaptive-forms/assets/image.png)


## 使用狀況 {#reasons-to-use-image-in-a-form}

在最適化表單中加入影像元件有幾個好處，包括：

* **品牌化**：影像可用來顯示建立表單的組織的標誌或名稱，有助於建立品牌認知度和可信度。

* **視覺輔助**：影像可做為視覺化輔助工具，協助使用者瞭解表單用途，有助於為使用者提供額外等級的資訊。

* **裝飾**：影像可用來增強表單的整體設計，並使其更具視覺吸引力。

* **使用者體驗**：影像可讓使用者透過清晰且直覺的方式存取及填寫表單欄位，進而讓表單更人性化。

## 版本和相容性 {#version-and-compatibility}

最適化Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 及更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和較新版本，但小於2.0.0。 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在的技術檔案中取得最適化Forms影像核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/image/v1/image). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).


## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的影像體驗。 您也可以輕鬆定義影像選項，提供順暢的使用者體驗。

![屬性標籤](/help/adaptive-forms/assets/image_properties.png)

* **名稱**  — 在表單和規則編輯器中，您可以使用表單元件的唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **標題**  — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。

* **記錄檔案繫結參考**  — 此選項可讓您將最適化表單欄位與記錄檔案欄位建立關聯。 當使用者在最適化表單的連結欄位中輸入任何值時，該值也會出現在相應記錄檔案的連結欄位中。 例如，記錄檔案繫結參考可用於根據在表單中輸入的客戶ID在記錄檔案中顯示客戶名稱和地址。 透過這種方式，AEM Forms可讓您產生記錄檔案，並提供收集和管理資料的順暢使用者體驗。

* **說明**  — 說明是簡短文字說明，提供有關特定影像用途的其他資訊或說明。

* **將資產拖曳至此處，或瀏覽檔案以上傳**  — 此選項可讓您使用滑鼠拖放功能拖放影像等資產。 您也可以使用從本機檔案系統上傳檔案 **瀏覽** 按鈕。 新增影像後，影像底部會顯示三個按鈕：
   * **編輯**  — 點選或按一下 **編輯** 在「資產編輯器」中管理資產的轉譯。
   * **清除**  — 點選或按一下 **清除** 以取消選取目前選取的影像。
   * **選取**  — 點選或按一下 **選取**  從「資產」資料夾中選取其他影像的選項。

* **替代文字**  — 此選項用於輸入提供影像的簡短描述性替代文字的文字，向視障使用者說明影像。

* **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。

* **唯讀**  — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理影像元件的CSS樣式。

### 樣式索引標籤 {#styles-tab}

索引標籤可用來定義和管理元件的CSS樣式。 最適化Forms影像核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/image_designdialog.png)

**預設CSS類別**：您可以為最適化Forms影像核心元件提供預設CSS類別。

**允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

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
>* [數字輸入](/help/adaptive-forms/components/number-input.md)
>* [面板容器](/help/adaptive-forms/components/panel-container.md)
>* [選項按鈕](/help/adaptive-forms/components/radio-button.md)
>* [重設按鈕](/help/adaptive-forms/components/reset-button.md)
>* [提交按鈕](/help/adaptive-forms/components/submit-button.md)
>* [電話輸入](/help/adaptive-forms/components/telephone-input.md)
>* [文字輸入](/help/adaptive-forms/components/text-input.md)
>* [文字](/help/adaptive-forms/components/text.md)
>* [標題](/help/adaptive-forms/components/title.md)
>* [精靈](/help/adaptive-forms/components/wizard.md)

## 另請參閱 {#see-also}

{{see-also}}