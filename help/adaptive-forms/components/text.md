---
title: 最適化Forms核心元件 — 文字
description: 使用或自訂最適化Forms文字核心元件。
role: Architect, Developer, Admin, User
exl-id: b8de68e4-ca0d-4ae5-9a04-104cc617f1be
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 1%

---

# 文字 {#text-adaptive-forms-core-component}

在最適化表單中，文字是指顯示在表單上供使用者閱讀的內容。 這可以包括用來標籤一組表單元素組的文字（例如文字欄位），以及提供給使用者的任何其他指示或資訊。

這也有助於將表單的結構分割成邏輯區段，讓使用者更容易理解並完成表單。 此外，也可用於協助工具，提供與其相關聯元素的簡短說明。 此類文字欄位通常會顯示在表單元件附近，例如之前或之後。

**範例**

![](/help/adaptive-forms/assets/text.png)

## 使用狀況 {#reasons-to-use-text-label}

在表單中使用文字有幾個原因：

* **提供指示**：文字可用來提供如何填寫表單或需要哪些資訊的說明。

* **提供內容**：文字可用於提供表單的內容，例如說明表單目的或收集資訊的組織。

* **將表單劃分為邏輯區段**：文字可用來將表單劃分為邏輯區段，讓使用者更容易理解和完成表單。

* **品牌與身分**：文字可用於品牌和身分識別目的，例如在表單中包含組織名稱。

## 版本和相容性 {#version-and-compatibility}

Adaptive Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 和更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和更新版本，但低於2.0.0。 |

如需核心元件版本和發行版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在以下位置的技術檔案中取得最適化Forms文字核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/text/v1/text). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以使用「設定」對話方塊輕鬆自訂訪客的文字型驗。 您也可以輕鬆定義文字選項，提供順暢的使用者體驗。

![基本索引標籤](/help/adaptive-forms/assets/text_properties.png)

* **名稱**  — 您可以在表單和規則編輯器中以唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。
* **隱藏元件**  — 選取選項，從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存使用者不需要看到或直接變更的資訊時，這會很有用。
* **唯讀**  — 選取選項，使元件不可編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。


## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理文字元件的CSS樣式。

### 樣式索引標籤 {#styles-tab}

索引標籤可用來定義和管理元件的CSS樣式。 最適化Forms文字核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/reset_designdialog.png)

* **預設CSS類別**：您可以為最適化Forms文字核心元件提供預設CSS類別。

* **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在調適型Forms編輯器中將這些樣式使用或套用至調適型表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只需返回「設計」對話方塊，更新樣式標籤中的樣式，然後儲存變更即可。
