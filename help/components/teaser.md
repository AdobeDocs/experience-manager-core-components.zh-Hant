---
title: 預告元件
description: 該預告元件可以顯示影像、標題、富格文本以及可選地連結到其它內容。
role: Architect, Developer, Admin, User
exl-id: ec75e168-6f3b-4dff-8df6-06ca7dc18688
source-git-commit: 395a1669cf3e17f649c23852addc37316b923bfd
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 6%

---

# 預告元件 {#teaser-component}

核心元件預告元件可以顯示影像、標題、富格文本，並可選地連結到其他內容。

## 使用狀況 {#usage}

該預告元件允許內容作者使用影像、標題或富格文本容易地建立預告，以進一步內容，並連結到其他內容或其他動作。

模板作者可以使用 [設計對話框](#design-dialog) 定義建立「呼叫操作」和添加連結的選項是否可用以及禁用各種顯示選項。 內容作者可以使用 [配置對話框](#configure-dialog) 要設定影像，請定義CTA、設定標題和說明，以及配置指向單個預告的連結。 的 [編輯對話框](image.md#edit-dialog) 的 [影像元件](image.md) 可訪問以修改預激影像。

## 版本和相容性 {#version-and-compatibility}

當前版本的Teaser元件是v2，該版本於2022年2月隨核心元件2.18.0版一起推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v2 | - | 相容 | 相容 |
| [v1](v1/teaser.md) | 相容 | 相容 | 相容 |

## 元件輸出示例 {#sample-component-output}

要體驗預告元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_teaser)。

### 技術詳細資訊 {#technical-details}

有關預告元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_teaser_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

內容作者可以使用配置對話框來定義單個預告的屬性。 還有 [編輯對話框](#edit-dialog) 修改預激影像。

### 連結頁籤 {#links-tab}

![預告元件的編輯對話框連結頁籤](/help/assets/teaser-edit-links.png)

Teaser 標題、說明和影像可以從所連結的頁面繼承，也可以從第一個行動號召中所連結的頁面繼承。如果連結或行動號召都未指定，則會從當前的頁面繼承標題、說明和影像。

* **連結**  — 此檔案連結到內容頁、外部URL或頁面錨點。
* **在新頁籤中開啟連結**  — 如果啟用，連結將在新瀏覽器頁籤中開啟。
* **行動要求**  — 此選項允許連結到多個目標。
   * 在繼承預告標題、說明或影像時，將使用第一個操作調用中連結的頁面。

### 文本頁籤 {#text-tab}

![預告元件的編輯對話框文本頁籤](/help/assets/teaser-edit-text.png)

* **前標題**  — 預標題將顯示在預告標題之前。
* **標題**  — 定義要顯示為預告標題的標題。
   * **從連結頁面獲取標題**  — 選中後，標題將填充連結頁面的標題。
* **說明**  — 定義要顯示為預告子標題的說明。
   * **從連結頁面獲取描述**  — 選中後，將使用連結頁面的說明填充說明。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

### 資產標籤 {#asset-tab}

![預告元件的編輯對話框影像頁籤](/help/assets/teaser-edit-image.png)

* **從頁面繼承特色影像**  — 使用連結頁面或當前頁面的頁面屬性中定義的影像（如果找不到）。
* **影像資產**  — 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點擊 **瀏覽** 從本地檔案系統上載。
   * 點擊或按一下 **清除** 來取消選擇當前選定的映像。
   * 點擊或按一下 **編輯** 至 [管理資產的格式副本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 的子菜單。
* **輔助工具的備選文本**  — 此欄位允許您為視力受損的用戶定義影像描述。
   * **從頁面繼承備選文本**  — 此選項使用連結資產值的替代說明 `dc:description` DAM中的元資料，或當前頁的元資料（如果未連結任何資產）。
* **不提供替代文本**  — 此選項標籤要被螢幕閱讀器等輔助技術忽略的影像，在這些情況下，影像純粹是裝飾性的，或者沒有向頁面傳送其他資訊。

>[!NOTE]
>
>[Dynamic Media特徵](image.md#dynamic-media) 當前在預激元件中不可用。

### 樣式頁籤 {#styles-tab-edit}

![預告清單元件的編輯對話框的「樣式」頁籤](/help/assets/teaser-edit-styles.png)

預告元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便下拉菜單可用。

## 編輯對話框 {#edit-dialog}

「預測元件」將影像渲染委託到 [影像元件](image.md)。 因此 [編輯對話框](影像元件的image.md#edit-dialog可用於內容作者操作預告影像。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者在使用此元件時具有的預告選項。

### 預告頁籤 {#teaser-tab}

![「預測元件」的設計對話框](/help/assets/teaser-design.png)

* **呼叫動作**
   * **禁用呼叫操作**  — 隱藏 **行動要求** 內容作者選項
* **元素**
   * **隱藏前標題**  — 隱藏 **前標題** 內容作者選項
   * **隱藏標題**  — 隱藏 **標題** 內容作者選項
      * 選中時 **標題類型** 隱藏
   * **隱藏說明**  — 隱藏 **說明** 內容作者選項
* **預設標題類型**  — 定義預告標題使用的H標籤。
* **影像委託**  — 資訊顯示，指示預告委託影像處理的元件。

### 樣式頁籤 {#styles-tab}

預告元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

預告元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
