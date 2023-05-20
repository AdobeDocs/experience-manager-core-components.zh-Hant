---
title: 自適應Forms核心元件 — 面板容器
description: 使用或自定義自適應Forms面板容器核心元件。
role: Architect, Developer, Admin, User
exl-id: 104836fe-8325-47de-978d-1ff2d6a9dd15
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '1696'
ht-degree: 0%

---

# 面板容器 {#panel-container-adaptive-forms-core-component}

在自適應窗體中，面板是容器元素，可用於對相關窗體元素進行分組。 它允許您以邏輯和有意義的方式對不同的表單元素進行分組和組織。 這有助於改善表單的整體結構和可讀性，使用戶更容易理解和導航。

面板可用於建立可折疊的部分，這可用於隱藏複雜或使用頻率較低的表單域，因此保持表單簡單且易於使用。 它還允許您包括其它元件，如文本、複選框和按鈕。

它還可用於設定不同的基於規則的操作，如提交表單、開啟網站、顯示/隱藏元件或添加面板實例。

**範例**

![](/help/adaptive-forms/assets/panel-container.png)

## 使用狀況 {#reasons-to-use-panel-container}

使用窗體中的面板有幾個原因，包括：

* **組織窗體元素**:可以使用面板將相關表單元素分組在一起，使用戶更容易理解和導航表單。

* **改進形狀結構**:通過將表單元素分組成面板，可以改善表單的整體結構和可讀性，使表單更容易理解。

* **建立可折疊部分**:面板可用於建立可折疊的部分，這可用於隱藏複雜或使用頻率較低的表單域，因此保持表單簡單且易於使用。

* **增強可用性**:通過使用面板來組織表單元素，使表單更易於用戶使用，從而提高完成率。

## 版本和相容性 {#version-and-compatibility}

自適應Forms手風琴核心元件於2023年2月發佈，作為用於Cloud Service的核心元件2.0.4的一部分，以及用於Forms或更晚版本的核心元件1.1.12的核心元件6.5.16.0的一部分。 下面是一個表，其中顯示了所有支援的版本AEM、相容性以及指向相應文檔的連結：

| 元件版本 | AEM as a Cloud Service  | AEM6.5.16.0Forms |
|---|---|---|
| v1 | 相容<br>[發行版2.0.4](/help/adaptive-forms/version.md) 之後 | 相容<br>[發行版1.1.12](/help/adaptive-forms/version.md) 晚但小於2.0.0。 |

有關核心元件版本和版本的資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 的子菜單。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

獲取有關自適應Forms面板容器核心元件的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer)。 有關開發核心元件的詳細資訊，請查看 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

通過「配置」對話框，您可以輕鬆地為訪問者自定義面板容器體驗。 您還可以輕鬆定義面板容器選項，以獲得無縫的用戶體驗。

### 基本標籤 {#basic-tab}

![基本頁籤](/help/adaptive-forms/assets/panelcontainer_basictab.png)

* **名稱**  — 您可以在表單和規則編輯器中輕鬆地使用其唯一名稱標識表單元件，但名稱不能包含空格或特殊字元。

* **標題**  — 使用其「標題」，您可以輕鬆地在窗體中標識元件，預設情況下，標題會顯示在元件的頂部。 如果未添加標題，則將顯示元件的名稱，而不顯示標題文本。

* **隱藏標題**  — 選擇用於隱藏元件標題的選項。

* **對象中的資料進行包裝**  — 選擇「在對象中包裝資料」，將嚮導中的欄位資料放在JSON對象中。 如果未選擇，則提交資料JSON具有嚮導欄位的平面結構。

* **佈局**  — 您可以為嚮導設定固定佈局（簡單）或靈活佈局（響應網格）。 「簡單」佈局將所有內容固定在適當位置，而「響應網格」允許您調整元件的位置以滿足您的需求。 例如，使用響應網格在單行表單中對齊「名字」、「中間名」和「姓氏」。

* **綁定引用**  — 綁定引用是對儲存在外部資料源中並以表單形式使用的資料元素的引用。 綁定引用允許您將資料動態綁定到表單域，以便表單可以顯示資料源中的最新資料。 例如，可以使用綁定引用根據輸入到表單中的客戶ID在表單中顯示客戶的名稱和地址。 綁定引用還可用於使用輸入到表單中的資料更新資料源。 通過這種方式，AEM Forms使您能夠建立與外部資料源交互的表單，從而為收集和管理資料提供無縫的用戶體驗。
* **隱藏元件**  — 選擇從窗體中隱藏元件的選項。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。 當您需要儲存用戶不需要看到或直接更改的資訊時，此功能非常有用。
* **禁用元件**  — 選擇禁用元件的選項。 禁用的元件不處於活動狀態或最終用戶不可編輯。 用戶可以查看欄位的值，但無法修改它。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。

### 幫助內容頁籤 {#help-content}

![「幫助內容」頁籤](/help/adaptive-forms/assets/panelcontainer_helptab.png)

