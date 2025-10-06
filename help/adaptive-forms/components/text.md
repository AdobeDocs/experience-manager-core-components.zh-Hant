---
title: 自適應表單核心元件 - 文字
description: 使用或自訂自適應表單文字核心元件。
role: Architect, Developer, Admin, User
exl-id: b8de68e4-ca0d-4ae5-9a04-104cc617f1be
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '996'
ht-degree: 100%

---


# 文字元件 {#text-adaptive-forms-core-component}

在自適應表單中，文字是指顯示在表單上以供使用者閱讀的內容。這可以包括用來標示一組表單元素 (例如文字欄位) 的文字，以及提供給使用者的任何其他指示或資訊。

這也可以協助將表單的結構分割成邏輯區段，讓使用者更容易理解並完成表單。此外，它也可以用作協助工具用途，為其關聯的元素提供簡要說明。此類文字欄位通常會顯示在表單元件附近，例如顯示於元件之前或之後。

{{traditional-aem}}

**範例**

![文字範例](/help/adaptive-forms/assets/text.png)

## 用途 {#reasons-to-use-text-label}

在表單中使用文字有幾個原因：

- **提供指示**：文字可用於提供如何填寫表單或需要哪些資訊的指示。

- **提供內容**：文字可用來提供表單的內容，例如說明表單的目的或收集資訊的組織。

- **將表單分割為邏輯區段**：文字可用來將表單分割為邏輯區段，讓使用者更容易理解並完成表單。

- **品牌化和身分識別**：文字可用於品牌化和身分識別目的，例如在表單中包含組織的名稱。

## 版本和相容性 {#version-and-compatibility}

自適應表單文字核心元件於 2023 年 2 月發行，屬於 Cloud Service 核心元件 2.0.4 和 AEM 6.5.16.0 Forms 或更新版本的核心元件 1.1.12 的一部分。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更新版本 |
|---|---|---|
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 與<br>[ 1.1.12 版](/help/adaptive-forms/version.md)及更新版本相容，但低於 2.0.0 版。 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/text/v1/text) 的技術文件中可找到自適應表單文字核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的文字體驗。同樣能夠輕鬆定義文字選項，以提供順暢無礙的使用者體驗。

### 基本索引標籤

![基本索引標籤](/help/adaptive-forms/assets/text_properties.png)

- **名稱** - 在表單和規則編輯器中，您可以使用其唯一名稱輕鬆識別表單元件，但該名稱不得包含空格或特殊字元。

- **繫結參考** - 繫結參考是指儲存在外部資料來源，並在表單中使用的資料元素的參考。繫結參考可讓您將資料動態繫結至表單欄位，讓表單可以顯示資料來源的最新資料。例如，繫結參考可用於根據輸入至表單的客戶 ID，在表單中顯示客戶的姓名和地址。繫結參考也可用於使用已輸入至表單中的資料更新資料來源。透過此方式，AEM Forms 可讓您建立與外部資料來源互動的表單，提供順暢無礙的使用者體驗，以收集和管理資料。
- **標示為未繫結的表單元素**：選取該選項，以設定未連結至任何結構描述的表單欄位。此選項可讓您儲存資料，且無需更新資料來源。還可讓您以自訂方式處理資料，不同於標準資料庫整合。
- **隱藏元件** - 選取該選項，以隱藏表單中的元件。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。這在您需要儲存使用者不需看到或直接變更的資訊時十分有用。
  <!--    **Read-only** - Select the option to make the component non-editable. The user can see the value of the field but cannot modify it. The component remains accessible for other purposes, such as using it for calculations in the Rule Editor.-->

## 設計對話框 {#design-dialog}

設計對話框可用於定義和管理文字元件的 CSS 樣式。

### 樣式索引標籤 {#styles-tab}

此索引標籤可用於定義和管理元件的 CSS 樣式。自適應表單文字核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話框](/help/adaptive-forms/assets/checkbox-style.png)

- **預設 CSS 類別**：您可以為自適應表單文字核心元件提供預設 CSS 類別。

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