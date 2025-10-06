---
title: 摺疊面板元件
description: 「核心元件摺疊面板」元件可讓您在頁面上建立以摺疊面板排列的面板集合。
role: Architect, Developer, Admin, User
exl-id: 1deb570a-3d8d-409e-805f-8460c49cf9bb
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '1102'
ht-degree: 100%

---


# 摺疊面板元件{#accordion-component}

「核心元件摺疊面板」元件可讓您在頁面上建立以摺疊面板排列的面板集合。

{{traditional-aem}}

## 用途 {#usage}

核心元件摺疊面板元件允許建立元件集合 (由面板組成)，並在頁面上以摺疊面板排列，類似於[索引標籤元件](tabs.md)，但允許展開和收合面板。

* 該摺疊面板的屬性可在[設定對話框](#configure-dialog)中定義。
* 摺疊面板的順序可以在設定對話框以及[選取面板彈出視窗](#select-panel-popover)中定義。
* 將摺疊面板元件新增至頁面時，可在[設計對話框](#design-dialog)中定義預設值。

## 版本和相容性 {#version-and-compatibility}

摺疊面板元件的目前版本為 v1，此版本於 2019 年 6 月隨著核心元件 2.5.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v1 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「摺疊面板元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_accordion_tw)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_accordion_v1_tw)有關摺疊面板元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 深度連結至面板 {#deep-linking}

摺疊面板、[輪播、](carousel.md)和[索引標籤元件](tabs.md)支援直接連結至元件中的面板。

執行方法：

1. 在頁面編輯器中使用&#x200B;**[以發佈頁面形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant#view-as-published)**&#x200B;選項，檢視含有元件的頁面。
1. 檢查頁面內容並識別面板的 ID。
   * 例如：`id="accordion-86196c94d3-item-ca319dbb0b"`
1. ID 可以使用井字號 (`#`) 附加至 URL 成為錨點。
   * 例如：`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

導覽至將面板 ID 作為錨點的 URL 時，瀏覽器會直接捲動至特定元件，並顯示指定的面板。如果面板預設為不展開，則將會自動展開。

## 摺疊面板和回應式設計 {#responsive-design}

所有「核心元件」都設計為可充分回應，以確保裝置間的順暢體驗。

某些進階元件 (如摺疊面板元件) 在實施專案的內容中可能需要特別考量，以保持在所有條件下的回應能力。如需詳細資訊，請參閱[核心元件的回應式設計](/help/responsive.md)文件。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義摺疊面板項目、其面板，以及其對頁面訪客的行為與顯示方式。

### 項目索引標籤 {#items-tab}

![摺疊面板元件編輯對話框的項目索引標籤](/help/assets/accordion-edit-items.png)

使用&#x200B;**新增**&#x200B;按鈕開啟元件選擇器，選擇要新增為面板的元件。新增後，就會在清單中新增一個項目，其中包含以下各欄：

* **圖示** - 面板元件類型的圖示，以便在清單中輕鬆識別。將滑鼠移至上方，即可看到包含完整元件名稱的工具提示。
* **說明** - 說明作為面板文字使用，預設為所選取的面板元件名稱。
* **刪除** - 點選或按一下，以從摺疊面板元件刪除該面板。
* **重新排列** - 點選或按一下並拖曳，以重新排列面板的順序。

>[!TIP]
>
>若縮小頁面檢視區，使編輯對話框進入全螢幕模式，則會隱藏&#x200B;**新增**&#x200B;按鈕。元件仍可新增至摺疊面板元件，只需[從元件瀏覽器拖曳並放置到頁面編輯器的摺疊面板元件上](https://helpx.adobe.com/tw/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)。

### 屬性索引標籤 {#properties-tab}

![摺疊面板元件編輯對話框的屬性索引標籤](/help/assets/accordion-edit-properties.png)

* **單一項目展開** - 選取後，此選項會強制一次展開單一摺疊面板項目。展開一個項目後，其他所有項目都會收合。
* **展開的項目** - 此選項會定義載入頁面時預設展開的項目。
   * 選取&#x200B;**單一項目展開** 時，必須選取一個面板。根據預設，會選取第一個面板。
   * 未選取&#x200B;**單一項目展開**&#x200B;時，此選項為多重選取且是選擇性的。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

## 選取面板彈出視窗 {#select-panel-popover}

內容作者可使用元件工具列中的&#x200B;**選取面板**&#x200B;選項，切換至不同面板進行編輯，亦可輕鬆重新排列摺疊面板內的面板順序。

![選取面板圖示](/help/assets/select-panel-icon.png)

在元件工具列中選取&#x200B;**選取面板**&#x200B;選項後，已設定的摺疊面板會顯示為下拉式清單。

![選取面板彈出視窗](/help/assets/select-panel-popover.png)

* 清單會根據指派給面板的排列方式排序，並反映在編號中。
* 首先顯示面板元件類型，後面接著以較淺的字體顯示面板說明。
* 在下拉式清單中點選或按一下項目，將編輯器中的視圖切換至該面板。
* 您可以使用拖曳控點就地重新排列面板。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可為使用摺疊面板元件的內容作者定義可用選項，以及在放置摺疊面板元件時所設定的預設值。

### 屬性索引標籤 {#properties-tab-design}

![設計對話框屬性索引標籤](/help/assets/accordion-design-properties.png)

* **允許的標題元素** - 此多選下拉式清單會定義允許由作者選取的摺疊面板項目標題 HTML 元素。
* **預設標題元素** - 此下拉式清單會定義預設摺疊面板項目標題 HTML 元素。

### 允許的元件索引標籤 {#allowed-components-tab}

**允許的元件**&#x200B;索引標籤用於定義可供內容作者作為項目新增至摺疊面板元件中面板的元件。

[在範本編輯器中定義版面容器的原則與屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant#editing-a-template-layout-template-author)時，允許的元件索引標籤與同名索引標籤的功能相同。

### 樣式索引標籤 {#styles-tab}

摺疊面板元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「摺疊面板元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
