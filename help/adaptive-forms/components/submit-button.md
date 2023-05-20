---
title: 自適應Forms核心元件 — 提交按鈕
description: 使用或自定義「自適應Forms提交」按鈕核心元件。
role: Architect, Developer, Admin, User
exl-id: e4b8e475-79b9-4c4d-9f11-a125a424d32b
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 1%

---

# 「提交」按鈕 {#submit-button}

自適應表單中的「提交」按鈕是允許用戶將表單資料提交到伺服器進行處理的按鈕。 按一下「提交」按鈕時，表單資料會發送到伺服器，在伺服器中可以儲存、處理或用於各種目的，如發送電子郵件或更新資料庫。

「提交」按鈕通常是填寫表單過程中的最後一步，用於啟動將表單資料發送到伺服器的過程。

## 使用狀況 {#reasons-to-use-submit-button}

在自適應表單中使用提交按鈕的原因有：

* **資料提交**:提交按鈕是將表單資料提交到伺服器進行處理的主要機制。

* **改善用戶體驗**:精心設計的提交按鈕可以通過提供關於表單提交過程的明確反饋並指示表單何時成功提交而改善用戶體驗。

* **資料驗證**:提交按鈕可用於觸發資料驗證檢查，確保表單資料在發送到伺服器之前完整且準確。


## 版本和相容性 {#version-and-compatibility}

自適應Forms手風琴核心元件於2023年2月發佈，作為用於Cloud Service的核心元件2.0.4的一部分，以及用於Forms或更晚版本的核心元件1.1.12的核心元件6.5.16.0的一部分。 下面是一個表，其中顯示了所有支援的版本AEM、相容性以及指向相應文檔的連結：

| 元件版本 | AEM as a Cloud Service  | AEM6.5.16.0Forms |
|---|---|---|
| v1 | 相容<br>[發行版2.0.4](/help/adaptive-forms/version.md) 之後 | 相容<br>[發行版1.1.12](/help/adaptive-forms/version.md) 晚但小於2.0.0。 |

有關核心元件版本和版本的資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 的子菜單。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

獲取有關Adaptive Sebmit按鈕核心元件的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button)。 有關開發核心元件的詳細資訊，請查看 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

通過「配置」對話框，您可以輕鬆地為訪問者自定義「提交」按鈕體驗。 您還可以輕鬆定義「提交」按鈕選項，以獲得無縫的用戶體驗。

### 基本標籤 {#basic-tab}

![基本標籤](/help/adaptive-forms/assets/button_basictab.png)

* **名稱**  — 您可以在表單和規則編輯器中輕鬆地使用其唯一名稱標識表單元件，但名稱不能包含空格或特殊字元。

* **標題**  — 使用其「標題」，您可以輕鬆地在窗體中標識元件，預設情況下，標題會顯示在元件的頂部。 如果未添加標題，則將顯示元件的名稱，而不顯示標題文本。

* **綁定引用**  — 綁定引用是對儲存在外部資料源中並以表單形式使用的資料元素的引用。 綁定引用允許您將資料動態綁定到表單域，以便表單可以顯示資料源中的最新資料。 例如，可以使用綁定引用根據輸入到表單中的客戶ID在表單中顯示客戶的名稱和地址。 綁定引用還可用於使用輸入到表單中的資料更新資料源。 通過這種方式，AEM Forms使您能夠建立與外部資料源交互的表單，從而為收集和管理資料提供無縫的用戶體驗。

* **隱藏元件**  — 選擇從窗體中隱藏元件的選項。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。 當您需要儲存用戶不需要看到或直接更改的資訊時，此功能非常有用。
* **禁用元件**  — 選擇禁用元件的選項。 禁用的元件不處於活動狀態或最終用戶不可編輯。 用戶可以查看欄位的值，但無法修改它。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。
* **只讀**  — 選擇選項，使元件不可編輯。 用戶可以查看欄位的值，但無法修改它。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。

### 幫助內容頁籤 {#help-content}

![「幫助內容」頁籤](/help/adaptive-forms/assets/button_helptab.png)

* **簡短描述**  — 簡短說明是簡短的文本說明，提供有關特定表單域目的的其他資訊或說明。 它有助於用戶瞭解應輸入到欄位中的資料類型，並可提供指導或示例以幫助確保輸入的資訊有效且符合所需標準。 預設情況下，短描述仍隱藏。 啟用 **始終顯示簡短說明** 的子菜單。

* **始終顯示簡短說明**  — 啟用選項以在元件下顯示簡短說明。

* **幫助文本**  — 幫助文本指向用戶提供的附加資訊或指導，以幫助用戶正確填寫表單域。 當用戶按一下該元件旁邊的幫助表徵圖(i)時，將顯示該表徵圖。 幫助文本提供了比表單域的標籤或佔位符文本更詳細的資訊，旨在幫助用戶瞭解該域的要求或約束。 還可提供建議或示例，使填寫表格更簡單、更準確。

### 協助工具 {#accessibility}

![輔助功能頁籤](/help/adaptive-forms/assets/button_accessibilitytab.png)

**螢幕閱讀器的文本**  — 螢幕閱讀器的文本是指供視障人士使用的輔助技術（如螢幕閱讀器）專門閱讀的附加文本。 此文本提供表單域目的的音頻說明，並可包括有關域標題、說明、名稱和任何相關消息的資訊（自定義文本）。 螢幕閱讀器文本有助於確保所有用戶都能訪問表單，包括那些有視覺障礙的用戶，並為他們提供對表單域及其要求的全面瞭解。

## 設計對話框 {#design-dialog}

「設計」對話框用於定義和管理「提交」按鈕元件的CSS樣式。

### 樣式頁籤 {#styles-tab}

該頁籤用於定義和管理元件的CSS樣式。 自適應Forms提交按鈕核心元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話框](/help/adaptive-forms/assets/reset_designdialog.png)


* **預設CSS類**:您可以為「自適應Forms提交」按鈕核心元件提供預設的CSS類。

* **允許的樣式**:可以通過提供表示樣式的名稱和CSS類來定義樣式。 例如，可以建立名為「bold text」的樣式，並提供CSS類「font-weight:粗體」。 可以在自適應Forms編輯器中使用這些樣式或將這些樣式應用於自適應表單。 要應用樣式，請在「自適應Forms」編輯器中，選擇要應用樣式的元件，導航到屬性對話框，然後從 **樣式** 的子菜單。 如果需要更新或修改樣式，只需返回到「設計」對話框，更新樣式頁籤中的樣式，並保存更改。
