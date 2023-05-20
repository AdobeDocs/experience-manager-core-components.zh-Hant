---
title: 折疊式元件
description: 核心元件折疊面板元件允許建立排列在頁面上折疊面板中的面板集合。
role: Architect, Developer, Admin, User
exl-id: 1deb570a-3d8d-409e-805f-8460c49cf9bb
source-git-commit: e8b3e55a42b6be6262d6f51b9569c0be3e8ce6c3
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 0%

---

# 折疊式元件{#accordion-component}

核心元件折疊面板元件允許建立排列在頁面上折疊面板中的面板集合。

## 使用狀況 {#usage}

核心元件折疊面板元件允許建立元件集合，這些元件組成為面板，並排列在頁面上的折疊面板中，類似於 [制表符元件](tabs.md)，但允許面板的展開和折疊。

* 可在 [配置對話框](#configure-dialog)。
* 可在「配置」對話框中定義折疊面板的順序以及 [選擇面板跨距](#select-panel-popover)。
* 將折疊元件添加到頁面時的預設值可以在 [設計對話框](#design-dialog)。

## 版本和相容性 {#version-and-compatibility}

當前版本的折疊式元件是v1，該版本於2019年6月隨核心元件2.5.0版一起推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗折疊式元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_accordion)。

## 技術詳細資訊 {#technical-details}

有關折疊式元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_accordion_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 到面板的深度連結 {#deep-linking}

手風琴， [旋轉木馬，](carousel.md) 和 [制表符元件](tabs.md) 支援直接連結到元件內的面板。

要執行此操作：

1. 使用 **[查看為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 的子菜單。
1. Inspect頁面內容並標識面板的ID。
   * 例如 `id="accordion-86196c94d3-item-ca319dbb0b"`
1. 該ID成為您可以使用哈希(`#`)。
   * 例如 `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

導航到面板ID為錨點的URL時，瀏覽器將直接滾動到特定元件並顯示指定的面板。 如果面板配置為預設情況下不展開，則會自動展開。

## 配置對話框 {#configure-dialog}

「配置」對話框允許內容作者定義折疊項、其面板以及訪問頁面的訪問者的行為和顯示方式。

### 項目頁籤 {#items-tab}

![折疊元件編輯對話框的「項」頁籤](/help/assets/accordion-edit-items.png)

使用 **添加** 按鈕開啟元件選擇器，以選擇要作為面板添加的元件。 添加後，將向清單中添加一個條目，該清單包含以下列：

* **表徵圖**  — 面板元件類型的表徵圖，便於在清單中進行標識。 將滑鼠移到工具提示中，以查看完整的元件名稱。
* **說明**  — 用作面板文本的說明，預設為為面板選擇的元件的名稱。
* **刪除**  — 點擊或按一下以從折疊元件中刪除面板。
* **重新排列**  — 按一下或按一下並拖動以重新排列面板的順序。

>[!TIP]
>
>如果縮小頁面的視區，使編輯對話框變為全屏， **添加** 按鈕。 元件仍可以通過 [從元件瀏覽器中拖動，然後放在頁面編輯器中的折疊元件上](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)。

### 屬性頁籤 {#properties-tab}

![折疊元件的編輯對話框的屬性頁籤](/help/assets/accordion-edit-properties.png)

* **單項擴展**  — 選中此選項後，將強制一次擴展單個折疊面板項。 展開一個項目後將折疊所有其它項目。
* **展開的項目**  — 此選項定義載入頁面時預設展開的項目。
   * 當 **單項擴展** 選中，必須選擇一個面板。 預設情況下，會選擇第一個面板。
   * 當 **單項擴展** 未選中，此選項是多選項，並且是可選的。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

## 選擇面板跨距 {#select-panel-popover}

內容作者可以使用 **選擇面板** 按鈕，將選定控制項在Tab鍵次序上移動。

![「選擇面板」表徵圖](/help/assets/select-panel-icon.png)

選擇 **選擇面板** 選項中，配置的折疊面板將顯示為下拉清單。

![選擇面板跨距](/help/assets/select-panel-popover.png)

* 清單按面板的指定排列排序，並反映在編號中。
* 首先顯示面板的元件類型，然後以較淺字型顯示面板的說明。
* 點擊或按一下下拉清單中的條目，將編輯器中的視圖切換到該面板。
* 通過使用拖動手柄，可以就地重新排列面板。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者可用的選項，內容作者使用折疊元件和放置折疊元件時設定的預設值。

### 屬性頁籤 {#properties-tab-design}

![「設計」對話框屬性頁籤](/help/assets/accordion-design-properties.png)

* **允許的標題元素**  — 此多選下拉框定義了作者允許選擇的折疊項標題HTML元素。
* **預設標題元素**  — 此下拉框定義預設折疊項標題HTML元素。

### 允許的元件頁籤 {#allowed-components-tab}

的 **允許的元件** 頁籤用於定義哪些元件可以作為項目由內容作者添加到折疊元件中的面板。

「允許的元件」頁籤的功能與同名的頁籤在 [在模板編輯器中定義佈局容器的策略和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### 樣式頁籤 {#styles-tab}

折疊元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

折疊元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