* **簡短描述**  — 簡短說明是簡短的文本說明，提供有關特定表單域目的的其他資訊或說明。 它有助於用戶瞭解應輸入到欄位中的資料類型，並可提供指導或示例以幫助確保輸入的資訊有效且符合所需標準。 預設情況下，短描述仍隱藏。 啟用 **始終顯示簡短說明** 的子菜單。

* **始終顯示簡短說明**  — 啟用選項以在元件下顯示簡短說明。

* **幫助文本**  — 幫助文本指向用戶提供的附加資訊或指導，以幫助用戶正確填寫表單域。 當用戶按一下該元件旁邊的幫助表徵圖(i)時，將顯示該表徵圖。 幫助文本提供了比表單域的標籤或佔位符文本更詳細的資訊，旨在幫助用戶瞭解該域的要求或約束。 還可提供建議或示例，使填寫表格更簡單、更準確。

### 輔助功能頁籤 {#accessibility}

![輔助功能頁籤](/help/adaptive-forms/assets/panelcontainer_accessibilitytab.png)

* **螢幕閱讀器的文本**  — 螢幕閱讀器的文本是指供視障人士使用的輔助技術（如螢幕閱讀器）閱讀的附加文本。 此文本提供表單域目的的音頻說明，並可包括有關域標題、說明、名稱和任何相關消息的資訊（自定義文本）。 螢幕閱讀器文本有助於確保所有用戶都能訪問表單，包括那些有視覺障礙的用戶，並為他們提供對表單域及其要求的全面瞭解。

* **HTML螢幕閱讀器要通知的角色** -HTML角色是用於指定HTML元素對輔助技術（如螢幕閱讀器）的用途的屬性。 角色屬性用於為元素提供附加的上下文和語義含義，使得螢幕閱讀器更容易解釋和向用戶宣佈內容。 例如，在AEM Forms，表單域的標籤可能具有「label」的角色，其輸入域可能具有「textbox」角色。 這有助於螢幕閱讀器瞭解標籤和輸入欄位之間的關係，並正確地向用戶宣佈它們。

## 設計對話框 {#design-dialog}

「設計」對話框用於定義和管理「面板」容器元件的CSS樣式。

### 允許的元件頁籤 {#allowed-components-tab}

![允許的元件頁籤](/help/adaptive-forms/assets/panel_allowedcomponent.png)

的 **允許的元件** 頁籤允許模板編輯器設定可作為項目添加到自適應Forms編輯器的面板容器元件中的面板的元件。

### 預設元件頁籤 {#default-component-tab}

此頁籤允許模板編輯器將可以作為項目添加到自適應Forms編輯器的面板容器元件中的面板中的元件映射到這些元件。

![面板預設元件](/help/adaptive-forms/assets/panel_defaultcomponent.png)

### 響應設定 {#responsive-settings}

此頁籤允許模板編輯器設定要在響應網格中顯示的列數。

![回應式格線](/help/adaptive-forms/assets/panel_responsivesettings.png)

### 「容器設定」頁籤 {#container-setting-tab}

容器設定頁籤允許在自適應Forms編輯器中設定元件的位置。

![容器設定](/help/adaptive-forms/assets/panel_settings.png)

* **佈局**:「簡單」佈局將所有內容都固定在位置，而「響應網格」允許您更改元件的位置以滿足您的需求。
* **禁用佈局**:也可以通過選擇 **禁用佈局** 複選框。
* **啟用背景影像**:此頁籤允許在模板編輯器中設定背景影像和顏色。
* **啟用背景顏色**:此頁籤允許在模板編輯器中設定背景顏色。

### 樣式頁籤 {#styles-tab}

該頁籤用於定義和管理元件的CSS樣式。 自適應Forms面板容器核心元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

![樣式頁籤](/help/adaptive-forms/assets/panel_style.png)

* **預設CSS類**:可以為自適應Forms核心元件提供預設CSS類。

* **允許的樣式**:可以通過提供表示樣式的名稱和CSS類來定義樣式。 例如，可以建立名為「bold text」的樣式，並提供CSS類「font-weight:粗體」。 您可以使用這些樣式或將這些樣式應用於自適應Forms中的自適應表單。 要應用樣式，請在自適應Forms編輯器中，選擇要將樣式應用到的元件，導航到屬性對話框，然後從 **樣式** 的子菜單。 如果需要更新或修改樣式，只需返回到「設計」對話框，更新樣式頁籤中的樣式，並保存更改。

* **HTML螢幕閱讀器要通知的角色** -HTML角色是用於指定HTML元素對輔助技術（如螢幕閱讀器）的用途的屬性。 角色屬性用於為元素提供附加的上下文和語義含義，使得螢幕閱讀器更容易解釋和向用戶宣佈內容。 例如，在AEM Forms，表單域的標籤可能具有「label」的角色，其輸入域可能具有「textbox」角色。 這有助於螢幕閱讀器瞭解標籤和輸入欄位之間的關係，並正確地向用戶宣佈它們。

