---
title: 適用性Forms核心元件 — 標題
description: 使用或自訂適用性Forms標題核心元件。
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 1%

---


# 標題 {#title-input-adaptive-forms-core-component}

在適用性表單中，「標題」是指出現在表單頂端的文字，通常位於標題下方。 使用標題元件指定標題。 此元件可新增至表單配置，且可編輯其文字以符合表單的用途或主題。 標題可作為表單的標籤或簡短說明給使用者，有助於區分表單與其他表單。

**範例**

![](/help/adaptive-forms/assets/title.png)

## 使用狀況 {#reasons-to-use-title-in-an-adaptive-form}

在表單中使用標題是個好做法的原因有幾個：

* **清晰度**:標題可清楚識別表單的用途，協助使用者了解需要提供哪些資訊。

* **組織**:標題可協助您依主題或用途整理表單，讓使用者更容易找到所需表單。

* **協助工具**:標題是有協助工具需求的使用者的關鍵元素，因為標題是螢幕助讀程式朗讀的，可協助使用者了解表單的內容。

* **品牌推廣**:標題也可用來顯示公司或組織的名稱，有助於建立對使用者的信任感和熟悉感。

* **導覽**:標題也可用來導覽表單，尤其是表單較長或複雜時。

* **搜尋引擎最佳化(SEO)**:表單上的標題在SEO中也有幫助，因為搜尋引擎會使用標題來判斷網頁與搜尋查詢的相關性。

整體而言，表單的標題是使用者體驗的重要一環，應用來為表單提供清晰簡潔的標籤，以協助使用者了解表單的內容和用途。

## 版本與相容性 {#version-and-compatibility}

適用性Forms標題核心元件已於2023年2月發行，其為核心元件2.0.4的一部分。下表顯示所有支援的版本、AEM相容性，以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service  |
| — | --- |
| v1 | 相容於<br>[版本2.0.4](/help/versions.md) 和 | 相容 | 相容 |

如需核心元件版本和版本的相關資訊，請參閱 [核心元件版本](/help/versions.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技術詳細資訊 {#technical-details}

取得下列主題的技術檔案中適用性Forms標題核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 配置對話框 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的標題體驗。 您也可以輕鬆定義標題選項，以提供順暢的使用者體驗。

![基本標籤](/help/adaptive-forms/assets/title_properties.png)

編輯對話方塊可讓內容作者定義標題文字並選取標題層級。

* **標題**  — 使用其「標題」，您可以輕鬆地在表單中識別元件，預設情況下，標題會顯示在元件上方。 如果未新增標題，則會顯示元件名稱，而非標題文字。
* **類型/大小**  — 定義標題的標題級別。
* **ID**  — 此選項可控制HTML和資料層中元件的唯一識別碼。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

## 設計對話方塊 {#design-dialog}

「設計對話方塊」可用來定義及管理日期選取器元件的CSS樣式。

### 標題

「標題」索引標籤可讓範本作者為表單作者設定預設和允許的HTML標題元素：

![設計對話框標題頁簽](/help/assets/accordion-design-properties.png)

* **允許的標題元素**:此清單包含多個選項，可讓範本作者選擇哪些標題元素可讓作者用於標題。

* **預設標題元素**:一個下拉式清單，用於設定標題元件的預設標題元素。


### 樣式標籤 {#styles-tab}

「設計對話方塊」可用來定義及管理元件的CSS樣式。 適用性Forms日期選取器核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

**預設CSS類**:您可以為適用性Forms日期選取器核心元件提供預設CSS類別。

**允許的樣式**:您可以提供代表樣式的名稱和CSS類別，以定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight:粗體」。 您可以在適用性Forms編輯器中，將這些樣式使用或套用至適用性表單。 若要套用樣式，請在適用性Forms編輯器中選取您要套用樣式的元件、導覽至屬性對話方塊，然後從 **樣式** 下拉式清單。 如果需要更新或修改樣式，只需返回「設計」對話框、更新樣式頁簽中的樣式並保存更改即可。

### 格式標籤 {#format-tab}

格式索引標籤可讓您指定預設和自訂日期格式。

