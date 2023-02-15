---
title: Teaser元件
description: 預告元件可顯示影像、標題、RTF，以及可選地連結至其他內容。
role: Architect, Developer, Admin, User
exl-id: ec75e168-6f3b-4dff-8df6-06ca7dc18688
source-git-commit: cfc86203051739cbcdc30be0fb10ccffa7d583a5
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 6%

---

# Teaser元件 {#teaser-component}

核心元件預告元件可顯示影像、標題、RTF，以及視需要連結至其他內容。

## 使用狀況 {#usage}

預告元件可讓內容作者使用影像、標題或RTF來輕鬆建立預告以進一步內容，並連結至更多內容或其他動作。

範本作者可使用 [設計對話](#design-dialog) 來定義建立動作呼叫和新增連結的選項是否可用，以及停用各種顯示選項。 內容作者可使用 [配置對話框](#configure-dialog) 若要設定影像，請定義CTA、設定標題和說明，以及設定個別預告的連結。 此 [編輯對話框](image.md#edit-dialog) 的 [影像元件](image.md) 可以存取以修改預告影像。

## 版本與相容性 {#version-and-compatibility}

目前的預告元件版本為v2，此版本於2022年2月2.18.0版核心元件推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v2 | - | 相容 | 相容 |
| [v1](v1/teaser.md) | 相容 | 相容 | 相容 |

## 範例元件輸出 {#sample-component-output}

若要體驗預告元件，並查看其設定選項、HTML和JSON輸出的範例，請造訪 [元件庫](https://adobe.com/go/aem_cmp_library_teaser).

### 技術詳細資訊 {#technical-details}

有關Teaser元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_teaser_v1).

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 配置對話框 {#configure-dialog}

內容作者可使用設定對話方塊來定義個別預告的屬性。 此外， [編輯對話框](#edit-dialog) 修改預告影像（如果已選取）。

### 連結標籤 {#links-tab}

![Teaser元件的編輯對話方塊連結索引標籤](/help/assets/teaser-edit-links.png)

Teaser 標題、說明和影像可以從所連結的頁面繼承，也可以從第一個行動號召中所連結的頁面繼承。如果連結或行動號召都未指定，則會從當前的頁面繼承標題、說明和影像。

* **連結**  — 此檔案連結至內容頁面、外部URL或頁面錨點。
* **在新索引標籤中開啟連結**  — 如果已啟用，連結會在新的瀏覽器標籤中開啟。
* **動作呼叫**  — 此選項可連結至多個目的地。
   * 繼承預告標題、說明或影像時，會使用第一個動作呼叫中連結的頁面。

### 文字索引標籤 {#text-tab}

![Teaser元件的編輯對話框文本頁簽](/help/assets/teaser-edit-text.png)

* **前置標題**  — 預先標題會顯示在預告標題之前。
* **標題**  — 定義標題，以顯示為預告的標題。
   * **從連結的頁面取得標題**  — 若勾選此選項，標題將會填入連結頁面的標題。
* **說明**  — 定義要顯示為預告子標題的說明。
   * **從連結的頁面取得說明**  — 若勾選此選項，描述將會填入連結頁面的說明。
* **ID**  — 此選項可控制HTML中和 [資料層](/help/developing/data-layer/overview.md).
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

### 資產標籤 {#asset-tab}

![Teaser元件的編輯對話方塊影像索引標籤](/help/assets/teaser-edit-image.png)

* **從頁面繼承精選影像**  — 使用在連結頁面或目前頁面的頁面屬性中定義的影像（若找不到）。
* **影像資產**  — 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點選 **瀏覽** 從本機檔案系統上傳的選項。
   * 點選或按一下 **清除** 以取消選取目前選取的影像。
   * 點選或按一下 **編輯** to [管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 在資產編輯器中。
* **協助工具的替代文字**  — 此欄位可讓您為視覺障礙使用者定義影像說明。
   * **從頁面繼承替代文字**  — 此選項使用 `dc:description` 中繼資料（若未連結任何資產）。
* **不提供替代文本**  — 如果影像純粹是裝飾性的，或未傳達其他資訊至頁面，此選項會標籤要由輔助技術（例如螢幕閱讀器）忽略的影像。

### 樣式標籤 {#styles-tab-edit}

![預告清單元件的編輯對話框的樣式頁簽](/help/assets/teaser-edit-styles.png)

Teaser元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling).

使用下拉式清單選取您要套用至元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須針對此元件在 [設計對話](#design-dialog) 讓下拉式功能表可供使用。

## 編輯對話方塊 {#edit-dialog}

預告元件會將影像呈現委派至 [影像元件](image.md). 因此， [編輯對話框](內容作者可使用影像元件的image.md#edit-dialog來操控預告影像。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者使用此元件時具有的宣傳預告選項。

### Teaser標籤 {#teaser-tab}

![預告元件的設計對話框](/help/assets/teaser-design.png)

* **呼叫動作**
   * **停用呼叫動作**  — 隱藏 **呼叫動作** 內容作者選項
* **元素**
   * **隱藏首頁**  — 隱藏 **前置標題** 內容作者選項
   * **隱藏標題**  — 隱藏 **標題** 內容作者選項
      * 選取 **標題類型** 隱藏
   * **隱藏說明**  — 隱藏 **說明** 內容作者選項
* **預設標題類型**  — 定義預告標題要使用的H標籤。
* **影像委派**  — 資訊顯示，指出Teaser委派影像處理的元件。

### 樣式標籤 {#styles-tab}

Teaser元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe用戶端資料層 {#data-layer}

Teaser元件支援 [Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
