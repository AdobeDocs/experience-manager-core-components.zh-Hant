---
title: 電子郵件影像元件
description: 電子郵件影像元件是自我調整影像元件，具備就地編輯的功能。
role: Architect, Developer, Admin, User
exl-id: f5d40047-3082-4edd-a5f6-6ab3e33997f9
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: tm+mt
source-wordcount: '1624'
ht-degree: 0%

---


# 電子郵件影像元件 {#email-image-component}

電子郵件影像元件是自我調整影像元件，具備就地編輯的功能。

## 使用情況 {#usage}

電子郵件影像元件提供最適化影像選擇和回應式行為，頁面訪客可延遲載入，內容作者可輕鬆拖放影像放置和設定。

* 範本作者可以在[設計對話方塊中定義影像寬度和其他設定。](#design-dialog)
* 內容編輯者可以在[設定對話方塊中上傳或選取資產。](#configure-dialog)

## 版本和相容性 {#version-and-compatibility}

電子郵件影像元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

如需核心元件版本的詳細資訊，請參閱檔案[電子郵件核心元件版本](/help/email/versions.md)。

## 回應式功能 {#responsive-features}

電子郵件影像元件提供強大的回應功能，立即可用。 在頁面範本層級，[設計對話方塊](#design-dialog)可用於定義影像資產的預設寬度。 然後，電子郵件影像元件將自動載入正確的寬度，以根據瀏覽器視窗的大小來顯示。 在視窗調整大小時，電子郵件影像元件會即時動態載入正確的影像大小。 元件開發人員無需擔心自訂媒體查詢的定義方式，因為電子郵件影像元件已最佳化以載入您的內容。

此外，電子郵件影像元件支援延遲載入，將實際影像資產的載入延遲到顯示在瀏覽器中時，藉此提高內容的回應能力。

>[!TIP]
>
>依預設，電子郵件影像元件由最適化影像Servlet提供技術支援。 如需其運作方式的詳細資訊，請參閱檔案[最適化影像Servlet](#adaptive-image-servlet)。

## Dynamic Media支援 {#dynamic-media}

電子郵件影像元件支援[動態媒體](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=zh-Hant#dynamicmedia)資產。 [啟用時，](#design-dialog)這些功能可讓您使用簡單的拖放功能，或透過資產瀏覽器，像處理任何其他影像一樣新增Dynamic Media影像資產。 此外，也支援影像修飾元、影像預設集和智慧型裁切。

使用電子郵件核心元件建置的電子郵件體驗可包含豐富、Sensei支援、穩定、高效能、跨平台的Dynamic Media影像功能。

## SVG支援 {#svg-support}

電子郵件影像元件支援可縮放向量圖形(SVG)。

* 支援從DAM拖放SVG資產以及從本機檔案系統上傳SVG檔案。
* 原始SVG檔案會串流處理（略過轉換）。
* 對於SVG影像，「智慧型影像」和「智慧型大小」會設定為影像模型中的空白陣列。

### 安全性 {#security}

基於安全考量，影像編輯器絕對不會直接呼叫原始SVG。 透過`<img src=“path-to-component”>`呼叫。 這可防止瀏覽器執行內嵌於SVG檔案中的任何指令碼。

### 技術細節 {#technical-details}

您可以在GitHub上找到有關電子郵件影像元件[的最新技術檔案。](https://adobe.com/go/aem_cmp_tech_email_image_v1)

在[核心元件開發人員檔案中可找到有關開發核心元件的進一步詳細資料。](/help/developing/overview.md)

影像元件支援[schema.org微資料。](https://schema.org)

## 設定對話方塊 {#configure-dialog}

電子郵件影像元件提供設定對話方塊，其中會定義影像本身及其說明和基本屬性。

### 資產標籤 {#asset-tab}

電子郵件影像元件之設定對話方塊的![資產標籤](/help/email/assets/email-image-configure-asset.png)

* **從頁面**&#x200B;繼承精選影像 — 此選項使用連結頁面[&#128279;](page.md)的精選影像或目前頁面的精選影像（如果未連結影像）。

* **協助工具的替代文字** — 此欄位可讓您為視障使用者定義影像的說明。

   * **從頁面**&#x200B;繼承替代文字 — 此選項使用DAM中`dc:description`中繼資料之連結資產值的替代說明，或是使用目前頁面的替代說明（如果未連結資產）。

* **影像資產**
   * 從[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hant)拖放資產，或點選&#x200B;**瀏覽**&#x200B;選項，以從本機檔案系統上傳。
   * 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下「**編輯**」以[在Asset Editor中管理資產](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=zh-Hant)的轉譯。

* **不提供替代文字** — 此選項會將影像標籤為被熒幕閱讀器等輔助技術忽略，以用於影像純粹起裝飾作用或不向頁面傳達額外資訊的情況。

* **停用延遲載入** — 此選項會預先載入所有影像元件，而不視需要載入。

### 中繼資料標籤 {#metadata-tab}

影像元件之設定對話方塊的![中繼資料標籤](/help/email/assets/email-image-configure-metadata.png)

* **預設集型別** — 這定義了可用影像預設集的型別，可以是&#x200B;**影像預設集**&#x200B;或&#x200B;**智慧型裁切**，而且僅在[Dynamic Media功能](#dynamic-meida)啟用時可用。
   * **影像預設集** — 當選取&#x200B;**影像預設集**&#x200B;的&#x200B;**預設集型別**&#x200B;時，下拉式&#x200B;**影像預設集**&#x200B;可供使用，並允許從可用的Dynamic Media預設集中選取。 這只有在為選取的資產定義了預設集時才能使用。
   * **智慧型裁切** — 選取&#x200B;**智慧型裁切**&#x200B;的&#x200B;**預設型別**&#x200B;時，下拉式清單&#x200B;**轉譯**&#x200B;可供使用，並允許從所選資產的可用轉譯中進行選取。 這只有在為選取的資產定義了轉譯時才可用。
   * **影像修飾元** — 在這裡可以定義其他Dynamic Media影像伺服命令，以`&`分隔，無論選取哪個&#x200B;**預設集型別**。
* **標題** — 影像的其他相關資訊，預設會顯示於影像下方。
   * **從DAM取得註解** — 勾選時，影像的註解文字將會填入DAM中`dc:title`中繼資料的值。 僅在從DAM中選擇資產時可用。
   * **以快顯視窗顯示註解** — 檢查後，註解不會顯示在影像下方，但如在某些瀏覽器中將滑鼠懸停在影像上，註解會以快顯視窗顯示。
* **連結** — 將影像連結到其他資源。
   * 使用「選取」對話方塊可連結至其他AEM資源。
   * 如果未連結至AEM資源，請輸入絕對URL。 非絕對URL將會解譯為相對於AEM。
   * **在新索引標籤中開啟連結** — 此選項會在新的瀏覽器視窗中開啟連結。
* **ID** — 此選項允許控制HTML中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS造成影響。
* **固定為** — 此選項會定義影像的寬度（畫素）。
* **將影像縮放至可用的寬度** — 此選項會將`"width":"100%"`套用至影像樣式屬性。

>[!TIP]
>
>**智慧型裁切**&#x200B;和&#x200B;**影像預設集**&#x200B;是互斥選項。 如果作者需要使用影像預設集以及智慧型裁切轉譯，該作者必須使用&#x200B;**影像修飾元**&#x200B;來手動新增預設集。

### 樣式索引標籤 {#styles-tab-edit}

電子郵件影像元件之[編輯]對話方塊的![樣式索引標籤](/help/assets/image-configure-styles.png)

電子郵件影像元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的選取具有相同的效果。

必須在[設計對話方塊](#design-dialog)中為此元件設定樣式，才能使用索引標籤。

## 設計對話方塊 {#design-dialog}

### 主要標籤 {#main-tab}

![影像元件的設計對話方塊主索引標籤](/help/email/assets/email-image-design-main.png)

* **啟用DM功能** — 檢查時，[可以使用Dynamic Media功能](#dynamic-media)。
   * 只有在環境中啟用Dynamic Media時，才會顯示此選項。
* **啟用Web最佳化影像** — 檢查完畢後，[Web最佳化影像傳送服務](/help/developing/web-optimized-image-delivery.md)會傳送WebP格式的影像，平均將影像大小減少25%。
   * 此選項僅在AEMaaCS中可用。
   * 取消勾選或無法使用網頁最佳化的影像傳遞服務時，會使用[最適化影像Servlet](/help/developing/adaptive-image-servlet.md)。
* **影像為裝飾性** — 定義將影像元件新增至頁面時，是否自動啟用裝飾性影像選項。
* **從DAM取得替代文字** — 定義在將影像元件新增至頁面時，是否自動啟用從DAM擷取替代文字的選項。
* **從DAM取得註解** — 定義在將影像元件新增至頁面時，是否自動啟用從DAM擷取註解的選項。
* **以快顯視窗顯示註解** — 定義將影像元件新增至頁面時，是否自動啟用以快顯視窗顯示影像註解的選項。
* **調整寬度** — 此值用於調整作為DAM資產的基本影像的寬度。
   * 影像的外觀比例將會保留。
   * 如果該值大於影像的實際寬度，則該值無效。
   * 此值對SVG影像沒有影響。

您可以定義影像的寬度（單位為畫素），元件會根據瀏覽器大小自動載入最適當的寬度。 這是電子郵件影像元件之[回應式功能](#responsive-features)的重要部分。

* **寬度** — 定義影像的寬度（以畫素為單位），元件會根據瀏覽器大小自動載入最適當的寬度。
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增其他大小。
      * 使用抓取操作框可重新排列大小。
      * 使用&#x200B;**刪除**&#x200B;圖示來移除寬度。
   * 依預設，影像載入會延遲到影像可見為止。
      * 選取選項&#x200B;**停用延遲載入**&#x200B;以在頁面載入時載入影像。
* **JPEG品質** — 轉換（例如縮放或裁切）的JPEG影像的品質係數（以從0到100的百分比表示）。
* **預設寬度** — 將在設計對話方塊中使用的預設影像寬度（畫素）

>[!TIP]
>
>請參閱檔案[最適化影像Servlet](/help/developing/adaptive-image-servlet.md)，瞭解如何透過仔細定義寬度來最佳化轉譯選擇的秘訣。

### 樣式索引標籤 {#styles-tab}

電子郵件影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
