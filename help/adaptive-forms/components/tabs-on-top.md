---
title: 自適應Forms核心元件 — 頂部的制表符
description: 使用或自定義頂部核心元件上的自適應Forms頁籤。
role: Architect, Developer, Admin, User
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 2%

---


# 索引標籤在頂端 {#tabs-on-top-adaptive-forms-core-component}

「自適應表單」中的「頂部制表符」佈局是一種將表單的相關欄位和部分組織並分組為單獨頁籤的方法。 每個標籤都由標籤來表示，標籤通常位於表單的頂部，並包含一組特定的表單域和節。 此佈局允許用戶輕鬆瀏覽和訪問表單的不同部分，使其更易於用戶使用，而且不會太難以承受。 當表單包含許多欄位和節時，通常使用它，並且需要將它們分成較小、可管理的塊。 制表符還可通過允許用戶使用鍵盤快捷鍵瀏覽表單來幫助改進輔助功能，使殘疾用戶更容易訪問表單。

**範例**

![](/help/adaptive-forms/assets/tabs.png)

## 使用狀況 {#reasons-to-use-tab-on-the-top-layout}

在「自適應表單」中使用頂部佈局上的制表符有幾個原因：

* **組織**:頁籤可用於將表單的不同部分組織為不同的類別，使用戶能夠更輕鬆地導航和查找所需資訊。

* **空間保護**:制表符一次只允許窗體的一個部分可見，有助於節省頁面空間。

* **改善用戶體驗**:制表符可使表格更美觀、更易於使用，從而改善用戶體驗。

* **移動友好**:通過減少滾動並使欄位之間的切換變得更容易，制表符使表單更具移動性。

總之，頁籤可使表單更有條理、更高空間效率、更方便用戶和更易訪問。

## 版本和相容性 {#version-and-compatibility}

自適應Forms手風琴核心元件於2023年2月發佈，作為用於Cloud Service的核心元件2.0.4的一部分，以及用於Forms或更晚版本的核心元件1.1.12的核心元件6.5.16.0的一部分。 下面是一個表，其中顯示了所有支援的版本AEM、相容性以及指向相應文檔的連結：

| 元件版本 | AEM as a Cloud Service  | AEM6.5.16.0Forms |
|---|---|---|
| v1 | 相容<br>[發行版2.0.4](/help/adaptive-forms/version.md) 之後 | 相容<br>[發行版1.1.12](/help/adaptive-forms/version.md) 晚但小於2.0.0。 |

有關核心元件版本和版本的資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 的子菜單。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

獲取有關頂級核心元件上的自適應Forms標籤的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/tabsontop/v1/tabsontop)。 有關開發核心元件的詳細資訊，請查看 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

通過「配置」對話框，您可以輕鬆地自定義您的頁籤，以獲得訪問者的頂級體驗。 您還可以輕鬆地在頂部選項上定義頁籤，以獲得無縫的用戶體驗。

## 設計對話框 {#design-dialog}
