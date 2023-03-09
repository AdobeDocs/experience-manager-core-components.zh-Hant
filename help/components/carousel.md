---
title: 轉盤元件
description: 轉盤元件可讓內容作者以旋轉轉盤呈現內容。
role: Architect, Developer, Admin, User
exl-id: 3331214c-a05c-47e1-b54c-fbfd1045bd60
source-git-commit: e0d3790b265ab27ac2116f0d8daf1a18ecd3d714
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 1%

---

# 轉盤元件{#carousel-component}

核心元件轉盤元件可讓內容作者在可導覽的轉盤中呈現內容。

## 使用狀況 {#usage}

內容作者可使用轉盤元件，在旋轉的投影片轉盤中組織內容。

此 [編輯對話框](#edit-dialog) 可讓內容作者建立、命名和排序多張投影片，並啟用延遲的自動轉換。 使用 [設計對話](#design-dialog)，範本作者可定義可新增至輪播的元件、啟用或停用自動轉變，以及自訂樣式。

## 版本與相容性 {#version-and-compatibility}

轉盤元件的目前版本為v1，已於2018年10月隨核心元件2.2.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容於<br>[版本2.17.4](/help/versions.md) 和之前 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱本檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗轉盤元件並查看其設定選項的範例以及HTML和JSON輸出，請造訪 [元件庫](https://adobe.com/go/aem_cmp_library_carousel).

### 技術詳細資訊 {#technical-details}

輪播元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_carousel_v1).

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 面板的深層連結 {#deep-linking}

轉盤， [標籤，](tabs.md) 和 [折疊式功能表元件](accordion.md) 支援直接連結至元件內的面板。

要執行此操作：

1. 使用檢視包含元件的頁面 **[檢視為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 選項。
1. Inspect頁面內容並識別面板ID。
   * 例如 `id="carousel-bfe4fa6647-item-47f1a7ca67-tabpanel"`
1. 此ID會成為您可使用雜湊附加至URL的錨點(`#`)。
   * 例如 `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#carousel-bfe4fa6647-item-47f1a7ca67-tabpanel`

導覽至面板ID為錨點的URL，瀏覽器將直接捲動至特定元件並顯示指定的面板。 如果面板設定為預設不顯示，則會自動捲動至。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者新增、重新命名和重新排列投影片，以及定義自動轉變設定。

### 項目標籤 {#items-tab}

![轉盤元件編輯對話方塊的「項目」索引標籤](/help/assets/carousel-edit-items.png)

使用 **新增** 按鈕，開啟元件選取器以選擇要新增為索引標籤的元件。 新增後，會將項目新增至清單，其中包含下列欄：

* **圖示**  — 頁簽的元件類型表徵圖，以便在清單中輕鬆識別。 將滑鼠移至以顯示完整的元件名稱，作為工具提示。
* **說明**  — 用作標籤文本的說明，預設為為標籤選擇的元件的名稱。
* **刪除**  — 點選或按一下，從標籤元件中刪除標籤。
* **重新排序**  — 點選或按一下並拖曳以排序標籤。

>[!TIP]
>
>如果頁面的檢視區縮小，使編輯對話方塊變成全螢幕，則 **新增** 按鈕。 元件仍可依下列方式新增至轉盤元件： [從元件瀏覽器拖曳，並拖放至頁面編輯器中的轉盤元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser).

### 屬性標籤 {#properties-tab}

![輪播元件的編輯對話方塊的屬性標籤](/help/assets/carousel-edit-properties.png)

在 **屬性** 頁簽，內容作者可以將投影片設定為自動轉變。

* **活動項**  — 內容作者可定義載入頁面時作用中的索引標籤。
* **自動轉換幻燈片**  — 活動時，元件在指定的延遲後自動前進到下一張幻燈片。
* **轉換延遲**  — 選取「自動轉變」投影片時，此值用於定義轉變之間的延遲（以毫秒為單位）。
* **停用暫留時的自動暫停**  — 何時 **自動轉換幻燈片** 選取時，當游標停留在輪播上時，輪播轉變會自動暫停。 選取此選項，使轉變不會暫停。
* **ID**  — 此選項可控制HTML中和 [資料層](/help/developing/data-layer/overview.md).
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

>[!NOTE]
>
>在中時，不會啟用幻燈片預先控制項 **編輯** 模式。 使用 [**預覽** 模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode) 或 **[檢視為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 選擇以已發佈內容讀者身分與轉盤互動。
>
>自動進階功能在 **編輯** 模式。 使用 **[檢視為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 選項，以閱讀已發佈內容的方式查看自動進階功能。

### 協助工具標籤 {#accessibility-tab}

![轉盤元件編輯對話方塊的協助工具標籤](/help/assets/carousel-edit-accessibility.png)

在 **協助工具** 索引標籤中，可為 [ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 輪播的aria-label屬性的值，用於描述輪播的內容
* **上一個**  — 輪播導覽的上一個按鈕標籤的aria-label屬性值
* **下一個**  — 輪播導覽下一個按鈕標籤的aria-label屬性值
* **播放**  — 輪播導覽的播放按鈕標籤的aria-label屬性值
* **暫停**  — 輪播導覽的暫停按鈕標籤的aria-label屬性值
* **塔布利特**  — 輪播導覽項目清單標籤的aria-label屬性值
* **將項目的Aria標籤設定為其標題**  — 如果勾選此選項，系統會自動將轉盤項目標題設為其標籤說明。

## 選擇面板 {#select-panel}

內容作者可使用 **選擇面板** 選項，以更改為不同的幻燈片進行編輯，並輕鬆重新排列幻燈片的順序。

![「選擇」面板表徵圖](/help/assets/select-panel-icon.png)

選取 **選擇面板** 選項，則配置的幻燈片將顯示為下拉清單。

* 清單按幻燈片的分配排列排序，並反映在編號中。
* 首先顯示幻燈片的元件類型，然後以較淺的字型顯示幻燈片的說明。

![選取面板](/help/assets/select-panel-popover.png)

* 點選或按一下下拉式清單中的項目，將編輯器中的檢視切換至該投影片。
* 可使用拖動控制滑塊就地重新排序幻燈片。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義哪些元件可新增為轉盤元件的投影片，以及定義自動轉換預設值和哪些自訂樣式可供內容作者使用。

### 屬性標籤 {#properties-tab-1}

此 **屬性** 索引標籤可用來定義內容作者將輪播元件新增至頁面時投影片轉變的預設設定。

![輪盤元件的設計對話框](/help/assets/carousel-design.png)

* **自動轉換幻燈片**  — 定義當內容作者將輪播元件新增至頁面時，預設會啟用自動將輪播推進至下一張投影片的選項。
* **在開頭附加控制元素**  — 若勾選此選項，控制元素將放置在轉盤項目前，以改善協助工具。

### 「允許的元件」頁簽 {#allowed-components-tab}

此 **允許的元件** 索引標籤可用來定義內容作者可將哪些元件新增為投影片至轉盤元件。

當 [在模板編輯器中定義佈局容器的策略和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式標籤 {#styles-tab}

轉盤元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe用戶端資料層 {#data-layer}

轉盤元件支援 [Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
