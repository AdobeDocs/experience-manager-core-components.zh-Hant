---
title: 電子郵件影像元件
description: 電子郵件影像元件是自我調整影像元件，具備就地編輯的功能。
role: Architect, Developer, Admin, User
exl-id: f5d40047-3082-4edd-a5f6-6ab3e33997f9
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 0%

---


# 電子郵件影像元件 {#email-image-component}

電子郵件影像元件是自我調整影像元件，具備就地編輯的功能。

## 使用狀況 {#usage}

電子郵件影像元件提供最適化影像選擇和回應式行為，頁面訪客可延遲載入，內容作者可輕鬆拖放影像放置和設定。

* 範本作者可以在下列位置定義影像寬度和其他設定： [設計對話方塊。](#design-dialog)
* 內容編輯者可以上傳或選取 [設定對話方塊。](#configure-dialog)

## 版本和相容性 {#version-and-compatibility}

電子郵件影像元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [電子郵件核心元件版本](/help/email/versions.md).

## 回應式功能 {#responsive-features}

電子郵件影像元件提供強大的回應式功能，立即可用。 在頁面範本層級， [設計對話方塊](#design-dialog) 可用來定義影像資產的預設寬度。 然後，電子郵件影像元件將自動載入正確的寬度，以根據瀏覽器視窗的大小來顯示。 在視窗調整大小時，電子郵件影像元件會即時動態載入正確的影像大小。 元件開發人員無需擔心自訂媒體查詢的定義方式，因為電子郵件影像元件已最佳化以載入您的內容。

此外，電子郵件影像元件支援延遲載入，將實際影像資產的載入延遲到瀏覽器中可見時，以提高內容的回應速度。

>[!TIP]
>
>依預設，電子郵件影像元件是由Adaptive Image Servlet提供技術支援。 請參閱檔案 [最適化影像Servlet](#adaptive-image-servlet) 瞭解其運作方式的詳細資訊。

## Dynamic Media支援 {#dynamic-media}

電子郵件影像元件支援 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html#dynamicmedia) 資產。 [啟用時，](#design-dialog) 這些功能可讓您透過簡單的拖放功能或透過資產瀏覽器，像新增任何其他影像一樣新增Dynamic Media影像資產。 此外，也支援影像修飾元、影像預設集和智慧型裁切。

使用電子郵件核心元件建置的電子郵件體驗可包含豐富、Sensei支援、穩健、高效能、跨平台的Dynamic Media影像功能。

## SVG支援 {#svg-support}

電子郵件影像元件支援可縮放向量圖形(SVG)。

* 支援從DAM拖放SVG資產以及從本機檔案系統上傳SVG檔案。
* 將原始SVG檔案串流（跳過轉換）。
* 對於SVG影像，「智慧型影像」和「智慧型大小」會設定為影像模型中的空陣列。

### 安全性 {#security}

基於安全考量，影像編輯器絕對不會直接呼叫原始SVG。 會透過呼叫 `<img src=“path-to-component”>`. 這可防止瀏覽器執行SVG檔案中內嵌的任何指令碼。

### 技術細節 {#technical-details}

有關電子郵件影像元件的最新技術檔案 [在GitHub上可找到。](https://adobe.com/go/aem_cmp_tech_email_image_v1)

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案。](/help/developing/overview.md)

影像元件支援 [schema.org microdata.](https://schema.org)

## 設定對話方塊 {#configure-dialog}

電子郵件影像元件提供設定對話方塊，其中影像本身與其說明和基本屬性一起定義。

### 資產標籤 {#asset-tab}

![電子郵件影像元件之「設定」對話方塊的「資產」索引標籤](/help/email/assets/email-image-configure-asset.png)

* **從頁面繼承精選影像**  — 此選項使用 [連結頁面的精選影像](page.md) 或目前頁面的精選影像（如果未連結影像）。

* **協助工具的替代文字**  — 此欄位可讓您為視障使用者定義影像說明。

   * **從頁面繼承替代文字**  — 此選項使用連結資產值的替代說明， `dc:description` DAM中的中繼資料，或目前頁面的中繼資料（若未連結資產）。

* **影像資產**
   * 從拖放資產 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點選 **瀏覽** 從本機檔案系統上傳的選項。
   * 點選或按一下 **清除** 以取消選取目前選取的影像。
   * 點選或按一下 **編輯** 至 [管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) （在Asset Editor中）。

* **不提供替代文字**  — 此選項會針對影像純粹起裝飾作用或不向頁面傳達額外資訊的情況，將影像標籤為被熒幕閱讀器等輔助技術忽略。

* **停用延遲載入**  — 此選項會預先載入所有影像元件，而不會視需要載入。

### 中繼資料標籤 {#metadata-tab}

![影像元件「設定」對話方塊的「中繼資料」標籤](/help/email/assets/email-image-configure-metadata.png)

* **預設集型別**  — 這定義了可用的影像預設集型別，可以 **影像預設集** 或 **智慧型裁切**、和僅在以下情況下可用： [Dynamic Media功能](#dynamic-meida) 已啟用。
   * **影像預設集**  — 時間 **預設集型別** 之 **影像預設集** 已選取，下拉式清單 **影像預設集** 可使用，並允許從可用的Dynamic Media預設集中選擇。 只有在為選取的資產定義了預設集時，才能使用此選項。
   * **智慧型裁切**  — 時間 **預設集型別** 之 **智慧型裁切** 在下拉式清單中選取 **轉譯** 可使用，並允許從所選資產的可用轉譯中進行選擇。 這只有在為選取的資產定義了轉譯時才可用。
   * **影像修飾元**  — 您可在這裡定義其他Dynamic Media影像伺服命令，區隔為 `&`，無論哪一個 **預設集型別** 「 」已選取。
* **註解**  — 影像的其他相關資訊，預設會顯示於影像下方。
   * **從DAM取得圖片說明**  — 勾選後，影像的註解文字將會填入 `dc:title` dam中的中繼資料。 僅當從DAM中選擇資產時可用。
   * **以快顯視窗顯示註解**  — 檢查完畢後，註解不會顯示在影像下方，但如在某些瀏覽器中將滑鼠懸停在影像上，註解會以快顯模式顯示。
* **連結**  — 將影像連結至其他資源。
   * 使用選取對話方塊來連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非解決方案URL將解譯為相對於AEM。
   * **在新標籤中開啟連結**  — 此選項會在新的瀏覽器視窗中開啟連結。
* **ID**  — 此選項可讓您控制HTML中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS造成影響。
* **修正方式**  — 此選項會定義影像的寬度（畫素）。
* **將影像縮放至可用寬度**  — 此選項適用 `"width":"100%"` 至影像樣式屬性。

>[!TIP]
>
>**智慧型裁切** 和 **影像預設集** 是互斥選項。 如果作者需要使用影像預設集以及智慧型裁切轉譯，該作者必須使用 **影像修飾元** 以手動新增預設集。

### 樣式索引標籤 {#styles-tab-edit}

![電子郵件影像元件「編輯」對話方塊的「樣式」索引標籤](/help/assets/image-configure-styles.png)

電子郵件影像元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的效果相同。

必須在以下位置為此元件設定樣式： [設計對話方塊](#design-dialog) 讓索引標籤可用。

## 設計對話方塊 {#design-dialog}

### 主要標籤 {#main-tab}

![影像元件的「設計」對話方塊主索引標籤](/help/email/assets/email-image-design-main.png)

* **啟用DM功能**  — 檢查時， [Dynamic Media功能](#dynamic-media) 可用。
   * 此選項僅在環境中啟用Dynamic Media時顯示。
* **啟用Web最佳化的影像**  — 檢查時， [網頁最佳化的影像傳遞服務](/help/developing/web-optimized-image-delivery.md) 將以WebP格式傳送影像，平均將影像大小減少25%。
   * 此選項僅適用於AEMaaCS。
   * 取消勾選或Web最佳化的影像傳送服務無法使用時， [最適化影像Servlet](/help/developing/adaptive-image-servlet.md) 已使用。
* **裝飾性影像**  — 定義將影像元件新增至頁面時，是否自動啟用裝飾性影像選項。
* **從DAM取得替代文字** — 定義將影像元件新增至頁面時，是否自動啟用從DAM擷取替代文字的選項。
* **從DAM取得圖片說明**  — 定義將影像元件新增至頁面時，是否自動啟用從DAM擷取註解的選項。
* **以快顯視窗顯示註解**  — 定義將影像元件新增至頁面時，是否自動啟用以快顯視窗顯示影像註解的選項。
* **調整寬度**  — 此值用於調整作為DAM資產的基本影像的寬度。
   * 將會保留影像的外觀比例。
   * 如果該值大於影像的實際寬度，則該值無效。
   * 此值對SVG影像沒有影響。

您可以定義影像的寬度清單（以畫素為單位），元件會根據瀏覽器大小自動載入最適合的寬度。 這是 [回應式功能](#responsive-features) 電子郵件影像元件的。

* **寬度**  — 定義影像的寬度（以畫素為單位），元件會根據瀏覽器大小自動載入最適合的寬度。
   * 點選或按一下 **新增** 按鈕以新增其他大小。
      * 使用抓取操作框來重新排列大小。
      * 使用 **刪除** 圖示可移除寬度。
   * 依預設，影像載入會延遲到它們變成可見為止。
      * 選取選項 **停用延遲載入** 以在頁面載入時載入影像。
* **JPEG品質**  — 轉換（例如縮放或裁切）的JPEG影像的品質因數（以從0到100的百分比表示）。
* **預設寬度**  — 將在設計對話方塊中使用的預設影像寬度（以畫素為單位）

>[!TIP]
>
>檢視檔案 [最適化影像Servlet](/help/developing/adaptive-image-servlet.md) 提供透過仔細定義寬度來最佳化轉譯選擇的秘訣。

### 樣式索引標籤 {#styles-tab}

電子郵件影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
