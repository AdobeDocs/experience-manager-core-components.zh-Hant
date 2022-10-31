---
title: 影像元件
description: 核心元件影像元件是自適應影像元件。
role: Architect, Developer, Admin, User
exl-id: c5e57f4b-139f-40e7-8d79-be9a74360b63
source-git-commit: f0971db66cbbf8221c12cedf108eee3bca8a527a
workflow-type: tm+mt
source-wordcount: '1678'
ht-degree: 1%

---

# 影像元件{#image-component}

核心元件影像元件是自適應影像元件。

## 使用狀況 {#usage}

「影像元件」提供適用性影像選取及對頁面訪客具有延遲載入的回應式行為，以及為內容作者提供簡易的影像放置。

範本作者可在 [設計對話](#design-dialog). 內容編輯器可以上傳或選取 [配置對話框。](#configure-dialog)

## 版本與相容性 {#version-and-compatibility}

目前的影像元件版本為v3，此版本於2022年2月2.18.0版核心元件時推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v3 | - | 相容 | 相容 |
| [v2](v2/image.md) | 相容 | 相容 | 相容 |
| [v1](v1/image-v1.md) | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱本檔案 [核心元件版本](/help/versions.md).

## 回應式功能 {#responsive-features}

影像元件隨附立即可用的強大回應式功能。 在頁面範本層級， [設計對話](#design-dialog) 可用來定義影像資產的預設寬度。 影像元件會根據瀏覽器視窗的大小自動載入顯示的正確寬度。 視窗調整大小時，影像元件會動態載入正確的影像大小。 元件開發人員無需擔心定義自訂媒體查詢，因為影像元件已最佳化以載入您的內容。

此外，影像元件支援延遲載入，將實際影像資產的載入延遲到在瀏覽器中顯示為止，以提高頁面的回應速度。

>[!TIP]
>
>依預設，影像元件由最適化影像Servlet提供技術支援。 請查看該文檔 [適用性影像Servlet](#adaptive-image-servlet) 以取得運作方式的詳細資訊。

## Dynamic Media支援 {#dynamic-media}

影像元件(截至 [版本2.13.0](/help/versions.md))支援 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html#dynamicmedia) 資產。 [啟用後，](#design-dialog) 這些功能可讓您透過簡單的拖放功能，或透過「資產」瀏覽器，新增Dynamic Media影像資產，如同其他影像一樣。 此外，還支援影像修飾元、影像預設集和智慧型裁切。

以核心元件建置的網頁體驗，可提供豐富、Sensei支援、強大、高效能、跨平台的Dynamic Media影像功能。

## SVG支援 {#svg-support}

影像元件支援可縮放向量圖形(SVG)。

* 從DAM拖放SVG資產，以及從本機檔案系統上傳SVG檔案均受支援。
* 原始SVG檔案流化（跳過轉換）。
* 對於SVG影像，「智慧影像」和「智慧大小」設為影像模型中的空陣列。

### 安全性 {#security}

基於安全考量，影像編輯器絕不會直接呼叫原始SVG。 它被調用 `<img src=“path-to-component”>`. 這會防止瀏覽器執行任何內嵌在SVG檔案中的指令碼。

>[!NOTE]
>
>SVG支援需要2.1.0版或更新版本的核心元件，以及 [服務包2](https://experienceleague.adobe.com/docs/experience-manager-64/release-notes/sp-release-notes.html) AEM 6.4或更新版本，以支援 [影像編輯器功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/image-editor.html) 在AEM中。

## 範例元件輸出 {#sample-component-output}

若要體驗影像元件，並查看其設定選項、HTML和JSON輸出的範例，請造訪 [元件庫](https://adobe.com/go/aem_cmp_library_image).

### 技術詳細資訊 {#technical-details}

影像元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_image_v3).

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

影像元件支援 [schema.org microdata](https://schema.org).

## 配置對話框 {#configure-dialog}

影像元件提供設定對話方塊，定義影像本身及其說明和基本屬性。

### 資產標籤 {#asset-tab}

![影像元件設定對話方塊的資產標籤](/help/assets/image-configure-asset.png)

* **從頁面繼承精選影像**  — 此選項使用 [連結頁面的精選影像](page.md) 或目前頁面的精選影像（若未連結）。

* **協助工具的替代文字**  — 此欄位可讓您為視覺障礙使用者定義影像說明。

   * **從頁面繼承替代文字**  — 此選項使用 `dc:description` 中繼資料（若未連結任何資產）。

* **影像資產**
   * 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點選 **瀏覽** 從本機檔案系統上傳的選項。
   * 點選或按一下 **清除** 以取消選取目前選取的影像。
   * 點選或按一下 **編輯** to [管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 在資產編輯器中。

* **不提供替代文本**  — 如果影像純粹是裝飾性的，或未傳達其他資訊至頁面，此選項會標籤要由輔助技術（例如螢幕閱讀器）忽略的影像。

### 中繼資料索引標籤 {#metadata-tab}

![影像元件的配置對話框的元資料頁簽](/help/assets/image-configure-metadata.png)

* **預設類型**  — 這會定義可用的影像預設集類型， **影像預設集** 或 **智慧型裁切**，和僅適用於 [Dynamic Media功能](#dynamic-meida) 的URL區段。
   * **影像預設集**  — 何時 **預設類型** of **影像預設集** ，則下拉式清單中的 **影像預設集** 可用，允許從可用的Dynamic Media預設集中選取。 只有為選取的資產定義了預設集時，才可使用此功能。
   * **智慧型裁切**  — 何時 **預設類型** of **智慧型裁切** 已選取下拉式清單 **轉譯** 可用，允許從所選資產的可用轉譯中選取。 只有為選取的資產定義轉譯時，才可使用此功能。
   * **影像修飾元**  — 可在此處定義其他Dynamic Media影像伺服命令，依 `&`，無論 **預設類型** 中所有規則的URL。
* **註解**  — 影像的其他資訊，預設顯示在影像下方。
   * **從DAM取得註解**  — 若勾選此選項，影像的註解文字將會填入 `dc:title` DAM中的中繼資料。
   * **將標題顯示為快顯視窗**  — 若勾選此選項，註解不會顯示在影像下方，但會在將游標暫留在影像上時，以某些瀏覽器顯示的快顯視窗顯示。
* **連結**  — 將影像連結至其他資源。
   * 使用選取對話方塊連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非溶質URL會解譯為相對於AEM。
   * **在新索引標籤中開啟連結**  — 此選項會在新瀏覽器視窗中開啟連結。
* **ID**  — 此選項可控制HTML中和 [資料層](/help/developing/data-layer/overview.md).
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

>[!TIP]
>
>**智慧型裁切** 和 **影像預設集** 是互斥的選項。 如果作者需要使用影像預設集和智慧型裁切轉譯，則作者必須使用 **影像修飾元** 來手動添加預設集。

### 樣式標籤 {#styles-tab-edit}

![影像元件的編輯對話框的樣式頁簽](/help/assets/image-configure-styles.png)

影像元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling).

使用下拉式清單選取您要套用至元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須針對此元件在 [設計對話](#design-dialog) 讓下拉式功能表可供使用。

## 設計對話方塊 {#design-dialog}

### 主要標籤 {#main-tab}

![影像元件的設計對話方塊主索引標籤](/help/assets/image-design-main.png)

* **啟用DM功能**  — 若勾選， [Dynamic Media功能](#dynamic-media) 的URL區段。
   * 只有在環境中啟用Dynamic Media時，才會顯示此選項。
* **啟用Web優化映像**  — 若勾選， [web最佳化的影像傳送服務](/help/developing/web-optimized-image-delivery.md) 會以WebP格式傳送影像，平均將影像大小減少25%。
   * 此選項僅適用於AEMaaCS。
   * 取消勾選或網頁最佳化影像傳送服務無法使用時， [適用性影像Servlet](/help/developing/adaptive-image-servlet.md) 中所有規則的URL區段。
* **停用延遲載入**  — 若勾選此選項，元件將預先載入所有影像，而不會延遲載入。
* **影像是裝飾**  — 定義將影像元件新增至頁面時是否自動啟用裝飾影像選項。
* **從DAM取得替代文字** — 定義將影像元件新增至頁面時，從DAM擷取替代文字的選項是否自動啟用。
* **從DAM取得註解**  — 定義將影像元件新增至頁面時，從DAM擷取註解的選項是否自動啟用。
* **將標題顯示為快顯視窗**  — 定義將影像元件新增至頁面時，將影像標題顯示為快顯視窗的選項是否自動啟用。
* **調整寬度**  — 此值可用來調整DAM資產基礎影像的寬度。
   * 將保留影像的長寬比。
   * 如果值大於影像的實際寬度，則此值將無效。
   * 此值對SVG影像沒有影響。

您可以定義影像的寬度清單（以像素為單位），元件會根據瀏覽器大小自動載入最適當的寬度。 這是 [回應式功能](#responsive-features) 的下限。

* **寬度**  — 以像素定義影像的寬度清單，元件會根據瀏覽器大小自動載入最適當的寬度。
   * 點選或按一下 **新增** 按鈕以添加其他大小。
      * 使用抓握手柄重新排列大小的順序。
      * 使用 **刪除** 表徵圖以移除寬度。
   * 依預設，載入影像會延遲，直到變成可見為止。
      * 選取選項 **停用延遲載入** 以在頁面載入時載入影像。
* **JPEG品質**  — 已轉換（例如縮放或裁切）JPEG影像的品質因數（百分比為0和100）。

>[!TIP]
>
>請參閱檔案 [適用性影像Servlet](/help/developing/adaptive-image-servlet.md) 請參閱謹慎定義寬度以最佳化轉譯選取的秘訣。

### 樣式標籤 {#styles-tab}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe用戶端資料層 {#data-layer}

影像元件支援 [Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
