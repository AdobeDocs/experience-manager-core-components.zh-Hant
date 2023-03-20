---
title: 適用性Forms核心元件 — 文字
description: 使用或自訂適用性Forms文字核心元件。
role: Architect, Developer, Admin, User
exl-id: b8de68e4-ca0d-4ae5-9a04-104cc617f1be
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 1%

---

# 文字 {#text-adaptive-forms-core-component}

在適用性表單中，文字是指表單上顯示的內容，供使用者閱讀。 這可以包括用於標籤一組表單元素的文本，如文本欄位，以及提供給用戶的任何附加說明或資訊。

這也有助於將表單的結構分割為邏輯區段，讓使用者更容易了解並完成表單。 此外，它也可用於協助工具，以簡短說明其關聯的元素。 這類文字欄位通常顯示在表單元件附近，例如其之前或之後。

**範例**

![](/help/adaptive-forms/assets/text.png)

## 使用狀況 {#reasons-to-use-text-label}

在表單中使用文字有幾個原因：

* **提供指示**:文字可用來提供如何填寫表單或需要哪些資訊的說明。

* **提供內容**:文字可用來提供表單的上下文，例如說明表單的用途或收集資訊的組織。

* **將表單分割為邏輯區段**:文字可用來將表單分割為邏輯區段，讓使用者更容易了解並完成表單。

* **品牌和身份**:文字可用於品牌和身分用途，例如在表單中加入組織名稱。

## 版本與相容性 {#version-and-compatibility}

適用性Forms折疊式功能表核心元件已於2023年2月發行，作為Cloud Service核心元件2.0.4的一部分，以及AEM 6.5.16.0 Forms或更新版本核心元件1.1.12的一部分。 下表顯示所有支援的版本、AEM相容性，以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 和 | 相容於<br>[版本1.1.12](/help/adaptive-forms/version.md) 和2.0.0以下的。 |

如需核心元件版本和版本的相關資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

取得下列主題的技術檔案中適用性Forms文字核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/text/v1/text). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 配置對話框 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的文字型驗。 您也可以輕鬆定義文字選項，以提供順暢的使用者體驗。

![基本標籤](/help/adaptive-forms/assets/text_properties.png)

* **名稱**  — 您可以在表單和規則編輯器中，以唯一的名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **系結參考**  — 綁定引用是對資料元素的引用，該資料元素儲存在外部資料源中，並用於表單中。 系結參考可讓您將資料動態系結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，系結參考可用來根據在表單中輸入的客戶ID，在表單中顯示客戶的名稱和地址。 系結參考也可用來使用輸入表單的資料更新資料來源。 如此一來，AEM Forms便能讓您建立與外部資料來源互動的表單，為收集和管理資料提供順暢的使用者體驗。
* **隱藏元件**  — 選取從表單中隱藏元件的選項。 元件仍可供其他用途存取，例如在規則編輯器中用於計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這個功能會很實用。
* **唯讀**  — 選取選項，使元件不可編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可供其他用途存取，例如在規則編輯器中用於計算。


## 設計對話方塊 {#design-dialog}

「設計對話框」用於定義和管理文本元件的CSS樣式。

### 樣式標籤 {#styles-tab}

索引標籤可用來定義及管理元件的CSS樣式。 適用性Forms文字核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/reset_designdialog.png)

* **預設CSS類**:您可以為適用性Forms文字核心元件提供預設CSS類別。

* **允許的樣式**:您可以提供代表樣式的名稱和CSS類別，以定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight:粗體」。 您可以在適用性Forms編輯器中，將這些樣式使用或套用至適用性表單。 若要套用樣式，請在適用性Forms編輯器中選取您要套用樣式的元件、導覽至屬性對話方塊，然後從 **樣式** 下拉式清單。 如果需要更新或修改樣式，只需返回「設計」對話框、更新樣式頁簽中的樣式並保存更改即可。
