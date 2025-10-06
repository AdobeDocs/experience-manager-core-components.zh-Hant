---
title: 輪播元件
description: 輪播元件可讓內容作者以旋轉輪播的形式呈現內容。
role: Architect, Developer, Admin, User
exl-id: 3331214c-a05c-47e1-b54c-fbfd1045bd60
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '1317'
ht-degree: 100%

---


# 輪播元件{#carousel-component}

核心元件輪播元件可讓內容作者以可導覽輪播的形式呈現內容。

{{traditional-aem}}

## 用途 {#usage}

內容作者可使用輪播元件，將內容整理至旋轉的投影片輪播中。

[編輯對話框](#edit-dialog)可讓內容作者建立、命名及排序多個投影片，以及啟用自動轉場附延遲設定。使用[設計對話框](#design-dialog)，範本作者可以定義哪些元件可以新增到輪播、啟用或停用自動轉場，以及自訂樣式。

## 版本和相容性 {#version-and-compatibility}

輪播元件的目前版本為 v1，此版本於 2018 年 10 月隨著核心元件 2.2.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「輪播元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_carousel)」。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_carousel_v1)有關輪播元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 深度連結至面板 {#deep-linking}

輪播、[索引標籤](tabs.md)和[摺疊面板元件](accordion.md)支援直接連結至元件中的面板。

執行方法：

1. 在頁面編輯器中使用&#x200B;**[以發佈頁面形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;選項，檢視含有元件的頁面。
1. 檢查頁面內容並識別面板的 ID。
   * 例如：`id="carousel-bfe4fa6647-item-47f1a7ca67-tabpanel"`
1. ID 會成為您可以使用井字號 (`#`) 附加至 URL 的錨點。
   * 例如：`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#carousel-bfe4fa6647-item-47f1a7ca67-tabpanel`

導覽至將面板 ID 作為錨點的 URL 時，瀏覽器會直接捲動至特定元件，並顯示指定的面板。如果面板預設為不顯示，則會自動捲動至該處。

## 輪播與回應式設計 {#responsive-design}

所有「核心元件」都設計為可充分回應，以確保裝置間的順暢體驗。

某些進階元件 (如輪播元件) 在實施專案的內容中可能需要特別考量，以保持在所有條件下的回應能力。如需詳細資訊，請參閱[核心元件的回應式設計](/help/responsive.md)文件。

## 編輯對話框 {#edit-dialog}

內容作者可以使用編輯對話框來新增、重新命名和重新排列投影片，並定義自動轉場設定。

### 項目索引標籤 {#items-tab}

![輪播元件編輯對話框的項目索引標籤](/help/assets/carousel-edit-items.png)

使用&#x200B;**新增**&#x200B;按鈕開啟元件選擇器，選擇要新增為索引標籤的元件。新增後，就會在清單中新增一個項目，其中包含以下各欄：

* **圖示** - 索引標籤元件類型的圖示，以便在清單中輕鬆識別。將滑鼠移至上方，即可看到包含完整元件名稱的工具提示。
* **說明** - 說明作為索引標籤文字使用，預設為所選取的索引標籤元件名稱。
* **刪除** - 點選或按一下，以從索引標籤元件刪除該索引標籤。
* **重新排序** - 點選或按一下並拖曳以排序索引標籤。

>[!TIP]
>
>若縮小頁面檢視區，使編輯對話框進入全螢幕模式，則會隱藏&#x200B;**新增**&#x200B;按鈕。元件仍可新增至輪播元件，只需[從元件瀏覽器拖曳並放置到頁面編輯器的輪播元件上](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser)。

### 屬性索引標籤 {#properties-tab}

![輪播元件編輯對話框的屬性索引標籤](/help/assets/carousel-edit-properties.png)

在&#x200B;**屬性**&#x200B;索引標籤上，內容作者可以將投影片設定為自動轉場。

* **作用中項目** - 內容作者可定義頁面載入時為作用中的索引標籤。
* **投影片自動轉場** - 作用中時，元件會在指定的延遲時間後自動前進到下一張投影片。
* **轉場延遲** - 選取投影片自動轉場時，此值可用來定義轉場之間的延遲時間 (以毫秒為單位)。
* **停用游標停留時自動暫停** - 選取&#x200B;**投影片自動轉場**&#x200B;時，只要游標停留在輪播上，輪播轉場就會自動暫停。選取此選項時，轉場將不會暫停。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

>[!NOTE]
>
>在&#x200B;**編輯**&#x200B;模式中不會啟用投影片前進控制項。使用&#x200B;[**預覽**&#x200B;模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)或&#x200B;**[以發佈頁面形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;選項，可像已發佈內容的讀者那樣與輪播互動。
>
>在&#x200B;**編輯**&#x200B;模式下不會啟用自動前進功能。使用&#x200B;**[以發佈頁面形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;選項，可以像已發佈內容的讀者那樣檢視自動前進功能。

### 協助工具索引標籤 {#accessibility-tab}

![輪播元件編輯對話框的協助工具索引標籤](/help/assets/carousel-edit-accessibility.png)

在&#x200B;**協助工具**&#x200B;索引標籤上，可以設定元件的 [ARIA 協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤值。

* **標籤** - 輪播的 aria-label 屬性值，功用是說明輪播內容
* **上一個** - 輪播導覽的上一個按鈕標籤的 aria-label 屬性值
* **下一個** - 輪播導覽的下一個按鈕標籤的 aria-label 屬性值
* **播放** - 輪播導覽的播放按鈕標籤的 aria-label 屬性值
* **暫停** - 輪播導覽的暫停按鈕標籤的 aria-label 屬性值
* **索引標籤清單** - 輪播導覽的項目清單標籤的 aria-label 屬性值
* **將項目的 aria 標籤設定為其標題** - 如果勾選，此選項會自動將輪播項目標題設定為其 aria-label 說明。

## 選取面板 {#select-panel}

內容作者可使用元件工具列中的&#x200B;**選取面板**&#x200B;選項，切換至不同投影片進行編輯，亦可輕鬆重新排列投影片的順序。

![選取面板圖示](/help/assets/select-panel-icon.png)

在元件工具列中選取&#x200B;**選取面板**&#x200B;選項後，已設定的投影片會顯示為下拉式清單。

* 清單會根據指派給投影片的排列方式排序，並反映在編號中。
* 首先顯示投影片元件類型，後面接著以較淺的字體顯示投影片說明。

![選取面板](/help/assets/select-panel-popover.png)

* 在下拉式清單中點選或按一下項目，將編輯器中的視圖切換至該投影片。
* 您可以使用拖曳控點就地重新排列投影片。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義哪些元件可作為投影片新增至輪播元件，也可定義自動轉場預設值以及可供內容作者使用的自訂樣式。

### 屬性索引標籤 {#properties-tab-1}

當內容作者將輪播元件新增到頁面時，**屬性**&#x200B;索引標籤將用於定義投影片轉場的預設設定。

![輪播元件的設計對話框](/help/assets/carousel-design.png)

* **投影片自動轉場** - 定義內容作者將輪播元件新增至頁面時，是否預設啟用輪播自動前進到下一張投影片的選項。
* **將控制元素前置** - 勾選後，控制元素將會置於輪播項目的前面以改善可用性。

### 允許的元件索引標籤 {#allowed-components-tab}

**允許的元件**&#x200B;索引標籤用於定義可供內容作者作為投影片新增至對話框元件的元件。

[在範本編輯器中定義版面容器的原則與屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)時，允許的元件索引標籤與同名索引標籤的功能相同。

### 樣式索引標籤 {#styles-tab}

輪播元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「輪播元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
