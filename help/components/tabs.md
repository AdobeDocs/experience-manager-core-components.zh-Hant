---
title: 索引標籤元件
description: 「索引標籤元件」允許建立多個索引標籤，以在頁面上整理內容。
role: Architect, Developer, Admin, User
exl-id: 0031c5f3-447c-4932-898f-2f453801e492
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '1038'
ht-degree: 100%

---


# 索引標籤元件 {#tabs-component}

「核心元件索引標籤元件」可讓您將內容組織到多個索引標籤上。

{{traditional-aem}}

## 用途 {#usage}

「索引標籤元件」可讓內容作者在多個索引標籤內整理頁面內容。

[編輯對話框](#edit-dialog)可讓內容作者定義多個索引標籤，並設定作用中的索引標籤。使用[設計對話框](#design-dialog)，範本作者可以定義哪些元件可以加入索引標籤並自訂樣式。

>[!TIP]
>
>支援巢狀索引標籤元件 (索引標籤內的索引標籤)。
>
>可以使用[內容樹狀結構](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hant#content-tree)尋找/選取簡單 (非巢狀) 索引標籤元件，但不適用於巢狀索引標籤。

## 版本和相容性 {#version-and-compatibility}

「索引標籤元件」的目前版本為 v1，此版本於 2018 年 10 月隨著「核心元件」2.2.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「索引標籤元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_tabs_tw)。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_tabs_v1_tw)有關「索引標籤元件」的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 深度連結至面板 {#deep-linking}

索引標籤、[輪播](carousel.md)和[摺疊面板元件](accordion.md)支援直接連結至元件中的面板。

執行方法：

1. 在頁面編輯器中使用&#x200B;**[以發佈頁面形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant#view-as-published)**&#x200B;選項，檢視含有元件的頁面。
1. 檢查頁面內容並識別面板的 ID。
   * 例如：`id="accordion-86196c94d3-item-ca319dbb0b"`
1. ID 可以使用井字號 (`#`) 附加至 URL 成為錨點。
   * 例如：`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

導覽至將面板 ID 作為錨點的 URL 時，瀏覽器會直接捲動至特定元件，並顯示指定的面板。如果面板預設為不展開，則將會自動展開。

## 索引標籤和回應式設計 {#responsive-design}

所有「核心元件」都設計為可充分回應，以確保裝置間的順暢體驗。

某些進階元件 (如索引標籤元件) 在實施專案的內容中可能需要特別考量，以保持在所有條件下的回應能力。如需詳細資訊，請參閱[核心元件的回應式設計](/help/responsive.md)文件。

## 編輯對話框 {#edit-dialog}

編輯對話框可讓內容作者建立、重新命名和重新排列索引標籤，並可定義作用中索引標籤。

### 項目索引標籤 {#items-tab}

![索引標籤元件的編輯對話框項目索引標籤](/help/assets/tabs-edit-items.png)

使用&#x200B;**新增**&#x200B;按鈕開啟元件選擇器，選擇要新增為索引標籤的元件。新增後，就會在清單中新增一個項目，其中包含以下各欄：

* **圖示** - 索引標籤元件類型的圖示，以便在清單中輕鬆識別。將滑鼠移至上方，即可看到包含完整元件名稱的工具提示。
* **說明** - 說明作為索引標籤文字使用，預設為所選取的索引標籤元件名稱。
* **刪除** - 點選或按一下，以從索引標籤元件刪除該索引標籤。
* **重新排列** - 點選或按一下並拖曳，以重新排列索引標籤的順序。

>[!TIP]
>
>若縮小頁面檢視區，使編輯對話框進入全螢幕模式，則會隱藏&#x200B;**新增**&#x200B;按鈕。元件仍可新增至索引標籤元件，只需[從元件瀏覽器拖曳並放置到頁面編輯器的索引標籤元件上](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant#inserting-a-component)。

### 屬性索引標籤 {#properties-tab}

![索引標籤元件的編輯對話框屬性索引標籤](/help/assets/tabs-edit-properties.png)

* **作用中項目** - 內容作者可定義頁面載入時為作用中的索引標籤。
   * 使用&#x200B;**預設**&#x200B;選項，將會選取第一個索引標籤。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

### 協助工具索引標籤 {#accessibility-tab}

![索引標籤元件的編輯對話框協助工具索引標籤](/help/assets/tabs-edit-accessibility.png)

在&#x200B;**協助工具**&#x200B;索引標籤上，可以設定元件的 [ARIA 協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤值。

* **標籤** - 元件的 ARIA 標籤屬性值

## 選取面板 {#select-panel}

內容作者可使用元件工具列中的&#x200B;**選取面板**&#x200B;選項，切換至不同面板進行編輯，亦可輕鬆重新排列索引標籤的順序。

![選取面板圖示](/help/assets/select-panel-icon.png)

在元件工具列中選取&#x200B;**選取面板**&#x200B;選項後，已設定的索引標籤會顯示為下拉式清單。

* 清單會根據指派給索引標籤的排列方式排序，並反映在編號中。
* 首先顯示索引標籤元件類型，後面接著以較淺的字體顯示索引標籤說明。

![選取面板彈出視窗](/help/assets/select-panel-popover.png)

* 在下拉式清單中點選或按一下項目，將編輯器中的視圖切換至該索引標籤。
* 您可以使用拖曳控點就地重新排列索引標籤。

>[!NOTE]
>
>作者無法在&#x200B;**編輯**&#x200B;模式中選取索引標籤。使用&#x200B;**[預覽](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant#preview-mode)**&#x200B;模式或&#x200B;**[以發佈頁面形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant#view-as-published)**&#x200B;選項，可像已發佈內容的讀者那樣與索引標籤互動。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義以項目形式新增至索引標籤元件的元件，以及可供內容作者使用的自訂樣式。

### 允許的元件索引標籤 {#allowed-components-tab}

**允許的元件**&#x200B;索引標籤用於定義可供內容作者作為項目新增至索引標籤元件的元件。

[在範本編輯器中定義版面容器的原則與屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)時，允許的元件索引標籤與同名索引標籤的功能相同。

### 樣式索引標籤 {#styles-tab}

「索引標籤元件」支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「索引標籤元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
