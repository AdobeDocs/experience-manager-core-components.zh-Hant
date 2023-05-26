---
title: 索引標籤元件
description: 索引標籤元件可讓您建立多個索引標籤，以在一個頁面上排列內容。
role: Architect, Developer, Admin, User
exl-id: 0031c5f3-447c-4932-898f-2f453801e492
source-git-commit: e8b3e55a42b6be6262d6f51b9569c0be3e8ce6c3
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 0%

---

# 索引標籤元件 {#tabs-component}

核心元件索引標籤元件可將內容整理到多個索引標籤上。

## 使用狀況 {#usage}

索引標籤元件可讓內容作者在多個索引標籤中組織頁面內容。

此 [編輯對話方塊](#edit-dialog) 允許內容作者定義多個索引標籤並設定作用中索引標籤。 使用 [設計對話方塊](#design-dialog)，範本作者可以定義哪些元件可以新增到索引標籤並自訂樣式。

>[!TIP]
>
>支援巢狀標籤元件（標籤內的標籤）。
>
>可以使用來定位/選取簡單（非巢狀）索引標籤元件 [內容樹狀結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree)，但巢狀索引標籤不可是。

## 版本和相容性 {#version-and-compatibility}

索引標籤元件的目前版本是v1，此版本隨2018年10月的核心元件2.2.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容於<br>[版本2.17.4](/help/versions.md) 和先前的 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗索引標籤元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_tabs).

### 技術細節 {#technical-details}

有關索引標籤元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_tabs_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 深層連結至面板 {#deep-linking}

標籤、 [輪播，](carousel.md) 和 [摺疊式功能表元件](accordion.md) 支援直接連結至元件中的面板。

若要這麼做：

1. 使用檢視含有元件的頁面 **[檢視已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 頁面編輯器中的選項。
1. Inspect頁面內容並識別面板的ID。
   * 例如 `id="accordion-86196c94d3-item-ca319dbb0b"`
1. 此ID會成為您可以使用雜湊(`#`)。
   * 例如 `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

導覽至將面板ID作為錨點的URL，瀏覽器會直接捲動至特定元件並顯示指定的面板。 如果面板依預設設定為不展開，則會自動展開。

## 編輯對話方塊 {#edit-dialog}

內容作者可以使用「編輯」對話方塊來建立、重新命名和重新排列標籤，以及定義作用中的標籤。

### 專案標籤 {#items-tab}

![索引標籤元件的「編輯」對話方塊專案索引標籤](/help/assets/tabs-edit-items.png)

使用 **新增** 按鈕來開啟元件選擇器，選擇要新增為索引標籤的元件。 新增後，一個專案會新增到清單中，包含以下欄：

* **圖示**  — 標籤的元件型別圖示，用於方便在清單中識別。 將滑鼠移到上方以檢視完整的元件名稱作為工具提示。
* **說明**  — 用作索引標籤文字的說明，預設為為索引標籤選取的元件名稱。
* **刪除**  — 點選或按一下以從索引標籤元件中刪除索引標籤。
* **重新排列**  — 點選或按一下並拖曳以重新排列標籤。

>[!TIP]
>
>如果減小頁面檢視區，使編輯對話方塊變成全熒幕， **新增** 按鈕將會隱藏。 元件仍可透過以下方式新增至索引標籤元件 [從元件瀏覽器拖曳並放置在頁面編輯器的索引標籤元件上](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component).

### 屬性標籤 {#properties-tab}

![標籤元件的「編輯」對話方塊屬性標籤](/help/assets/tabs-edit-properties.png)

* **使用中的專案**  — 內容作者可以定義載入頁面時處於作用中狀態的索引標籤。
   * 使用 **預設** 選項，則會選取第一個索引標籤。
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 協助工具標籤 {#accessibility-tab}

![索引標籤元件的「編輯」對話方塊輔助功能索引標籤](/help/assets/tabs-edit-accessibility.png)

於 **協助工具** 標籤，可設定的值 [ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性值

## 選取面板 {#select-panel}

內容作者可以使用 **選取面板** 元件工具列上的選項，以變更為不同的面板進行編輯，以及輕鬆地重新排列索引標籤。

![選取面板圖示](/help/assets/select-panel-icon.png)

選取 **選取面板** 選項時，已設定的索引標籤會顯示為下拉式清單。

* 清單會依指派的標籤排列順序排列，並會反映在編號中。
* 首先顯示標籤的元件型別，然後是較細字型的標籤說明。

![「選取面板」彈出視窗](/help/assets/select-panel-popover.png)

* 在下拉式清單中點選或按一下專案，會在編輯器中將檢視切換到該標籤。
* 您可以使用拖曳操作框就地重新排列標籤。

>[!NOTE]
>
>索引標籤在中無法由作者選取 **編輯** 模式。 使用 **[預覽](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)** 模式或 **[檢視已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 以已發佈內容讀者身分與索引標籤互動的選項。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些元件可新增為索引標籤元件的專案，以及定義哪些自訂樣式可供內容作者使用。

### 允許的元件索引標籤 {#allowed-components-tab}

此 **允許的元件** tab可用來定義哪些元件可由內容作者新增為索引標籤元件的專案。

「允許的元件」標籤的功能與相同名稱的標籤的功能相同，當 [在範本編輯器中定義配置容器的原則和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式索引標籤 {#styles-tab}

索引標籤元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe使用者端資料層 {#data-layer}

索引標籤元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
