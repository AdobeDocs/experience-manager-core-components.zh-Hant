---
title: 電子郵件映像元件
description: 電子郵件影像元件是具有就地編輯功能的自適應影像元件。
role: Architect, Developer, Admin, User
exl-id: f5d40047-3082-4edd-a5f6-6ab3e33997f9
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 0%

---


# 電子郵件映像元件 {#email-image-component}

電子郵件影像元件是具有就地編輯功能的自適應影像元件。

## 使用狀況 {#usage}

電子郵件影像元件具有自適應影像選擇和響應行為，對頁面訪問者具有延遲載入功能，並且為內容作者提供了易於拖放的影像放置和配置。

* 影像寬度和附加設定可由模板作者在 [設計對話框。](#design-dialog)
* 內容編輯器可以在 [配置對話框。](#configure-dialog)

## 版本和相容性 {#version-and-compatibility}

電子郵件映像元件的當前版本是v1，該版本於2022年10月隨電子郵件核心元件的第x版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [電子郵件核心元件版本](/help/email/versions.md)。

## 響應功能 {#responsive-features}

電子郵件映像元件具有強大的響應功能，即可開箱即用。 在頁面模板級別， [設計對話框](#design-dialog) 可用於定義影像資產的預設寬度。 然後，電子郵件影像元件將自動載入正確的寬度以根據瀏覽器窗口的大小顯示。 在調整窗口大小時，電子郵件影像元件會動態載入正確的影像大小。 由於電子郵件映像元件已優化以載入您的內容，因此元件開發人員無需擔心定義自定義媒體查詢。

此外，電子郵件映像元件支援延遲載入，以推遲實際映像資產的載入，直到其在瀏覽器中可見為止，從而提高內容的響應能力。

>[!TIP]
>
>預設情況下，電子郵件映像元件由Adaptive Image Servlet提供電源。 請參閱文檔 [自適應影像Servlet](#adaptive-image-servlet) 詳細瞭解它的工作原理。

## Dynamic Media支援 {#dynamic-media}

電子郵件映像元件支援 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html#dynamicmedia) 資產。 [啟用後，](#design-dialog) 這些功能提供了通過簡單的拖放功能或通過資產瀏覽器添加Dynamic Media映像資產的功能，就像您添加任何其他映像一樣。 此外，還支援影像修飾符、影像預設和智慧作物。

您使用電子郵件核心元件構建的電子郵件體驗可以具備豐富、Sensei支援、強健、高效能、跨平台的Dynamic Media映像功能。

## SVG支援 {#svg-support}

電子郵件影像元件支援可縮放向量圖形(SVG)。

* 支援從DAM拖放SVG資產和從本地檔案系統上載SVG檔案。
* 原始SVG檔案被流式傳輸（跳過轉換）。
* 對於SVG影像，「智慧影像」和「智慧大小」被設定為影像模型中的空陣列。

### 安全性 {#security}

出於安全原因，影像編輯器從未直接調用原始SVG。 它被調用 `<img src=“path-to-component”>`。 這會阻止瀏覽器執行嵌入在SVG檔案中的任何指令碼。

### 技術詳細資訊 {#technical-details}

有關電子郵件映像元件的最新技術文檔 [中。](https://adobe.com/go/aem_cmp_tech_email_image_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔。](/help/developing/overview.md)

映像元件支援 [schema.org微資料。](https://schema.org)

## 配置對話框 {#configure-dialog}

電子郵件映像元件提供了一個配置對話框，在該對話框中定義映像本身及其說明和基本屬性。

### 資產標籤 {#asset-tab}

![「電子郵件映像元件」的「配置」對話框的「資產」頁籤](/help/email/assets/email-image-configure-asset.png)

* **從頁面繼承特色影像**  — 此選項使用 [連結頁面的特色影像](page.md) 或當前頁面的特色影像。

* **輔助工具的備選文本**  — 此欄位允許您為視力受損的用戶定義影像描述。

   * **從頁面繼承備選文本**  — 此選項使用連結資產值的替代說明 `dc:description` DAM中的元資料，或當前頁的元資料（如果未連結任何資產）。

* **影像資產**
   * 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點擊 **瀏覽** 從本地檔案系統上載。
   * 點擊或按一下 **清除** 來取消選擇當前選定的映像。
   * 點擊或按一下 **編輯** 至 [管理資產的格式副本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 的子菜單。

* **不提供替代文本**  — 此選項標籤要被螢幕閱讀器等輔助技術忽略的影像，在這些情況下，影像純粹是裝飾性的，或者沒有向頁面傳送其他資訊。

* **禁用延遲載入**  — 此選項預載所有映像元件，而不根據需要載入。

### 元資料頁籤 {#metadata-tab}

![映像元件的配置對話框的元資料頁籤](/help/email/assets/email-image-configure-metadata.png)

* **預設類型**  — 這定義了可用影像預設的類型 **影像預設** 或 **智慧裁剪**，且僅在 [Dynamic Media特徵](#dynamic-meida) 的子菜單。
   * **影像預設**  — 時間 **預設類型** 共 **影像預設** 的 **影像預設** 可用，允許從可用的Dynamic Media預設中進行選擇。 僅當為所選資產定義預設時，才可用。
   * **智慧裁剪**  — 時間 **預設類型** 共 **智慧裁剪** 已選擇 **格式副本** 可用，允許從選定資產的可用格式副本中進行選擇。 僅當為所選資產定義格式副本時，才可使用此選項。
   * **影像修飾符**  — 此處可以分隔其他Dynamic Media影像服務命令 `&`，無論 **預設類型** 的子菜單。
* **標題**  — 影像的其他資訊，預設顯示在影像下方。
   * **從DAM獲取標題**  — 選中後，將使用 `dc:title` 元資料。 僅當從DAM中選擇資產時才可用。
   * **將標題顯示為彈出窗口**  — 選中後，標題不會顯示在影像下方，而是當懸停在影像上方時，由某些瀏覽器顯示的彈出窗口。
* **連結**  — 將映像連結到其他資源。
   * 使用選擇對話框連結到另AEM一資源。
   * 如果未連結到AEM資源，請輸入絕對URL。 非溶質URL將被解釋為相對於AEM。
   * **在新頁籤中開啟連結**  — 此選項在新瀏覽器窗口中開啟連結。
* **ID**  — 此選項允許控制HTML中元件的唯一標識符。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS。
* **已修復**  — 此選項定義影像的寬度（以像素為單位）。
* **將影像縮放到可用寬度**  — 此選項適用 `"width":"100%"` 的子菜單。

>[!TIP]
>
>**智慧裁剪** 和 **影像預設** 是相互排斥的選項。 如果作者需要使用影像預設和Smart Crop格式副本，則作者將必須使用 **影像修飾符** 來手動添加預設。

### 樣式頁籤 {#styles-tab-edit}

![電子郵件影像元件的編輯對話框的「樣式」頁籤](/help/assets/image-configure-styles.png)

電子郵件映像元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便該頁籤可用。

## 設計對話框 {#design-dialog}

### 主頁籤 {#main-tab}

![「影像元件」的設計對話框主頁籤](/help/email/assets/email-image-design-main.png)

* **啟用DM功能**  — 選中後， [Dynamic Media特徵](#dynamic-media) 的雙曲餘切值。
   * 僅當在環境中啟用Dynamic Media時，才顯示此選項。
* **啟用Web優化映像**  — 選中後， [Web優化的影像傳遞服務](/help/developing/web-optimized-image-delivery.md) 將以WebP格式提供影像，平均將影像大小減少25%。
   * 此選項僅在AEMaCS中可用。
   * 當未選中或Web優化映像交付服務不可用時， [自適應影像Servlet](/help/developing/adaptive-image-servlet.md) 的子菜單。
* **影像是裝飾性的**  — 定義在將影像元件添加到頁面時是否自動啟用裝飾影像選項。
* **從DAM獲取替代文本** — 定義在將影像元件添加到頁面時是否自動啟用從DAM檢索替代文本的選項。
* **從DAM獲取標題**  — 定義在將影像元件添加到頁面時是否自動啟用從DAM檢索標題的選項。
* **將標題顯示為彈出窗口**  — 定義在將影像元件添加到頁面時是否自動啟用將影像標題顯示為彈出窗口的選項。
* **調整寬度**  — 此值用於調整DAM資產基礎影像的寬度。
   * 將保留影像的長寬比。
   * 如果該值大於影像的實際寬度，則此值將無效。
   * 此值對SVG影像沒有影響。

您可以為影像定義寬度清單（以像素為單位），元件將根據瀏覽器大小自動載入最合適的寬度。 這是 [響應特徵](#responsive-features) 的子菜單。

* **寬度**  — 定義影像的寬度清單（以像素為單位），元件根據瀏覽器大小自動載入最合適的寬度。
   * 點擊或按一下 **添加** 按鈕以添加其他大小。
      * 使用抓取手柄重新排列大小的順序。
      * 使用 **刪除** 表徵圖以刪除寬度。
   * 預設情況下，將延遲載入影像，直到其可見。
      * 選擇選項 **禁用延遲載入** 在載入頁面時載入影像。
* **JPEG質量**  — 變換（例如縮放或裁切）JPEG影像的質量系數（以百分比表示，從0到100）。
* **預設寬度**  — 將在設計對話框中使用的影像的預設寬度（像素）

>[!TIP]
>
>查看文檔 [自適應影像Servlet](/help/developing/adaptive-image-servlet.md) 用於通過仔細定義寬度來優化格式副本選擇的提示。

### 樣式頁籤 {#styles-tab}

電子郵件映像元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
