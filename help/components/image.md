---
title: 影像元件
description: 核心元件影像元件是自我調整影像元件。
role: Architect, Developer, Admin, User
exl-id: c5e57f4b-139f-40e7-8d79-be9a74360b63
source-git-commit: ad911040d7e47fc3884071005c17accf8edd0a62
workflow-type: tm+mt
source-wordcount: '2062'
ht-degree: 0%

---


# 影像元件 {#image-component}

核心元件影像元件是自我調整影像元件。

## 使用情況 {#usage}

影像元件提供最適化影像選擇和回應式行為，頁面訪客可延遲載入，內容作者可輕鬆放置影像。

內容作者可以使用[編輯對話方塊](#edit-dialog)來編輯影像資產，例如套用裁切或旋轉影像。

範本作者可以在[設計對話方塊](#design-dialog)中定義影像寬度和其他設定。 內容編輯者可以在[設定對話方塊中上傳或選取資產。](#configure-dialog)

## 版本和相容性 {#version-and-compatibility}

影像元件的目前版本是v3，此版本隨2022年2月的核心元件發行版本2.18.0的發佈引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|--- |--- |--- |---|---|
| v3 | - | 相容 | 相容 | 相容 |
| [v2](v2/image.md) | 相容 | 相容 | - | 相容 |
| [v1](v1/image-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 回應式功能 {#responsive-features}

影像元件提供強大的回應式功能，立即可用。 在頁面範本層級，[設計對話方塊](#design-dialog)可用於定義影像資產的預設寬度。 影像元件會自動載入正確的寬度，以根據瀏覽器視窗的大小來顯示。 視窗調整大小時，影像元件會即時動態載入正確的影像大小。 元件開發人員無需擔心自訂媒體查詢的定義方式，因為影像元件已最佳化以載入您的內容。

此外，影像元件支援延遲載入，將實際影像資產的載入延遲到顯示在瀏覽器中為止，藉此提高頁面的回應能力。

>[!TIP]
>
>依預設，影像元件由最適化影像Servlet提供技術支援。 請參閱[最適化影像Servlet](/help/developing/adaptive-image-servlet.md)，瞭解其運作方式的詳細資訊。

### 與v2的差異 {#v2-differences}

與影像元件第2版不同，第3版使用瀏覽器原生回應。 這表示它會為瀏覽器提供一組不同寬度影像的來源，而瀏覽器會挑選最佳來源。

大部分時候，瀏覽器偏好在本機縮小較大的寬度以符合較小的檢視區，而非從伺服器擷取較小的寬度影像。 這是預期會出現的情況，以及為什麼不應該將影像元件用於藝術方向（不同的檢視區會有不同的影像/裁切）。

[如需詳細資訊，請參閱影像元件](https://github.com/adobe/aem-core-wcm-components/tree/main/content/src/content/jcr_root/apps/core/wcm/components/image/v3/image#javascript-data-attribute-bindings)的技術檔案。

## Dynamic Media支援 {#dynamic-media}

影像元件（截至[版本2.13.0](/help/versions.md)）支援[動態媒體](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/dynamicmedia/dynamic-media.html?lang=zh-Hant)資產。 [啟用時，](#design-dialog)這些功能可讓您使用簡單的拖放功能，或透過資產瀏覽器，像處理任何其他影像一樣新增Dynamic Media影像資產。 此外，也支援影像修飾元、影像預設集和智慧型裁切。

使用核心元件建立的網頁體驗可包含豐富、Sensei支援、穩定、高效能、跨平台的Dynamic Media影像功能。

## 遠端Assets支援 {#remote-assets}

影像元件（截至[版本2.23.2](/help/versions.md)）支援遠端資產。 [設定之後，](/help/developing/remote-assets.md)您可以從遠端服務為您的影像元件選取資產。

## SVG支援 {#svg-support}

影像元件支援可縮放向量圖形(SVG)。

* 支援從DAM拖放SVG資產以及上傳從本機檔案系統上傳的SVG檔案。
* 原始SVG檔案會串流處理（略過轉換）。
* 對於SVG影像，「智慧型影像」和「智慧型大小」會設定為影像模型中的空白陣列。

### 安全性 {#security}

基於安全考量，影像編輯器絕對不會直接呼叫原始SVG。 透過`<img src="path-to-component">`呼叫。 這可防止瀏覽器執行內嵌於SVG檔案中的任何指令碼。

## 範例元件輸出 {#sample-component-output}

若要體驗影像元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_image_tw)。

### 技術細節 {#technical-details}

在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_image_v3_tw)上可找到有關影像元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

影像元件支援[schema.org微資料](https://schema.org)。

## 編輯對話方塊 {#edit-dialog}

「編輯」對話方塊可讓內容作者裁切和縮放影像。

視您已啟用[動態媒體](#dynamic-media)或已啟用[遠端Assets支援](#remote-assets)而定，可用於編輯影像的選項會有所不同。

### 標準資產編輯 {#standard-assets}

如果您正在編輯標準AEM資產，可以按一下影像元件內容功能表中的&#x200B;**編輯**&#x200B;圖示。

![影像元件的編輯對話方塊](/help/assets/image-edit.png)

* 開始裁切

  ![開始裁切圖示](/help/assets/image-start-crop.png)

  選取此選項會開啟預先定義裁切比例的下拉式清單。

   * 選擇選項&#x200B;**移除裁切**&#x200B;以顯示原始資產。

  選取裁切選項後，請使用藍色控點來調整影像上的裁切大小。

  ![裁切選項](/help/assets/image-crop-options.png)

* 向右旋轉

  ![向右旋轉圖示](/help/assets/image-rotate-right.png)

  使用此選項可將影像向右（順時針）旋轉90°。

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
>GIF影像不支援影像編輯操作。 在編輯模式下對GIF所做的任何此類變更都不會持續存在。

### Dynamic Media資產編輯 {#dynamic-media-assets}

如果您已啟用[Dynamic Media功能，則必須在資產主控台中執行影像本身的](#dynamic-media)編輯。

## 設定對話方塊 {#configure-dialog}

影像元件提供「設定」對話方塊，其中定義了影像本身及其說明和基本屬性。

### 資產標籤 {#asset-tab}

影像元件之設定對話方塊的![資產標籤](/help/assets/image-configure-asset.png)

* **從頁面**&#x200B;繼承精選影像 — 此選項使用連結頁面[&#128279;](page.md)的精選影像或目前頁面的精選影像（如果未連結影像）。

* **影像資產** — 如果選取&#x200B;**從頁面**&#x200B;繼承精選影像，則會自動填入此資產。 取消選取可透過設定以下選項來手動定義影像。

   * 從[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hant)拖放資產，或點選&#x200B;**瀏覽**&#x200B;選項，以便您可以從本機檔案系統上傳。
   * 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下&#x200B;**挑選**&#x200B;以開啟[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hant)，讓您能夠選取影像。
      * 如果已啟用[遠端判斷提示支援](#remote-assets)，則您有多個選項可以挑選資產：
         * 從本機AEM資產庫選取&#x200B;**本機**。
         * **遠端**&#x200B;從AEM執行個體外部的Dynamic Media媒體庫選取。
   * 點選或按一下「**編輯**」以[在Asset Editor中管理資產](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=zh-Hant)的轉譯。

* **協助工具的替代文字** — 此欄位可讓您為視障使用者定義影像的說明。

   * **從頁面**&#x200B;繼承替代文字 — 此選項使用DAM中`dc:description`中繼資料之連結資產值的替代說明，或是使用目前頁面的替代說明（如果未連結資產）。

* **不提供替代文字** — 將影像標籤為被熒幕閱讀器等輔助技術忽略，以用於影像純粹起裝飾作用或不向頁面傳達額外資訊的情況。

### 中繼資料標籤 {#metadata-tab}

影像元件之設定對話方塊的![中繼資料標籤](/help/assets/image-configure-metadata.png)

* **預設集型別** — 這定義了可用影像預設集的型別，可以是&#x200B;**影像預設集**&#x200B;或&#x200B;**智慧型裁切**，而且僅在[Dynamic Media功能](#dynamic-meida)啟用時可用。
   * **影像預設集** — 當選取&#x200B;**影像預設集**&#x200B;的&#x200B;**預設集型別**&#x200B;時，下拉式&#x200B;**影像預設集**&#x200B;可供使用，並允許從可用的Dynamic Media預設集中選取。 這只有在為選取的資產定義了預設集時才能使用。
   * **智慧型裁切** — 當選取了&#x200B;**智慧型裁切**&#x200B;的&#x200B;**預設型別**&#x200B;時，下拉式清單&#x200B;**轉譯**&#x200B;可供使用，並允許從所選資產的可用轉譯中選擇。 這只有在為選取的資產定義了轉譯時才可用。
   * **影像修飾元** — 在這裡可以定義其他Dynamic Media影像伺服命令，以`&`分隔，無論選取哪個&#x200B;**預設集型別**。
* **標題** — 影像的其他相關資訊，預設會顯示於影像下方。
   * **從DAM取得註解** — 檢查時，影像的註解文字會以DAM中`dc:title`中繼資料的值填入。
   * **以快顯視窗顯示註解** — 檢查後，註解不會顯示在影像下方，但如在某些瀏覽器中將滑鼠懸停在影像上，註解會以快顯視窗顯示。
* **連結** — 將影像連結到其他資源。
   * 使用「選取」對話方塊可連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非絕對URL會解譯為相對於AEM。
   * **在新索引標籤中開啟連結** — 此選項會在新的瀏覽器視窗中開啟連結。
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

>[!TIP]
>
>**智慧型裁切**&#x200B;和&#x200B;**影像預設集**&#x200B;是互斥選項。 如果作者必須使用影像預設集以及智慧型裁切轉譯，則作者必須使用&#x200B;**影像修飾元**&#x200B;來手動新增預設集。

### 樣式索引標籤 {#styles-tab-edit}

影像元件![&#128279;](/help/assets/image-configure-styles.png)之[編輯]對話方塊的樣式索引標籤

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的選取具有相同的效果。

必須在[設計對話方塊](#design-dialog)中為此元件設定樣式，下拉式功能表才能使用。

## 設計對話方塊 {#design-dialog}

### 主要標籤 {#main-tab}

![影像元件的設計對話方塊主索引標籤](/help/assets/image-design-main.png)

* **啟用DM功能** — 檢查時，[可以使用Dynamic Media功能](#dynamic-media)。
   * 只有在環境中啟用Dynamic Media時，才會顯示此選項。
* **啟用Web最佳化影像** — 檢查後，[Web最佳化影像傳送服務](/help/developing/web-optimized-image-delivery.md)會以WebP格式傳送影像，平均將影像大小減少25%。
   * 此選項僅在AEMaaCS中可用。
   * 取消勾選或無法使用網頁最佳化的影像傳遞服務時，會使用[最適化影像Servlet](/help/developing/adaptive-image-servlet.md)。
* **停用延遲載入** — 選取後，元件會預先載入所有影像，而不會延遲載入。
* **影像為裝飾性** — 定義將影像元件新增至頁面時，是否自動啟用裝飾性影像選項。
* **從DAM取得替代文字** — 定義在將影像元件新增至頁面時，是否自動啟用從DAM擷取替代文字的選項。
* **從DAM取得註解** — 定義在將影像元件新增至頁面時，是否自動啟用從DAM擷取註解的選項。
* **以快顯視窗顯示註解** — 定義將影像元件新增至頁面時，是否自動啟用以快顯視窗顯示影像註解的選項。
* **調整寬度** — 此值用於調整作為DAM資產的基本影像的寬度。
   * 影像的外觀比例會保留。
   * 如果該值大於影像的實際寬度，則該值無效。
   * 此值對SVG影像沒有影響。

您可以定義影像的寬度（以畫素為單位），元件會根據瀏覽器大小自動載入最適當的寬度。 這是影像元件的[回應式功能](#responsive-features)的重要部分。

* **寬度** — 定義影像的寬度（以畫素為單位），元件會根據瀏覽器大小自動載入最適當的寬度。
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增其他大小。
      * 使用抓取操作框可重新排列大小順序。
      * 使用&#x200B;**刪除**&#x200B;圖示來移除寬度。
   * 依預設，影像載入會延遲到影像可見為止。
      * 選取選項&#x200B;**停用延遲載入**，以便在頁面載入時載入影像。
* **JPEG品質** — 轉換（例如，縮放或裁切）的JPEG影像的品質係數（以從0到100的百分比表示）。

>[!TIP]
>
>請參閱檔案[最適化影像Servlet](/help/developing/adaptive-image-servlet.md)，瞭解如何透過仔細定義寬度來最佳化轉譯選擇的秘訣。

### 樣式索引標籤 {#styles-tab}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe使用者端資料層 {#data-layer}

影像元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
