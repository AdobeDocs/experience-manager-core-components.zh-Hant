---
title: 旋轉木馬元件
description: 「旋轉旋轉旋轉旋轉旋轉旋轉旋轉旋轉旋轉旋轉旋轉旋轉旋轉。
role: Architect, Developer, Admin, User
exl-id: 3331214c-a05c-47e1-b54c-fbfd1045bd60
source-git-commit: e0d3790b265ab27ac2116f0d8daf1a18ecd3d714
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 0%

---

# 旋轉木馬元件{#carousel-component}

核心元件旋轉傳送器元件允許內容作者在可導航旋轉傳送器中呈現內容。

## 使用狀況 {#usage}

內容作者使用「旋轉旋轉旋轉的旋轉旋轉的旋轉旋轉的旋轉旋轉旋轉的旋轉旋轉旋轉的旋轉旋轉旋轉的旋轉旋轉旋轉的旋轉旋轉旋轉旋轉的旋轉旋轉旋轉旋轉的旋轉旋轉旋轉旋轉。

的 [編輯對話框](#edit-dialog) 允許內容作者建立、命名和訂購多張幻燈片，並允許延遲自動轉換。 使用 [設計對話框](#design-dialog)，模板作者可以定義哪些元件可以添加到旋轉傳送器中，啟用或禁用自動過渡，以及自定義樣式。

## 版本和相容性 {#version-and-compatibility}

當前版本的Carousel元件是v1，該版本於2018年10月隨核心元件2.2.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗Carousel元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_carousel)。

### 技術詳細資訊 {#technical-details}

有關旋轉傳送元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_carousel_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 到面板的深度連結 {#deep-linking}

旋轉木馬， [頁籤，](tabs.md) 和 [折疊式元件](accordion.md) 支援直接連結到元件內的面板。

要執行此操作：

1. 使用 **[查看為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 的子菜單。
1. Inspect頁面內容並標識面板的ID。
   * 例如 `id="carousel-bfe4fa6647-item-47f1a7ca67-tabpanel"`
1. 該ID成為您可以使用哈希(`#`)。
   * 例如 `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#carousel-bfe4fa6647-item-47f1a7ca67-tabpanel`

導航到面板ID為錨點的URL時，瀏覽器將直接滾動到特定元件並顯示指定的面板。 如果面板配置為預設不顯示，則會自動滾動該面板。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者添加、更名和重新排列幻燈片，並定義自動轉換設定。

### 項目頁籤 {#items-tab}

![「旋轉軸元件」的「編輯」(Edit)對話框的「項目」(Items)頁籤](/help/assets/carousel-edit-items.png)

使用 **添加** 的子菜單。 添加後，將向清單中添加一個條目，該清單包含以下列：

* **表徵圖**  — 頁籤的元件類型表徵圖，便於在清單中進行標識。 將滑鼠移到工具提示中，以查看完整的元件名稱。
* **說明**  — 用作頁籤文本的說明，預設為為頁籤選擇的元件的名稱。
* **刪除**  — 點擊或按一下以從頁籤元件中刪除頁籤。
* **重新排序**  — 點擊或按一下並拖動以訂購頁籤。

>[!TIP]
>
>如果縮小頁面的視區，使編輯對話框變為全屏， **添加** 按鈕。 元件仍可以通過 [從元件瀏覽器中拖動，然後放在頁面編輯器中的「旋轉軸元件」上](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser)。

### 屬性頁籤 {#properties-tab}

![「旋轉軸元件」的「編輯」對話框的「屬性」頁籤](/help/assets/carousel-edit-properties.png)

在 **屬性** 頁籤，內容作者可以將幻燈片設定為自動轉換。

* **活動項**  — 內容作者可以定義載入頁面時處於活動狀態的頁籤。
* **自動轉換幻燈片**  — 活動時，元件將在指定延遲後自動進入下一張幻燈片。
* **過渡延遲**  — 選中「自動轉換」幻燈片時，此值用於定義轉換之間的延遲（以毫秒為單位）。
* **在懸停時禁用自動暫停**  — 時間 **自動轉換幻燈片** 選中後，當游標懸停在旋轉盤上時，旋轉盤過渡將自動暫停。 選擇此選項，以便過渡不會暫停。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

>[!NOTE]
>
>在中時不啟用幻燈片預放控制項 **編輯** 的子菜單。 使用 [**預覽** 模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode) 或 **[查看為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 選項，作為已發佈內容的讀者與旋轉傳送帶進行交互。
>
>在中時不啟用自動高級功能 **編輯** 的子菜單。 使用 **[查看為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 的子菜單。

### 輔助功能頁籤 {#accessibility-tab}

![「旋轉傳送元件」的「編輯」對話框的「輔助功能」頁籤](/help/assets/carousel-edit-accessibility.png)

在 **輔助功能** 頁籤，可為 [ARIA輔助功能](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 描述旋轉木馬內容的旋轉木馬的詠嘆調標籤屬性的值
* **上一個**  — 旋轉木馬導航上一個按鈕標籤的「箭頭標籤」屬性的值
* **下一個**  — 旋轉木馬導航的下一個按鈕標籤的詠嘆調標籤屬性的值
* **播放**  — 旋轉木馬導航的播放按鈕標籤的詠嘆調標籤屬性的值
* **暫停**  — 旋轉木馬導航的暫停按鈕標籤的詠嘆調標籤屬性的值
* **建立**  — 旋轉木馬導航的項目清單標籤的詠嘆調標籤屬性的值
* **將項目的詠嘆調標籤設定為其標題**  — 如果選中，此選項會自動將旋轉木馬項目標題設定為其詠嘆調標籤說明。

## 選擇面板 {#select-panel}

內容作者可以使用 **選擇面板** 按鈕，將選定控制項在Tab鍵次序中上移一個位置。

![「選擇面板」表徵圖](/help/assets/select-panel-icon.png)

選擇 **選擇面板** 選項中，所配置的幻燈片將顯示為下拉框。

* 清單按幻燈片的指定排列排序，並反映在編號中。
* 首先顯示幻燈片的元件類型，然後以較淺字型顯示幻燈片的說明。

![選取面板](/help/assets/select-panel-popover.png)

* 點擊或按一下下拉清單中的條目，將編輯器中的視圖切換到該幻燈片。
* 可使用拖動控制滑塊就地重新排序幻燈片。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義哪些元件可以作為幻燈片添加到旋轉傳送元件中，以及定義自動轉換預設值以及哪些自定義樣式可供內容作者使用。

### 屬性頁籤 {#properties-tab-1}

的 **屬性** 頁籤用於定義內容作者將旋轉傳送元件添加到頁面時幻燈片過渡的預設設定。

![「旋轉軸元件的設計」對話框](/help/assets/carousel-design.png)

* **自動轉換幻燈片**  — 定義當內容作者將旋轉傳送元件添加到頁面時，是否在預設情況下啟用自動將旋轉傳送器推進到下一張幻燈片的選項。
* **前置控制元素**  — 選中後，控制元素將放在傳送帶項目前，以提高可訪問性。

### 允許的元件頁籤 {#allowed-components-tab}

的 **允許的元件** 頁籤用於定義哪些元件可以作為幻燈片由內容作者添加到「旋轉軸元件」中。

「允許的元件」頁籤的功能與同名的頁籤在 [在模板編輯器中定義佈局容器的策略和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式頁籤 {#styles-tab}

旋轉軸元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

旋轉軸元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
