---
title: 自適應表單核心元件 - 影像
description: 使用或自訂自適應表單影像核心元件。
role: Architect, Developer, Admin, User
exl-id: 9ee42d5d-16e3-4973-8364-5bc512ebe72e
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '1056'
ht-degree: 100%

---


# 影像元件{#image-adaptive-forms-core-component}

自適應表單中的影像元件是一種在表單中包含影像的方式。這些影像可用來增強表單的整體設計、提供其他資訊，或作為視覺輔助以協助使用者了解表單的用途。影像元件可用來在表單中新增標誌、照片或圖形。

協助工具方面，請務必指定影像的&#x200B;**替代文字**，為影像提供簡短的描述性替代文字，向無法看到影像的使用者說明影像。

{{traditional-aem}}

**範例**

![範例](/help/adaptive-forms/assets/image.png)


## 用途 {#reasons-to-use-image-in-a-form}

在自適應表單中加入影像元件有多項好處，包括：

- **品牌化**：影像可用來顯示建立表單之組織的標誌或名稱，有助於建立品牌認知度和可信度。

- **視覺輔助**：影像可做為視覺輔助工具，協助使用者了解表單用途，進而為使用者提供額外層級的資訊。

- **裝飾**：影像可用來增強表單的整體設計，並使其更吸引人。

- **使用者體驗**：透過影像，可讓使用者以清晰直觀的方式存取及填寫表單欄位，使表單更加易於使用。

## 版本和相容性 {#version-and-compatibility}

自適應表單影像核心元件於 2023 年 2 月發行，屬於 Cloud Service 核心元件 2.0.4 和 AEM 6.5.16.0 Forms 或更新版本的核心元件 1.1.12 的一部分。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更新版本 |
|---|---|---|
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 與<br>[ 1.1.12 版](/help/adaptive-forms/version.md)及更新版本相容，但低於 2.0.0 版。 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_tw). -->

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/image/v1/image) 的技術文件中可找到自適應表單影像核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。


## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的影像體驗。同樣能夠輕鬆定義影像選項，以提供順暢無礙的使用者體驗。

![屬性索引標籤](/help/adaptive-forms/assets/image_properties.png)

- **名稱** - 在表單和規則編輯器中，您可以使用其唯一名稱輕鬆識別表單元件，但該名稱不得包含空格或特殊字元。

- **標題** - 您可以使用其標題輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。若未新增標題，則會顯示該元件的名稱而非標題文字。

- **標示為未繫結的表單元素**：選取該選項，以設定未連結至任何結構描述的表單欄位。此選項可讓您儲存資料，且無需更新資料來源。還可讓您以自訂方式處理資料，不同於標準資料庫整合。

<!--   **Document of Record bind reference** - This option allows you to associate an Adaptive Form field with Document of Record field. When user enters any value in a linked field of an Adaptive Form that value also appears in the linked field of the corresponding Document of Record. For example, a Document of Record bind reference can be used to display a customer's name and address in a Document of Record, based on the customer's ID entered into the form. In this way, AEM Forms enable you to generate Document of Record and offers a seamless user experience for collecting and managing data.-->

- **說明** - 說明是簡短文字說明，提供特定影像用途的其他資訊或說明。

- **將資產拖放到此處或瀏覽要上傳的檔案** - 此選項允許以滑鼠拖放的方式放置影像等資產。您也可以使用&#x200B;**瀏覽**&#x200B;按鈕，從本機檔案系統上傳檔案。新增影像後，影像底部會顯示三個按鈕：
   - **編輯** - 點選或按一下&#x200B;**「編輯」**，以在「資產編輯器」中管理資產的轉譯。
   - **清除** - 點選或按一下&#x200B;**「清除」**，取消選取目前選取的影像。
   - **挑選** - 點選或按一下&#x200B;**挑選**&#x200B;選項，從資產資料夾中選取其他影像。

- **替代文字** - 選項用於輸入為影像提供簡短且具描述性的替代文字，以向視障使用者說明影像內容。

- **隱藏元件** - 選取該選項，以隱藏表單中的元件。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。這在您需要儲存使用者不需看到或直接變更的資訊時十分有用。

<!--   **Read-only** - Select the option to make the component non-editable. The user can see the value of the field but cannot modify it. The component remains accessible for other purposes, such as using it for calculations in the Rule Editor.
-->

## 設計對話框 {#design-dialog}

設計對話框可用於定義和管理影像元件的 CSS 樣式。

### 樣式索引標籤 {#styles-tab}

此索引標籤可用於定義和管理元件的 CSS 樣式。自適應表單影像核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話框](/help/adaptive-forms/assets/checkbox-style.png)

- **預設 CSS 類別**：您可以為自適應表單影像核心元件提供預設 CSS 類別。

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話框](/help/adaptive-forms/assets/checkbox-customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性 (鍵值對) 與自適應表單核心元件建立關聯。自訂屬性會反映在元件的無周邊轉譯屬性區段中。可讓您建立根據自訂屬性值調整的動態表單行為。例如，開發人員可以為行動裝置、桌上型電腦或網頁平台設計各種無周邊表單元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱，以識別自訂屬性群組。還可以新增、刪除或重新排列多個自訂屬性群組。新增自訂屬性群組後，您可以看到下列選項：

   - **鍵值對**：按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，即可新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳，以重新排列自訂屬性名稱和自訂屬性值的順序。

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}