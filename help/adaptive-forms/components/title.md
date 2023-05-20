---
title: 自適應Forms核心元件 — 標題
description: 使用或自定義自適應Forms標題核心元件。
role: Architect, Developer, Admin, User
exl-id: 33eac885-8d66-4a5c-9a32-0ba11e6de293
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 1%

---

# 標題 {#title-input-adaptive-forms-core-component}

在自適應表單中，「標題」是指出現在表單頂部的文本，通常位於標題下方。 標題是使用標題元件指定的。 此元件可以添加到表單佈局，並且可以編輯其文本以匹配表單的用途或主題。 標題作為表單的標籤或用戶對表單的簡短描述，有助於區分表單與其他表單。

**範例**

![](/help/adaptive-forms/assets/title.png)

## 使用狀況 {#reasons-to-use-title-in-an-adaptive-form}

有幾個原因可以解釋，為什麼在表單中使用標題是一種好做法：

* **清晰**:標題可以清楚地確定表單的用途，幫助用戶瞭解他們需要提供哪些資訊。

* **組織**:標題可幫助按主題或目的組織表單，使用戶更容易找到所需表單。

* **輔助功能**:標題是具有輔助功能需求的用戶的關鍵要素，因為螢幕閱讀器會大聲讀出標題，從而幫助用戶瞭解表單的上下文。

* **品牌**:標題還可用於顯示公司或組織的名稱，這有助於建立對用戶的信任和熟悉感。

* **導航**:標題也可用於瀏覽表單，尤其是當表單較長或複雜時。

* **搜索引擎優化(SEO)**:在表單上設定標題也有助於SEO，因為搜索引擎使用標題來確定網頁與搜索查詢的相關性。

總的來說，表單的標題是用戶體驗的一個重要方面，它應用於為表單提供清晰簡潔的標籤，幫助用戶理解表單的上下文和目的。

## 版本和相容性 {#version-and-compatibility}

自適應Forms手風琴核心元件於2023年2月發佈，作為用於Cloud Service的核心元件2.0.4的一部分，以及用於Forms或更晚版本的核心元件1.1.12的核心元件6.5.16.0的一部分。 下面是一個表，其中顯示了所有支援的版本AEM、相容性以及指向相應文檔的連結：

| 元件版本 | AEM as a Cloud Service  | AEM6.5.16.0Forms |
|---|---|---|
| v1 | 相容<br>[發行版2.0.4](/help/adaptive-forms/version.md) 之後 | 相容<br>[發行版1.1.12](/help/adaptive-forms/version.md) 晚但小於2.0.0。 |

有關核心元件版本和版本的資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 的子菜單。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技術詳細資訊 {#technical-details}

獲取有關自適應Forms標題核心元件的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title)。 有關開發核心元件的詳細資訊，請查看 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

通過「配置」對話框，您可以輕鬆地為訪問者自定義標題體驗。 您還可以輕鬆定義標題選項，以獲得無縫的用戶體驗。

![基本頁籤](/help/adaptive-forms/assets/title_properties.png)

編輯對話框允許內容作者定義標題文本並選擇標題級別。

* **標題**  — 使用其「標題」，您可以輕鬆地在窗體中標識元件，預設情況下，標題會顯示在元件的頂部。 如果未添加標題，則將顯示元件的名稱，而不顯示標題文本。
* **類型/大小**  — 定義標題的標題級別。
* **ID**  — 此選項允許控制HTML和資料層中元件的唯一標識符。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

## 設計對話框 {#design-dialog}

「設計」頁籤用於定義和管理日期選取器元件的CSS樣式。

### 標題

「標題」頁籤允許模板作者為表單作者設定預設和允許的HTML標題元素：

![「設計」對話框標題頁籤](/help/adaptive-forms/assets/title_heading.png)

* **允許的標題元素**:包含多個選項的清單，模板作者可以選擇哪些標題元素可以構成作者用於標題。

* **預設標題元素**:一個下拉清單，用於設定「標題」元件的預設標題元素。

### 樣式頁籤 {#styles-tab}

該頁籤用於定義和管理元件的CSS樣式。 自適應Forms選日期器核心元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

![「設計」對話框標題頁籤](/help/adaptive-forms/assets/title_styles.png)

* **預設CSS類**:可以為自適應Forms日期選取器核心元件提供預設CSS類。

* **允許的樣式**:可以通過提供表示樣式的名稱和CSS類來定義樣式。 例如，可以建立名為「bold text」的樣式，並提供CSS類「font-weight:粗體」。 可以在自適應Forms編輯器中使用這些樣式或將這些樣式應用於自適應表單。 要應用樣式，請在「自適應Forms」編輯器中，選擇要應用樣式的元件，導航到屬性對話框，然後從 **樣式** 的子菜單。 如果需要更新或修改樣式，只需返回到「設計」對話框，更新樣式頁籤中的樣式，並保存更改。

### 「格式」頁籤 {#format-tab}

「格式」頁籤允許您指定預設和自定義日期格式。

![格式頁籤](/help/adaptive-forms/assets/title_styles.png)


