---
title: 收合式選單元件
description: 「核心元件摺疊式功能表」元件可讓您在頁面上建立以摺疊式功能表排列的面板集合。
role: Architect, Developer, Admin, User
exl-id: 1deb570a-3d8d-409e-805f-8460c49cf9bb
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '1102'
ht-degree: 1%

---


# 收合式選單元件{#accordion-component}

「核心元件摺疊式功能表」元件可讓您在頁面上建立以摺疊式功能表排列的面板集合。

{{traditional-aem}}

## 使用情況 {#usage}

核心元件摺疊式功能表元件允許建立元件集合（由面板組成），並在頁面上以摺疊式功能表排列，類似於[索引標籤元件](tabs.md)，但允許展開和摺疊面板。

* 摺疊式功能表的屬性可在[設定對話方塊](#configure-dialog)中定義。
* 摺疊面板的順序可以在「設定」對話方塊以及[選取面板彈出視窗](#select-panel-popover)中定義。
* 將摺疊式功能表元件新增至頁面時的預設值可以在[設計對話方塊](#design-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

摺疊式功能表元件的目前版本是v1，此版本隨2019年6月的核心元件發行版本2.5.0的發佈引入，說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v1 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗摺疊式功能表元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_accordion)。

## 技術細節 {#technical-details}

在GitHub](https://adobe.com/go/aem_cmp_tech_accordion_v1)上可找到有關摺疊式功能表元件[的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 面板的深層連結 {#deep-linking}

摺疊式功能表、[輪播、](carousel.md)及[索引標籤元件](tabs.md)支援直接連結至元件中的面板。

若要這麼做：

1. 在頁面編輯器中使用&#x200B;**[以發佈的形式檢視](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;選項，檢視含有元件的頁面。
1. 檢查頁面內容並識別面板的ID。
   * 例如`id="accordion-86196c94d3-item-ca319dbb0b"`
1. ID會成為您可以使用雜湊(`#`)附加至URL的錨點。
   * 例如`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

導覽至將面板ID當作錨點的URL，瀏覽器會直接捲動至特定元件，並顯示指定的面板。 如果面板預設為不展開，則會自動展開。

## 摺疊面板和回應式設計 {#responsive-design}

所有核心元件的設計都可充分回應，確保裝置間的順暢體驗。

有些進階元件（例如摺疊式功能表元件）在執行專案的內容中可能需要特別考量，以保持在所有條件下的回應能力。 如需詳細資訊，請參閱檔案[核心元件的回應式設計](/help/responsive.md)。

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義摺疊式功能表專案、其面板，以及對於頁面的訪客它會如何表現和顯示。

### 專案標籤 {#items-tab}

摺疊式元件之編輯對話方塊的![專案索引標籤](/help/assets/accordion-edit-items.png)

使用&#x200B;**新增**&#x200B;按鈕開啟元件選擇器，選擇要新增為面板的元件。 新增專案後，專案會新增到清單中，包含以下欄：

* **圖示** — 面板的元件型別圖示，可在清單中輕鬆識別。 將滑鼠移到上方以檢視完整的元件名稱作為工具提示。
* **描述** — 用來做為面板文字的描述，預設為針對面板選取的元件名稱。
* **刪除** — 點選或按一下以從摺疊式功能表元件刪除面板。
* **重新排列** — 點選或按一下並拖曳以重新排列面板。

>[!TIP]
>
>如果減少頁面的檢視區以便讓編輯對話方塊變成全熒幕，將會隱藏&#x200B;**新增**&#x200B;按鈕。 您仍可透過[從元件瀏覽器拖曳並放置在頁面編輯器](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)中的摺疊式元件上，將元件新增至摺疊式元件。

### 屬性標籤 {#properties-tab}

摺疊式功能表元件](/help/assets/accordion-edit-properties.png)之編輯對話方塊的![屬性標籤

* **單一專案展開** — 選取時，此選項會強制一次展開單一摺疊專案。 展開一個專案後，其他所有專案都會摺疊。
* **展開的專案** — 此選項會定義載入頁面時預設展開的專案。
   * 選取&#x200B;**單一專案展開**&#x200B;時，必須選取一個面板。 依預設，會選取第一個面板。
   * 未選取&#x200B;**單一專案展開**&#x200B;時，此選項為多重選取且是選擇性的。
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

## 選取面板彈出視窗 {#select-panel-popover}

內容作者可以使用元件工具列上的&#x200B;**選取面板**&#x200B;選項，變更到不同的面板進行編輯，以及輕鬆地重新排列摺疊中的面板。

![選取面板圖示](/help/assets/select-panel-icon.png)

在元件工具列中選取&#x200B;**選取面板**&#x200B;選項後，已設定的摺疊式功能表面板會顯示為下拉式清單。

![選取面板彈出視窗](/help/assets/select-panel-popover.png)

* 清單會依指派的面板排列方式排序，並反映在編號中。
* 首先顯示面板的元件型別，然後是較細字型的面板說明。
* 在下拉式清單中點選或按一下專案，會在編輯器中將檢視切換至該面板。
* 您可以使用拖曳操作框就地重新排列面板。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些選項可供使用摺疊式功能表元件的內容作者使用，以及在放置摺疊式功能表元件時的預設設定。

### 屬性標籤 {#properties-tab-design}

![設計對話方塊屬性索引標籤](/help/assets/accordion-design-properties.png)

* **允許的標題元素** — 此多選下拉式清單會定義允許由作者選取的收合式選單專案標題HTML元素。
* **預設標題元素** — 此下拉式清單會定義預設摺疊式功能表專案標題HTML元素。

### 允許的元件標籤 {#allowed-components-tab}

**允許的元件**&#x200B;索引標籤是用來定義哪些元件可由內容作者新增為摺疊式元件中的面板。

當[在範本編輯器中定義配置容器的原則與屬性時，「允許的元件」索引標籤的功能與相同名稱的索引標籤相同。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### 樣式索引標籤 {#styles-tab}

摺疊式功能表元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

摺疊式功能表元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
