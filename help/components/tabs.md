---
title: 制表符元件
description: 「頁簽元件」允許建立多個頁簽，以在頁面上排列內容。
role: Architect, Developer, Admin, User
exl-id: 0031c5f3-447c-4932-898f-2f453801e492
source-git-commit: e8b3e55a42b6be6262d6f51b9569c0be3e8ce6c3
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 1%

---

# 制表符元件 {#tabs-component}

核心元件索引標籤元件可讓內容組織至多個索引標籤。

## 使用狀況 {#usage}

標籤元件可讓內容作者在多個標籤內組織頁面內容。

此 [編輯對話框](#edit-dialog) 可讓內容作者定義多個標籤，並設定使用中的標籤。 使用 [設計對話](#design-dialog)，範本作者可定義可新增至索引標籤的元件，並自訂樣式。

>[!TIP]
>
>支援巢狀定位元件（定位點內的定位點）。
>
>可使用 [內容樹](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree)，但巢狀索引標籤不可。

## 版本與相容性 {#version-and-compatibility}

標籤元件的目前版本為v1，已於2018年10月隨核心元件2.2.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容於<br>[版本2.17.4](/help/versions.md) 和之前 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱本檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗標籤元件，並查看其設定選項的範例以及HTML和JSON輸出，請造訪 [元件庫](https://adobe.com/go/aem_cmp_library_tabs).

### 技術詳細資訊 {#technical-details}

關於標籤元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_tabs_v1).

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 面板的深層連結 {#deep-linking}

這些標籤， [轉盤，](carousel.md) 和 [折疊式功能表元件](accordion.md) 支援直接連結至元件內的面板。

要執行此操作：

1. 使用檢視包含元件的頁面 **[檢視為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 選項。
1. Inspect頁面內容並識別面板ID。
   * 例如 `id="accordion-86196c94d3-item-ca319dbb0b"`
1. 此ID會成為您可使用雜湊附加至URL的錨點(`#`)。
   * 例如 `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

導覽至面板ID為錨點的URL，瀏覽器將直接捲動至特定元件並顯示指定的面板。 如果面板預設設定為不展開，則會自動展開。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者建立、重新命名和重新排列索引標籤，以及定義使用中索引標籤。

### 項目標籤 {#items-tab}

![制表符元件的編輯對話框項頁簽](/help/assets/tabs-edit-items.png)

使用 **新增** 按鈕，開啟元件選取器以選擇要新增為索引標籤的元件。 新增後，會將項目新增至清單，其中包含下列欄：

* **圖示**  — 頁簽的元件類型表徵圖，以便在清單中輕鬆識別。 將滑鼠移至以顯示完整的元件名稱，作為工具提示。
* **說明**  — 用作標籤文本的說明，預設為為標籤選擇的元件的名稱。
* **刪除**  — 點選或按一下，從索引標籤元件中刪除索引標籤。
* **重新排列**  — 點選或按一下並拖曳以重新排列索引標籤的順序。

>[!TIP]
>
>如果頁面的檢視區縮小，使編輯對話方塊變成全螢幕，則 **新增** 按鈕。 元件仍可以通過以下方式添加到標籤元件 [從元件瀏覽器拖曳，並拖曳至頁面編輯器中的標籤元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component).

### 屬性標籤 {#properties-tab}

![頁簽元件的編輯對話框屬性頁簽](/help/assets/tabs-edit-properties.png)

* **活動項**  — 內容作者可定義載入頁面時作用中的索引標籤。
   * 使用 **預設** 選項，則會選取第一個索引標籤。
* **ID**  — 此選項可控制HTML中和 [資料層](/help/developing/data-layer/overview.md).
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

### 協助工具標籤 {#accessibility-tab}

![頁簽元件的編輯對話框輔助工具頁簽](/help/assets/tabs-edit-accessibility.png)

在 **協助工具** 索引標籤中，可為 [ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性值

## 選擇面板 {#select-panel}

內容作者可使用 **選擇面板** 選項，以更改為不同的面板進行編輯，並輕鬆重新排列頁簽的順序。

![「選擇」面板表徵圖](/help/assets/select-panel-icon.png)

選取 **選擇面板** 選項，則配置的頁簽將顯示為下拉清單。

* 清單按頁簽的分配排列排序，並反映在編號中。
* 頁簽的元件類型將首先顯示，然後以較淺的字型顯示頁簽的說明。

![選取面板彈出視窗](/help/assets/select-panel-popover.png)

* 點選或按一下下拉式清單中的項目，將編輯器中的檢視切換至該標籤。
* 可使用拖動控點就地重新排列頁簽。

>[!NOTE]
>
>當位於 **編輯** 模式。 使用 **[預覽](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)** 模式或 **[檢視為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 選項，以讀取已發佈內容時與標籤互動。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義哪些元件可新增為索引標籤元件的項目，以及定義哪些自訂樣式可供內容作者使用。

### 「允許的元件」頁簽 {#allowed-components-tab}

此 **允許的元件** 索引標籤可用來定義內容作者可將哪些元件新增為索引標籤元件的項目。

當 [在模板編輯器中定義佈局容器的策略和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式標籤 {#styles-tab}

標籤元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe用戶端資料層 {#data-layer}

標籤元件支援 [Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
