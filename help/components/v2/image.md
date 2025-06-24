---
title: 影像元件(v2)
description: 核心元件影像元件是自我調整影像元件，具備就地編輯的功能。
role: Architect, Developer, Admin, User
exl-id: 3f2b93f9-c48d-43ef-a78a-accd5090fe6f
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '2048'
ht-degree: 1%

---


# 影像元件(v2) {#image-component}

核心元件影像元件是自我調整影像元件，具備就地編輯的功能。

## 使用情況 {#usage}

影像元件提供最適化影像選擇和回應式行為，頁面訪客可延遲載入，內容作者可輕鬆放置和裁切影像。

範本作者可以在[設計對話方塊](#design-dialog)中定義影像寬度以及裁切和其他設定。 內容編輯者可以在[設定對話方塊](#configure-dialog)上傳或選取資產，並在[編輯對話方塊](#edit-dialog)裁切影像。 為了增加便利性，您也可以簡單地就地修改影像。

## 版本和相容性 {#version-and-compatibility}

本檔案說明影像元件v2，此版本隨2018年1月的核心元件發行版本2.0.0的發佈引入。

>[!CAUTION]
>
>本檔案說明影像元件v1。
>
>如需目前版本的影像元件的詳細資訊，請參閱[影像元件](/help/components/image.md)檔案。

## 回應式功能 {#responsive-features}

影像元件提供強大的回應式功能，立即可用。 在頁面範本層級，[設計對話方塊](#design-dialog)可用於定義影像資產的預設寬度。 然後，影像元件會自動載入正確的寬度，以根據瀏覽器視窗的大小來顯示。 視窗調整大小時，影像元件會即時動態載入正確的影像大小。 元件開發人員無需擔心自訂媒體查詢的定義方式，因為影像元件已最佳化以載入您的內容。

此外，影像元件支援延遲載入，將實際影像資產的載入延遲到顯示在瀏覽器中為止，藉此提高頁面的回應能力。

>[!TIP]
>
>影像元件由最適化影像Servlet提供技術支援。 如需其運作方式的詳細資訊，請參閱檔案[最適化影像Servlet](#adaptive-image-servlet)。

## Dynamic Media支援 {#dynamic-media}

影像元件（截至[版本2.13.0](/help/versions.md)）支援[動態媒體](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=en#dynamicmedia)資產。 [啟用時，](#design-dialog)這些功能可讓您使用簡單的拖放功能，或透過資產瀏覽器，像處理任何其他影像一樣新增Dynamic Media影像資產。 此外，也支援影像修飾元、影像預設集和智慧型裁切。

使用核心元件建立的網頁體驗現在具備豐富、Sensei支援、穩定、高效能、跨平台的Dynamic Media影像功能。

## SVG支援 {#svg-support}

影像元件支援可縮放向量圖形(SVG)。

* 支援從DAM拖放SVG資產以及從本機檔案系統上傳SVG檔案。
* 原始SVG檔案會串流處理（略過轉換）。
* 對於SVG影像，「智慧型影像」和「智慧型大小」會設定為影像模型中的空白陣列。

### 安全性 {#security}

基於安全考量，影像編輯器絕對不會直接呼叫原始SVG。 透過`<img src=“path-to-component”>`呼叫。 這可防止瀏覽器執行內嵌於SVG檔案中的任何指令碼。

## 範例元件輸出 {#sample-component-output}

若要體驗影像元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_image)。

### 技術細節 {#technical-details}

在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_image_v2)上可找到有關影像元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

影像元件支援[schema.org微資料](https://schema.org)。

## 設定對話方塊 {#configure-dialog}

除了標準[編輯對話方塊](#edit-dialog)和[設計對話方塊](#design-dialog)之外，影像元件還提供設定對話方塊，其中影像本身與其描述和基本屬性一起定義。

### 資產標籤 {#asset-tab}

影像元件之設定對話方塊的![資產標籤](/help/assets/image-configure-asset.png)

* **影像資產**
   * 從[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)拖放資產，或點選&#x200B;**瀏覽**&#x200B;選項，以從本機檔案系統上傳。
   * 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下&#x200B;**編輯**&#x200B;以[在資產編輯器中管理資產](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)的轉譯。

### 中繼資料標籤 {#metadata-tab}

影像元件之設定對話方塊的![中繼資料標籤](/help/assets/image-configure-metadata.png)

* **預設集型別** — 這定義了可用影像預設集的型別，可以是&#x200B;**影像預設集**&#x200B;或&#x200B;**智慧型裁切**，而且僅在[Dynamic Media功能](#dynamic-meida)啟用時可用。
   * **影像預設集** — 選取&#x200B;**影像預設集**&#x200B;的&#x200B;**預設集型別**&#x200B;時，下拉式清單&#x200B;**影像預設集**&#x200B;可供使用，並允許從可用的Dynamic Media預設集中選取。 這只有在為選取的資產定義了預設集時才能使用。
   * **智慧型裁切** — 選取&#x200B;**智慧型裁切**&#x200B;的&#x200B;**預設型別**&#x200B;時，下拉式清單&#x200B;**轉譯**&#x200B;可供使用，並允許從所選資產的可用轉譯中進行選取。 這只有在為選取的資產定義了轉譯時才可用。
   * **影像修飾元** — 在這裡可以定義其他Dynamic Media影像伺服命令，以`&`分隔，無論選取哪個&#x200B;**預設集型別**。
* **影像為裝飾性** — 檢查輔助技術是否應忽略影像，因此不需要替代文字。 這僅適用於裝飾性影像。
* **替代文字** — 影像含義或功能的替代文字，適用於視障讀者。
   * **從DAM取得替代文字** — 勾選時，影像的替代文字將會填入DAM中`dc:description`中繼資料的值。
* **標題** — 影像的其他相關資訊，預設會顯示於影像下方。
   * **從DAM取得註解** — 勾選時，影像的註解文字將會填入DAM中`dc:title`中繼資料的值。
   * **以快顯視窗顯示註解** — 檢查後，註解不會顯示在影像下方，但如在某些瀏覽器中將滑鼠懸停在影像上，註解會以快顯視窗顯示。
* **連結** — 將影像連結到其他資源。
   * 使用「選取」對話方塊可連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非絕對URL將會解譯為相對於AEM。
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

>[!TIP]
>
>**智慧型裁切**&#x200B;和&#x200B;**影像預設集**&#x200B;是互斥選項。 如果作者需要使用影像預設集以及智慧型裁切轉譯，該作者必須使用&#x200B;**影像修飾元**&#x200B;來手動新增預設集。

## 編輯對話方塊 {#edit-dialog}

此編輯對話方塊可讓內容作者裁切、修改啟動地圖及縮放影像。

>[!NOTE]
>
>裁切、旋轉和縮放功能不適用於Dynamic Media資產。 如果已啟用[Dynamic Media功能](#dynamic-media)，對Dynamic Media資產的任何這類編輯都應該透過[設定對話方塊](#configure-dialog)執行。

![影像元件的編輯對話方塊](/help/assets/image-edit.png)

* 開始裁切

  ![開始裁切圖示](/help/assets/image-start-crop.png)

  選取此選項會開啟預先定義裁切比例的下拉式清單。

   * 選擇選項&#x200B;**手繪**&#x200B;來定義您自己的裁切。
   * 選擇選項&#x200B;**移除裁切**&#x200B;以顯示原始資產。

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

就地編輯器也可用於修改影像。 由於空間限制，僅基本選項內嵌。 如需完整的編輯選項，請使用全熒幕模式。

![影像就地編輯選項](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>GIF影像不支援影像編輯操作（裁切、翻轉、旋轉）。 在編輯模式下對GIF所做的任何此類變更都不會持續存在。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義內容作者在使用此元件時的裁切、上傳、旋轉和上傳選項。

### 主要標籤 {#main-tab}

在&#x200B;**主要**&#x200B;標籤上，您可以定義影像的寬度（以畫素為單位），元件將會根據瀏覽器大小自動載入最適當的寬度。 這是影像元件的[回應式功能](#responsive-features)的重要部分。

此外，您可以定義在作者將元件新增至頁面時，要自動或停用哪些一般元件選項。

![影像元件的設計對話方塊主索引標籤](/help/assets/image-design-main-v2.png)

* **啟用DM功能** — 勾選後，即可使用[動態媒體功能](#dynamic-media)。
* **啟用Web最佳化影像** — 勾選後，[Web最佳化影像傳送服務](/help/developing/web-optimized-image-delivery.md)將以WebP格式傳送影像，平均將影像大小減少25%。
   * 此選項僅在AEMaaCS中可用。
   * 取消勾選或Web最佳化的影像傳遞服務無法使用時，會使用[最適化影像Servlet](/help/developing/adaptive-image-servlet.md)。
* **啟用延遲載入** — 定義在將影像元件新增至頁面時，是否自動啟用延遲載入選項。
* **影像為裝飾性** — 定義將影像元件新增至頁面時，是否自動啟用裝飾性影像選項。
* **從DAM取得替代文字** — 定義在將影像元件新增至頁面時，是否自動啟用從DAM擷取替代文字的選項。
* **從DAM取得註解** — 定義在將影像元件新增至頁面時，是否自動啟用從DAM擷取註解的選項。
* **以快顯視窗顯示註解** — 定義將影像元件新增至頁面時，是否自動啟用以快顯視窗顯示影像註解的選項。
* **停用UUID追蹤** — 勾選以停用影像資產的UUID追蹤。
* **寬度** — 定義影像的寬度（以畫素為單位），元件會根據瀏覽器大小自動載入最適當的寬度。
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增其他大小。
      * 使用抓取操作框來重新排列大小。
      * 使用&#x200B;**刪除**&#x200B;圖示來移除寬度。
   * 依預設，影像載入會延遲到影像可見為止。
      * 選取選項&#x200B;**停用延遲載入**&#x200B;以在頁面載入時載入影像。
* **JPEG品質** — 轉換（例如縮放或裁切）的JPEG影像的品質係數（以從0到100的百分比表示）。

>[!TIP]
>
>請參閱檔案[最適化影像Servlet](#adaptive-image-servlet)，瞭解如何透過仔細定義寬度來最佳化轉譯選擇的秘訣。

### 功能標籤 {#features-tab}

在&#x200B;**功能**&#x200B;標籤上，您可以定義在使用元件時內容作者可用的選項，包括上傳選項、方向以及裁切選項。

* 來源

  ![影像元件的設計對話方塊[功能]索引標籤](/help/assets/image-design-features-source.png)

  選取選項&#x200B;**允許從檔案系統上傳資產**，以允許內容作者從其本機電腦上傳影像。 若要強制內容作者僅從AEM中選取資產，請取消選取此選項。

* 方向

  ![影像元件的設計對話方塊[功能]索引標籤](/help/assets/image-design-features-orientation.png)

* **旋轉**
使用此選項可允許內容作者使用&#x200B;**向右旋轉**&#x200B;選項。
* **翻轉**
使用此選項可允許內容作者使用&#x200B;**水準翻轉**&#x200B;和&#x200B;**垂直翻轉**&#x200B;選項。

  >[!CAUTION]
  >
  >**Flip**&#x200B;選項預設為停用。 啟用此選項會在影像元件的編輯對話方塊中顯示&#x200B;**垂直翻轉**&#x200B;和&#x200B;**水準翻轉**&#x200B;按鈕，但AEM目前不支援此功能，且不會保留使用這些選項所做的任何變更。

* 裁切

  ![影像元件的設計對話方塊[功能]索引標籤](/help/assets/image-design-features-cropping.png)

  選取選項&#x200B;**允許裁切**，以允許內容作者在編輯對話方塊中裁切元件中的影像。
   * 按一下「新增&#x200B;**&#x200B;**」以新增預先定義的裁切外觀比例。
   * 輸入描述性名稱，此名稱將顯示在&#x200B;**開始裁切**&#x200B;下拉式清單中。
   * 輸入外觀的數字比例。
   * 使用拖曳操作框來重新排列長寬比
   * 使用垃圾桶圖示可刪除外觀比例。

  >[!CAUTION]
  >
  >請注意，在AEM中，裁切比例定義為&#x200B;**高度/寬度**。 這和寬度/高度比的傳統定義不同，並且是由於舊有相容性的原因完成的。只要您提供明確的比率名稱，內容作者就不會察覺任何差異，因為該名稱會顯示在UI中，而非比率本身。

### 樣式索引標籤 {#styles-tab-1}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

影像元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
