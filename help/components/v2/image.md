---
title: 影像元件(v2)
description: 核心元件影像元件是自適應影像元件特徵就地編輯。
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: tm+mt
source-wordcount: '2228'
ht-degree: 0%

---


# 影像元件(v2) {#image-component}

核心元件影像元件是具有就地編輯功能的自適應影像元件。

## 使用狀況 {#usage}

影像元件具有自適應影像選擇和響應行為，對頁面訪問者具有延遲載入以及對內容作者易於影像放置和裁剪。

影像寬度以及裁剪和附加設定可由模板作者在 [設計對話框](#design-dialog)。 內容編輯器可以在 [配置對話框](#configure-dialog) 並在 [編輯對話框](#edit-dialog)。 為了更方便，還提供了影像的簡單就地修改。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了2018年1月隨核心元件2.0.0版而推出的影像元件v2。

>[!CAUTION]
>
>本文檔介紹「影像元件」的v1。
>
>有關當前版本的映像元件的詳細資訊，請參閱 [影像元件](/help/components/image.md) 的子菜單。

## 響應功能 {#responsive-features}

影像元件具有強大的響應功能，即可開箱即用。 在頁面模板級別， [設計對話框](#design-dialog) 可用於定義影像資產的預設寬度。 然後，影像元件將自動載入正確的寬度以根據瀏覽器窗口的大小進行顯示。 在調整窗口大小時，影像元件會動態載入正確的影像大小。 由於映像元件已優化以載入您的內容，因此元件開發人員無需擔心定義自定義媒體查詢。

此外，映像元件支援延遲載入，以延遲實際映像資產的載入，直到其在瀏覽器中可見為止，從而提高頁面的響應能力。

>[!TIP]
>
>請參閱一節 [自適應影像Servlet](#adaptive-image-servlet) 有關這些功能的更多技術詳細資訊，以及優化格式副本選擇的提示。

## Dynamic Media支援 {#dynamic-media}

影像元件(截至 [發行版2.13.0](/help/versions.md))支援 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=en#dynamicmedia) 資產。 [啟用後，](#design-dialog) 這些功能提供了通過簡單的拖放功能或通過資產瀏覽器添加Dynamic Media映像資產的功能，就像您添加任何其他映像一樣。 此外，還支援影像修飾符、影像預設和智慧作物。

您使用核心元件構建的Web體驗不能提供豐富、Sensei支援、強健、高效能、跨平台的Dynamic Media映像功能。

## SVG支援 {#svg-support}

影像元件支援可縮放向量圖形(SVG)。

* 支援從DAM拖放SVG資產和從本地檔案系統上載SVG檔案。
* 將流化原始SVG檔案的Adaptive Image Servlet流（跳過轉換）。
* 對於SVG影像，「智慧影像」和「智慧大小」被設定為影像模型中的空陣列。

### 安全性 {#security}

出於安全原因，影像編輯器從未直接調用原始SVG。 它被調用 `<img src=“path-to-component”>`。 這會阻止瀏覽器執行嵌入在SVG檔案中的任何指令碼。

>[!CAUTION]
>
>SVG支援要求2.1.0版或更高版本的核心元件以及 [服務包2](https://experienceleague.adobe.com/docs/experience-manager-64/release-notes/sp-release-notes.html?lang=zh-Hant) 支援AEM6.4或更高版本 [影像編輯器功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/components-templates/image-editor.html) 內AEM。

## 元件輸出示例 {#sample-component-output}

要體驗映像元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_image)。

### 技術詳細資訊 {#technical-details}

有關映像元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_image_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

映像元件支援 [schema.org微資料](https://schema.org)。

## 配置對話框 {#configure-dialog}

除了 [編輯對話框](#edit-dialog) 和 [設計對話框](#design-dialog)，影像元件提供一個配置對話框，其中定義了影像本身及其說明和基本屬性。

### 資產標籤 {#asset-tab}

![「映像元件的配置」對話框的「資產」頁籤](/help/assets/image-configure-asset.png)

* **影像資產**
   * 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點擊 **瀏覽** 從本地檔案系統上載。
   * 點擊或按一下 **清除** 來取消選擇當前選定的映像。
   * 點擊或按一下 **編輯** 至 [管理資產的格式副本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 的子菜單。

### 元資料頁籤 {#metadata-tab}

![映像元件的配置對話框的元資料頁籤](/help/assets/image-configure-metadata.png)

* **預設類型**  — 這定義了可用影像預設的類型 **影像預設** 或 **智慧裁剪**，且僅在 [Dynamic Media特徵](#dynamic-meida) 的子菜單。
   * **影像預設**  — 時間 **預設類型** 共 **影像預設** 下拉框 **影像預設** 可用，允許從可用的Dynamic Media預設中進行選擇。 僅當為所選資產定義預設時，才可用。
   * **智慧裁剪**  — 時間 **預設類型** 共 **智慧裁剪** 已選擇下拉 **格式副本** 可用，允許從選定資產的可用格式副本中進行選擇。 僅當為所選資產定義格式副本時，才可使用此選項。
   * **影像修飾符**  — 此處可以分隔其他Dynamic Media影像服務命令 `&`，無論 **預設類型** 的子菜單。
* **影像是裝飾性的**  — 檢查影像是否應被輔助技術忽略，因此不需要替代文本。 這僅適用於裝飾性影像。
* **備選文本**  — 視障讀者對影像含義或功能的文字選擇。
   * **從DAM獲取替代文本**  — 選中後，影像的替代文本將填充 `dc:description` 元資料。
* **標題**  — 影像的其他資訊，預設顯示在影像下方。
   * **從DAM獲取標題**  — 選中後，將使用 `dc:title` 元資料。
   * **將標題顯示為彈出窗口**  — 選中後，標題不會顯示在影像下方，而是當懸停在影像上方時，由某些瀏覽器顯示的彈出窗口。
* **連結**  — 將映像連結到其他資源。
   * 使用選擇對話框連結到另AEM一資源。
   * 如果未連結到AEM資源，請輸入絕對URL。 非溶質URL將被解釋為相對於AEM。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

>[!TIP]
>
>**智慧裁剪** 和 **影像預設** 是相互排斥的選項。 如果作者需要使用影像預設和Smart Crop格式副本，則作者將必須使用 **影像修飾符** 來手動添加預設。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者裁剪、修改啟動映射和縮放影像。

>[!NOTE]
>
>裁剪、旋轉和縮放功能不適用於Dynamic Media資產。 如果 [Dynamic Media特徵](#dynamic-media) 啟用，任何此類對Dynamic Media資產的編輯都應通過 [配置對話框。](#configure-dialog)

![影像元件的編輯對話框](/help/assets/image-edit.png)

* 開始裁剪

   ![「開始裁剪」表徵圖](/help/assets/image-start-crop.png)

   選擇此選項將開啟預定義裁剪比例的下拉框。

   * 選擇選項 **自由手** 來定義自己的作物。
   * 選擇選項 **刪除裁剪** 顯示原始資產。

   選擇裁剪選項後，使用藍色手柄來調整影像上的裁剪大小。

   ![裁剪選項](/help/assets/image-crop-options.png)

* 向右旋轉

   ![向右旋轉表徵圖](/help/assets/image-rotate-right.png)

   使用此選項將影像向右（順時針）旋轉90°。

* 水準翻轉

   ![水準翻轉表徵圖](/help/assets/image-flip-horizontal.png)

   使用此選項可水準翻轉影像或沿y軸旋轉180°影像。

* 垂直翻轉

   ![垂直翻轉表徵圖](/help/assets/image-flip-vertical.png)

   使用此選項可垂直翻轉影像或沿x軸旋轉180°影像。

* 重設縮放

   ![重置縮放表徵圖](/help/assets/image-reset-zoom.png)

   如果影像已縮放，則使用此選項重置縮放級別。

* 開啟縮放滑塊

   ![開啟縮放滑塊表徵圖](/help/assets/image-zoom.png)

   使用此選項可顯示滑塊以控制影像的縮放級別。

   ![縮放滑塊控制項](/help/assets/image-zoom-slider.png)

就地編輯器也可用於修改影像。 由於空間限制，只有基本選項可線上使用。 對於完全編輯選項，請使用全屏模式。

![影像就地編輯選項](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>GIF影像不支援影像編輯操作（裁剪、翻轉、旋轉）。 在編輯模式下對GIF所做的任何此類更改都不會保留。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者在使用此元件時具有的裁剪、上載和旋轉及上載選項。

### 主頁籤 {#main-tab}

在 **主** 頁籤，您可以定義影像的寬度清單（以像素為單位），元件將根據瀏覽器大小自動載入最合適的寬度。 這是 [響應特徵](#responsive-features) 表徵圖。

此外，當作者將元件添加到頁面時，還可以定義自動或禁用哪些常規元件選項。

![「影像元件」的設計對話框主頁籤](/help/assets/image-design-main.png)

* **啟用DM功能**  — 選中後，啟用 [Dynamic Media特徵](#dynamic-media) 的雙曲餘切值。
* **啟用延遲載入**  — 定義在將影像元件添加到頁面時是否自動啟用延遲載入選項。
* **影像是裝飾性的**  — 定義在將影像元件添加到頁面時是否自動啟用裝飾影像選項。
* **從DAM獲取替代文本** — 定義在將影像元件添加到頁面時是否自動啟用從DAM檢索替代文本的選項。
* **從DAM獲取標題**  — 定義在將影像元件添加到頁面時是否自動啟用從DAM檢索標題的選項。
* **將標題顯示為彈出窗口**  — 定義在將影像元件添加到頁面時是否自動啟用將影像標題顯示為彈出窗口的選項。
* **禁用UUID跟蹤**  — 選中以禁用對映像資產的UUID的跟蹤。
* **寬度**  — 定義影像的寬度清單（以像素為單位），元件根據瀏覽器大小自動載入最合適的寬度。
   * 點擊或按一下 **添加** 按鈕以添加其他大小。
      * 使用抓握手柄重新排列大小的順序。
      * 使用 **刪除** 表徵圖以刪除寬度。
   * 預設情況下，將延遲載入影像，直到其可見。
      * 選擇選項 **禁用延遲載入** 在載入頁面時載入影像。
* **JPEG質量**  — 變換（例如縮放或裁切）JPEG影像的質量系數（以百分比表示，從0到100）。

>[!TIP]
>
>請參閱一節 [自適應影像Servlet](#adaptive-image-servlet) 有關其功能的更多技術詳細資訊，以及通過仔細定義寬度來優化格式副本選擇的提示。

### 功能頁籤 {#features-tab}

在 **功能** 頁籤，您可以定義在使用元件（包括上載選項、方向和裁剪選項）時內容作者可以使用的選項。

* 來源

   ![「影像元件」的「設計」對話框的「特徵」頁籤](/help/assets/image-design-features-source.png)

   選擇選項 **允許從檔案系統上載資產** 允許內容作者從本地電腦上傳影像。 要強制內容作者僅從中選擇資AEM產，請取消選擇此選項。

* 方向

   ![「影像元件」的「設計」對話框的「特徵」頁籤](/help/assets/image-design-features-orientation.png)

* **旋轉**
使用此選項允許內容作者使用 
**向右旋轉** 的雙曲餘切值。
* **翻轉**
使用此選項允許內容作者使用 
**水準翻轉** 和 **垂直翻轉** 頁籤

   >[!CAUTION]
   >
   >的 **翻轉** 選項。 啟用它將顯示 **垂直翻轉** 和 **水準翻轉** 影像元件的「編輯」對話框中的按鈕，但當前不支援該功能AEM，並且不會保留使用這些選項所做的任何更改。

* 裁切

   ![「影像元件」的「設計」對話框的「特徵」頁籤](/help/assets/image-design-features-cropping.png)

   選擇選項 **允許裁剪** 允許內容作者在「編輯」對話框的元件中裁剪影像。
   * 按一下 **添加** 添加預定義的裁剪縱橫比。
   * 輸入描述性名稱，該名稱將在 **開始裁剪** 下拉清單。
   * 輸入縱橫比。
   * 使用拖動手柄重新排列長寬比的順序
   * 使用垃圾桶表徵圖刪除縱橫比。

   >[!CAUTION]
   >
   >請注意，AEM在中，裁剪縱橫比定義為 **高度/寬度**。 這不同於傳統的寬度/高度定義，是出於傳統相容性原因。 只要您提供比率的明確名稱，內容作者就不會察覺到任何差異，因為該名稱顯示在UI中，而不是比率本身。

### 樣式頁籤 {#styles-tab-1}

映像元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## 自適應影像Servlet {#adaptive-image-servlet}

影像元件使用核心元件的自適應影像Servlet。 [自適應映像Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) 負責影像處理和流式處理，開發人員可以利用 [核心元件的自定義](/help/developing/customizing.md)。

### 優化格式副本選擇 {#optimizing-rendition-selection}

Adaptive Image Servlet將嘗試根據請求的影像大小和類型選擇最佳格式副本。 建議同步定義DAM格式副本和影像元件允許的寬度，以便Adaptive Image Servlet盡可能少地處理。

這將提高效能，並避免某些影像無法被底層影像處理庫正確處理。

>[!NOTE]
>
>通過 `Last-Modified` 頭由Adaptive Image Servlet支援，但快取的 `Last-Modified` 標題 [需要在Dispatcher中啟用](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#caching-http-response-headers)。
>
>[項AEM目原型](/help/developing/archetype/overview.md)的Dispatcher配置示例已包含此配置。

## Adobe客戶端資料層 {#data-layer}

映像元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
