---
title: 輪播元件
description: 轉盤元件可讓內容作者在旋轉轉盤中顯示內容。
role: Architect, Developer, Admin, User
exl-id: 3331214c-a05c-47e1-b54c-fbfd1045bd60
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '1317'
ht-degree: 1%

---


# 輪播元件{#carousel-component}

核心元件轉盤元件可讓內容作者以可導覽的轉盤呈現內容。

{{traditional-aem}}

## 使用情況 {#usage}

內容作者可使用轉盤元件，將內容整理在旋轉的幻燈片轉盤中。

[編輯對話方塊](#edit-dialog)可讓內容作者建立、命名及排序多個幻燈片，以及啟用自動切換並延遲。 使用[設計對話方塊](#design-dialog)，範本作者可以定義哪些元件可以新增到輪播、啟用或停用自動切換，以及自訂樣式。

## 版本和相容性 {#version-and-compatibility}

輪播元件的目前版本是v1，此版本隨2018年10月的核心元件2.2.0版的發佈引入，說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗轉盤元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_carousel)。

### 技術細節 {#technical-details}

在GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1)上可找到有關轉盤元件[的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 面板的深層連結 {#deep-linking}

轉盤、[標籤、](tabs.md)和[摺疊式功能表元件](accordion.md)支援直接連結至元件中的面板。

若要這麼做：

1. 在頁面編輯器中使用&#x200B;**[以發佈的形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;選項，檢視含有元件的頁面。
1. 檢查頁面內容並識別面板的ID。
   * 例如`id="carousel-bfe4fa6647-item-47f1a7ca67-tabpanel"`
1. ID會成為您可以使用雜湊(`#`)附加至URL的錨點。
   * 例如`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#carousel-bfe4fa6647-item-47f1a7ca67-tabpanel`

導覽至將面板ID當作錨點的URL，瀏覽器會直接捲動至特定元件，並顯示指定的面板。 如果面板設定為預設不顯示，則會自動捲動至。

## 輪播和回應式設計 {#responsive-design}

所有核心元件的設計都可充分回應，確保裝置間的順暢體驗。

部分進階元件（如轉盤元件）可能需要在實施專案的內容中特別考量，以在所有情況下保持回應能力。 如需詳細資訊，請參閱檔案[核心元件的回應式設計](/help/responsive.md)。

## 編輯對話方塊 {#edit-dialog}

內容作者可以使用「編輯」對話方塊來新增、重新命名和重新排列幻燈片，以及定義自動切換效果設定。

### 專案標籤 {#items-tab}

轉盤元件](/help/assets/carousel-edit-items.png)的編輯對話方塊的![專案標籤

使用&#x200B;**新增**&#x200B;按鈕開啟元件選擇器，選擇要新增為索引標籤的元件。 新增專案後，專案會新增到清單中，包含以下欄：

* **圖示** — 標籤元件型別的圖示，可在清單中輕鬆識別。 將滑鼠移到上方以檢視完整的元件名稱作為工具提示。
* **描述** — 用作索引標籤文字的描述，預設為針對索引標籤選取的元件名稱。
* **刪除** — 點選或按一下以從索引標籤元件中刪除索引標籤。
* **重新排序** — 點選或按一下並拖曳以排序標籤。

>[!TIP]
>
>如果減少頁面的檢視區以便讓編輯對話方塊變成全熒幕，將會隱藏&#x200B;**新增**&#x200B;按鈕。 元件仍可透過[從元件瀏覽器拖曳並放置在頁面編輯器的轉盤元件上來新增至轉盤元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser)。

### 屬性標籤 {#properties-tab}

轉盤元件](/help/assets/carousel-edit-properties.png)的編輯對話方塊的![屬性標籤

在&#x200B;**屬性**&#x200B;標籤上，內容作者可以設定投影片自動切換。

* **作用中專案** — 內容作者可以定義載入頁面時作用中的索引標籤。
* **自動切換投影片** — 啟用時，元件會在指定的延遲之後自動前進到下一張投影片。
* **切換延遲** — 選取自動切換幻燈片時，此值可用來定義切換之間的延遲（以毫秒為單位）。
* **停用暫留時自動暫停** — 選取&#x200B;**自動切換投影片**&#x200B;時，只要游標暫留在輪播上，輪播切換就會自動暫停。 選取此選項，轉變將不會暫停。
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

>[!NOTE]
>
>在&#x200B;**編輯**&#x200B;模式中不會啟用幻燈片前進控制項。 使用&#x200B;[**預覽**&#x200B;模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)或&#x200B;**[以發佈的形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;選項，可以像已發佈內容的讀者那樣與輪播互動。
>
>在&#x200B;**編輯**&#x200B;模式下不會啟用自動前進功能。 使用&#x200B;**[以發佈的形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;選項，可以像已發佈內容的讀者那樣檢視自動前進功能。

### 協助工具標籤 {#accessibility-tab}

![轉盤元件[編輯]對話方塊的[協助工具]索引標籤](/help/assets/carousel-edit-accessibility.png)

在&#x200B;**協助工具**&#x200B;標籤上，可以為元件設定[ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤的值。

* **Label** — 轉盤的aria-label屬性值，用以描述轉盤的內容
* **Previous** — 輪播導覽的上一個按鈕標籤的aria-label屬性值
* **下一步** — 轉盤導覽的下一個按鈕標籤的aria-label屬性值
* **播放** — 轉盤導覽的播放按鈕標籤的aria-label屬性值
* **Pause** — 輪播導覽的暫停按鈕標籤的aria-label屬性值
* **標籤清單** — 輪播導覽的專案清單標籤的aria-label屬性值
* **將專案的aria標籤設定為其標題** — 如果勾選，此選項會自動將輪播專案標題設定為其aria-label說明。

## 選取面板 {#select-panel}

內容作者可以使用元件工具列上的&#x200B;**選取面板**&#x200B;選項，變更到不同的幻燈片進行編輯，以及輕鬆地重新排列幻燈片的順序。

![選取面板圖示](/help/assets/select-panel-icon.png)

在元件工具列中選取&#x200B;**選取面板**&#x200B;選項後，已設定的幻燈片會顯示為下拉式清單。

* 清單會依指派給幻燈片的排列方式排序，並會反映在編號中。
* 首先顯示幻燈片的元件型別，然後是較細字型的幻燈片說明。

![選取面板](/help/assets/select-panel-popover.png)

* 在下拉式清單中點選或按一下專案，會在編輯器中將檢視切換至該幻燈片。
* 您可以使用拖曳操作框就地重新排序幻燈片。

## 設計對話方塊 {#design-dialog}

範本作者可以使用「設計」對話方塊來定義哪些元件可以新增為轉盤元件的投影片，以及定義自動切換預設值和哪些自訂樣式可供內容作者使用。

### 屬性標籤 {#properties-tab-1}

當內容作者將轉盤元件新增到頁面時，**屬性**&#x200B;索引標籤是用來定義幻燈片轉換的預設設定。

![輪播元件的[設計]對話方塊](/help/assets/carousel-design.png)

* **自動切換投影片** — 定義內容作者在將轉盤元件新增至頁面時，是否預設啟用自動將轉盤前進到下一張投影片的選項。
* **在控制項元素前面加上** — 勾選後，控制項元素會放在轉盤專案的前面，以改善協助工具。

### 允許的元件標籤 {#allowed-components-tab}

**允許的元件**&#x200B;索引標籤是用來定義哪些元件可由內容作者新增為轉盤元件的投影片。

當[在範本編輯器中定義配置容器的原則與屬性時，「允許的元件」索引標籤的功能與相同名稱的索引標籤相同。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式索引標籤 {#styles-tab}

轉盤元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

轉盤元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
