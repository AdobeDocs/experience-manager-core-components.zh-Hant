---
title: 最適化Forms核心元件 — 標題
description: 使用或自訂最適化Forms標題核心元件。
role: Architect, Developer, Admin, User
exl-id: 33eac885-8d66-4a5c-9a32-0ba11e6de293
source-git-commit: 732efc9ed450aa31078ecaad65c0c306679fe97e
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 1%

---

# 表單標題元件{#title-input-adaptive-forms-core-component}

在調適型表單中，「標題」是指出現在表單頂端的文字，通常在標題下方。 使用Title元件指定標題。 此元件可新增至表單版面，其文字可編輯以符合表單的用途或主題。 標題可為使用者提供表單的標籤或簡短說明，有助於區分表單與其他表單。

**範例**

標題![&#128279;](/help/adaptive-forms/assets/title.png)的範例

## 使用情況 {#reasons-to-use-title-in-an-adaptive-form}

在表單中使用標題是好的作法的原因有幾個：

- **清晰度**：標題可清楚識別表單的用途，協助使用者瞭解他們需要提供哪些資訊。

- **組織**：標題可協助您依主題或目的組織表單，讓使用者更容易找到所需的表單。

- **協助工具**：標題是有協助工具需求之使用者的關鍵元素，因為熒幕朗讀程式會大聲朗讀標題，協助使用者瞭解表單的內容。

- **品牌**：標題也可用來顯示公司或組織的名稱，有助於建立信任感和熟悉感。

- **導覽**：標題對於瀏覽表單也很有用，尤其是表單很長或很複雜時。

- **搜尋引擎最佳化(SEO)**：在表單上設定標題也有助於進行SEO，因為搜尋引擎會使用該標題來判斷網頁與搜尋查詢的相關性。

整體而言，表單標題是使用者體驗的重要方面，其應用於為表單提供簡潔清晰的標籤，以協助使用者瞭解表單的情境和用途。

## 版本和相容性 {#version-and-compatibility}

最適化Forms標題核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 與<br>[版本2.0.4](/help/adaptive-forms/version.md)和更新版本相容 | 與<br>[版本1.1.12](/help/adaptive-forms/version.md)及更新版本相容，但小於2.0.0。 |

如需核心元件版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_tw). -->


## 技術細節 {#technical-details}

在[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title)上的技術檔案中取得最適化Forms標題核心元件的最新資訊。 如需開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的標題體驗。 您也可以輕鬆定義標題選項，以提供順暢的使用者體驗。

![基本索引標籤](/help/adaptive-forms/assets/title_properties.png)

編輯對話方塊可讓內容作者定義標題文字並選取標題層級。

- **標題** — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。
- **Type /Size** — 定義標題的標題層級。
- **ID** — 此選項允許控制HTML和資料層中元件的唯一識別碼。
   - 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   - 若指定ID，作者應負責確認該ID為唯一ID。
   - 變更ID會對CSS、JS和資料層追蹤造成影響。

## 設計對話方塊 {#design-dialog}

「設計」索引標籤可用來定義和管理表單標題元件的CSS樣式。

### 標題

「標題」標籤可讓範本作者為表單作者設定預設和允許的HTML標題元素：

![設計對話方塊標題標籤](/help/adaptive-forms/assets/title_heading.png)

- **允許的標題元素**：包含多個選項的清單，可讓範本作者選擇哪些標題元素可組成作者可用於標題。

- **預設標題元素**：為標題元件設定預設標題元素的下拉式清單。

### 樣式索引標籤 {#styles-tab}

索引標籤可用來定義和管理元件的CSS樣式。 最適化Forms日期選擇器核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話方塊標題標籤](/help/adaptive-forms/assets/title_styles.png)

- **預設CSS類別**：您可以為最適化Forms標題核心元件提供預設CSS類別。

- **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至屬性對話方塊，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 格式標籤 {#format-tab}

格式索引標籤可讓您指定預設和自訂日期格式。

![格式標籤](/help/adaptive-forms/assets/title_styles.png)

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=zh-Hant)

-->

## 相關文章 {#related-articles}


{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}