---
title: 電子郵件影像元件
description: 電子郵件影像元件是可就地編輯的最適化影像元件。
role: Architect, Developer, Admin, User
exl-id: f5d40047-3082-4edd-a5f6-6ab3e33997f9
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---


# 電子郵件影像元件 {#email-image-component}

電子郵件影像元件是可就地編輯的最適化影像元件。

## 使用狀況 {#usage}

「電子郵件影像元件」提供適用性的影像選取以及針對頁面訪客延遲載入的回應式行為，以及為內容作者輕鬆拖放影像放置和設定。

* 範本作者可在 [設計對話方塊。](#design-dialog)
* 內容編輯器可以上傳或選取 [配置對話框。](#configure-dialog)

## 版本與相容性 {#version-and-compatibility}

電子郵件影像元件的目前版本為v1，已於2022年10月隨電子郵件核心元件第x版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱本檔案 [電子郵件核心元件版本](/help/email/versions.md).

## 回應式功能 {#responsive-features}

電子郵件影像元件隨附立即可用的強大回應式功能。 在頁面範本層級， [設計對話](#design-dialog) 可用來定義影像資產的預設寬度。 然後，電子郵件影像元件會自動載入正確的寬度以根據瀏覽器視窗的大小顯示。 視窗調整大小時，電子郵件影像元件會動態載入正確的影像大小。 元件開發人員無需擔心定義自訂媒體查詢，因為電子郵件影像元件已最佳化以載入您的內容。

此外，電子郵件影像元件支援延遲載入，將實際影像資產的載入推遲到瀏覽器中顯示為止，以提高內容的回應速度。

>[!TIP]
>
>依預設，電子郵件影像元件由適用性影像Servlet提供技術支援。 請查看該文檔 [適用性影像Servlet](#adaptive-image-servlet) 以取得運作方式的詳細資訊。

## Dynamic Media支援 {#dynamic-media}

電子郵件影像元件支援 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html#dynamicmedia) 資產。 [啟用後，](#design-dialog) 這些功能可讓您透過簡單的拖放功能，或透過「資產」瀏覽器，新增Dynamic Media影像資產，如同其他影像一樣。 此外，還支援影像修飾元、影像預設集和智慧型裁切。

使用電子郵件核心元件建立的電子郵件體驗可提供豐富、Sensei支援、強大、高效能、跨平台的Dynamic Media影像功能。

## SVG支援 {#svg-support}

電子郵件影像元件支援可縮放向量圖形(SVG)。

* 從DAM拖放SVG資產，以及從本機檔案系統上傳SVG檔案均受支援。
* 原始SVG檔案流化（跳過轉換）。
* 對於SVG影像，「智慧影像」和「智慧大小」設為影像模型中的空陣列。

### 安全性 {#security}

基於安全考量，影像編輯器絕不會直接呼叫原始SVG。 它被調用 `<img src=“path-to-component”>`. 這會防止瀏覽器執行任何內嵌在SVG檔案中的指令碼。

## 範例元件輸出 {#sample-component-output}

若要體驗電子郵件影像元件，並查看其設定選項、HTML和JSON輸出的範例，請造訪 [元件庫。](https://adobe.com/go/aem_cmp_library_email_image)

### 技術詳細資訊 {#technical-details}

電子郵件影像元件的最新技術檔案 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_image_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案。](/help/developing/overview.md)

影像元件支援 [schema.org微資料。](https://schema.org)

## 配置對話框 {#configure-dialog}

電子郵件影像元件提供設定對話方塊，定義影像本身及其說明和基本屬性。

### 資產標籤 {#asset-tab}

![電子郵件影像元件設定對話方塊的資產標籤](/help/email/assets/email-image-configure-asset.png)

* **從頁面繼承精選影像**  — 此選項使用 [連結頁面的精選影像](page.md) 或目前頁面的精選影像（若未連結）。

* **協助工具的替代文字**  — 此欄位可讓您為視覺障礙使用者定義影像說明。

   * **從頁面繼承替代文字**  — 此選項使用 `dc:description` 中繼資料（若未連結任何資產）。

* **影像資產**
   * 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點選 **瀏覽** 從本機檔案系統上傳的選項。
   * 點選或按一下 **清除** 以取消選取目前選取的影像。
   * 點選或按一下 **編輯** to [管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) （在資產編輯器中）。

* **不提供替代文本**  — 如果影像純粹是裝飾性的，或未傳達其他資訊至頁面，此選項會標籤要由輔助技術（例如螢幕閱讀器）忽略的影像。

* **停用延遲載入**  — 此選項會預先載入所有影像元件，而不會視需要載入。

### 中繼資料索引標籤 {#metadata-tab}

![影像元件的配置對話框的元資料頁簽](/help/email/assets/email-image-configure-metadata.png)

* **預設類型**  — 這會定義可用的影像預設集類型， **影像預設集** 或 **智慧型裁切**，和僅適用於 [Dynamic Media功能](#dynamic-meida) 的URL區段。
   * **影像預設集**  — 何時 **預設類型** of **影像預設集** ，則下拉式清單 **影像預設集** 可用，允許從可用的Dynamic Media預設集中選取。 只有為選取的資產定義了預設集時，才可使用此功能。
   * **智慧型裁切**  — 何時 **預設類型** of **智慧型裁切** 已選取下拉式清單 **轉譯** 可用，允許從所選資產的可用轉譯中選取。 只有為選取的資產定義轉譯時，才可使用此功能。
   * **影像修飾元**  — 此處可以分隔其他Dynamic Media影像伺服命令 `&`，無論 **預設類型** 中所有規則的URL。
* **註解**  — 影像的其他資訊，預設顯示在影像下方。
   * **從DAM取得註解**  — 若勾選此選項，影像的註解文字將會填入 `dc:title` DAM中的中繼資料。 只有從DAM中選擇資產時才可用。
   * **將標題顯示為快顯視窗**  — 若勾選此選項，註解不會顯示在影像下方，但會在將游標暫留在影像上時，以某些瀏覽器顯示的快顯視窗顯示。
* **連結**  — 將影像連結至其他資源。
   * 使用選取對話方塊連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非溶質URL會解譯為相對於AEM。
   * **在新索引標籤中開啟連結**  — 此選項會在新瀏覽器視窗中開啟連結。
* **ID**  — 此選項可控制HTML中元件的唯一標識符。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會對CSS造成影響。
* **已修正為**  — 此選項以像素定義影像的寬度。
* **將影像縮放為可用寬度**  — 此選項適用 `"width":"100%"` 至影像樣式屬性。

>[!TIP]
>
>**智慧型裁切** 和 **影像預設集** 是互斥的選項。 如果作者需要使用影像預設集和智慧型裁切轉譯，則作者必須使用 **影像修飾元** 來手動添加預設集。

### 樣式標籤 {#styles-tab-edit}

![電子郵件影像元件編輯對話方塊的樣式標籤](/help/assets/image-configure-styles.png)

電子郵件影像元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單選取您要套用至元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須針對此元件在 [設計對話](#design-dialog) 讓索引標籤可用。

## 設計對話方塊 {#design-dialog}

### 主要標籤 {#main-tab}

![影像元件的設計對話方塊主索引標籤](/help/email/assets/email-image-design-main.png)

* **啟用DM功能**  — 若勾選， [Dynamic Media功能](#dynamic-media) 的URL區段。
   * 只有在環境中啟用Dynamic Media時，才會顯示此選項。
* **啟用Web優化映像**  — 若勾選， [web最佳化的影像傳送服務](/help/developing/web-optimized-image-delivery.md) 會以WebP格式傳送影像，平均將影像大小減少25%。
   * 此選項僅適用於AEMaaCS。
   * 取消勾選或當網頁最佳化影像傳送服務無法使用時， [適用性影像Servlet](/help/developing/adaptive-image-servlet.md) 中所有規則的URL區段。
* **影像是裝飾**  — 定義將影像元件新增至頁面時是否自動啟用裝飾影像選項。
* **從DAM取得替代文字** — 定義將影像元件新增至頁面時，從DAM擷取替代文字的選項是否自動啟用。
* **從DAM取得註解**  — 定義將影像元件新增至頁面時，從DAM擷取註解的選項是否自動啟用。
* **將標題顯示為快顯視窗**  — 定義將影像元件新增至頁面時，將影像標題顯示為快顯視窗的選項是否自動啟用。
* **調整寬度**  — 此值可用來調整DAM資產基礎影像的寬度。
   * 將保留影像的長寬比。
   * 如果值大於影像的實際寬度，則此值將無效。
   * 此值對SVG影像沒有影響。

您可以定義影像的寬度清單（以像素為單位），元件會根據瀏覽器大小自動載入最適當的寬度。 這是 [回應式功能](#responsive-features) 電子郵件影像元件。

* **寬度**  — 以像素定義影像的寬度清單，元件會根據瀏覽器大小自動載入最適當的寬度。
   * 點選或按一下 **新增** 按鈕以添加其他大小。
      * 使用抓握手柄重新排列大小的順序。
      * 使用 **刪除** 表徵圖以移除寬度。
   * 依預設，載入影像會延遲，直到變成可見為止。
      * 選取選項 **停用延遲載入** 以在頁面載入時載入影像。
* **JPEG品質**  — 已轉換（例如縮放或裁切）JPEG影像的品質因數（百分比為0和100）。
* **預設寬度**  — 設計對話方塊中將使用的影像預設寬度（像素）

>[!TIP]
>
>請參閱檔案 [適用性影像Servlet](/help/developing/adaptive-image-servlet.md) 請參閱謹慎定義寬度以最佳化轉譯選取的秘訣。

### 樣式標籤 {#styles-tab}

電子郵件影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).