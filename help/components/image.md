---
title: 影像元件
description: 核心元件影像元件是就地編輯的自適應影像元件功能。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 影像元件{#image-component}

核心元件影像元件是具就地編輯功能的自適應影像元件。

## 使用狀況 {#usage}

「影像元件」的功能包括最適化影像選擇和回應式行為，為頁面訪客提供延遲載入，以及為內容作者提供簡易的影像放置和裁切功能。

範本作者可在設計對話方塊中定義影像寬度、裁切和其他 [設定](#design-dialog)。 內容編輯器可以在「設定」對話方塊中上 [傳或選取資產](#configure-dialog) ，並在「編輯」對話方 [塊中裁切影像](#edit-dialog)。 為方便起見，酒店還提供簡單的就地修改影像。

## 自適應功能 {#responsive-features}

影像元件隨附強穩、立即可用的回應式功能。 在頁面範本層級，可 [以使用設計](#design-dialog) 對話方塊來定義影像資產的預設寬度。 然後影像元件會自動載入正確的寬度以根據瀏覽器視窗的大小顯示。 視窗調整大小時，影像元件會動態載入正確的影像大小。 由於影像元件已最佳化以載入您的內容，所以元件開發人員不需擔心定義自訂媒體查詢。

此外，影像元件支援延遲載入，將實際影像資產延遲載入，直到在瀏覽器中顯示為止，以提高頁面的回應速度。

## 版本與相容性 {#version-and-compatibility}

目前的影像元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM As a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 | 相容 |
| [v1](v1/image-v1.md) | 相容 | 相容 | 相容 | - |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](/help/versions.md)。

## SVG支援 {#svg-support}

影像元件支援可縮放向量圖形(SVG)。

* 支援從DAM拖放SVG資產，以及從本機檔案系統上傳SVG檔案。
* 最適化影像伺服器串流化原始SVG檔案（跳過轉換）。
* 對於SVG影像，「智慧影像」和「智慧尺寸」設定為影像模型中的空陣列。

### 安全性 {#security}

出於安全原因，影像編輯器不會直接呼叫原始SVG。 它叫穿了 `<img src=“path-to-component”>`。 這可防止瀏覽器執行嵌入在SVG檔案中的任何指令碼。

>[!CAUTION]
>
>SVG支援需要2.1.0版核心元件或更新版本，以及 [AEM 6.4的](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/sp-release-notes.html) service pack 2 [，或](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) AEM 6.3或更新版本的 [service pack 3](https://docs.adobe.com/content/help/en/experience-manager-64/developing/components/image-editor.html) ，以支援AEM中的新影像編輯器功能。

## 元件輸出示例 {#sample-component-output}

若要體驗影像元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](https://adobe.com/go/aem_cmp_library_image)。

### 技術詳細資訊 {#technical-details}

有關影像元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_image_v2)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。

>[!NOTE]
>
>自2.1.0版核心元件起，影像元件支援 [schema.org微資料](https://schema.org)。

## 配置對話框 {#configure-dialog}

除了標準的編輯 [對話框](#edit-dialog) 和設 [計對話框外](#design-dialog)，映像元件還提供配置對話框，其中定義了映像本身及其說明和基本屬性。

### 資產標籤 {#asset-tab}

![](/help/assets/screen_shot_2018-01-08at114245.png)

* **影像資產**
   * 從資產瀏覽器中 [拖放資產](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) ，或點選 **** 瀏覽選項，從本機檔案系統上傳。
   * 點選或按一 **下「清除** 」以取消選取目前選取的影像。
   * 點選或按一 **下「編輯** 」, [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 在資產編輯器中管理資產的轉譯。

### 中繼資料標籤 {#metadata-tab}

![](/help/assets/screen_shot_2018-01-08at114527.png)

* **影像是裝飾**&#x200B;性檢查影像是否應由輔助技術忽略，因此不需要替代文字。 這僅適用於裝飾性影像。
* **替代文**&#x200B;字：視障讀者可選擇影像的意義或功能。
   * 從DAM取得替代文字——勾選影像的替代文字時，會填入DAM中中繼資料 `dc:description` 的值。

* **Caption**（標題）影像的其他資訊，預設會顯示在影像下方。
   * **從DAM取得標**&#x200B;題勾選影像的標題文字時，會填入DAM中中繼資料 `dc:title` 的值。
   * **將標題顯示為快顯**：勾選時，標題不會顯示在影像下方，但是當將滑鼠暫留在影像上時，某些瀏覽器會顯示為快顯。

* **連結**
   * 將影像連結至其他資源。
   * 使用選取對話方塊連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非溶質URL將會解譯為相對於AEM。

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者裁切、修改啟動地圖，以及縮放影像。

![](/help/assets/chlimage_1-8.png)

* 開始裁切

   ![](/help/assets/chlimage_1-9.png)

   選取此選項會開啟預先定義的裁切比例的下拉式清單。

   * 選擇「自由手 **」選項** ，以定義您自己的裁切。
   * 選擇「移除裁 **切」選項** ，以顯示原始資產。
   選取裁切選項後，使用藍色控點來調整影像上的裁切大小。

   ![](/help/assets/chlimage_1-10.png)

* 向右旋轉

   ![](/help/assets/chlimage_1-11.png)

   使用此選項可將影像向右（順時針）旋轉90度。

* 水準翻轉

   ![](/help/assets/screen_shot_2018-04-16at091404.png)

   使用此選項可以水準翻轉影像，或沿y軸以180°的方式旋轉影像。

* 垂直翻轉

   ![](/help/assets/screen_shot_2018-04-16at091410.png)

   使用此選項可垂直翻轉影像，或沿x軸以180°旋轉影像。

* 啟動地圖

   >[!CAUTION]
   >
   >Launch map功能需要Core Components 2.1.0版或更高版本，以及 [AEM 6.4的](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/sp-release-notes.html) service pack 2 [，或](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) AEM 6.3或更高版本的 [Service Pack 3](https://docs.adobe.com/content/help/en/experience-manager-64/developing/components/image-editor.html) ，以支援AEM中的新影像編輯器功能。

   ![](/help/assets/chlimage_1-12.png)

   使用此選項可將啟動映射套用至影像。 選取此選項會開啟新視窗，讓使用者可選取地圖的形狀：

   * **新增矩形地圖**
   * **新增圓形圖**
   * **新增多邊形地圖**
      * 依預設會新增三角形地圖。 連按兩下形狀的一行，在新側面加入新的藍色調整大小控制點。
   一旦選擇了地圖形狀，該形狀被疊加在影像上以允許調整大小。 拖放藍色的調整大小控點，以調整形狀。

   ![](/help/assets/chlimage_1-13.png)

   調整啟動地圖大小後，按一下它以開啟浮動工具列，以定義連結的路徑。

   * **路徑**
      * 使用「路徑選擇器」選項，在AEM中選取路徑
      * 如果路徑不在AEM中，請使用絕對URL。 非絕對路徑會相對於AEM進行解譯。
   * **替代文本**&#x200B;路徑目標的替代說明
   * **目標**
      * **相同標籤**
      * **新標籤**
      * **父框架**
      * **上框架**
   點選或按一下要儲存的藍色核取標籤、要取消的黑色x，以及紅色垃圾桶來刪除地圖。

   ![](/help/assets/chlimage_1-14.png)

* 重設縮放

   ![](/help/assets/chlimage_1-15.png)

   如果影像已經縮放，請使用此選項來重設縮放等級。

* 開啟縮放滑桿

   ![](/help/assets/chlimage_1-16.png)

   使用此選項可顯示滑塊以控制影像的縮放級別。

   ![](/help/assets/chlimage_1-17.png)

就地編輯器也可用於修改影像。 由於空間限制，只有基本選項串聯可用。 如需完整編輯選項，請使用全螢幕模式。

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>GIF影像不支援影像編輯作業（裁切、翻轉、旋轉）。 在編輯模式下對GIF所做的任何此類更改都不會持續存在。

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者使用此元件時的裁切、上傳和旋轉及上傳選項。

### 主頁籤 {#main-tab}

在「主 **要** 」標籤上，您可以定義影像的寬度清單（以像素為單位），元件會根據瀏覽器大小自動載入最適當的寬度。 這是影像元件回應式功 [能的重](#responsive-features) 要部分。

此外，您可以定義作者將元件新增至頁面時，會自動或停用的一般元件選項。

![](/help/assets/screenshot_2018-10-19at102756.png)

* **啟用延遲載入**：在將影像元件新增至頁面時，定義是否自動啟用延遲載入選項。
* **影像是裝飾**&#x200B;性：在將影像元件新增至頁面時，定義裝飾性影像選項是否已自動啟用。
* **從DAM取得替代文字** Define（定義）在將影像元件新增至頁面時，是否自動啟用從DAM擷取替代文字的選項。
* **從DAM取得標題**&#x200B;在將影像元件新增至頁面時，是否自動啟用從DAM擷取標題的選項，請定義。
* **以快顯方式顯示標題**：在將影像元件新增至頁面時，定義是否自動啟用將影像標題顯示為快顯的選項。
* **停用UUID追蹤**&#x200B;檢查以停用影像資產的UUID追蹤。

* **Widths**&#x200B;定義影像的寬度清單（以像素為單位），元件會根據瀏覽器大小自動載入最適當的寬度。
   * 點選或按一下「 **新增** 」按鈕以新增其他大小。
      * 使用抓握手柄重新排列尺寸順序。
      * 使用「刪 **除** 」圖示移除寬度。
   * 依預設，影像載入會延遲至可見為止。
      * 選取「停用 **延遲載入** 」選項，以在頁面載入時載入影像。
* **JPEG品質**&#x200B;轉換（例如縮放或裁切）JPEG影像的品質因數（百分比為0和100）。

>[!CAUTION]
>
>自2.2.0版核心元件起，即可使用「JPEG品質」選項。

>[!NOTE]
>
>自核心元件2.2.0版起，影像元件會將唯一的UUID屬性新增至影像資產，以便追蹤並分析個別資產接收的檢視次數。 `data-asset-id`

### 功能標籤 {#features-tab}

在「功 **能** 」(Features)頁籤上，您可以定義使用元件時，內容作者可以使用哪些選項，包括上載選項、方向和裁切選項。

* 來源

   ![](/help/assets/chlimage_1-19.png)

   選取「允許 **從檔案系統上傳資產** 」選項，允許內容作者從其本機電腦上傳影像。 若要強制內容作者僅從AEM選取資產，請取消選取此選項。

* 方向

   ![](/help/assets/chlimage_1-20.png)

* **旋轉**：使用此選項可讓內容作者使用「向右旋轉 **」選項** 。
* **反向(** Flip)使用此選項可讓內容作者使用「水準翻轉」( **Flip Horizontally** )和「垂直 **翻轉」(Flip Predital** )選項。

   >[!CAUTION]
   >
   >預設情 **況下** ,「反向」(Flip)選項是禁用的。 啟用它會在影像元件的編輯對話方塊中顯示「垂直翻轉 ******** 」和「水準翻轉」按鈕，但AEM目前不支援此功能，而且使用這些選項所做的任何變更都不會持續存在。

* 裁切

   ![](/help/assets/chlimage_1-21.png)

   選取「允 **許裁切** 」選項，可讓內容作者在編輯對話方塊中裁切元件中的影像。
   * 按一 **下「新增** 」以新增預先定義的裁切外觀比例。
   * 輸入描述性名稱，此名稱將顯示在「開始裁 **切** 」下拉式清單中。
   * 輸入長寬的數值比。
   * 使用拖動控制滑塊重新排列長寬比順序
   * 使用垃圾桶圖示來刪除外觀比例。
   >[!CAUTION]
   >
   >請注意，在AEM中，裁切外觀比例會定義為 **高度／寬度**。 這與傳統的寬度／高度定義不同，而且是基於舊有相容性的原因。 只要您提供清楚的比率名稱，內容作者就不會察覺到任何差異，因為該名稱會顯示在UI中，而非比率本身。

### 樣式標籤 {#styles-tab-1}

影像元件支援AEM [Style系統](/help/get-started/authoring.md#component-styling)。

## 最適化影像伺服器 {#adaptive-image-servelet}

影像元件使用核心元件的自適應影像伺服器。 [Adaptive Image Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) 負責影像處理和流處理，開發人員可以利用它們對核心組 [件的自定義](/help/developing/customizing.md)。

>[!NOTE]
>
>Adaptive Image Servelet支 `Last-Modified` 援透過標題的條件式請求，但必須在Dispatcher中 `Last-Modified` 啟 [用標題的快取](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#caching-http-response-headers)。
>
>[AEM Project Archetype的範例Dispatcher組態已包含此組態。](/help/developing/archetype/overview.md)
