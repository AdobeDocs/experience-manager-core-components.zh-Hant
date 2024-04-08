---
title: 最適化Forms核心元件 — 影像
description: 使用或自訂最適化Forms影像核心元件。
role: Architect, Developer, Admin, User
exl-id: 9ee42d5d-16e3-4973-8364-5bc512ebe72e
source-git-commit: 337f3b40f0a6046e4161d8365fc8ecc7d029cdcd
workflow-type: tm+mt
source-wordcount: '1057'
ht-degree: 1%

---

# 影像 {#image-adaptive-forms-core-component}

最適化表單中的影像元件是一種在表單中包含影像的方式。 這些影像可用來增強表單的整體設計、提供其他資訊，或作為視覺輔助以幫助使用者瞭解表單的用途。 影像元件可用來在表單中新增標誌、像片或圖形。

若想取得協助工具，請務必指定 **替代文字** 影像的替代文字，為影像提供簡短描述性文字，向看不見影像的使用者提供說明。


**範例**

![範例](/help/adaptive-forms/assets/image.png)


## 使用情況 {#reasons-to-use-image-in-a-form}

在最適化表單中加入影像元件有幾個好處，包括：

- **品牌化**：影像可用來顯示建立表單的組織的標誌或名稱，有助於建立品牌認知度和可信度。

- **視覺輔助**：影像可做為視覺化輔助工具，協助使用者瞭解表單用途，有助於為使用者提供額外等級的資訊。

- **裝飾**：影像可用來增強表單的整體設計，並使其更具視覺吸引力。

- **使用者體驗**：影像可讓使用者透過清晰且直覺的方式存取及填寫表單欄位，進而讓表單更人性化。

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

- **名稱**  — 在表單和規則編輯器中，您可以使用表單元件的唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

- **標題**  — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。

- **標籤為未繫結表單元素**：選取選項以設定未連結至任何結構的表單欄位。 此選項可讓您儲存資料而不更新資料來源。 它也可讓您以自訂方式處理資料，與標準資料庫整合不同。

<!--   **Document of Record bind reference** - This option allows you to associate an Adaptive Form field with Document of Record field. When user enters any value in a linked field of an Adaptive Form that value also appears in the linked field of the corresponding Document of Record. For example, a Document of Record bind reference can be used to display a customer's name and address in a Document of Record, based on the customer's ID entered into the form. In this way, AEM Forms enable you to generate Document of Record and offers a seamless user experience for collecting and managing data.-->

- **說明**  — 說明是簡短文字說明，提供有關特定影像用途的其他資訊或說明。

- **將資產拖曳至此處，或瀏覽檔案以上傳**  — 此選項可讓您使用滑鼠拖放功能拖放影像等資產。 您也可以使用從本機檔案系統上傳檔案 **瀏覽** 按鈕。 新增影像後，影像底部會顯示三個按鈕：
   - **編輯**  — 點選或按一下 **編輯** 在「資產編輯器」中管理資產的轉譯。
   - **清除**  — 點選或按一下 **清除** 以取消選取目前選取的影像。
   - **選取**  — 點選或按一下 **選取**  從「資產」資料夾中選取其他影像的選項。

- **替代文字**  — 此選項用於輸入提供影像的簡短描述性替代文字的文字，向視障使用者說明影像。

- **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。

<!--   **Read-only** - Select the option to make the component non-editable. The user can see the value of the field but cannot modify it. The component remains accessible for other purposes, such as using it for calculations in the Rule Editor.
-->

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理影像元件的CSS樣式。

### 樣式索引標籤 {#styles-tab}

索引標籤可用來定義和管理元件的CSS樣式。 最適化Forms影像核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/checkbox-style.png)

- **預設CSS類別**：您可以為最適化Forms影像核心元件提供預設CSS類別。

- **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話方塊](/help/adaptive-forms/assets/checkbox-customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性（索引鍵/值組）與最適化表單核心元件建立關聯。 自訂屬性會反映在元件Headless轉譯的properties區段中。 它可讓您建立根據自訂屬性值調整的動態表單行為。 例如，開發人員可以為行動、桌上型電腦或Web平台設計各種無頭Forms元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱來識別自訂屬性群組。 您可以新增、刪除或重新排列多個自訂屬性群組。 新增自訂屬性群組後，您可以看到下列選項：

   - **索引鍵值配對**：您可以按一下「 」，新增多個自訂屬性名稱和自訂屬性值 **新增** 按鈕來設定每個自訂屬性群組。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳，以重新排列自訂屬性名稱和自訂屬性值的順序。

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}