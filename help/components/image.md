---
title: 影像元件
description: 核心元件影像元件是自適應影像元件特徵就地編輯。
role: Architect, Developer, Admin, User
exl-id: c5e57f4b-139f-40e7-8d79-be9a74360b63
source-git-commit: 1a02aea6cda2bb1f70ab97d7a439e2c8e64add52
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# 影像元件{#image-component}

核心元件影像元件是具有就地編輯功能的自適應影像元件。

## 使用狀況 {#usage}

影像元件具有自適應影像選擇和響應行為，對頁面訪問者具有延遲載入以及對內容作者易於影像放置和裁剪。

影像寬度和附加設定可由模板作者在 [設計對話框](#design-dialog)。 內容編輯器可以在 [配置對話框。](#configure-dialog)

## 版本和相容性 {#version-and-compatibility}

當前版本的映像元件是v3，該版本於2022年2月隨核心元件2.18.0版一起推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v3 | - | 相容 | 相容 |
| [v2](v2/image.md) | 相容 | 相容 | 相容 |
| [v1](v1/image-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 響應功能 {#responsive-features}

影像元件具有強大的響應功能，即可開箱即用。 在頁面模板級別， [設計對話框](#design-dialog) 可用於定義影像資產的預設寬度。 然後，影像元件將自動載入正確的寬度以根據瀏覽器窗口的大小進行顯示。 在調整窗口大小時，影像元件會動態載入正確的影像大小。 由於映像元件已優化以載入您的內容，因此元件開發人員無需擔心定義自定義媒體查詢。

此外，映像元件支援延遲載入，以延遲實際映像資產的載入，直到其在瀏覽器中可見為止，從而提高頁面的響應能力。

>[!TIP]
>
>請參閱一節 [自適應影像Servlet](#adaptive-image-servlet) 有關這些功能的更多技術詳細資訊，以及優化格式副本選擇的提示。

## Dynamic Media支援 {#dynamic-media}

影像元件(截至 [發行版2.13.0](/help/versions.md))支援 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html#dynamicmedia) 資產。 [啟用後，](#design-dialog) 這些功能提供了通過簡單的拖放功能或通過資產瀏覽器添加Dynamic Media映像資產的功能，就像您添加任何其他映像一樣。 此外，還支援影像修飾符、影像預設和智慧作物。

您使用核心元件構建的Web體驗不能提供豐富、Sensei支援、強健、高效能、跨平台的Dynamic Media映像功能。

## SVG支援 {#svg-support}

影像元件支援可縮放向量圖形(SVG)。

* 支援從DAM拖放SVG資產和從本地檔案系統上載SVG檔案。
* 將流化原始SVG檔案的Adaptive Image Servlet流（跳過轉換）。
* 對於SVG影像，「智慧影像」和「智慧大小」被設定為影像模型中的空陣列。

### 安全性 {#security}

出於安全原因，影像編輯器從未直接調用原始SVG。 它被調用 `<img src=“path-to-component”>`。 這會阻止瀏覽器執行嵌入在SVG檔案中的任何指令碼。

>[!NOTE]
>
>SVG支援要求2.1.0版或更高版本的核心元件以及 [服務包2](https://experienceleague.adobe.com/docs/experience-manager-64/release-notes/sp-release-notes.html?lang=zh-Hant) 支援AEM6.4或更高版本 [影像編輯器功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/image-editor.html) 內AEM。

## 元件輸出示例 {#sample-component-output}

要體驗映像元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_image)。

### 技術詳細資訊 {#technical-details}

有關映像元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_image_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

映像元件支援 [schema.org微資料](https://schema.org)。

## 配置對話框 {#configure-dialog}

影像元件提供了一個配置對話框，在該對話框中定義了影像本身及其說明和基本屬性。

### 資產標籤 {#asset-tab}

![「映像元件的配置」對話框的「資產」頁籤](/help/assets/image-configure-asset.png)

* **從頁面繼承特色影像**  — 此選項使用 [連結頁面的特色影像](page.md) 或當前頁面的特色影像。

* **輔助工具的備選文本**  — 此欄位允許您為視力受損的用戶定義影像描述。

   * **從頁面繼承備選文本**  — 此選項使用連結資產值的替代說明 `dc:description` DAM中的元資料，或當前頁的元資料（如果未連結任何資產）。

* **影像資產**
   * 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點擊 **瀏覽** 從本地檔案系統上載。
   * 點擊或按一下 **清除** 來取消選擇當前選定的映像。
   * 點擊或按一下 **編輯** 至 [管理資產的格式副本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 的子菜單。

* **不提供替代文本**  — 此選項標籤要被螢幕閱讀器等輔助技術忽略的影像，在這些情況下，影像純粹是裝飾性的，或者沒有向頁面傳送其他資訊。

### 元資料頁籤 {#metadata-tab}

![映像元件的配置對話框的元資料頁籤](/help/assets/image-configure-metadata.png)

* **預設類型**  — 這定義了可用影像預設的類型 **影像預設** 或 **智慧裁剪**，且僅在 [Dynamic Media特徵](#dynamic-meida) 的子菜單。
   * **影像預設**  — 時間 **預設類型** 共 **影像預設** 下拉框 **影像預設** 可用，允許從可用的Dynamic Media預設中進行選擇。 僅當為所選資產定義預設時，才可用。
   * **智慧裁剪**  — 時間 **預設類型** 共 **智慧裁剪** 已選擇下拉 **格式副本** 可用，允許從選定資產的可用格式副本中進行選擇。 僅當為所選資產定義格式副本時，才可使用此選項。
   * **影像修飾符**  — 此處可以分隔其他Dynamic Media影像服務命令 `&`，無論 **預設類型** 的子菜單。
* **標題**  — 影像的其他資訊，預設顯示在影像下方。
   * **從DAM獲取標題**  — 選中後，將使用 `dc:title` 元資料。
   * **將標題顯示為彈出窗口**  — 選中後，標題不會顯示在影像下方，而是當懸停在影像上方時，由某些瀏覽器顯示的彈出窗口。
* **連結**  — 將映像連結到其他資源。
   * 使用選擇對話框連結到另AEM一資源。
   * 如果未連結到AEM資源，請輸入絕對URL。 非溶質URL將被解釋為相對於AEM。
   * **在新頁籤中開啟連結**  — 此選項在新瀏覽器窗口中開啟連結。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

>[!TIP]
>
>**智慧裁剪** 和 **影像預設** 是相互排斥的選項。 如果作者需要使用影像預設和Smart Crop格式副本，則作者將必須使用 **影像修飾符** 來手動添加預設。

### 樣式頁籤 {#styles-tab-edit}

![「影像元件」的「編輯」對話框的「樣式」頁籤](/help/assets/image-configure-styles.png)

映像元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便下拉菜單可用。

## 設計對話框 {#design-dialog}

![「影像元件」的設計對話框主頁籤](/help/assets/image-design-main.png)

* **啟用DM功能**  — 選中後， [Dynamic Media特徵](#dynamic-media) 的雙曲餘切值。
   * 僅當在環境中啟用Dynamic Media時，才顯示此選項。
* **禁用延遲載入**  — 選中後，元件將預載入所有影像，而不會延遲載入。
* **影像是裝飾性的**  — 定義在將影像元件添加到頁面時是否自動啟用裝飾影像選項。
* **從DAM獲取替代文本** — 定義在將影像元件添加到頁面時是否自動啟用從DAM檢索替代文本的選項。
* **從DAM獲取標題**  — 定義在將影像元件添加到頁面時是否自動啟用從DAM檢索標題的選項。
* **將標題顯示為彈出窗口**  — 定義在將影像元件添加到頁面時是否自動啟用將影像標題顯示為彈出窗口的選項。
* **調整寬度**  — 此值用於調整DAM資產基礎影像的寬度。
   * 將保留影像的長寬比。
   * 如果該值大於影像的實際寬度，則此值將無效。
   * 此值對SVG影像沒有影響。

您可以為影像定義寬度清單（以像素為單位），元件將根據瀏覽器大小自動載入最合適的寬度。 這是 [響應特徵](#responsive-features) 表徵圖。

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

### 樣式頁籤 {#styles-tab}

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
