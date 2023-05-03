---
title: 影像元件(v2)
description: 核心元件影像元件是就地編輯的自適應影像元件功能。
role: Architect, Developer, Admin, User
exl-id: 3f2b93f9-c48d-43ef-a78a-accd5090fe6f
source-git-commit: 6c251cd03997dca8961b31498c6f5de3cfdc3793
workflow-type: tm+mt
source-wordcount: '2073'
ht-degree: 0%

---

# 影像元件(v2) {#image-component}

核心元件影像元件是具有就地編輯功能的自適應影像元件。

## 使用狀況 {#usage}

「影像元件」提供適用性的影像選取及具有延遲載入的回應式行為給頁面訪客，以及為內容作者輕鬆放置影像和裁切影像。

影像寬度以及裁切和其他設定可由範本作者在 [設計對話](#design-dialog). 內容編輯器可以上傳或選取 [配置對話框](#configure-dialog) 並裁切 [編輯對話框](#edit-dialog). 為了更方便，還可以簡單地就地修改影像。

## 版本與相容性 {#version-and-compatibility}

本檔案說明2018年1月核心元件2.0.0版推出的影像元件v2。

>[!CAUTION]
>
>本檔案說明影像元件的v1。
>
>如需目前版本影像元件的詳細資訊，請參閱 [影像元件](/help/components/image.md) 檔案。

## 回應式功能 {#responsive-features}

影像元件隨附立即可用的強大回應式功能。 在頁面範本層級， [設計對話](#design-dialog) 可用來定義影像資產的預設寬度。 影像元件會根據瀏覽器視窗的大小自動載入顯示的正確寬度。 視窗調整大小時，影像元件會動態載入正確的影像大小。 元件開發人員無需擔心定義自訂媒體查詢，因為影像元件已最佳化以載入您的內容。

此外，影像元件支援延遲載入，將實際影像資產的載入延遲到在瀏覽器中顯示為止，以提高頁面的回應速度。

>[!TIP]
>
>影像元件由最適化影像Servlet提供技術支援。 請查看該文檔 [適用性影像Servlet](#adaptive-image-servlet) 以取得運作方式的詳細資訊。

## Dynamic Media支援 {#dynamic-media}

影像元件(截至 [版本2.13.0](/help/versions.md))支援 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=en#dynamicmedia) 資產。 [啟用後，](#design-dialog) 這些功能可讓您透過簡單的拖放功能，或透過「資產」瀏覽器，新增Dynamic Media影像資產，如同其他影像一樣。 此外，還支援影像修飾元、影像預設集和智慧型裁切。

以核心元件建置的網頁體驗無法提供Sensei所提供的豐富、強大、高效能、跨平台的Dynamic Media影像功能。

## SVG支援 {#svg-support}

影像元件支援可縮放向量圖形(SVG)。

* 從DAM拖放SVG資產，以及從本機檔案系統上傳SVG檔案均受支援。
* 原始SVG檔案流化（跳過轉換）。
* 對於SVG影像，「智慧影像」和「智慧大小」設為影像模型中的空陣列。

### 安全性 {#security}

基於安全考量，影像編輯器絕不會直接呼叫原始SVG。 它被調用 `<img src=“path-to-component”>`. 這會防止瀏覽器執行任何內嵌在SVG檔案中的指令碼。

## 範例元件輸出 {#sample-component-output}

若要體驗影像元件，並查看其設定選項、HTML和JSON輸出的範例，請造訪 [元件庫](https://adobe.com/go/aem_cmp_library_image).

### 技術詳細資訊 {#technical-details}

影像元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_image_v2).

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

影像元件支援 [schema.org microdata](https://schema.org).

## 配置對話框 {#configure-dialog}

除了 [編輯對話框](#edit-dialog) 和 [設計對話](#design-dialog)，影像元件會提供設定對話方塊，定義影像本身及其說明和基本屬性。

### 資產標籤 {#asset-tab}

![影像元件設定對話方塊的資產標籤](/help/assets/image-configure-asset.png)

* **影像資產**
   * 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點選 **瀏覽** 從本機檔案系統上傳的選項。
   * 點選或按一下 **清除** 以取消選取目前選取的影像。
   * 點選或按一下 **編輯** to [管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 在資產編輯器中。

### 中繼資料索引標籤 {#metadata-tab}

![影像元件的配置對話框的元資料頁簽](/help/assets/image-configure-metadata.png)

* **預設類型**  — 這會定義可用的影像預設集類型， **影像預設集** 或 **智慧型裁切**，和僅適用於 [Dynamic Media功能](#dynamic-meida) 的URL區段。
   * **影像預設集**  — 何時 **預設類型** of **影像預設集** ，則下拉式清單中的 **影像預設集** 可用，允許從可用的Dynamic Media預設集中選取。 只有為選取的資產定義了預設集時，才可使用此功能。
   * **智慧型裁切**  — 何時 **預設類型** of **智慧型裁切** 已選取下拉式清單 **轉譯** 可用，允許從所選資產的可用轉譯中選取。 只有為選取的資產定義轉譯時，才可使用此功能。
   * **影像修飾元**  — 可在此處定義其他Dynamic Media影像伺服命令，依 `&`，無論 **預設類型** 中所有規則的URL。
* **影像是裝飾**  — 檢查輔助技術是否應忽略影像，因此不需要替代文字。 這僅適用於裝飾影像。
* **替代文字** 視障讀者的影像含義或功能的文本替代。
   * **從DAM取得替代文字**  — 若勾選此選項，影像的替代文字將會填入 `dc:description` DAM中的中繼資料。
* **註解**  — 影像的其他資訊，預設顯示在影像下方。
   * **從DAM取得註解**  — 若勾選此選項，影像的註解文字將會填入 `dc:title` DAM中的中繼資料。
   * **將標題顯示為快顯視窗**  — 若勾選此選項，註解不會顯示在影像下方，但會在將游標暫留在影像上時，以某些瀏覽器顯示的快顯視窗顯示。
* **連結**  — 將影像連結至其他資源。
   * 使用選取對話方塊連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非溶質URL會解譯為相對於AEM。
* **ID**  — 此選項可控制HTML中和 [資料層](/help/developing/data-layer/overview.md).
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

>[!TIP]
>
>**智慧型裁切** 和 **影像預設集** 是互斥的選項。 如果作者需要使用影像預設集和智慧型裁切轉譯，則作者必須使用 **影像修飾元** 來手動添加預設集。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者裁切、修改啟動對映，以及縮放影像。

>[!NOTE]
>
>裁切、旋轉和縮放功能不適用於Dynamic Media資產。 若 [Dynamic Media功能](#dynamic-media) 啟用後，應透過Dynamic Media資產執行任何此類編輯 [配置對話框。](#configure-dialog)

![影像元件的編輯對話方塊](/help/assets/image-edit.png)

* 開始裁切

   ![開始裁切圖示](/help/assets/image-start-crop.png)

   選取此選項會開啟預先定義的裁切比例的下拉式清單。

   * 選擇選項 **自由手** 來定義自己的裁切。
   * 選擇選項 **移除裁切** 來顯示原始資產。

   選取裁切選項後，使用藍色控點來調整影像上裁切的大小。

   ![裁切選項](/help/assets/image-crop-options.png)

* 向右旋轉

   ![右旋圖示](/help/assets/image-rotate-right.png)

   使用此選項將影像90°向右（順時針）旋轉。

* 水準翻轉

   ![水準翻轉圖示](/help/assets/image-flip-horizontal.png)

   使用此選項可以水準翻轉影像，或沿Y軸旋轉影像180°。

* 垂直翻轉

   ![垂直翻轉圖示](/help/assets/image-flip-vertical.png)

   使用此選項可垂直翻轉影像或沿x軸旋轉影像180°。

* 重設縮放

   ![重設縮放圖示](/help/assets/image-reset-zoom.png)

   如果影像已縮放，則使用此選項來重設縮放等級。

* 開啟縮放滑桿

   ![開啟縮放滑桿圖示](/help/assets/image-zoom.png)

   使用此選項可顯示滑塊以控制影像的縮放級別。

   ![縮放滑桿控制項](/help/assets/image-zoom-slider.png)

就地編輯器也可用來修改影像。 由於空間限制，只有基本選項可在內使用。 如需完整編輯選項，請使用全螢幕模式。

![影像就地編輯選項](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>影像編輯操作（裁切、翻轉、旋轉）不支援GIF影像。 在編輯模式中對GIF所做的任何此類變更都不會持續存在。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者使用此元件時擁有的裁切、上傳、旋轉和上傳選項。

### 主要標籤 {#main-tab}

在 **主要** 索引標籤，您可以為影像定義寬度清單（以像素為單位），元件會根據瀏覽器大小自動載入最適當的寬度。 這是 [回應式功能](#responsive-features) 的下限。

此外，您可以定義當作者將元件新增至頁面時，會自動或停用的一般元件選項。

![影像元件的設計對話方塊主索引標籤](/help/assets/image-design-main-v2.png)

* **啟用DM功能**  — 勾選後，啟用 [Dynamic Media功能](#dynamic-media) 的URL區段。
* **啟用Web優化映像**  — 若勾選， [網頁最佳化的影像傳送服務](/help/developing/web-optimized-image-delivery.md) 會以WebP格式傳送影像，平均將影像大小減少25%。
   * 此選項僅適用於AEMaaCS。
   * 取消勾選或網頁最佳化影像傳送服務無法使用時， [適用性影像Servlet](/help/developing/adaptive-image-servlet.md) 中所有規則的URL區段。
* **啟用延遲載入**  — 定義將影像元件新增至頁面時，延遲載入選項是否自動啟用。
* **影像是裝飾**  — 定義將影像元件新增至頁面時是否自動啟用裝飾影像選項。
* **從DAM取得替代文字** — 定義將影像元件新增至頁面時，從DAM擷取替代文字的選項是否自動啟用。
* **從DAM取得註解**  — 定義將影像元件新增至頁面時，從DAM擷取註解的選項是否自動啟用。
* **將標題顯示為快顯視窗**  — 定義將影像元件新增至頁面時，將影像標題顯示為快顯視窗的選項是否自動啟用。
* **停用UUID追蹤功能**  — 勾選「 」以停用影像資產UUID的追蹤功能。
* **寬度**  — 以像素定義影像的寬度清單，元件會根據瀏覽器大小自動載入最適當的寬度。
   * 點選或按一下 **新增** 按鈕以添加其他大小。
      * 使用抓握手柄重新排列大小的順序。
      * 使用 **刪除** 表徵圖以移除寬度。
   * 依預設，載入影像會延遲，直到變成可見為止。
      * 選取選項 **停用延遲載入** 以在頁面載入時載入影像。
* **JPEG品質**  — 已轉換（例如縮放或裁切）JPEG影像的品質因數（百分比為0和100）。

>[!TIP]
>
>請參閱檔案 [適用性影像Servlet](#adaptive-image-servlet) 請參閱謹慎定義寬度以最佳化轉譯選取的秘訣。

### 功能標籤 {#features-tab}

在 **功能** 索引標籤，您可以定義使用元件時，內容作者可使用的選項，包括上傳選項、方向和裁切選項。

* 來源

   ![「影像元件的設計」對話框「功能」頁簽](/help/assets/image-design-features-source.png)

   選取選項 **允許從檔案系統上傳資產** 允許內容作者從其本機電腦上傳影像。 若要強制內容作者僅從AEM選取資產，請取消選取此選項。

* 方向

   ![「影像元件的設計」對話框「功能」頁簽](/help/assets/image-design-features-orientation.png)

* **旋轉**
使用此選項可允許內容作者使用 
**向右旋轉** 選項。
* **翻轉**
使用此選項可允許內容作者使用 
**水準翻轉** 和 **垂直翻轉** 選項。

   >[!CAUTION]
   >
   >此 **翻轉** 選項預設為停用。 啟用後，將顯示 **垂直翻轉** 和 **水準翻轉** 按鈕，但AEM目前不支援此功能，且使用這些選項所做的任何變更將無法持續存在。

* 裁切

   ![「影像元件的設計」對話框「功能」頁簽](/help/assets/image-design-features-cropping.png)

   選取選項 **允許裁切** 允許內容作者在編輯對話方塊中裁切元件中的影像。
   * 按一下 **新增** 來新增預先定義的裁切外觀比例。
   * 輸入描述性名稱，該名稱將顯示在 **開始裁切** 下拉式清單。
   * 輸入外觀的數值比。
   * 使用拖動控制滑塊重新排列縱橫比的順序
   * 使用垃圾桶圖示來刪除外觀比例。

   >[!CAUTION]
   >
   >請注意，在AEM中，裁切外觀比率定義為 **高度/寬度**. 這與傳統的寬度/高度定義不同，因為舊版相容性原因而完成。 只要您提供比例的明確名稱，內容作者就不會察覺任何差異，因為該名稱會顯示在UI中，而非比例本身。

### 樣式標籤 {#styles-tab-1}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe用戶端資料層 {#data-layer}

影像元件支援 [Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
