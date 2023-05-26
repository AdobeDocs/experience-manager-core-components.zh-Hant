---
title: 最適化Forms核心元件 — 標題
description: 使用或自訂最適化Forms標題核心元件。
role: Architect, Developer, Admin, User
exl-id: 33eac885-8d66-4a5c-9a32-0ba11e6de293
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 1%

---

# 標題 {#title-input-adaptive-forms-core-component}

在最適化表單中，「標題」是指出現在表單頂端（通常在標題下方）的文字。 使用Title元件指定標題。 此元件可新增至表單版面，其文字可編輯以符合表單的用途或主題。 標題可為使用者提供表單的標籤或簡短說明，有助於區分表單與其他表單。

**範例**

![](/help/adaptive-forms/assets/title.png)

## 使用狀況 {#reasons-to-use-title-in-an-adaptive-form}

在表單中使用標題是好的作法的原因有幾個：

* **清晰度**：標題可清楚識別表單的用途，協助使用者瞭解他們需要提供的資訊。

* **組織**：標題可協助您依主題或目的組織表單，讓使用者更容易找到所需的表單。

* **協助工具**：標題是具備協助工具需求之使用者的關鍵元素，因為標題會由熒幕朗讀程式朗讀，協助使用者瞭解表單內容。

* **品牌化**：標題也可用來顯示公司或組織的名稱，有助於建立對使用者的信任和熟悉感。

* **導覽**：標題也可用於在表單中導覽，尤其是表單很長或複雜時。

* **搜尋引擎最佳化(SEO)**：在表單上設定標題也有助於進行SEO，因為搜尋引擎會使用標題來判斷網頁與搜尋查詢的相關性。

整體而言，表單標題是使用者體驗的重要方面，其應用於為表單提供簡潔清晰的標籤，以協助使用者瞭解表單的上下文和用途。

## 版本和相容性 {#version-and-compatibility}

Adaptive Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 和更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和更新版本，但低於2.0.0。 |

如需核心元件版本和發行版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技術細節 {#technical-details}

在以下位置的技術檔案中取得最適化Forms標題核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以使用「設定」對話方塊輕鬆自訂訪客的標題體驗。 您也可以輕鬆定義標題選項，提供順暢的使用者體驗。

![基本索引標籤](/help/adaptive-forms/assets/title_properties.png)

編輯對話方塊可讓內容作者定義標題文字並選取標題層級。

* **標題**  — 透過其Title ，您可以輕鬆識別表單中的元件，且根據預設，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件名稱而非標題文字。
* **型別/大小**  — 定義標題的標題等級。
* **ID**  — 此選項可讓您控制HTML和資料層中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

## 設計對話方塊 {#design-dialog}

「設計」索引標籤可用來定義和管理日期選擇器元件的CSS樣式。

### 標題

「標題」標籤可讓範本作者為表單作者設定預設和允許的HTML標題元素：

![設計對話方塊標題索引標籤](/help/adaptive-forms/assets/title_heading.png)

* **允許的標題元素**：含有多個選項的清單，可讓範本作者選擇哪些標題元素可以形成作者可用於標題。

* **預設標題元素**：為Title元件設定預設標題元素的下拉式清單。

### 樣式索引標籤 {#styles-tab}

索引標籤可用來定義和管理元件的CSS樣式。 最適化Forms日期選擇器核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊標題索引標籤](/help/adaptive-forms/assets/title_styles.png)

* **預設CSS類別**：您可以為最適化Forms日期選擇器核心元件提供預設CSS類別。

* **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在調適型Forms編輯器中將這些樣式使用或套用至調適型表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只需返回「設計」對話方塊，更新樣式標籤中的樣式，然後儲存變更即可。

### 格式標籤 {#format-tab}

「格式」索引標籤可讓您指定預設和自訂日期格式。

![格式標籤](/help/adaptive-forms/assets/title_styles.png)


