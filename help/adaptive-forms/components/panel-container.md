---
title: 最適化Forms核心元件 — 面板容器
description: 使用或自訂Adaptive Forms面板容器核心元件。
role: Architect, Developer, Admin, User
source-git-commit: b2c35d78ba0473273852deb678b34b5dd96cf51e
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 0%

---

# 面板容器 {#panel-container-adaptive-forms-core-component}

在最適化表單中，面板是容器元素，可用來將相關的表單元素群組在一起。 它可讓您以邏輯和有意義的方式分組和組織不同的表單元素。 這有助於改善表單的整體結構和可讀性，讓使用者更容易理解和導覽。

面板也可用來建立可摺疊的區段，這對於隱藏複雜或不常使用的表單欄位很有用，讓表單保持簡單且易於使用。 它也可讓您包含其他元件，例如文字、核取方塊、按鈕等。

它也可用來設定不同的規則型動作，例如提交表單、開啟網站、顯示/隱藏元件或新增面板的執行個體。

**範例**

![](/help/adaptive-forms/assets/panel-container.png)

## 使用狀況 {#reasons-to-use-panel-container}

在表單中使用面板有幾個理由，包括：

* **組織表單元素**：面板可用來將相關的表單元素群組在一起，讓使用者更容易理解和導覽表單。

* **改善表單結構**：將表單元素分組為面板，可改善表單的整體結構和可讀性，使其更易於理解。

* **建立可摺疊區段**：面板可用來建立可摺疊的區段，這對於隱藏複雜或不常使用的表單欄位很有用，讓表單保持簡單且易於使用。

* **增強可用性**：使用面板來組織表單元素，可讓表單更方便使用者且易於使用，進而提高完成率。

## 版本和相容性 {#version-and-compatibility}

Adaptive Forms面板容器核心元件於2023年2月發行，是核心元件2.0.4的一部分。下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service  |
| — | --- |
| v1 | 相容於<br>[版本2.0.4](/help/versions.md) 和更新版本 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱 [核心元件版本](/help/versions.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在以下位置的技術檔案中取得最適化Forms面板容器核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以使用「設定」對話方塊輕鬆自訂訪客的面板容器體驗。 您也可以輕鬆定義面板容器選項，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/basic-panel.png)

* **名稱**  — 您可以在表單和規則編輯器中以唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **標題**  — 透過其Title ，您可以輕鬆識別表單中的元件，且根據預設，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件名稱而非標題文字。

* **隱藏標題**  — 選取隱藏元件標題的選項。

* **將資料換行至物件**  — 選擇「在物件中繞排資料」，將精靈的欄位資料放在JSON物件內。 如果未選擇，則提交資料JSON的精靈欄位會具有平面結構。

* **版面**  — 您可以為精靈使用固定版面（簡單）或彈性版面（回應式格線）。 「簡單」版面可讓一切固定在原處，而「回應式格線」則可讓您調整元件位置，以符合您的需求。 例如，使用回應式格線將「名字」、「中間名」和「姓氏」在表單中以單列對齊。

* **繫結參考**  — 繫結參考是儲存在外部資料來源中並在表單中使用的資料元素的參考。 繫結參考可讓您將資料動態繫結至表單欄位，讓表單可顯示資料來源的最新資料。 例如，繫結參考可用於根據在表單中輸入的客戶ID在表單中顯示客戶名稱和地址。 繫結參考也可用來使用輸入表單中的資料更新資料來源。 透過這種方式，AEM Forms可讓您建立與外部資料來源互動的表單，提供順暢的使用者體驗來收集和管理資料。
* **隱藏元件**  — 選取選項，從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存使用者不需要看到或直接變更的資訊時，這會很有用。
* **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 重複面板標籤 {#repeat-panel}

![重複標籤](/help/adaptive-forms/assets/repeat-panel.png)

您可以使用重複性選項來複製面板容器及其子元件、定義最小和最大重複計數，以及簡化表單中類似區段的複製。 與面板容器元件互動並存取其設定時，會顯示下列選項：

* **讓精靈可重複**：可讓使用者啟用或停用重複測量功能的切換功能。
* **最小重複次數**：建立面板容器可重複的最小次數。 值為零表示「精靈」面板不會重複；預設值為零。
* **最大重複次數**：設定面板容器可重複的最大次數。 預設情況下，此值為無限制。

若要有效管理面板容器內的可重複區段，請依照以下提供的步驟操作： [建立具有可重複區段的表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html) 文章。

### 說明內容標籤 {#help-content}

![說明內容標籤](/help/adaptive-forms/assets/helpcontent-panel.png)


* **簡短說明**  — 簡短說明是簡短文字說明，提供有關特定表單欄位用途的其他資訊或說明。 它可協助使用者瞭解應在欄位中輸入什麼型別的資料，並可提供指引或範例來協助確保輸入的資訊有效並符合所需條件。 依預設，簡短說明仍會隱藏。 啟用 **一律顯示簡短說明** 選項來將它顯示在元件下方。

* **一律顯示簡短說明**  — 啟用選項以在元件下方顯示簡短說明。

* **說明文字**  — 說明文字是指為協助使用者正確填寫表單欄位，而提供給使用者的其他資訊或指引。 當使用者按一下置於元件旁的說明圖示(i)時，就會出現此選項。 說明文字提供比表單欄位的標籤或預留位置文字更詳細的資訊，其設計旨在協助使用者瞭解欄位的需求或限制。 它也可以提供建議或範例，使填寫表單更容易、更準確。

### 協助工具標籤 {#accessibility}

![協助工具索引標籤](/help/adaptive-forms/assets/accessibilty-panel.png)


* **熒幕助讀程式的文字**  — 熒幕助讀程式文字是指視力不佳人士使用的輔助技術（例如熒幕助讀程式）專門用於閱讀的其他文字。 此文字提供表單欄位用途的音訊說明，並可包含欄位標題、說明、名稱和任何相關訊息（自訂文字）的相關資訊。 熒幕助讀程式文字可協助確保表單可供所有使用者存取（包括視覺障礙使用者），並讓他們完全瞭解表單欄位及其需求。

* **熒幕助讀程式宣告的HTML角色** -HTML角色是一種屬性，用於指定HTML元素對輔助技術（如熒幕閱讀程式）的目的。 角色屬性可用來提供元素的其他上下文和語意意義，讓熒幕朗讀程式更容易向使用者解譯和宣告內容。 例如，在AEM Forms中，表單欄位的標籤可能具有「label」角色，而其輸入欄位的角色可能具有「textbox」。 這可協助熒幕助讀程式瞭解標籤和輸入欄位之間的關係，並正確地向使用者宣告這些內容。

