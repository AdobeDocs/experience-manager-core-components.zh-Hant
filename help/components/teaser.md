---
title: Teaser元件
description: Teaser元件可顯示影像、標題、RTF文字，並可選擇連結至其他內容。
role: Architect, Developer, Admin, User
exl-id: ec75e168-6f3b-4dff-8df6-06ca7dc18688
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 5%

---

# Teaser元件 {#teaser-component}

核心元件Teaser元件可顯示影像、標題、RTF文字，並可選擇連結至其他內容。

## 使用情況 {#usage}

Teaser元件可讓內容作者輕鬆建立Teaser，以使用影像、標題或RTF文字進一步擴充內容，並連結至進一步內容或其他動作。

範本作者可以使用[設計對話方塊](#design-dialog)來定義建立行動號召和新增連結的選項是否可用，以及停用各種顯示選項。 內容作者可以使用[設定對話方塊](#configure-dialog)來設定影像、定義CTA、設定標題和說明，以及設定個別Teaser的連結。 可以存取[影像元件](image.md)的[編輯對話方塊](image.md#edit-dialog)來修改Teaser影像。

## 版本和相容性 {#version-and-compatibility}

Teaser元件的目前版本是v2，此版本隨2022年2月的核心元件發行版本2.18.0的發佈引入，說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|---|---|---|---|---|
| v2 | - | 相容 | 相容 | 相容 |
| [v1](v1/teaser.md) | 相容 | 相容 | - | 相容 |

## 遠端Assets支援 {#remote-assets}

Teaser元件（截至[版本2.23.2](/help/versions.md)）支援遠端資產。 [設定之後，](/help/developing/remote-assets.md)您可以從Teaser元件的遠端服務中選取資產。

## 範例元件輸出 {#sample-component-output}

若要體驗Teaser元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_teaser)。

### 技術細節 {#technical-details}

您可以在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_teaser_v1)上找到有關Teaser元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

內容作者可以使用設定對話方塊來定義個別Teaser的屬性。 如果選取了[編輯對話方塊](#edit-dialog)以修改Teaser影像。

### 連結標籤 {#links-tab}

![Teaser元件的編輯對話方塊連結索引標籤](/help/assets/teaser-edit-links.png)

Teaser 標題、說明和影像可以從所連結的頁面繼承，也可以從第一個行動號召中所連結的頁面繼承。如果連結或行動號召都未指定，則會從當前的頁面繼承標題、說明和影像。

* **連結** — 此檔案連結至內容頁面、外部URL或頁面錨點。
* **在新標籤中開啟連結** — 如果啟用，將在新的瀏覽器標籤中開啟連結。
* **行動號召** — 此選項可連結至多個目的地。
   * 當繼承Teaser標題、說明或影像時，將使用第一個call-to-action中連結的頁面。

### 文字索引標籤 {#text-tab}

![Teaser元件的編輯對話方塊文字索引標籤](/help/assets/teaser-edit-text.png)

* **前置標題** — 前置標題會顯示在Teaser的標題之前。
* **標題** — 定義要顯示為Teaser標題的標題。
   * **從連結的頁面取得標題** — 勾選後，標題會填入連結頁面的標題。
* **描述** — 定義要顯示為Teaser子標題的描述。
   * **從連結的頁面取得說明** — 勾選後，說明將會填入連結頁面的說明。
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 資產標籤 {#asset-tab}

![Teaser元件的編輯對話方塊影像標籤](/help/assets/teaser-edit-image.png)

* **從頁面**&#x200B;繼承精選影像 — 使用連結頁面的頁面屬性中定義的影像，如果沒有找到，則使用目前頁面。
* **影像資產** — 從[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)拖放資產，或點選&#x200B;**瀏覽**&#x200B;選項，從本機檔案系統上傳。
   * 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下&#x200B;**挑選**&#x200B;以開啟[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)以選取影像。
      * 如果[遠端Assets支援](#remote-assets)已啟用，您有多個選項可挑選資產：
         * 從本機AEM資產庫選取&#x200B;**本機**。
         * **遠端**&#x200B;從AEM執行個體外部的Dynamic Media媒體庫選取。
   * 點選或按一下&#x200B;**編輯**&#x200B;以[在資產編輯器中管理資產](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)的轉譯。
* **協助工具的替代文字** — 此欄位可讓您為視障使用者定義影像的說明。
   * **從頁面**&#x200B;繼承替代文字 — 此選項使用DAM中`dc:description`中繼資料之連結資產值的替代說明，或是使用目前頁面的替代說明（如果未連結資產）。
* **不提供替代文字** — 此選項會將影像標籤為被熒幕閱讀器等輔助技術忽略，以用於影像純粹起裝飾作用或不向頁面傳達額外資訊的情況。

### 樣式索引標籤 {#styles-tab-edit}

Teaser清單元件之編輯對話方塊的![樣式索引標籤](/help/assets/teaser-edit-styles.png)

Teaser元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的選取具有相同的效果。

必須在[設計對話方塊](#design-dialog)中為此元件設定樣式，以便下拉式功能表可用。

## 編輯對話方塊 {#edit-dialog}

Teaser元件將影像演算委派給[影像元件](image.md)。 因此，內容作者可以使用[編輯對話方塊]（影像元件的image.md#edit-dialog）來處理Teaser影像。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義內容作者在使用此元件時具有的Teaser選項。

### Teaser索引標籤 {#teaser-tab}

![Teaser元件的設計對話方塊](/help/assets/teaser-design.png)

* **行動號召**
   * **停用呼叫動作** — 隱藏內容作者的&#x200B;**呼叫動作**&#x200B;選項
* **元素**
   * **隱藏前置標題** — 隱藏內容作者的&#x200B;**前置標題**&#x200B;選項
   * **隱藏標題** — 隱藏內容作者的&#x200B;**標題**&#x200B;選項
      * 選取時，會隱藏&#x200B;**標題型別**
   * **隱藏描述** — 隱藏內容作者的&#x200B;**描述**&#x200B;選項
* **預設標題型別** — 定義Teaser標題使用的H標籤。
* **影像委派** — 資訊性顯示，指出Teaser將影像處理委派給哪個元件。

### 樣式索引標籤 {#styles-tab}

Teaser元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe使用者端資料層 {#data-layer}

Teaser元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
