---
title: 制表符元件
description: 「頁籤元件」允許建立多個頁籤以在頁面上排列內容。
role: Architect, Developer, Admin, User
exl-id: 0031c5f3-447c-4932-898f-2f453801e492
source-git-commit: e8b3e55a42b6be6262d6f51b9569c0be3e8ce6c3
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 0%

---

# 制表符元件 {#tabs-component}

核心元件標籤元件允許將內容組織到多個標籤上。

## 使用狀況 {#usage}

「頁籤元件」允許內容作者在多個頁籤內組織頁面內容。

的 [編輯對話框](#edit-dialog) 允許內容作者定義多個頁籤並設定活動頁籤。 使用 [設計對話框](#design-dialog)，模板作者可以定義哪些元件可以添加到頁籤並自定義樣式。

>[!TIP]
>
>支援嵌套的頁籤元件（頁籤內的頁籤）。
>
>使用 [內容樹](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree)，但嵌套的頁籤不能是。

## 版本和相容性 {#version-and-compatibility}

標籤元件的當前版本為v1，該版本於2018年10月隨核心元件2.2.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗頁籤元件，並查看其配置選項示例以及HTML和JSON輸出，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_tabs)。

### 技術詳細資訊 {#technical-details}

有關Tabs元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_tabs_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 到面板的深度連結 {#deep-linking}

頁籤， [旋轉木馬，](carousel.md) 和 [折疊式元件](accordion.md) 支援直接連結到元件內的面板。

要執行此操作：

1. 使用 **[查看為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 的子菜單。
1. Inspect頁面內容並標識面板的ID。
   * 例如 `id="accordion-86196c94d3-item-ca319dbb0b"`
1. 該ID成為您可以使用哈希(`#`)。
   * 例如 `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

導航到面板ID為錨點的URL時，瀏覽器將直接滾動到特定元件並顯示指定的面板。 如果面板配置為預設情況下不展開，則會自動展開。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者建立、更名和重新排列頁籤以及定義活動頁籤。

### 項目頁籤 {#items-tab}

![頁籤元件的編輯對話框項頁籤](/help/assets/tabs-edit-items.png)

使用 **添加** 的子菜單。 添加後，將向清單中添加一個條目，該清單包含以下列：

* **表徵圖**  — 頁籤的元件類型表徵圖，便於在清單中進行標識。 將滑鼠移到工具提示中，以查看完整的元件名稱。
* **說明**  — 用作頁籤文本的說明，預設為為頁籤選擇的元件的名稱。
* **刪除**  — 按一下或按一下以從頁籤元件中刪除頁籤。
* **重新排列**  — 按一下或按一下並拖動以重新排列頁籤的順序。

>[!TIP]
>
>如果縮小頁面的視區，使編輯對話框變為全屏， **添加** 按鈕。 元件仍可通過以下方式添加到「制表符元件」 [從元件瀏覽器中拖動，然後放在頁面編輯器中的「頁籤元件」上](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)。

### 屬性頁籤 {#properties-tab}

![頁籤元件的編輯對話框屬性頁籤](/help/assets/tabs-edit-properties.png)

* **活動項**  — 內容作者可以定義載入頁面時處於活動狀態的頁籤。
   * 使用 **預設** 頁籤
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

### 輔助功能頁籤 {#accessibility-tab}

![頁籤元件的編輯對話框輔助功能頁籤](/help/assets/tabs-edit-accessibility.png)

在 **輔助功能** 頁籤，可為 [ARIA輔助功能](https://www.w3.org/WAI/standards-guidelines/aria/) 元件的標籤。

* **標籤**  — 元件的ARIA標籤屬性的值

## 選擇面板 {#select-panel}

內容作者可以使用 **選擇面板** 的子菜單。

![「選擇面板」表徵圖](/help/assets/select-panel-icon.png)

選擇 **選擇面板** 選項，配置的頁籤將顯示為下拉框。

* 清單按標籤的指定排列排序，並反映在編號中。
* 首先顯示頁籤的元件類型，然後以較淺字型顯示頁籤的說明。

![選擇面板跨距](/help/assets/select-panel-popover.png)

* 點擊或按一下下拉清單中的條目，將編輯器中的視圖切換到該頁籤。
* 通過使用拖動手柄，可以就地重新排列標籤。

>[!NOTE]
>
>在中時，作者無法選擇制表符 **編輯** 的子菜單。 使用 **[預覽](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)** 或 **[查看為已發佈](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** 選項，作為已發佈內容的讀取器與頁籤交互。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義哪些元件可以作為項目添加到頁籤元件中，並定義哪些自定義樣式可供內容作者使用。

### 允許的元件頁籤 {#allowed-components-tab}

的 **允許的元件** 頁籤用於定義哪些元件可以作為項目由內容作者添加到頁籤元件。

「允許的元件」頁籤的功能與同名的頁籤在 [在模板編輯器中定義佈局容器的策略和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 樣式頁籤 {#styles-tab}

頁籤元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

頁籤元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
