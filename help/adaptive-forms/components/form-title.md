---
title: 自適應表單核心元件 - 標題
description: 使用或自訂自適應表單標題核心元件。
role: Architect, Developer, Admin, User
exl-id: 33eac885-8d66-4a5c-9a32-0ba11e6de293
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '864'
ht-degree: 100%

---


# 表單標題元件{#title-input-adaptive-forms-core-component}

在自適應表單中，「標題」是指出現在表單頂端的文字，通常在頁首下方。使用標題元件指定標題。此元件可新增至表單版面，其文字可編輯以符合表單的用途或主題。標題可作為表單的標籤或簡短說明，可幫助使用者區分該表單與其他表單的不同。

{{traditional-aem}}

**範例**

![標題範例](/help/adaptive-forms/assets/title.png)

## 用途 {#reasons-to-use-title-in-an-adaptive-form}

在表單中使用標題是良好做法的原因有幾個：

- **清晰度**：標題可清楚識別表單的用途，協助使用者了解他們需要提供哪些資訊。

- **組織性**：標題有助於按主題或用途整理表單，讓使用者更容易找到所需的表單。

- **協助工具**：標題對於有協助工具需求的使用者是關鍵元素，因為螢幕助讀程式會大聲朗讀標題，協助使用者了解表單的內容。

- **品牌化**：標題也可用來顯示公司或組織的名稱，有助於建立使用者的信任感和熟悉感。

- **導覽**：標題對於瀏覽表單也很有用，尤其是表單很長或很複雜時。

- **搜尋引擎最佳化 (SEO)**：在表單上設定標題也有助於進行 SEO，因為搜尋引擎會使用該標題來判斷網頁與搜尋查詢的相關性。

整體而言，表單標題是使用者體驗的重要層面，應運用於為表單提供簡潔清晰的標籤，以協助使用者瞭解表單的內容脈絡和用途。

## 版本和相容性 {#version-and-compatibility}

自適應表單標題核心元件於 2023 年 2 月發行，屬於 Cloud Service 核心元件 2.0.4 和 AEM 6.5.16.0 Forms 或更新版本的核心元件 1.1.12 的一部分。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

| 元件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更新版本 |
|---|---|---|
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 與<br>[ 1.1.12 版](/help/adaptive-forms/version.md)及更新版本相容，但低於 2.0.0 版。 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title) 的技術文件中可找到自適應表單標題核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的標題體驗。同樣能夠輕鬆定義標題選項，以提供順暢無礙的使用者體驗。

![基本索引標籤](/help/adaptive-forms/assets/title_properties.png)

編輯對話框可讓內容作者定義標題文字並選取標題層級。

- **標題** - 您可以使用其標題輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。若未新增標題，則會顯示該元件的名稱而非標題文字。
- **類型/大小** - 定義標題的標題層級。
- **ID** - 此選項可讓您控制 HTML 和「資料層」中元件的唯一識別碼。
   - 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   - 若已指定 ID，則作者應確保其為唯一識別碼。
   - 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

## 設計對話框 {#design-dialog}

「設計索引標籤」可用於定義和管理表單標題元件的 CSS 樣式。

### 標題

標題索引標籤可讓範本作者為表單作者設定預設和允許的 HTML 標題元素：

![設計對話框標題索引標籤](/help/adaptive-forms/assets/title_heading.png)

- **允許的標題元素**：包含多個選項的清單，可讓範本作者選擇哪些標題元素可供表單作者用於標題。

- **預設標題元素**：為標題元件設定預設標題元素的下拉式清單。

### 樣式索引標籤 {#styles-tab}

此索引標籤可用於定義和管理元件的 CSS 樣式。自適應表單日期挑選器核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話框標題索引標籤](/help/adaptive-forms/assets/title_styles.png)

- **預設 CSS 類別**：您可以為自適應表單標題核心元件提供預設 CSS 類別。

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 格式索引標籤 {#format-tab}

格式索引標籤可讓您指定預設和自訂日期格式。

![格式索引標籤](/help/adaptive-forms/assets/title_styles.png)

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 相關文章 {#related-articles}


{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}