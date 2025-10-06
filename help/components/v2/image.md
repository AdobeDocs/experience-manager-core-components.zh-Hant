---
title: 影像元件 (v2)
description: 核心元件影像元件是具備就地編輯功能的最適化影像元件。
role: Architect, Developer, Admin, User
exl-id: 3f2b93f9-c48d-43ef-a78a-accd5090fe6f
index: n
source-git-commit: 3908828cf62043483a74e908204c3e9bf540300b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 影像元件 (v2) {#image-component}

「核心元件影像元件」是具備就地編輯功能的最適化影像元件。

## 用途 {#usage}

影像元件為頁面訪客提供最適化影像選擇和回應式行為並搭載延遲載入功能，而內容作者可輕鬆放置和裁切影像。

範本作者可以使用[設計對話框](#design-dialog)定義影像寬度、裁切和其他設定。內容編輯者可在[設定對話框](#configure-dialog)中上傳或選取資產，並在[編輯對話框](#edit-dialog)中裁切影像。為了增加便利性，也提供簡易的影像就地修改功能。

## 版本和相容性 {#version-and-compatibility}

本文件說明影像元件 v2，最初於 2018 年 1 月隨著核心元件 2.0.0 版發行導入。

>[!CAUTION]
>
>本文件說明影像元件 v1。
>
>如需影像元件目前版本的詳細資訊，請參閱[影像元件](/help/components/image.md)文件。

## 回應式功能 {#responsive-features}

「影像元件」提供可立即可用的強大回應式功能。在頁面範本層級，[設計對話框](#design-dialog)可用於定義影像資產的預設寬度。「影像元件」會自動載入正確的寬度，以根據瀏覽器視窗的大小來顯示。視窗調整大小時，「影像元件」會即時動態載入正確的影像大小。元件開發人員無需擔心自訂媒體查詢的定義方式，因為「影像元件」已針對內容載入進行最佳化。

此外，「影像元件」支援延遲載入，將實際影像資產的載入延遲到顯示在瀏覽器中為止，藉此提高頁面的回應能力。

>[!TIP]
>
>「影像元件」由「最適化影像 Servlet」提供支援。如需其運作方式的詳細資訊，請參閱[最適化影像 Servlet](/help/developing/adaptive-image-servlet.md) 文件。

## Dynamic Media 支援 {#dynamic-media}

影像元件 (截至 [2.13.0 版](/help/versions.md)) 支援 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=zh-hant#dynamicmedia) 資產。[啟用後，](#design-dialog)這些功能可讓您使用簡單的拖放功能，或透過資產瀏覽器，像處理任何其他影像一樣新增「Dynamic Media」影像資產。此外，同樣支援影像修飾元、影像預設集和智慧裁切。

使用「核心元件」建立的網頁體驗可包含豐富、Sensei 支援、穩定、高效能、跨平台的「Dynamic Media 影像」功能。

## SVG 支援 {#svg-support}

「影像元件」支援可縮放向量圖形 (SVG)。

* 支援從 DAM 拖放 SVG 資產以及上傳從本機檔案系統上傳的 SVG 檔案。
* 原始 SVG 檔案會串流處理 (略過轉換)。
* 對於 SVG 影像，「智慧型影像」和「智慧型大小」會設定為影像模型中的空白陣列。

### 安全性 {#security}

基於安全考量，「影像編輯器」絕對不會直接呼叫原始 SVG。而是透過 `<img src=“path-to-component”>` 呼叫。這可防止瀏覽器執行內嵌於 SVG 檔案中的任何指令碼。

## 範例元件輸出 {#sample-component-output}

若要體驗「影像元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_image_tw)」。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_image_v2_tw)有關影像元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

「影像元件」支援 [schema.org 結構化資料](https://schema.org)。

## 設定對話框 {#configure-dialog}

除了標準[編輯對話框](#edit-dialog)和[設計對話框](#design-dialog)之外，「影像元件」還提供設定對話框，其中定義影像本身及其說明和基本屬性。

### 資產索引標籤 {#asset-tab}

![影像元件設定對話框的資產索引標籤](/help/assets/image-configure-asset.png)

* **影像資產**
   * 從[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hant)拖曳資產，或點選&#x200B;**瀏覽**&#x200B;選項，以從本機檔案系統上傳。
   * 點選或按一下&#x200B;**「清除」**，取消選取目前選取的影像。
   * 點選或按一下&#x200B;**編輯**，以在 Asset Editor 中[管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=zh-Hant)。

### 後設資料索引標籤 {#metadata-tab}

![影像元件設定對話框的後設資料索引標籤](/help/assets/image-configure-metadata.png)

* **預設集類型** - 定義可用影像預設集的類型，可以是&#x200B;**影像預設集**&#x200B;或&#x200B;**智慧裁切**，而且僅在 [Dynamic Media 功能](#dynamic-meida)啟用時可用。
   * **影像預設集** - 當選取&#x200B;**影像預設集**&#x200B;的&#x200B;**預設集類型**&#x200B;時，**影像預設集**&#x200B;下拉式清單可供使用，並允許從可用的「Dynamic Media」預設集中選取。這只有在為選取的資產定義了預設集時才能使用。
   * **智慧裁切** - 當選取&#x200B;**智慧裁切**&#x200B;的&#x200B;**預設集類型**&#x200B;時，下拉式&#x200B;**轉譯**&#x200B;可供使用，並允許從所選資產的可用轉譯中選取。這只有在為選取的資產定義了轉譯時才能使用。
   * **影像修飾元** - 此處定義其他「Dynamic Media」影像命令，並以`&`分隔，無論選取哪個&#x200B;**預設集類型**&#x200B;均適用。
* **影像為裝飾性** - 若輔助技術可忽略該影像，因此不需要替代文字時，請勾選此選項。這僅適用於裝飾性影像。
* **替代文字** - 影像功能或含意的替代文字，以供有視覺障礙的讀者閱讀。
   * **從 DAM 取得替代文字** - 勾選後，影像的替代文字會以 DAM 中 `dc:description` 後設資料的值填入。
* **註解** - 影像的其他相關資訊，預設會顯示於影像下方。
   * **從 DAM 取得註解** - 勾選後，影像的註解文字會以 DAM 中 `dc:title` 後設資料的值填入。
   * **以快顯視窗顯示註解** - 勾選後，註解不會顯示在影像下方，但如在某些瀏覽器中將游標停留在影像上，註解會以快顯視窗顯示。
* **連結** - 將影像連結至其他資源。
   * 使用選取對話框可連結至其他 AEM 資源。
   * 如果未連結至 AEM 資源，請輸入絕對 URL。非絕對 URL 將解釋為相對於 AEM。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

>[!TIP]
>
>**智慧裁切**&#x200B;和&#x200B;**影像預設集**&#x200B;是互斥選項。如果作者必須使用影像預設集以及智慧裁切轉譯，則必須使用&#x200B;**影像修飾元**&#x200B;以手動新增預設集。

## 編輯對話框 {#edit-dialog}

此編輯對話框可讓內容作者裁切、修改啟動地圖及縮放影像。

>[!NOTE]
>
>裁切、旋轉和縮放功能不適用於 Dynamic Media 資產。如果已啟用 [Dynamic Media 功能](#dynamic-media)，對 Dynamic Media 資產的任何這類編輯都應該透過[設定對話框](#configure-dialog)執行。

![影像元件的編輯對話框](/help/assets/image-edit.png)

* 開始裁切

  ![開始裁切圖示](/help/assets/image-start-crop.png)

  選取此選項會開啟預先定義裁切比例的下拉式清單。

   * 選擇&#x200B;**手繪**&#x200B;選項來定義您自己的裁切。
   * 選擇&#x200B;**移除裁切**&#x200B;選項以顯示原始資產。

  選取裁切選項後，請使用藍色控點來調整影像上的裁切大小。

  ![裁切選項](/help/assets/image-crop-options.png)

* 向右旋轉

  ![向右旋轉圖示](/help/assets/image-rotate-right.png)

  使用此選項可將影像向右 (順時針) 旋轉 90°。

* 水平翻轉

  ![水平翻轉圖示](/help/assets/image-flip-horizontal.png)

  使用此選項可水平翻轉影像或沿 y 軸將影像旋轉 180°。

* 垂直翻轉

  ![垂直翻轉圖示](/help/assets/image-flip-vertical.png)

  使用此選項可垂直翻轉影像或沿 x 軸將影像旋轉 180°。

* 重設縮放

  ![重設縮放圖示](/help/assets/image-reset-zoom.png)

  如果影像已經縮放，請使用此選項來重設縮放等級。

* 開啟縮放滑桿

  ![開啟縮放滑桿圖示](/help/assets/image-zoom.png)

  使用此選項可顯示控制影像縮放等級的滑桿。

  ![縮放滑桿控制](/help/assets/image-zoom-slider.png)

就地編輯器也可用於修改影像。由於空間限制，僅基本選項內嵌。如需完整的編輯選項，請使用全螢幕模式。

![影像就地編輯選項](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>不支援 GIF 影像的影像編輯操作 (裁切、翻轉、旋轉)。在編輯模式下對 GIF 所做的任何此類變更將不會保留。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義內容作者使用此元件時所具備的裁切、上傳、以及旋轉與上傳選項。

### 主要索引標籤 {#main-tab}

在&#x200B;**主要**&#x200B;索引標籤上，您可以定義影像的寬度 (以像素為單位) 清單，元件會根據瀏覽器大小自動載入最適當的寬度。這是「影像元件」[回應式功能](#responsive-features)的重要部分。

此外，您可以定義在作者將元件新增至頁面時，要自動啟用或停用哪些一般元件選項。

![影像元件的設計對話框主要索引標籤](/help/assets/image-design-main-v2.png)

* **啟用 DM 功能** - 勾選後，即可啟用 [Dynamic Media 功能](#dynamic-media)。
* **啟用網頁最佳化影像** - 勾選後，[網頁最佳化影像傳遞服務](/help/developing/web-optimized-image-delivery.md)會以 WebP 格式傳送影像，平均將影像大小減少 25%。
   * 此選項僅在 AEMaaCS 中可用。
   * 取消勾選或無法使用網頁最佳化影像傳遞服務時，會使用[最適化影像 Servlet](/help/developing/adaptive-image-servlet.md)。
* **啟用延遲載入** - 定義在將影像元件新增至頁面時，是否自動啟用延遲載入選項。
* **影像為裝飾性** - 定義將影像元件新增至頁面時，是否自動啟用裝飾性影像選項。
* **從 DAM 取得替代文字** - 定義在將影像元件新增至頁面時，是否自動啟用從 DAM 擷取替代文字的選項。
* **從 DAM 取得註解** - 定義在將影像元件新增至頁面時，是否自動啟用從 DAM 擷取註解的選項。
* **以快顯視窗顯示註解** - 定義將影像元件新增至頁面時，是否自動啟用以快顯視窗顯示影像註解的選項。
* **停用 UUID 追蹤** - 勾選以停用影像資產的 UUID 追蹤。
* **寬度** - 定義影像的寬度 (以像素為單位) 清單，元件會根據瀏覽器大小自動載入最適當的寬度。
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增其他大小。
      * 使用抓取控點，以重新排列大小順序。
      * 使用&#x200B;**刪除**&#x200B;圖示來移除寬度。
   * 根據預設，影像載入會延遲到影像可見為止。
      * 選取&#x200B;**停用延遲載入**&#x200B;選項，以便在頁面載入時載入影像。
* **JPEG 品質** - 轉換後 (例如縮放或裁切) 的 JPEG 影像品質係數 (以 0 到 100 的百分比表示)。

>[!TIP]
>
>請參閱[最適化影像 Servlet](/help/developing/adaptive-image-servlet.md) 文件，瞭解如何透過仔細定義寬度來最佳化轉譯選擇的秘訣。

### 功能索引標籤 {#features-tab}

在&#x200B;**功能**&#x200B;索引標籤上，您可以定義內容作者在使用元件時可用的選項，包括上傳選項、方向以及裁切選項。

* 來源

  ![影像元件的設計對話框功能索引標籤](/help/assets/image-design-features-source.png)

  選取&#x200B;**允許從檔案系統上傳資產**&#x200B;選項，以允許內容作者從其本機電腦上傳影像。若要強制內容作者僅從 AEM 中選取資產，請取消選取此選項。

* 方向

  ![影像元件的設計對話框功能索引標籤](/help/assets/image-design-features-orientation.png)

* **旋轉**
使用此選項可允許內容作者使用&#x200B;**向右旋轉**&#x200B;選項。
* **翻轉**
使用此選項可允許內容作者使用&#x200B;**水平翻轉**&#x200B;和&#x200B;**垂直翻轉**&#x200B;選項。

  >[!CAUTION]
  >
  >**翻轉**&#x200B;選項預設為停用。啟用此選項會在影像元件的編輯對話框中顯示&#x200B;**垂直翻轉**&#x200B;和&#x200B;**水平翻轉**&#x200B;按鈕，但 AEM 目前不支援此功能，因此不會保留使用這些選項所做的任何變更。

* 裁切

  ![影像元件的設計對話框功能索引標籤](/help/assets/image-design-features-cropping.png)

  選取&#x200B;**允許裁切**&#x200B;選項以允許內容作者在編輯對話框中裁切元件中的影像。
   * 按一下&#x200B;**新增**&#x200B;以新增預先定義的裁切外觀比例。
   * 輸入描述性名稱，此名稱將顯示在&#x200B;**開始裁切**&#x200B;下拉式清單中。
   * 輸入外觀的數字比例。
   * 使用拖曳控點來重新排列外觀比例
   * 使用垃圾桶圖示可刪除外觀比例。

  >[!CAUTION]
  >
  >請注意，在 AEM 中，裁切外觀比例定義為&#x200B;**高度/寬度**。這和寬度/高度比的傳統定義不同，主要是為了維持與舊版系統的相容性。只要您提供明確的比例名稱，內容作者就不會察覺任何差異，因為該名稱會顯示在 UI 中，而非比例本身。

### 樣式索引標籤 {#styles-tab-1}

影像元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「影像元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
