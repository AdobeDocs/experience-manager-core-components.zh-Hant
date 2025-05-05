---
title: 索引標籤元件
description: 索引標籤元件可讓您建立多個索引標籤，以在一個頁面上排列內容。
role: Architect, Developer, Admin, User
exl-id: 0031c5f3-447c-4932-898f-2f453801e492
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 0%

---


# 索引標籤元件 {#tabs-component}

核心元件索引標籤元件可讓您將內容組織到多個索引標籤上。

## 使用情況 {#usage}

索引標籤元件可讓內容作者在多個索引標籤內整理頁面內容。

[編輯對話方塊](#edit-dialog)可讓內容作者定義多個索引標籤並設定作用中的索引標籤。 使用[設計對話方塊](#design-dialog)，範本作者可以定義哪些元件可以加入索引標籤並自訂樣式。

>[!TIP]
>
>支援巢狀標籤元件（標籤內的標籤）。
>
>可以使用[內容樹狀結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hant#content-tree)來尋找/選取簡單（非巢狀）索引標籤元件，但是無法巢狀索引標籤。

## 版本和相容性 {#version-and-compatibility}

索引標籤元件的目前版本是v1，此版本隨2018年10月的核心元件發行版本2.2.0的發佈引入，說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|--- |--- |--- |---|---|
| v1 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗索引標籤元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_tabs_tw)。

### 技術細節 {#technical-details}

在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_tabs_v1_tw)上可找到有關索引標籤元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 面板的深層連結 {#deep-linking}

索引標籤、[轉盤、](carousel.md)和[摺疊式功能表元件](accordion.md)支援直接連結至元件中的面板。

若要這麼做：

1. 在頁面編輯器中使用&#x200B;**[以發佈的形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant#view-as-published)**&#x200B;選項，檢視含有元件的頁面。
1. 檢查頁面內容並識別面板的ID。
   * 例如`id="accordion-86196c94d3-item-ca319dbb0b"`
1. ID會成為您可以使用雜湊(`#`)附加至URL的錨點。
   * 例如`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

導覽至將面板ID當作錨點的URL，瀏覽器會直接捲動至特定元件，並顯示指定的面板。 如果面板預設為不展開，則會自動展開。

## 標籤和回應式設計 {#responsive-design}

所有核心元件的設計都可充分回應，確保裝置間的順暢體驗。

有些進階元件（如標籤元件）在執行專案的內容中可能需要特別考量，以保持在所有條件下的回應能力。 如需詳細資訊，請參閱檔案[核心元件的回應式設計](/help/responsive.md)。

## 編輯對話方塊 {#edit-dialog}

內容作者可以使用「編輯」對話方塊來建立、重新命名和重新排列標籤，以及定義作用中的標籤。

### 專案標籤 {#items-tab}

![索引標籤元件的編輯對話方塊專案索引標籤](/help/assets/tabs-edit-items.png)

使用&#x200B;**新增**&#x200B;按鈕開啟元件選擇器，選擇要新增為索引標籤的元件。 新增專案後，專案會新增到清單中，包含以下欄：

* **圖示** — 標籤元件型別的圖示，可在清單中輕鬆識別。 將滑鼠移到上方以檢視完整的元件名稱作為工具提示。
* **描述** — 用作索引標籤文字的描述，預設為針對索引標籤選取的元件名稱。
* **刪除** — 點選或按一下以從索引標籤元件刪除索引標籤。
* **重新排列** — 點選或按一下並拖曳以重新排列標籤。

>[!TIP]
>
>如果減少頁面的檢視區以便讓編輯對話方塊變成全熒幕，將會隱藏&#x200B;**新增**&#x200B;按鈕。 元件仍可透過從元件瀏覽器拖曳並放置在頁面編輯器的索引標籤元件上[新增到索引標籤元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant#inserting-a-component)。

### 屬性標籤 {#properties-tab}

![索引標籤元件的編輯對話方塊屬性索引標籤](/help/assets/tabs-edit-properties.png)

* **作用中專案** — 內容作者可以定義載入頁面時作用中的索引標籤。
   * 透過&#x200B;**預設**&#x200B;選項，將會選取第一個索引標籤。
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 協助工具標籤 {#accessibility-tab}

![索引標籤元件的編輯對話方塊協助工具索引標籤](/help/assets/tabs-edit-accessibility.png)

在&#x200B;**協助工具**&#x200B;標籤上，可以為元件設定[ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤的值。

* **標籤** — 元件的ARIA標籤屬性值

## 選取面板 {#select-panel}

內容作者可以使用元件工具列上的&#x200B;**選取面板**&#x200B;選項，變更到不同的面板進行編輯，以及輕鬆地重新排列索引標籤。

![選取面板圖示](/help/assets/select-panel-icon.png)

在元件工具列中選取&#x200B;**選取面板**&#x200B;選項後，已設定的索引標籤會顯示為下拉式清單。

* 清單會依指派的標籤排列方式排序，並會反映在編號中。
* 首先顯示標籤的元件型別，然後是較細字型的標籤說明。

![選取面板彈出視窗](/help/assets/select-panel-popover.png)

* 在下拉式清單中點選或按一下專案，會在編輯器中將檢視切換至該索引標籤。
* 您可以使用拖曳操作框就地重新排列標籤。

>[!NOTE]
>
>作者在&#x200B;**編輯**&#x200B;模式中無法選取索引標籤。 使用&#x200B;**[預覽](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant#preview-mode)**&#x200B;模式或&#x200B;**[以發佈的形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant#view-as-published)**&#x200B;選項，可以像已發佈內容的讀者那樣與索引標籤互動。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些元件可新增為索引標籤元件的專案，並定義哪些自訂樣式可供內容作者使用。

### 允許的元件標籤 {#allowed-components-tab}

**允許的元件**&#x200B;索引標籤是用來定義哪些元件可由內容作者新增為索引標籤元件的專案。

當[在範本編輯器中定義配置容器的原則與屬性時，「允許的元件」索引標籤的功能與相同名稱的索引標籤相同。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)

### 樣式索引標籤 {#styles-tab}

索引標籤元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe使用者端資料層 {#data-layer}

索引標籤元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
