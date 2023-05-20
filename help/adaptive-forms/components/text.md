---
title: 自適應Forms核心元件 — 文本
description: 使用或自定義自適應Forms文本核心元件。
role: Architect, Developer, Admin, User
exl-id: b8de68e4-ca0d-4ae5-9a04-104cc617f1be
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 1%

---

# 文字 {#text-adaptive-forms-core-component}

在自適應表單中，文本是指表單上顯示的內容，供用戶閱讀。 這可以包括用於標籤一組表單元素（如文本欄位）的文本，以及提供給用戶的任何附加說明或資訊。

這也有助於將表單的結構劃分為邏輯部分，使用戶更容易理解和完成表單。 此外，它還可用於輔助功能，以簡要描述與之關聯的元素。 此類文本欄位通常顯示在表單元件附近，如其前或後。

**範例**

![](/help/adaptive-forms/assets/text.png)

## 使用狀況 {#reasons-to-use-text-label}

在表單中使用文本有以下幾個原因：

* **提供說明**:文本可用於提供有關如何填寫表單或需要哪些資訊的說明。

* **提供上下文**:文本可用於提供表單的上下文，如說明表單的用途或收集資訊的組織。

* **將表單分為邏輯部分**:文本可用於將表單劃分為邏輯部分，使用戶更容易理解和完成表單。

* **品牌和身份**:文本可用於品牌和身份目的，例如在表單中包括組織名稱。

## 版本和相容性 {#version-and-compatibility}

自適應Forms手風琴核心元件於2023年2月發佈，作為用於Cloud Service的核心元件2.0.4的一部分，以及用於Forms或更晚版本的核心元件1.1.12的核心元件6.5.16.0的一部分。 下面是一個表，其中顯示了所有支援的版本AEM、相容性以及指向相應文檔的連結：

| 元件版本 | AEM as a Cloud Service  | AEM6.5.16.0Forms |
|---|---|---|
| v1 | 相容<br>[發行版2.0.4](/help/adaptive-forms/version.md) 之後 | 相容<br>[發行版1.1.12](/help/adaptive-forms/version.md) 晚但小於2.0.0。 |

有關核心元件版本和版本的資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 的子菜單。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

獲取有關自適應Forms文本核心元件的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/text/v1/text)。 有關開發核心元件的詳細資訊，請查看 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

通過「配置」對話框，您可以輕鬆地為訪問者定制文本體驗。 您還可以輕鬆定義文本選項，以獲得無縫的用戶體驗。

![基本頁籤](/help/adaptive-forms/assets/text_properties.png)

* **名稱**  — 您可以在表單和規則編輯器中輕鬆地使用其唯一名稱標識表單元件，但名稱不能包含空格或特殊字元。

* **綁定引用**  — 綁定引用是對儲存在外部資料源中並以表單形式使用的資料元素的引用。 綁定引用允許您將資料動態綁定到表單域，以便表單可以顯示資料源中的最新資料。 例如，可以使用綁定引用根據輸入到表單中的客戶ID在表單中顯示客戶的名稱和地址。 綁定引用還可用於使用輸入到表單中的資料更新資料源。 通過這種方式，AEM Forms使您能夠建立與外部資料源交互的表單，從而為收集和管理資料提供無縫的用戶體驗。
* **隱藏元件**  — 選擇從窗體中隱藏元件的選項。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。 當您需要儲存用戶不需要看到或直接更改的資訊時，此功能非常有用。
* **只讀**  — 選擇選項，使元件不可編輯。 用戶可以查看欄位的值，但無法修改它。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。


## 設計對話框 {#design-dialog}

「設計」對話框用於定義和管理文本元件的CSS樣式。

### 樣式頁籤 {#styles-tab}

該頁籤用於定義和管理元件的CSS樣式。 自適應Forms文本核心元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話框](/help/adaptive-forms/assets/reset_designdialog.png)

* **預設CSS類**:可以為自適應Forms文本核心元件提供預設CSS類。

* **允許的樣式**:可以通過提供表示樣式的名稱和CSS類來定義樣式。 例如，可以建立名為「bold text」的樣式，並提供CSS類「font-weight:粗體」。 可以在自適應Forms編輯器中使用這些樣式或將這些樣式應用於自適應表單。 要應用樣式，請在「自適應Forms」編輯器中，選擇要應用樣式的元件，導航到屬性對話框，然後從 **樣式** 的子菜單。 如果需要更新或修改樣式，只需返回到「設計」對話框，更新樣式頁籤中的樣式，並保存更改。
