---
title: 影像元件(v2)
description: 核心元件影像元件是最適化影像元件，具備就地編輯的功能。
role: Architect, Developer, Admin, User
exl-id: 3f2b93f9-c48d-43ef-a78a-accd5090fe6f
source-git-commit: 6c251cd03997dca8961b31498c6f5de3cfdc3793
workflow-type: tm+mt
source-wordcount: '2073'
ht-degree: 0%

---

# 影像元件(v2) {#image-component}

核心元件影像元件是自我調整影像元件，具備就地編輯的功能。

## 使用狀況 {#usage}

影像元件提供最適化影像選擇和回應式行為，頁面訪客可延遲載入，內容作者可輕鬆放置和裁切影像。

範本作者可以在中定義影像寬度、裁切以及其他設定。 [設計對話方塊](#design-dialog). 內容編輯者可以上傳或選取 [設定對話方塊](#configure-dialog) 並裁切影像 [編輯對話方塊](#edit-dialog). 為了增加便利性，您也可以使用簡單的影像就地修改。

## 版本和相容性 {#version-and-compatibility}

本檔案說明影像元件v2，此版本隨2018年1月的核心元件發行版本2.0.0的發佈引入。

>[!CAUTION]
>
>本檔案說明影像元件v1。
>
>如需目前版本的影像元件的詳細資訊，請參閱 [影像元件](/help/components/image.md) 檔案。

## 回應式功能 {#responsive-features}

影像元件隨附強大的回應式功能，立即可用。 在頁面範本層級， [設計對話方塊](#design-dialog) 可用來定義影像資產的預設寬度。 然後，影像元件會自動載入正確的寬度，以根據瀏覽器視窗的大小來顯示。 視窗調整大小時，影像元件會即時動態載入正確的影像大小。 元件開發人員無需擔心自訂媒體查詢的定義方式，因為影像元件已最佳化以載入您的內容。

此外，影像元件支援延遲載入，將實際影像資產的載入延遲到顯示在瀏覽器中時，以提高頁面的回應速度。

>[!TIP]
>
>影像元件由最適化影像Servlet提供技術支援。 請參閱檔案 [最適化影像Servlet](#adaptive-image-servlet) 瞭解其運作方式的詳細資訊。

## Dynamic Media支援 {#dynamic-media}

影像元件(截至 [版本2.13.0](/help/versions.md))支援 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=en#dynamicmedia) 資產。 [啟用時，](#design-dialog) 這些功能可讓您透過簡單的拖放功能或透過資產瀏覽器，像新增任何其他影像一樣新增Dynamic Media影像資產。 此外，也支援影像修飾元、影像預設集和智慧型裁切。

使用核心元件建立的網頁體驗無法具備豐富、Sensei支援、健全、高效能、跨平台的Dynamic Media影像功能。

## SVG支援 {#svg-support}

影像元件支援可縮放的向量圖形(SVG)。

* 支援從DAM拖放SVG資產以及從本機檔案系統上傳SVG檔案。
* 將原始SVG檔案串流（跳過轉換）。
* 對於SVG影像，「智慧型影像」和「智慧型大小」會設定為影像模型中的空陣列。

### 安全性 {#security}

基於安全考量，影像編輯器絕對不會直接呼叫原始SVG。 會透過呼叫 `<img src=“path-to-component”>`. 這可防止瀏覽器執行SVG檔案中內嵌的任何指令碼。

## 範例元件輸出 {#sample-component-output}

若要體驗影像元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_image).

### 技術細節 {#technical-details}

有關影像元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_image_v2).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

影像元件支援 [schema.org microdata](https://schema.org).

## 設定對話方塊 {#configure-dialog}

除了標準 [編輯對話方塊](#edit-dialog) 和 [設計對話方塊](#design-dialog)，影像元件會提供「設定」對話方塊，其中會定義影像本身及其說明和基本屬性。

### 資產標籤 {#asset-tab}

![影像元件「設定」對話方塊的「資產」標籤](/help/assets/image-configure-asset.png)

* **影像資產**
   * 從拖放資產 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點選 **瀏覽** 從本機檔案系統上傳的選項。
   * 點選或按一下 **清除** 以取消選取目前選取的影像。
   * 點選或按一下 **編輯** 至 [管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 在資產編輯器中。

### 中繼資料標籤 {#metadata-tab}

![影像元件「設定」對話方塊的「中繼資料」標籤](/help/assets/image-configure-metadata.png)

* **預設集型別**  — 這定義了可用的影像預設集型別，可以 **影像預設集** 或 **智慧型裁切**、和僅在以下情況下可用： [Dynamic Media功能](#dynamic-meida) 已啟用。
   * **影像預設集**  — 時間 **預設集型別** 之 **影像預設集** 已選取，下拉式選單 **影像預設集** 可使用，並允許從可用的Dynamic Media預設集中選擇。 只有在為選取的資產定義了預設集時，才能使用此選項。
   * **智慧型裁切**  — 時間 **預設集型別** 之 **智慧型裁切** 在下拉式選單中選取 **轉譯** 可使用，並允許從所選資產的可用轉譯中進行選擇。 這只有在為選取的資產定義了轉譯時才可用。
   * **影像修飾元**  — 您可在這裡定義其他Dynamic Media影像伺服命令，區隔為 `&`，無論哪一個 **預設集型別** 「 」已選取。
* **裝飾性影像**  — 檢查輔助技術是否應忽略影像，因此不需要替代文字。 這僅適用於裝飾性影像。
* **替代文字**  — 影像含義或功能的替代文字，適用於視障讀者。
   * **從DAM取得替代文字**  — 勾選後，影像的替代文字將會填入 `dc:description` dam中的中繼資料。
* **註解**  — 影像的其他相關資訊，預設會顯示於影像下方。
   * **從DAM取得圖片說明**  — 勾選後，影像的註解文字將會填入 `dc:title` dam中的中繼資料。
   * **以快顯視窗顯示註解**  — 檢查完畢後，註解不會顯示在影像下方，但如在某些瀏覽器中將滑鼠懸停在影像上，註解會以快顯模式顯示。
* **連結**  — 將影像連結至其他資源。
   * 使用選取對話方塊來連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非解決方案URL將解譯為相對於AEM。
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

>[!TIP]
>
>**智慧型裁切** 和 **影像預設集** 是互斥選項。 如果作者需要使用影像預設集以及智慧型裁切轉譯，該作者必須使用 **影像修飾元** 以手動新增預設集。

## 編輯對話方塊 {#edit-dialog}

內容作者可以使用「編輯」對話方塊裁切、修改啟動地圖及縮放影像。

>[!NOTE]
>
>裁切、旋轉和縮放功能不適用於Dynamic Media資產。 如果 [Dynamic Media功能](#dynamic-media) 已啟用，對Dynamic Media資產的任何這類編輯都應該透過 [設定對話方塊。](#configure-dialog)

![影像元件的「編輯」對話方塊](/help/assets/image-edit.png)

* 開始裁切

   ![開始裁切圖示](/help/assets/image-start-crop.png)

   選取此選項會開啟預先定義裁切比例的下拉式清單。

   * 選擇選項 **手繪** 以定義您自己的裁切。
   * 選擇選項 **移除裁切** 以顯示原始資產。

   選取裁切選項後，請使用藍色控點來調整影像上的裁切大小。

   ![裁切選項](/help/assets/image-crop-options.png)

* 向右旋轉

   ![向右旋轉圖示](/help/assets/image-rotate-right.png)

   使用此選項可將影像向右（順時針）旋轉90°。

* 水準翻轉

   ![水準翻轉圖示](/help/assets/image-flip-horizontal.png)

   使用此選項可水準翻轉影像或沿y軸將影像旋轉180°。

* 垂直翻轉

   ![垂直翻轉圖示](/help/assets/image-flip-vertical.png)

   使用此選項可垂直翻轉影像或沿x軸將影像旋轉180°。

* 重設縮放

   ![重設縮放圖示](/help/assets/image-reset-zoom.png)

   如果影像已經縮放，請使用此選項來重設縮放等級。

* 開啟縮放滑桿

   ![開啟縮放滑桿圖示](/help/assets/image-zoom.png)

   使用此選項可顯示控制影像縮放等級的滑桿。

   ![縮放滑桿控制項](/help/assets/image-zoom-slider.png)

就地編輯器也可用來修改影像。 由於空間限制，僅基本選項內嵌提供。 如需完整編輯選項，請使用全熒幕模式。

![影像就地編輯選項](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>GIF影像不支援影像編輯操作（裁切、翻轉、旋轉）。 在編輯模式下對GIF所做的任何此類變更都不會持續存在。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義內容作者在使用此元件時的裁切、上傳、輪換和上傳選項。

### 主要標籤 {#main-tab}

於 **主要** 索引標籤您可以定義影像的寬度（以畫素為單位），元件會根據瀏覽器大小自動載入最適合的寬度。 這是 [回應式功能](#responsive-features) 影像元件的。

此外，您可以定義在作者將元件新增至頁面時，會自動或停用哪些一般元件選項。

![影像元件的「設計」對話方塊主索引標籤](/help/assets/image-design-main-v2.png)

* **啟用DM功能**  — 選取時，啟用 [Dynamic Media功能](#dynamic-media) 可用。
* **啟用Web最佳化的影像**  — 若勾選， [網頁最佳化的影像傳遞服務](/help/developing/web-optimized-image-delivery.md) 將以WebP格式傳送影像，平均將影像大小減少25%。
   * 此選項僅適用於AEMaaCS。
   * 取消勾選或Web最佳化的影像傳送服務無法使用時， [最適化影像Servlet](/help/developing/adaptive-image-servlet.md) 已使用。
* **啟用延遲載入**  — 定義將影像元件新增至頁面時，是否自動啟用延遲載入選項。
* **裝飾性影像**  — 定義將影像元件新增至頁面時，是否自動啟用裝飾性影像選項。
* **從DAM取得替代文字** — 定義將影像元件新增至頁面時，是否自動啟用從DAM擷取替代文字的選項。
* **從DAM取得圖片說明**  — 定義將影像元件新增至頁面時，是否自動啟用從DAM擷取註解的選項。
* **以快顯視窗顯示註解**  — 定義將影像元件新增至頁面時，是否自動啟用以快顯視窗顯示影像註解的選項。
* **停用UUID追蹤**  — 勾選以停用影像資產的UUID追蹤。
* **寬度**  — 定義影像的寬度（以畫素為單位），元件會根據瀏覽器大小自動載入最適合的寬度。
   * 點選或按一下 **新增** 按鈕以新增其他大小。
      * 使用抓取控點來重新排列大小。
      * 使用 **刪除** 圖示可移除寬度。
   * 依預設，影像載入會延遲到它們變成可見為止。
      * 選取選項 **停用延遲載入** 以在頁面載入時載入影像。
* **JPEG品質**  — 轉換（例如縮放或裁切）的JPEG影像的品質因數（以從0到100的百分比表示）。

>[!TIP]
>
>檢視檔案 [最適化影像Servlet](#adaptive-image-servlet) 提供透過仔細定義寬度來最佳化轉譯選擇的秘訣。

### 功能標籤 {#features-tab}

於 **功能** 索引標籤您可以定義在使用元件時內容作者可用的選項，包括上傳選項、方向和裁切選項。

* 來源

   ![影像元件的「設計」對話方塊「功能」索引標籤](/help/assets/image-design-features-source.png)

   選取選項 **允許從檔案系統上傳資產** 允許內容作者從其本機電腦上傳影像。 若要強制內容作者僅從AEM中選取資產，請取消選取此選項。

* 方向

   ![影像元件的「設計」對話方塊「功能」索引標籤](/help/assets/image-design-features-orientation.png)

* **旋轉**
使用此選項可允許內容作者使用 
**向右旋轉** 選項。
* **翻轉**
使用此選項可允許內容作者使用 
**水準翻轉** 和 **垂直翻轉** 選項。

   >[!CAUTION]
   >
   >此 **翻轉** 選項預設為停用。 啟用時將會顯示 **垂直翻轉** 和 **水準翻轉** 按鈕，但AEM目前不支援此功能，且不會保留使用這些選項所做的任何變更。

* 裁切

   ![影像元件的「設計」對話方塊「功能」索引標籤](/help/assets/image-design-features-cropping.png)

   選取選項 **允許裁切** 讓內容作者在「編輯」對話方塊中裁切元件中的影像。
   * 按一下 **新增** 以新增預先定義的裁切外觀比例。
   * 輸入描述性名稱，該名稱將顯示在 **開始裁切** 下拉式清單。
   * 輸入外觀的數字比例。
   * 使用拖曳操作框來重新排列長寬比
   * 使用垃圾桶圖示可刪除長寬比。

   >[!CAUTION]
   >
   >請注意，在AEM中，裁切比例定義為 **高度/寬度**. 這與傳統的寬度/高度定義不同，這樣做是出於舊版相容性的原因。 只要您提供明確的比率名稱，內容作者就不會察覺到任何差異，因為該名稱顯示在UI中，而不是比率本身。

### 樣式索引標籤 {#styles-tab-1}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe使用者端資料層 {#data-layer}

影像元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
