---
title: 折疊式面板元件
description: 核心元件折疊式功能表元件可建立以頁面上折疊式功能表排列的面板集合。
role: Architect, Developer, Admin, User
exl-id: 1deb570a-3d8d-409e-805f-8460c49cf9bb
source-git-commit: e8b3e55a42b6be6262d6f51b9569c0be3e8ce6c3
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 1%

---

# 折疊式面板元件{#accordion-component}

核心元件折疊式功能表元件可建立以頁面上折疊式功能表排列的面板集合。

## 使用狀況 {#usage}

核心元件折疊式功能表元件可建立元件集合，以面板形式組成，並排列在頁面上的折疊式功能表中，類似於 [制表符元件](tabs.md)，但允許展開和折疊面板。

* 折疊式功能表的屬性可在 [配置對話框](#configure-dialog).
* 折疊式功能表的面板順序可在設定對話方塊中定義，也可在 [選擇面板彈出窗口](#select-panel-popover).
* 將折疊式功能表元件新增至頁面時，其預設值可在 [設計對話](#design-dialog).

## 版本與相容性 {#version-and-compatibility}

折疊式功能表元件的目前版本為v1，已於2019年6月隨核心元件2.5.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容於<br>[版本2.17.4](/help/versions.md) 和之前 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱本檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗折疊式功能表元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪 [元件庫](https://adobe.com/go/aem_cmp_library_accordion).

## 技術詳細資訊 {#technical-details}

折疊式功能表元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_accordion_v1).

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 面板的深層連結 {#deep-linking}

手風琴， [轉盤，](carousel.md) 和 [標籤元件](tabs.md) 支援直接連結至元件內的面板。

要執行此操作：

1. 使用檢視包含元件的頁面 **[檢視為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 選項。
1. Inspect頁面內容並識別面板ID。
   * 例如 `id="accordion-86196c94d3-item-ca319dbb0b"`
1. 此ID會成為您可使用雜湊附加至URL的錨點(`#`)。
   * 例如 `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

導覽至面板ID為錨點的URL，瀏覽器將直接捲動至特定元件並顯示指定的面板。 如果面板預設設定為不展開，則會自動展開。

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者定義折疊式功能表項目、其面板，以及該項目的行為和顯示方式，供造訪頁面的訪客使用。

### 項目標籤 {#items-tab}

![折疊式功能表元件的編輯對話方塊的「項目」索引標籤](/help/assets/accordion-edit-items.png)

使用 **新增** 按鈕，開啟元件選取器以選擇要新增為面板的元件。 新增後，會將項目新增至清單，其中包含下列欄：

* **圖示**  — 面板的元件類型表徵圖，以便在清單中輕鬆識別。 將滑鼠移至以顯示完整的元件名稱，作為工具提示。
* **說明**  — 用作面板文本的說明，預設為為面板選擇的元件的名稱。
* **刪除**  — 點選或按一下，從折疊式功能表元件中刪除面板。
* **重新排列**  — 點選或按一下並拖曳，重新排列面板的順序。

>[!TIP]
>
>如果頁面的檢視區縮小，使編輯對話方塊變成全螢幕，則 **新增** 按鈕。 元件仍可依下列方式新增至折疊式功能表元件： [從元件瀏覽器拖曳，並拖曳至頁面編輯器中的折疊式功能表元件](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent).

### 屬性標籤 {#properties-tab}

![折疊式功能表元件的編輯對話框的屬性頁簽](/help/assets/accordion-edit-properties.png)

* **單項擴展**  — 選取時，此選項會強制一次展開單一折疊式功能表項目。 展開一個項目就會折疊所有其他項目。
* **展開的項目**  — 此選項會定義載入頁面時依預設展開的項目。
   * 當 **單項擴展** 已選取，則必須選取一個面板。 依預設，會選取第一個面板。
   * 當 **單項擴展** 未選取，此選項為多選項，且為選用選項。
* **ID**  — 此選項可控制HTML中和 [資料層](/help/developing/data-layer/overview.md).
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

## 選擇面板彈出窗口 {#select-panel-popover}

內容作者可使用 **選擇面板** 選項，以變更為不同的面板進行編輯，並輕鬆重新排列折疊式功能表內面板的順序。

![「選擇」面板表徵圖](/help/assets/select-panel-icon.png)

選取 **選擇面板** 選項，則配置的折疊式面板會顯示為下拉式清單。

![選取面板彈出視窗](/help/assets/select-panel-popover.png)

* 該清單按所分配的面板排列排列，並反映在編號中。
* 面板的元件類型首先顯示，然後以較淺的字型顯示面板的說明。
* 點選或按一下下拉式清單中的項目，將編輯器中的檢視切換至該面板。
* 通過拖動控點可以就地重新排列面板。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者可使用折疊式功能表元件的選項，以及放置折疊式功能表元件時設定的預設值。

### 屬性標籤 {#properties-tab-design}

![「設計」對話框屬性頁簽](/help/assets/accordion-design-properties.png)

* **允許的標題元素**  — 此多選下拉式清單定義作者可選取的折疊式功能表項目標題HTML元素。
* **預設標題元素**  — 此下拉式清單定義預設折疊式功能表項目標題HTML元素。

### 「允許的元件」頁簽 {#allowed-components-tab}

此 **允許的元件** 索引標籤可用來定義哪些元件可由內容作者新增為折疊式功能表元件中的面板的項目。

當 [在模板編輯器中定義佈局容器的策略和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### 樣式標籤 {#styles-tab}

折疊式功能表元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe用戶端資料層 {#data-layer}

折疊式功能表元件支援 [Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
