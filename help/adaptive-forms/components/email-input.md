---
title: 自適應Forms核心元件 — 電子郵件輸入
description: 使用或自定義自適應Forms電子郵件輸入核心元件。
role: Architect, Developer, Admin, User
exl-id: f6a2974b-991e-4cea-9ef8-0b03e8975eeb
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---

# 電子郵件輸入 {#Email-input-adaptive-forms-core-component}

自適應表單電子郵件輸入核心元件用於收集用戶的電子郵件地址。 電子郵件輸入欄位允許瀏覽器驗證輸入的資料是否是有效的電子郵件地址格式。 它通常表示為文本框，並具有模式驗證以僅接受有效的電子郵件地址。 電子郵件輸入欄位可以進一步使用諸如&quot;required&quot;、&quot;placeholder&quot;和&quot;pattern&quot;等附加屬性自定義，以設定輸入資料的驗證。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

將電子郵件輸入元件納入自適應表單是有益的原因有幾：

* **方便用戶**:電子郵件輸入使用戶更容易輸入其電子郵件地址，因為它可以清楚地顯示欄位中預期的資料。

* **個性化通信**:通過表單從用戶收集電子郵件地址，可進行個性化通信，如發送確認電子郵件或新聞稿。

* **線索生成**:通過通過表單收集電子郵件地址，企業可以構建其電子郵件清單並將其用於潛在顧客生成。

* **用戶驗證**:電子郵件地址可以用作訪問受限內容或服務的驗證手段。

* **反饋集合**:反饋表單中的電子郵件輸入允許企業與用戶通信，以便跟蹤或澄清其反饋。

## 版本和相容性 {#version-and-compatibility}

自適應Forms手風琴核心元件於2023年2月發佈，作為用於Cloud Service的核心元件2.0.4的一部分，以及用於Forms或更晚版本的核心元件1.1.12的核心元件6.5.16.0的一部分。 下面是一個表，其中顯示了所有支援的版本AEM、相容性以及指向相應文檔的連結：

| 元件版本 | AEM as a Cloud Service  | AEM6.5.16.0Forms |
|---|---|---|
| v1 | 相容<br>[發行版2.0.4](/help/adaptive-forms/version.md) 之後 | 相容<br>[發行版1.1.12](/help/adaptive-forms/version.md) 晚但小於2.0.0。 |

有關核心元件版本和版本的資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 的子菜單。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

獲取有關自適應Forms電子郵件輸入核心元件的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/emailinput/v1/emailinput)。 有關開發核心元件的詳細資訊，請查看 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

通過「配置」對話框，您可以輕鬆地為訪問者自定義電子郵件輸入體驗。 您還可以輕鬆定義電子郵件輸入選項，以獲得無縫的用戶體驗。

### 基本標籤 {#basic-tab}

![基本頁籤](/help/adaptive-forms/assets/email_basictab.png)

* **名稱**  — 名稱在規則編輯器中唯一標識元件。名稱字串中不允許使用特殊字元和空格。

* **標題**  — 使用其「標題」，您可以輕鬆地在窗體中標識元件，預設情況下，標題會顯示在元件的頂部。 如果未添加標題，則將顯示元件的名稱，而不顯示標題文本。

* **隱藏標題**  — 選擇用於隱藏元件標題的選項。

* **佔位符文本**  — 表單元件中的佔位符文本是指在輸入欄位中顯示的短標籤或提示，提示用戶在該欄位中應輸入何種類型的資訊。 當用戶開始在欄位中鍵入內容時，佔位符文本將消失，如果欄位為空，則會重新顯示。 它為用戶提供可視提示，但不充當欄位的永久標籤或值。

* **綁定引用**  — 綁定引用是對儲存在外部資料源中並以表單形式使用的資料元素的引用。 綁定引用允許您將資料動態綁定到表單域，以便表單可以顯示資料源中的最新資料。 例如，可以使用綁定引用根據輸入到表單中的客戶ID在表單中顯示客戶的名稱和地址。 綁定引用還可用於使用輸入到表單中的資料更新資料源。 通過這種方式，AEM Forms使您能夠建立與外部資料源交互的表單，從而為收集和管理資料提供無縫的用戶體驗。
* **隱藏元件**  — 選擇從窗體中隱藏元件的選項。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。 當您需要儲存用戶不需要看到或直接更改的資訊時，此功能非常有用。
* **禁用元件**  — 選擇禁用元件的選項。 禁用的元件不處於活動狀態或最終用戶不可編輯。 用戶可以查看欄位的值，但無法修改它。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。
* **只讀**  — 選擇選項，使元件不可編輯。 用戶可以查看欄位的值，但無法修改它。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。

* **預設值**  — 此選項允許您在表單欄位中添加預設值。 如果 **禁用的元件** 或 **只讀元件** 的子菜單。 如果用戶未在表單欄位中輸入值，則在提交表單時提交此值


