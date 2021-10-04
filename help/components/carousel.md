---
title: 轉盤元件
description: 轉盤元件可讓內容作者以旋轉轉盤呈現內容。
role: Architect, Developer, Admin, User
exl-id: 3331214c-a05c-47e1-b54c-fbfd1045bd60
source-git-commit: 888719359f9a1d1c9dccff97fb639b332f2be54c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 轉盤元件{#carousel-component}

核心元件轉盤元件可讓內容作者在可導覽的轉盤中呈現內容。

## 使用狀況 {#usage}

內容作者可使用轉盤元件，在旋轉的投影片轉盤中組織內容。

[edit dialog](#edit-dialog)允許內容作者建立、命名和排序多張投影片，並啟用延遲的自動轉換。 範本作者可使用[設計對話方塊](#design-dialog)定義哪些元件可新增至輪播、啟用或停用自動轉變，以及自訂樣式。

## 版本與相容性 {#version-and-compatibility}

轉盤元件的目前版本為v1，已於2018年10月隨核心元件2.2.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗轉盤元件並查看其設定選項的範例以及HTML和JSON輸出，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_carousel)。

### 技術詳細資訊 {#technical-details}

如需輪播元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者新增、重新命名和重新排列投影片，以及定義自動轉變設定。

### 項目標籤 {#items-tab}

![轉盤元件編輯對話方塊的「項目」索引標籤](/help/assets/carousel-edit-items.png)

使用&#x200B;**Add**&#x200B;按鈕開啟元件選擇器，以選擇要添加為頁簽的元件。 新增後，會將項目新增至清單，其中包含下列欄：

* **圖示**  — 索引標籤的元件類型圖示，以便在清單中輕鬆識別。將滑鼠移至以顯示完整的元件名稱，作為工具提示。
* **說明**  — 用作標籤文本的說明，預設為為標籤選擇的元件的名稱。
* **刪除**  — 點選或按一下，從標籤元件中刪除標籤。
* **重新排序**  — 點選或按一下並拖曳以排序標籤。

>[!TIP]
>
>如果頁面的檢視區縮小，使編輯對話方塊變成全螢幕，則會隱藏&#x200B;**Add**&#x200B;按鈕。 從元件瀏覽器拖曳並拖曳至頁面編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser)中的轉盤元件，仍可將元件新增至轉盤元件。[

### 屬性標籤 {#properties-tab}

![輪播元件的編輯對話方塊的屬性標籤](/help/assets/carousel-edit-properties.png)

在&#x200B;**Properties**&#x200B;標籤上，內容作者可以設定投影片以自動轉換。

* **自動轉換幻燈片**  — 當活動時，元件將在指定的延遲後自動前進到下一張幻燈片。
* **轉變延遲**  — 選取「自動轉變」投影片時，此值可用來定義轉變之間的延遲（以毫秒為單位）。
* **停用暫留時的自動暫停**  — 選取「 **自動** 轉變」投影片時，每當游標暫留在轉盤上時，轉盤轉變會自動暫停。選取此選項，使轉變不會暫停。
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

>[!NOTE]
>
>在&#x200B;**Edit**&#x200B;模式下，不會啟用幻燈片預設控制項。 使用&#x200B;[**預覽**&#x200B;模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)或&#x200B;**[檢視為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;選項，在已發佈內容讀者身分時與輪播互動。
>
>在&#x200B;**Edit**&#x200B;模式下，不會啟用自動提前功能。 使用&#x200B;**[以已發佈的形式查看](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;選項，將自動提前功能視為已發佈內容的讀者。

### 協助工具標籤 {#accessibility-tab}

![轉盤元件編輯對話方塊的協助工具標籤](/help/assets/carousel-edit-accessibility.png)

在&#x200B;**協助工具**&#x200B;標籤上，可以為元件的[ARIA協助工具](https://www.w3.org/WAI/standards-guidelines/aria/)標籤設定值。

* **標籤**  — 元件的ARIA標籤屬性值

## 選擇面板 {#select-panel}

內容作者可以使用元件工具欄上的&#x200B;**選擇面板**&#x200B;選項來更改為不同的幻燈片進行編輯，並輕鬆重新排列幻燈片的順序。

![「選擇」面板表徵圖](/help/assets/select-panel-icon.png)

在元件工具欄中選取&#x200B;**選取面板**&#x200B;選項後，會將已設定的投影片顯示為下拉式清單。

* 清單按幻燈片的分配排列排序，並反映在編號中。
* 首先顯示幻燈片的元件類型，然後以較淺的字型顯示幻燈片的說明。

![選取面板](/help/assets/select-panel-popover.png)

* 點選或按一下下拉式清單中的項目，將編輯器中的檢視切換至該投影片。
* 可使用拖動控制滑塊就地重新排序幻燈片。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義哪些元件可新增為轉盤元件的投影片，以及定義自動轉換預設值和哪些自訂樣式可供內容作者使用。

### 屬性標籤 {#properties-tab-1}

**屬性**&#x200B;標籤用於定義內容作者將轉盤元件新增至頁面時投影片轉變的預設設定。

![輪盤元件的設計對話框](/help/assets/carousel-design.png)

* **自動轉換投影片**  — 定義當內容作者將轉盤元件新增至頁面時，預設會啟用自動將轉盤推進至下一張投影片的選項。
* **轉變延遲**  — 定義內容作者將輪播元件新增至頁面時，投影片之間轉變延遲的預設值（以毫秒為單位）。
* **停用暫留時的自動暫停**  — 定義當內容作者選取的「自動轉移投影片」時，是否 **啟用** 停用自動投影片暫停的選項。

### 「允許的元件」頁簽 {#allowed-components-tab}

**允許的元件**&#x200B;標籤用於定義哪些元件可由內容作者以投影片形式新增至轉盤元件。

[在模板編輯器中定義佈局容器的策略和屬性時，「允許的元件」頁簽的功能與同名頁簽的功能相同。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式標籤 {#styles-tab}

轉盤元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe用戶端資料層 {#data-layer}

轉盤元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
