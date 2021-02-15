---
title: 影像元件
description: 核心元件影像元件是就地編輯的自適應影像元件功能。
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '2170'
ht-degree: 1%

---


# 影像元件{#image-component}

核心元件影像元件是具就地編輯功能的自適應影像元件。

## 使用狀況 {#usage}

「影像元件」的功能包括最適化影像選擇和回應式行為，為頁面訪客提供延遲載入，以及為內容作者提供簡易的影像放置和裁切功能。

範本作者可在[設計對話方塊](#design-dialog)中定義影像寬度以及裁切和其他設定。 內容編輯器可以在[configure dialog](#configure-dialog)中上傳或選擇資產，並在[編輯對話框](#edit-dialog)中裁切影像。 為方便起見，酒店還提供簡單的就地修改影像。

## 自適應功能{#responsive-features}

影像元件隨附強穩、立即可用的回應式功能。 在頁面範本層級，[設計對話方塊](#design-dialog)可用來定義影像資產的預設寬度。 然後影像元件會自動載入正確的寬度以根據瀏覽器視窗的大小顯示。 視窗調整大小時，影像元件會動態載入正確的影像大小。 由於影像元件已最佳化以載入您的內容，所以元件開發人員不需擔心定義自訂媒體查詢。

此外，影像元件支援延遲載入，以延遲實際影像資產的載入，直到在瀏覽器中顯示為止，提高頁面的回應速度。

## 動態媒體支援{#dynamic-media}

影像元件（從[版本2.13.0](/help/versions.md)開始）支援[動態媒體](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=en#dynamicmedia)資產。 [啟用後，](#design-dialog) 這些功能可讓您以簡單的拖放方式或透過資產瀏覽器，新增動態媒體影像資產，就像新增任何其他影像一樣。此外，還支援影像修飾元、影像預設集和智慧裁切。

您使用核心元件建立的網頁體驗無法提供豐富、Sensei支援、強穩、高效能、跨平台的動態媒體影像功能。

## 版本和相容性{#version-and-compatibility}

目前的影像元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](v1/image-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## SVG支援{#svg-support}

影像元件支援可縮放向量圖形(SVG)。

* 支援從DAM拖放SVG資產，以及從本機檔案系統上傳SVG檔案。
* 將原始SVG檔案流化的自適應影像Servlet流（跳過轉換）。
* 對於SVG影像，「智慧影像」和「智慧尺寸」設定為影像模型中的空陣列。

### 安全性 {#security}

出於安全原因，影像編輯器不會直接呼叫原始SVG。 它通過`<img src=“path-to-component”>`調用。 這可防止瀏覽器執行嵌入在SVG檔案中的任何指令碼。

>[!CAUTION]
>
>SVG支援需要AEM 6.4或更高版本的核心元件版本2.1.0及[service pack 2](https://docs.adobe.com/content/help/zh-Hant/experience-manager-64/release-notes/sp-release-notes.html)，以支援AEM中的[影像編輯器功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/image-editor.html)。

## 元件輸出示例{#sample-component-output}

若要體驗影像元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_image)。

### 技術詳細資訊{#technical-details}

有關映像元件[的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_image_v2)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

映像元件支援[schema.org microdata](https://schema.org)。

## 配置對話框{#configure-dialog}

除了標準的[編輯對話框](#edit-dialog)和[設計對話框](#design-dialog)外，影像元件還提供了配置對話框，其中定義了影像本身及其說明和基本屬性。

### 資產標籤{#asset-tab}

![「映像元件」的「配置」對話框的「資產」頁籤](/help/assets/image-configure-asset.png)

* **影像資產**
   * 從[資產瀏覽器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)拖放資產，或點選&#x200B;**browse**&#x200B;選項，從本機檔案系統上傳。
   * 點選或按一下&#x200B;**Clear**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下「編輯&#x200B;****」，在資產編輯器中管理資產](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)的轉譯。[

### 中繼資料標籤{#metadata-tab}

![影像元件設定對話方塊的中繼資料索引標籤](/help/assets/image-configure-metadata.png)

* **預設類型** -這定義了可用的影像預設類型( **Image** Presetor  **Smart Crop**)，並且僅在啟用動態媒體功能時 [](#dynamic-meida) 才可用。
   * **影像預設集** -選取「預設 **的** 影像 **預設集」時，下拉式清單會提供「影像預設集」，允許從可用的「動態媒體」預設集**  **** 中進行選取。只有為所選資產定義了預設集時，才可使用此選項。
   * **智慧型裁切** -選取「 **Preset** Typeof  **Smart**  **** Cropis」時，下拉式清單「重新定義」可供使用，允許從所選資產的可用轉譯中選取。只有在為所選資產定義轉譯時，才可使用此功能。
   * **影像修飾元** -您可在此處以分隔方式定義其他動態媒體影像伺服指令，不論 `&`選取的是 **哪個** 預設類型。
* **影像是裝飾性** -檢查協助技術是否應忽略影像，因此不需要替代文字。這僅適用於裝飾性影像。
* **替代文字** -視障讀者，影像意義或功能的文字替代文字。
   * **從DAM取得替代文字** -勾選影像的替代文字時，會填入DAM中中繼資 `dc:description` 料的值。
* **標題** -影像的其他相關資訊，預設顯示在影像下方。
   * **從DAM取得標題** -勾選影像的標題文字時，將會填入DAM中中繼資 `dc:title` 料的值。
   * **以快顯方式顯示標題** -勾選後，標題不會顯示在影像下方，但是當將滑鼠暫留在影像上時，某些瀏覽器會顯示為快顯。
* **連結** -將影像連結至其他資源。
   * 使用選取對話方塊連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非溶質URL將會解譯為相對於AEM。
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

>[!TIP]
>
>**智慧型** Crop和影 **像預** 設集是互斥的選項。如果作者需要使用影像預設集和智慧型裁切轉譯，則作者必須使用&#x200B;**影像修飾元**&#x200B;來手動新增預設集。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者裁切、修改啟動地圖，以及縮放影像。

>[!NOTE]
>
>裁切、旋轉和縮放功能不適用於動態媒體資產。 如果[動態媒體功能](#dynamic-media)已啟用，則應透過[設定對話方塊，執行對動態媒體資產的任何此類編輯。](#configure-dialog)

![影像元件的編輯對話方塊](/help/assets/image-edit.png)

* 開始裁切

   ![開始裁切圖示](/help/assets/image-start-crop.png)

   選取此選項會開啟預先定義的裁切比例的下拉式清單。

   * 選擇「Free Hand」（自由手）選項&#x200B;**以定義您自己的裁切。**
   * 選擇「移除裁切」選項&#x200B;**以顯示原始資產。**

   選取裁切選項後，使用藍色控點來調整影像上的裁切大小。

   ![裁切選項](/help/assets/image-crop-options.png)

* 向右旋轉

   ![向右旋轉圖示](/help/assets/image-rotate-right.png)

   使用此選項可將影像向右（順時針）旋轉90度。

* 水準翻轉

   ![水準翻轉圖示](/help/assets/image-flip-horizontal.png)

   使用此選項可以水準翻轉影像，或沿y軸以180°的方式旋轉影像。

* 垂直翻轉

   ![垂直翻轉圖示](/help/assets/image-flip-vertical.png)

   使用此選項可垂直翻轉影像，或沿x軸以180°旋轉影像。

* 重設縮放

   ![重設縮放圖示](/help/assets/image-reset-zoom.png)

   如果影像已經縮放，請使用此選項來重設縮放等級。

* 開啟縮放滑桿

   ![開啟縮放滑桿圖示](/help/assets/image-zoom.png)

   使用此選項可顯示滑塊以控制影像的縮放級別。

   ![縮放滑桿控制](/help/assets/image-zoom-slider.png)

就地編輯器也可用於修改影像。 由於空間限制，只有基本選項串聯可用。 如需完整編輯選項，請使用全螢幕模式。

![影像就地編輯選項](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>GIF影像不支援影像編輯作業（裁切、翻轉、旋轉）。 在編輯模式下對GIF所做的任何此類更改都不會持續存在。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義內容作者使用此元件時的裁切、上傳和旋轉及上傳選項。

### 主頁籤{#main-tab}

在&#x200B;**Main**&#x200B;標籤上，您可以定義影像的寬度清單（以像素為單位），元件會根據瀏覽器大小自動載入最適當的寬度。 這是影像元件[回應式功能](#responsive-features)的重要部分。

此外，您可以定義作者將元件新增至頁面時，會自動或停用的一般元件選項。

![「影像元件」的設計對話框主頁籤](/help/assets/image-design-main.png)

* **啟用DM功能** -勾選後，即可使用啟 [用的](#dynamic-media) 動態媒體功能。
* **啟用延遲載入** -定義將影像元件新增至頁面時，是否自動啟用延遲載入選項。
* **影像是裝飾** -定義在將影像元件新增至頁面時是否自動啟用裝飾影像選項。
* **從DAM取得替代文字**-定義在將影像元件新增至頁面時，是否自動啟用從DAM擷取替代文字的選項。
* **從DAM取得標題** -定義在將影像元件新增至頁面時，是否自動啟用從DAM擷取標題的選項。
* **將標題顯示為彈出式選項** -定義將影像元件新增至頁面時，是否自動啟用將影像標題顯示為彈出式選項。
* **停用UUID追蹤** -檢查以停用影像資產的UUID追蹤。
* **Widths**  —— 定義影像的寬度清單（以像素為單位），元件會根據瀏覽器大小自動載入最適當的寬度。
   * 點選或按一下「新增&#x200B;****」按鈕以新增其他大小。
      * 使用抓握手柄重新排列尺寸順序。
      * 使用&#x200B;**Delete**&#x200B;圖示移除寬度。
   * 依預設，影像載入會延遲至可見為止。
      * 選取「停用延遲載入&#x200B;**」選項，以在頁面載入時載入影像。**
* **JPEG品質** -轉換（例如縮放或裁切）JPEG影像的品質因數（百分比為0和100）。

### 功能標籤{#features-tab}

在&#x200B;**功能**&#x200B;標籤上，您可以定義當使用元件時，內容作者可使用哪些選項，包括上傳選項、方向和裁切選項。

* 來源

   ![「影像元件」的「設計」對話框的「功能」頁籤](/help/assets/image-design-features-source.png)

   選取「允許資產從檔案系統上傳」選項&#x200B;**，允許內容作者從本機電腦上傳影像。**&#x200B;若要強制內容作者僅從AEM選取資產，請取消選取此選項。

* 方向

   ![「影像元件」的「設計」對話框的「功能」頁籤](/help/assets/image-design-features-orientation.png)

* **旋**
轉使用此選項可讓內容作者使用 
**旋轉** 右鍵。
* **反向(**
Flip)使用此選項可讓內容作者使用 
**「水準** 翻轉」和「垂直 **翻** 轉」選項。

   >[!CAUTION]
   >
   >預設情況下，**Flip**&#x200B;選項被禁用。 啟用此功能後，會在影像元件的編輯對話方塊中顯示&#x200B;**垂直翻轉**&#x200B;和&#x200B;**水準翻轉**&#x200B;按鈕，但AEM目前不支援此功能，而且使用這些選項所做的任何變更都不會持續存在。

* 裁切

   ![「影像元件」的「設計」對話框的「功能」頁籤](/help/assets/image-design-features-cropping.png)

   選擇「允許裁切」選項&#x200B;**，允許內容作者在編輯對話框的元件中裁切影像。**
   * 按一下&#x200B;**添加**&#x200B;添加預定義的裁切外觀比例。
   * 輸入描述性名稱，該名稱將顯示在&#x200B;**開始裁切**&#x200B;下拉式清單中。
   * 輸入長寬的數值比。
   * 使用拖動控制滑塊重新排列長寬比順序
   * 使用垃圾桶圖示來刪除外觀比例。

   >[!CAUTION]
   >
   >請注意，在AEM中，裁切長寬比的定義為&#x200B;**height/width**。 這與傳統的寬度／高度定義不同，而且是基於舊有相容性的原因。 只要您提供清楚的比率名稱，內容作者就不會察覺到任何差異，因為該名稱會顯示在UI中，而非比率本身。

### 樣式標籤{#styles-tab-1}

影像元件支援AEM [Style System](/help/get-started/authoring.md#component-styling)。

## 最適化影像Servlet {#adaptive-image-servlet}

映像元件使用核心元件的自適應映像Servlet。 [Adaptive Image ](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) Servlets負責影像處理和流處理，可供開發人員在其核心元件 [定制中使用](/help/developing/customizing.md)。

>[!NOTE]
>
>通過`Last-Modified`標頭的條件請求受Adaptive Image Servlet支援，但`Last-Modified`標頭[的快取需要在Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#caching-http-response-headers)中啟用。
>
>[AEM Project Archetype的範例Dispatcher組態已包含此組態。](/help/developing/archetype/overview.md)

## Adobe用戶端資料層{#data-layer}

影像元件支援[Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
