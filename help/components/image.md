---
title: 影像元件
description: 核心元件影像元件是就地編輯的自適應影像元件功能。
role: Architect, Developer, Admin, User
exl-id: c5e57f4b-139f-40e7-8d79-be9a74360b63
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '2170'
ht-degree: 1%

---

# 影像元件{#image-component}

核心元件影像元件是具有就地編輯功能的自適應影像元件。

## 使用狀況 {#usage}

「影像元件」提供適用性的影像選取及具有延遲載入的回應式行為給頁面訪客，以及為內容作者輕鬆放置影像和裁切影像。

範本作者可在[設計對話方塊](#design-dialog)中定義影像寬度以及裁切和其他設定。 內容編輯器可以上傳或選取[設定對話方塊](#configure-dialog)中的資產，並在[編輯對話方塊](#edit-dialog)中裁切影像。 為了更方便，還可以簡單地就地修改影像。

## 回應式功能 {#responsive-features}

影像元件隨附立即可用的強大回應式功能。 在頁面範本層級，可使用[設計對話方塊](#design-dialog)定義影像資產的預設寬度。 影像元件會根據瀏覽器視窗的大小自動載入顯示的正確寬度。 視窗調整大小時，影像元件會動態載入正確的影像大小。 元件開發人員無需擔心定義自訂媒體查詢，因為影像元件已最佳化以載入您的內容。

此外，影像元件支援延遲載入，將實際影像資產的載入延遲到在瀏覽器中顯示為止，以提高頁面的回應速度。

## Dynamic Media支援 {#dynamic-media}

影像元件(自[發行版本2.13.0](/help/versions.md)起)支援[Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=en#dynamicmedia)資產。 [啟用後，](#design-dialog) 這些功能可讓您透過簡單的拖放功能，或透過資產瀏覽器，新增Dynamic Media影像資產，就像新增任何其他影像一樣。此外，還支援影像修飾元、影像預設集和智慧型裁切。

以核心元件建置的網路體驗無法提供豐富、由Sensei提供支援、強大、高效能、跨平台的Dynamic Media影像功能。

## 版本與相容性 {#version-and-compatibility}

目前的影像元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](v1/image-v1.md) | 相容 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## SVG支援 {#svg-support}

影像元件支援可縮放向量圖形(SVG)。

* 支援從DAM拖放SVG資產，以及從本機檔案系統上傳SVG檔案。
* 最適化影像Servlet流流式處理原始SVG檔案（跳過轉換）。
* 對於SVG影像，「智慧影像」和「智慧大小」設定為影像模型中的空陣列。

### 安全性 {#security}

基於安全考量，影像編輯器絕不會直接呼叫原始SVG。 會透過`<img src=“path-to-component”>`呼叫。 這會防止瀏覽器執行SVG檔案中內嵌的任何指令碼。

>[!CAUTION]
>
>SVG支援需要2.1.0版或更新版本的核心元件，以及適用於AEM 6.4或更高版本的[service pack 2](https://docs.adobe.com/content/help/zh-Hant/experience-manager-64/release-notes/sp-release-notes.html)，以支援AEM內的[影像編輯器功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/image-editor.html)。

## 範例元件輸出 {#sample-component-output}

若要體驗影像元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_image)。

### 技術詳細資訊 {#technical-details}

您可在GitHub](https://adobe.com/go/aem_cmp_tech_image_v2)上找到影像元件[的最新技術檔案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

影像元件支援[schema.org microdata](https://schema.org)。

## 配置對話框 {#configure-dialog}

除了標準[edit dialog](#edit-dialog)和[design dialog](#design-dialog)之外，影像元件還提供配置對話框，在其中定義影像本身及其說明和基本屬性。

### 資產標籤 {#asset-tab}

![影像元件設定對話方塊的資產標籤](/help/assets/image-configure-asset.png)

* **影像資產**
   * 從[資產瀏覽器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)拖放資產，或點選&#x200B;**browse**&#x200B;選項，從本機檔案系統上傳。
   * 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下「**編輯** 」，在資產編輯器中[管理資產](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)的轉譯。

### 中繼資料索引標籤 {#metadata-tab}

![影像元件的配置對話框的元資料頁簽](/help/assets/image-configure-metadata.png)

* **預設類型**  — 這會定義可用的影像預設集類型( **影像** 保留器 **智慧型裁切**)，並且僅在啟用Dynamic Media功 [](#dynamic-meida) 能時可用。
   * **影像預設**  — 選取「 **影像** 預設 **類型」時，** 下拉式清單即可使用「影 **像預** 設」，以便從可用的Dynamic Media預設集中選取。只有為選取的資產定義了預設集時，才可使用此功能。
   * **智慧型裁切**  — 選取「 **智** 慧型 **的預** 設類型」時，下拉式清單 **** 可供使用，以便從所選資產的可用轉譯中選取。只有為選取的資產定義轉譯時，才可使用此功能。
   * **影像修飾元**  — 無論選取的預設類型為何，都可在此處以分隔定義其他Dynamic Media影 `&`像伺服命 **令，** 以取用。
* **影像是裝飾性的**  — 檢查影像是否應由輔助技術忽略，因此不需要替代文字。這僅適用於裝飾影像。
* **替代文字**  — 視覺障礙讀者影像意義或功能的文字替代項目。
   * **從DAM取得替代文字**  — 勾選此選項時，影像的替代文字將會填入DAM中中繼資 `dc:description` 料的值。
* **註解**  — 影像的其他資訊，預設顯示在影像下方。
   * **從DAM取得註解**  — 勾選此選項時，影像的註解文字將會填入DAM中 `dc:title` 中繼資料的值。
   * **將字幕顯示為快顯視窗**  — 若勾選此選項，字幕不會顯示在影像下方，但會顯示為將游標暫留在影像上時，由某些瀏覽器顯示的快顯視窗。
* **連結**  — 將影像連結至其他資源。
   * 使用選取對話方塊連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非溶質URL會解譯為相對於AEM。
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

>[!TIP]
>
>**智** 慧交叉 **和影** 像預設是互斥選項。如果作者需要使用影像預設集與智慧型裁切轉譯，則作者必須使用&#x200B;**影像修飾元**&#x200B;以手動新增預設集。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者裁切、修改啟動對映，以及縮放影像。

>[!NOTE]
>
>裁切、旋轉和縮放功能不適用於Dynamic Media資產。 如果啟用[Dynamic Media功能](#dynamic-media)，則應透過[設定對話方塊執行對Dynamic Media資產的任何這類編輯。](#configure-dialog)

![影像元件的編輯對話方塊](/help/assets/image-edit.png)

* 開始裁切

   ![開始裁切圖示](/help/assets/image-start-crop.png)

   選取此選項會開啟預先定義的裁切比例的下拉式清單。

   * 選擇選項&#x200B;**自由手**&#x200B;以定義您自己的裁切。
   * 選擇選項&#x200B;**移除裁切**&#x200B;以顯示原始資產。

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
>GIF影像不支援影像編輯操作（裁切、翻轉、旋轉）。 在編輯模式中對GIF所做的任何此類變更都不會持續存在。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者使用此元件時擁有的裁切、上傳、旋轉和上傳選項。

### 主要標籤 {#main-tab}

在&#x200B;**Main**&#x200B;標籤上，您可以定義影像的寬度清單（像素），元件將根據瀏覽器大小自動載入最合適的寬度。 這是影像元件[回應式功能](#responsive-features)的重要部分。

此外，您可以定義當作者將元件新增至頁面時，會自動或停用的一般元件選項。

![影像元件的設計對話方塊主索引標籤](/help/assets/image-design-main.png)

* **啟用DM功能**  — 勾選此選項後，即可使 [用啟](#dynamic-media) 用Dynamic Media功能。
* **啟用延遲載入**  — 定義將影像元件新增至頁面時，延遲載入選項是否自動啟用。
* **影像是裝飾**  — 在將影像元件新增至頁面時，定義裝飾影像選項是否自動啟用。
* **從DAM取得替代文字** — 將影像元件新增至頁面時，定義從DAM擷取替代文字的選項是否會自動啟用。
* **從DAM取得註解**  — 將影像元件新增至頁面時，定義從DAM擷取註解的選項是否自動啟用。
* **將標題顯示為彈出式**  — 定義將影像元件新增至頁面時，將影像標題顯示為彈出式視窗的選項是否自動啟用。
* **停用UUID追蹤**  — 檢查以停用影像資產UUID的追蹤。
* **寬度**  — 以像素定義影像的寬度清單，元件會根據瀏覽器大小自動載入最適當的寬度。
   * 點選或按一下&#x200B;**Add**&#x200B;按鈕以新增其他大小。
      * 使用抓握手柄重新排列大小的順序。
      * 使用&#x200B;**Delete**&#x200B;圖示來移除寬度。
   * 依預設，載入影像會延遲，直到變成可見為止。
      * 選取選項&#x200B;**停用延遲載入**&#x200B;以在頁面載入時載入影像。
* **JPEG品質**  — 用於轉換（例如縮放或裁切）JPEG影像的品質因數（以百分比表示，從0到100）。

### 功能標籤 {#features-tab}

在&#x200B;**Features**&#x200B;標籤上，您可以定義使用元件時，內容作者可使用的選項，包括上傳選項、方向和裁切選項。

* 來源

   ![「影像元件的設計」對話框「功能」頁簽](/help/assets/image-design-features-source.png)

   選取「允許從檔案系統上傳資產&#x200B;**」選項，允許內容作者從其本機電腦上傳影像。**&#x200B;若要強制內容作者僅從AEM選取資產，請取消選取此選項。

* 方向

   ![「影像元件的設計」對話框「功能」頁簽](/help/assets/image-design-features-orientation.png)

* ****
旋轉使用此選項可允許內容作者使用 
**旋轉** 右鍵。
* ****
反向使用此選項可允許內容作者使用 
**「水準** 翻轉」和「垂直 **翻** 轉」選項。

   >[!CAUTION]
   >
   >預設情況下禁用&#x200B;**Flip**&#x200B;選項。 啟用後，將在影像元件的編輯對話方塊中顯示&#x200B;**垂直翻轉**&#x200B;和&#x200B;**水準翻轉**&#x200B;按鈕，但AEM目前不支援此功能，且使用這些選項所做的任何變更都不會持續存在。

* 裁切

   ![「影像元件的設計」對話框「功能」頁簽](/help/assets/image-design-features-cropping.png)

   選取「**允許裁切**」選項，以允許內容作者在編輯對話方塊中裁切元件中的影像。
   * 按一下&#x200B;**Add**&#x200B;以新增預先定義的裁切長寬比。
   * 輸入描述性名稱，該名稱將顯示在&#x200B;**開始裁切**&#x200B;下拉式清單中。
   * 輸入外觀的數值比。
   * 使用拖動控制滑塊重新排列縱橫比的順序
   * 使用垃圾桶圖示來刪除外觀比例。

   >[!CAUTION]
   >
   >請注意，在AEM中，裁切長寬比定義為&#x200B;**height/width**。 這與傳統的寬度/高度定義不同，因為舊版相容性原因而完成。 只要您提供比例的明確名稱，內容作者就不會察覺任何差異，因為該名稱會顯示在UI中，而非比例本身。

### 樣式標籤 {#styles-tab-1}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## 適用性影像Servlet {#adaptive-image-servlet}

影像元件使用核心元件的最適化影像Servlet。 [負責影像](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) 處理和串流的適用性影像伺服器，可供開發人員在自訂核心元 [件時加以運用](/help/developing/customizing.md)。

>[!NOTE]
>
>適用性影像Servlet支援透過`Last-Modified`標頭的條件式請求，但`Last-Modified`標頭[的快取必須在Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#caching-http-response-headers)中啟用。
>
>[AEM專案原型的](/help/developing/archetype/overview.md)範例Dispatcher設定已包含此設定。

## Adobe用戶端資料層 {#data-layer}

影像元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
