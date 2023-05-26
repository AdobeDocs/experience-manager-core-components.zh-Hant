---
title: 收合式選單元件
description: 核心元件摺疊式功能表元件可讓您在頁面上建立以摺疊式功能表排列的面板集合。
role: Architect, Developer, Admin, User
exl-id: 1deb570a-3d8d-409e-805f-8460c49cf9bb
source-git-commit: e8b3e55a42b6be6262d6f51b9569c0be3e8ce6c3
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 0%

---

# 收合式選單元件{#accordion-component}

核心元件摺疊式功能表元件可讓您在頁面上建立以摺疊式功能表排列的面板集合。

## 使用狀況 {#usage}

「核心元件摺疊式功能表」元件可用來建立元件集合（由面板組成），並在頁面上以摺疊式功能表排列，類似於 [索引標籤元件](tabs.md)，但允許展開和收合面板。

* 摺疊式功能表的屬性可在以下位置定義： [設定對話方塊](#configure-dialog).
* 摺疊面板的順序可在「設定」對話方塊中定義，也可在 [選取面板彈出視窗](#select-panel-popover).
* 將摺疊式功能表元件新增至頁面時的預設值可在下列位置定義： [設計對話方塊](#design-dialog).

## 版本和相容性 {#version-and-compatibility}

摺疊式功能表元件的目前版本是v1，此版本隨2019年6月的核心元件2.5.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容於<br>[版本2.17.4](/help/versions.md) 和先前的 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗摺疊式功能表元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_accordion).

## 技術細節 {#technical-details}

有關摺疊式功能表元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_accordion_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 深層連結至面板 {#deep-linking}

風琴折， [輪播，](carousel.md) 和 [索引標籤元件](tabs.md) 支援直接連結至元件中的面板。

若要這麼做：

1. 使用檢視含有元件的頁面 **[檢視已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 頁面編輯器中的選項。
1. Inspect頁面內容並識別面板的ID。
   * 例如 `id="accordion-86196c94d3-item-ca319dbb0b"`
1. 此ID會成為您可以使用雜湊(`#`)。
   * 例如 `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

導覽至將面板ID作為錨點的URL，瀏覽器會直接捲動至特定元件並顯示指定的面板。 如果面板依預設設定為不展開，則會自動展開。

## 設定對話方塊 {#configure-dialog}

「設定」對話方塊可讓內容作者定義摺疊式功能表專案、其面板，以及對於頁面的訪客它會如何表現和顯示。

### 專案標籤 {#items-tab}

![摺疊式元件之「編輯」對話方塊的「專案」索引標籤](/help/assets/accordion-edit-items.png)

使用 **新增** 按鈕來開啟元件選擇器，選擇要新增為面板的元件。 新增後，一個專案會新增到清單中，包含以下欄：

* **圖示**  — 面板的元件型別圖示，用於方便在清單中識別。 將滑鼠移到上方以檢視完整的元件名稱作為工具提示。
* **說明**  — 用作面板文字的說明，預設為為為面板選取的元件名稱。
* **刪除**  — 點選或按一下以從摺疊式功能表元件中刪除面板。
* **重新排列**  — 點選或按一下並拖曳以重新排列面板。

>[!TIP]
>
>如果減小頁面檢視區，使編輯對話方塊變成全熒幕， **新增** 按鈕將會隱藏。 元件仍可透過以下方式新增至摺疊式功能表元件 [從元件瀏覽器拖放至頁面編輯器中的摺疊式功能表元件](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent).

### 屬性標籤 {#properties-tab}

![摺疊式功能表元件「編輯」對話方塊的「屬性」標籤](/help/assets/accordion-edit-properties.png)

* **展開單一專案**  — 選取時，此選項會強制一次展開單一收合式選單專案。 展開一個專案後，其他所有專案都會收合。
* **展開的專案**  — 此選項會定義載入頁面時預設展開的專案。
   * 時間 **展開單一專案** ，則必須選取一個面板。 依預設，會選取第一個面板。
   * 時間 **展開單一專案** 未選取，此選項為多重選取且為選用。
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

## 「選取面板」彈出視窗 {#select-panel-popover}

內容作者可以使用 **選取面板** 元件工具列上的選項，以變更為不同的面板進行編輯，以及輕鬆地重新排列摺疊中的面板。

![選取面板圖示](/help/assets/select-panel-icon.png)

選取 **選取面板** 選項時，已設定的摺疊面板會顯示為下拉式清單。

![「選取面板」彈出視窗](/help/assets/select-panel-popover.png)

* 清單會依指派的面板排列順序排列，並會反映在編號中。
* 首先顯示面板的元件型別，然後是較細字型的面板說明。
* 在下拉式清單中點選或按一下專案，會在編輯器中將檢視切換到該面板。
* 您可以使用拖曳操作框就地重新排列面板。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些選項可供使用摺疊式功能表元件的內容作者使用，以及在放置摺疊式功能表元件時的預設設定。

### 屬性標籤 {#properties-tab-design}

![設計對話方塊屬性索引標籤](/help/assets/accordion-design-properties.png)

* **允許的標題元素**  — 此多選下拉式清單會定義允許作者選取的收合式選單專案標題HTML元素。
* **預設標題元素**  — 此下拉式清單會定義預設收合式選單專案標題HTML元素。

### 允許的元件索引標籤 {#allowed-components-tab}

此 **允許的元件** tab可用來定義哪些元件可由內容作者新增為摺疊式功能表元件中的面板專案。

「允許的元件」標籤的功能與相同名稱的標籤的功能相同，當 [在範本編輯器中定義配置容器的原則和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### 樣式索引標籤 {#styles-tab}

摺疊式功能表元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe使用者端資料層 {#data-layer}

摺疊式功能表元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