### 驗證頁籤 {#validation-tab}

![驗證頁籤](/help/adaptive-forms/assets/email_validationtab.png)

* **必需**  — 如果要在「自適應表單」中顯示元件，請選擇此選項。 無法選擇 **隱藏元件** 或 **禁用元件**  的 **基本** 頁籤

* **錯誤消息**  — 此選項允許您輸入一條消息，如果 **必需** 複選框，並且表單域為空。

* **指令碼驗證消息**  — 此選項允許您輸入在指令碼驗證失敗時顯示的消息。

* **最大字元數**  — 此選項允許您指定欄位中允許的最大字元數。 如果輸入的字元大於中指定的值 **最大字元數**，螢幕上出現錯誤資訊。 的 **最大字元錯誤消息** 對話框，您可以添加自定義錯誤消息。

* **最大字元錯誤消息** - **最大字元錯誤消息** 對話框允許您在輸入的字元數大於在 **最大字元數** 的雙曲餘切值。

* **最小字元數**  — 此選項允許您指定欄位中允許的最小字元數。 如果輸入的字元小於中指定的值 **最小字元數**，螢幕上出現錯誤資訊。 的 **最小字元錯誤消息** 對話框，您可以添加自定義錯誤消息。

* **最小字元錯誤消息** - **最小字元錯誤消息** 對話框允許您在輸入的字元數小於在 **最小字元數** 的雙曲餘切值。

<br>

    **驗證模式**選項允許您輸入模式以驗證輸入的電子郵件ID。 如果電子郵件ID無法使用**Pattern*選項中輸入的值進行驗證，則螢幕上將顯示錯誤消息。
    * **模式** — 此選項允許您輸入允許的電子郵件驗證模式。 也允許使用規則運算式。
    * **錯誤消息** — 如果電子郵件ID未能與**Pattern**選項中輸入的值進行驗證，則此選項允許您輸入顯示在螢幕上的消息

### 幫助內容頁籤 {#help-content-tab}

![「幫助內容」頁籤](/help/adaptive-forms/assets/email_helptab.png)

* **簡短描述**  — 簡短說明是簡短的文本說明，提供有關特定表單域目的的其他資訊或說明。 它有助於用戶瞭解應輸入到欄位中的資料類型，並可提供指導或示例以幫助確保輸入的資訊有效且符合所需標準。 預設情況下，短描述仍隱藏。 啟用 **始終顯示簡短說明** 的子菜單。

* **始終顯示簡短說明**  — 啟用選項以在元件下顯示簡短說明。

* **幫助文本**  — 幫助文本指向用戶提供的附加資訊或指導，以幫助用戶正確填寫表單域。 當用戶按一下該元件旁邊的幫助表徵圖(i)時，將顯示該表徵圖。 幫助文本提供了比表單域的標籤或佔位符文本更詳細的資訊，旨在幫助用戶瞭解該域的要求或約束。 還可提供建議或示例，使填寫表格更簡單、更準確。

### 輔助功能頁籤 {#accessibility-tab}

![輔助功能頁籤](/help/adaptive-forms/assets/email_accessibilitytab.png)

**螢幕閱讀器的文本**  — 螢幕閱讀器的文本是指供視障人士使用的輔助技術（如螢幕閱讀器）專門閱讀的附加文本。 此文本提供表單域目的的音頻說明，並可包括有關域標題、說明、名稱和任何相關消息的資訊（自定義文本）。 螢幕閱讀器文本有助於確保所有用戶都能訪問表單，包括那些有視覺障礙的用戶，並為他們提供對表單域及其要求的全面瞭解。

## 設計對話框 {#design-dialog}

「設計」對話框用於定義和管理電子郵件輸入元件的CSS樣式。

### 樣式頁籤 {#styles-tab}

該頁籤用於定義和管理元件的CSS樣式。 自適應Forms電子郵件輸入核心元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

![樣式頁籤](/help/adaptive-forms/assets/email_designdialog.png)

* **預設CSS類**:您可以為Adaptive Forms電子郵件輸入核心元件提供預設CSS類。

* **允許的樣式**:可以通過提供表示樣式的名稱和CSS類來定義樣式。 例如，可以建立名為「bold text」的樣式，並提供CSS類「font-weight:粗體」。 可以在自適應Forms編輯器中使用這些樣式或將這些樣式應用於自適應表單。 要應用樣式，請在「自適應Forms」編輯器中，選擇要應用樣式的元件，導航到屬性對話框，然後從 **樣式** 的子菜單。 如果需要更新或修改樣式，只需返回到「設計」對話框，更新樣式頁籤中的樣式，並保存更改。

### 「格式」頁籤 {#format-tab}

「格式」頁籤允許您指定預設和自定義日期格式。

![「設計」頁籤](/help/adaptive-forms/assets/emailinput_designformattab.png)

