---
title: 電子郵件影像元件
description: 「電子郵件影像元件」是具備就地編輯功能的最適化影像元件。
role: Architect, Developer, Admin, User
exl-id: f5d40047-3082-4edd-a5f6-6ab3e33997f9
index: false
source-git-commit: 8952f6c574fe1e21ff35e95bc0af6433f0363e77
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 98%

---


# 電子郵件影像元件 {#email-image-component}

「電子郵件影像元件」是具備就地編輯功能的最適化影像元件。

## 用途 {#usage}

「電子郵件影像元件」為頁面訪客提供最適化影像選擇和回應式行為並搭載延遲載入功能，而內容作者可輕鬆拖放影像和設定。

* 範本作者可以使用[設計對話框](#design-dialog)定義影像寬度與其他設定。
* 內容編輯者可以使用[設定對話框](#configure-dialog)上傳或選取資產。

## 版本和相容性 {#version-and-compatibility}

電子郵件影像元件的目前版本為 v1，此版本於 2022 年 10 月隨著電子郵件核心元件 x 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[電子郵件核心元件版本](/help/email/versions.md)文件。

## 回應式功能 {#responsive-features}

「電子郵件影像元件」提供可立即可用的強大回應式功能。在頁面範本層級，[設計對話框](#design-dialog)可用於定義影像資產的預設寬度。「電子郵件影像元件」會自動載入正確的寬度，以根據瀏覽器視窗的大小來顯示。視窗調整大小時，「電子郵件影像元件」會即時動態載入正確的影像大小。元件開發人員無需擔心自訂媒體查詢的定義方式，因為「電子郵件影像元件」已最佳化，以載入您的內容。

此外，「電子郵件影像元件」支援延遲載入，將實際影像資產的載入延遲到顯示在瀏覽器中為止，藉此提高內容的回應能力。

>[!TIP]
>
>預設情況下，「電子郵件影像元件」由「最適化影像 Servlet」提供支援。如需其運作方式的詳細資訊，請參閱[最適化影像 Servlet](#adaptive-image-servlet) 文件。

## Dynamic Media 支援 {#dynamic-media}

「電子郵件影像元件」支援 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=zh-Hant#dynamicmedia) 資產。[啟用後，](#design-dialog)這些功能可讓您使用簡單的拖放功能，或透過資產瀏覽器，像處理任何其他影像一樣新增「Dynamic Media」影像資產。此外，同樣支援影像修飾元、影像預設集和智慧裁切。

使用電子郵件核心元件建置的電子郵件體驗可以包含豐富、支援Adobe AI、強大、高效能、跨平台的Dynamic Media影像功能。

## SVG 支援 {#svg-support}

「電子郵件影像元件」支援可縮放向量圖形 (SVG)。

* 支援從 DAM 拖放 SVG 資產以及上傳從本機檔案系統上傳的 SVG 檔案。
* 原始 SVG 檔案會串流處理 (略過轉換)。
* 對於 SVG 影像，「智慧型影像」和「智慧型大小」會設定為影像模型中的空白陣列。

### 安全性 {#security}

基於安全考量，「影像編輯器」絕對不會直接呼叫原始 SVG。而是透過 `<img src=“path-to-component”>` 呼叫。這可防止瀏覽器執行內嵌於 SVG 檔案中的任何指令碼。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_image_v1_tw)有關「電子郵件影像元件」的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件。](/help/developing/overview.md)

「影像元件」支援 [schema.org 結構化資料](https://schema.org)。

## 設定對話框 {#configure-dialog}

「電子郵件影像元件」提供設定對話框，其中定義該影像本身、其說明和基本屬性。

### 資產索引標籤 {#asset-tab}

![電子郵件影像元件設定對話框的資產索引標籤](/help/email/assets/email-image-configure-asset.png)

* **從頁面繼承精選影像** - 此選項使用[連結頁面的精選影像](page.md)，若未連結至該影像，則會使用目前頁面的精選影像。

* **協助工具替代文字** - 此欄位可讓您為視障使用者定義影像的說明。

   * **從頁面繼承替代文字** - 此選項會使用 DAM 中 `dc:description` 後設資料所連結資產值的替代說明，若未連結任何資產，則會使用目前頁面的替代說明。

* **影像資產**
   * 從[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hant)拖曳資產，或點選&#x200B;**瀏覽**&#x200B;選項，以從本機檔案系統上傳。
   * 點選或按一下&#x200B;**「清除」**，取消選取目前選取的影像。
   * 點選或按一下&#x200B;**編輯**，以在 Asset Editor 中[管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=zh-Hant)。

* **不提供替代文字** - 此選項會標記該影像被螢幕助讀程式等輔助技術忽略，適用於影像僅用於裝飾或不向頁面傳達額外資訊的情況。

* **停用延遲載入** - 此選項會預先載入所有影像元件，無需依需要載入。

### 後設資料索引標籤 {#metadata-tab}

![影像元件設定對話框的後設資料索引標籤](/help/email/assets/email-image-configure-metadata.png)

* **預設集類型** - 定義可用影像預設集的類型，可以是&#x200B;**影像預設集**&#x200B;或&#x200B;**智慧裁切**，而且僅在 [Dynamic Media 功能](#dynamic-meida)啟用時可用。
   * **影像預設集** - 當選取&#x200B;**影像預設集**&#x200B;的&#x200B;**預設集類型**&#x200B;時，**影像預設集**&#x200B;下拉式清單可供使用，並允許從可用的「Dynamic Media」預設集中選取。這只有在為選取的資產定義了預設集時才能使用。
   * **智型裁切** - 當選取&#x200B;**智慧裁切**&#x200B;的&#x200B;**預設集類型**&#x200B;時，**轉譯**&#x200B;下拉式清單可供使用，並允許從所選資產的可用轉譯中選取。這只有在為選取的資產定義了轉譯時才能使用。
   * **影像修飾元** - 此處定義其他「Dynamic Media」影像命令，並以`&`分隔，無論選取哪個&#x200B;**預設集類型**&#x200B;均適用。
* **註解** - 影像的其他相關資訊，預設會顯示於影像下方。
   * **從 DAM 取得註解** - 勾選後，影像的註解文字會以 DAM 中 `dc:title` 後設資料的值填入。僅適用於從 DAM 中選取資產時。
   * **以快顯視窗顯示註解** - 勾選後，註解不會顯示在影像下方，但如在某些瀏覽器中將游標停留在影像上，註解會以快顯視窗顯示。
* **連結** - 將影像連結至其他資源。
   * 使用選取對話框可連結至其他 AEM 資源。
   * 如果未連結至 AEM 資源，請輸入絕對 URL。非絕對 URL 將解釋為相對於 AEM。
   * **在新索引標籤中開啟連結** - 此選項會在新的瀏覽器視窗中開啟連結。
* **ID** - 此選項允許控制 HTML 中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS 產生影響。
* **固定為** - 此選項定義影像的寬度 (以像素為單位)。
* **將影像縮放至可用寬度** - 此選項將 `"width":"100%"` 套用至影像樣式屬性。

>[!TIP]
>
>**智慧裁切**&#x200B;和&#x200B;**影像預設集**&#x200B;是互斥選項。如果作者必須使用影像預設集以及智慧裁切轉譯，則必須使用&#x200B;**影像修飾元**&#x200B;以手動新增預設集。

### 樣式索引標籤 {#styles-tab-edit}

![電子郵件影像元件編輯對話框的樣式索引標籤](/help/assets/image-configure-styles.png)

「電子郵件影像元件」支援 AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單，選取想要套用至元件的樣式。在編輯對話框中所做的選取，與從元件工具列中選擇具有相同效果。

元件樣式必須在[設計對話框](#design-dialog)中設定，才能使用該索引標籤。

## 設計對話框 {#design-dialog}

### 主要索引標籤 {#main-tab}

![影像元件的設計對話框主要索引標籤](/help/email/assets/email-image-design-main.png)

* **啟用 DM 功能** - 勾選後，即可使用 [Dynamic Media 功能](#dynamic-media)。
   * 只有在環境中啟用「Dynamic Media」時，才會顯示此選項。
* **啟用網頁最佳化影像** - 勾選後，[網頁最佳化影像傳遞服務](/help/developing/web-optimized-image-delivery.md)會以 WebP 格式傳送影像，平均將影像大小減少 25%。
   * 此選項僅在 AEMaaCS 中可用。
   * 取消勾選或無法使用網頁最佳化的影像傳遞服務時，會使用[最適化影像 Servlet](/help/developing/adaptive-image-servlet.md)。
* **影像為裝飾性** - 定義將影像元件新增至頁面時，是否自動啟用裝飾性影像選項。
* **從 DAM 取得替代文字** - 定義在將影像元件新增至頁面時，是否自動啟用從 DAM 擷取替代文字的選項。
* **從 DAM 取得註解** - 定義在將影像元件新增至頁面時，是否自動啟用從 DAM 擷取註解的選項。
* **以快顯視窗顯示註解** - 定義將影像元件新增至頁面時，是否自動啟用以快顯視窗顯示影像註解的選項。
* **調整寬度** - 此值用於調整作為 DAM 資產的基本影像的寬度。
   * 影像的外觀比例會保留。
   * 如果該值大於影像的實際寬度，則該值無效。
   * 此值對 SVG 影像沒有影響。

您可以定義影像的寬度 (以像素為單位) 清單，元件會根據瀏覽器大小自動載入最適當的寬度。這是「電子郵件影像元件」[回應式功能](#responsive-features) 的重要部分。

* **寬度** - 定義影像的寬度 (以像素為單位) 清單，元件會根據瀏覽器大小自動載入最適當的寬度。
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增其他大小。
      * 使用抓取控點，以重新排列大小的順序。
      * 使用&#x200B;**刪除**&#x200B;圖示來移除寬度。
   * 根據預設，影像載入會延遲到影像可見為止。
      * 選取&#x200B;**停用延遲載入**&#x200B;選項，以便在頁面載入時載入影像。
* **JPEG 品質** - 轉換後 (例如縮放或裁切) 的 JPEG 影像品質係數 (以 0 到 100 的百分比表示)。
* **預設寬度** - 設計對話框中將使用的影像預設寬度 (以像素為單位)

>[!TIP]
>
>請參閱[最適化影像 Servlet](/help/developing/adaptive-image-servlet.md) 文件，瞭解如何透過仔細定義寬度來最佳化轉譯選擇的秘訣。

### 樣式索引標籤 {#styles-tab}

電子郵件影像元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
