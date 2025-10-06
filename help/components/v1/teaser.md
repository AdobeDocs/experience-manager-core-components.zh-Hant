---
title: Teaser 元件 (v1)
description: Teaser 元件可顯示影像、標題、RTF 文字，並可選擇性連結至更多內容。
role: Architect, Developer, Admin, User
exl-id: 48e56938-660a-43e7-9e62-8069283ae73f
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '722'
ht-degree: 100%

---


# Teaser 元件 (v1) {#teaser-component}

「核心元件 Teaser 元件」可顯示影像、標題、RTF 文字，並可選擇性連結至更多內容。

## 用途 {#usage}

「Teaser 元件」可讓內容作者使用影像、標題或 RTF 文字輕鬆建立更多內容的 Teaser，並連結至更多內容或其他動作。

範本作者可使用[設計對話框](#design-dialog)，定義建立行動號召和新增連結的選項是否可用，以及停用各種顯示選項。內容作者可使用[設定對話框](#configure-dialog)設定影像、定義 CTA、設定標題與說明，並設定個別 Teaser 的連結。透過存取[影像元件](image-v1.md)的[編輯對話框](image-v1.md#edit-dialog)，即可修改 Teaser 影像。

## 版本和相容性 {#version-and-compatibility}

本文件說明 Teaser 元件 v1，最初於 2018 年 7 月隨著核心元件 2.1.0 版發行導入。

>[!CAUTION]
>
>本文件說明 Teaser 元件 v1。
>
>如需 Teaser 元件目前版本的詳細資訊，請參閱 [Teaser 元件](/help/components/teaser.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「Teaser 元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_teaser)」。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_teaser_v1)有關 Teaser 元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

內容作者可以使用設定對話框定義個別 Teaser 的屬性。若已選取 Teaser 影像，同樣可透過[編輯對話框](#edit-dialog)修改。

### 影像 {#image}

![Teaser 元件的編輯對話框影像索引標籤](/help/assets/teaser-edit-image.png)

* **影像資產**
   * 從[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)拖曳資產，或點選&#x200B;**瀏覽**&#x200B;選項，以從本機檔案系統上傳。
   * 點選或按一下&#x200B;**「清除」**，取消選取目前選取的影像。
   * 點選或按一下&#x200B;**編輯**，以在 Asset Editor 中[管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)。

>[!NOTE]
>
>[Dynamic Media 功能](image-v1.md#dynamic-media)目前無法在 Teaser 元件中使用。

### 文字 {#text}

![Teaser 元件的編輯對話框文字索引標籤](/help/assets/teaser-edit-text.png)

* **前置標題** - 前置標題將顯示在 Teaser 標題之前。
* **標題** - 定義要顯示為 Teaser 標題的標題。
   * **從連結的頁面取得標題** - 勾選後，標題將填入連結頁面的標題。
* **說明** - 定義要顯示為 Teaser 副標題的說明。
   * **從連結頁面取得說明** - 勾選後，說明將填入連結頁面的說明。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

### 連結與動作 {#links-actions}

![Teaser 元件的編輯對話框連結索引標籤](/help/assets/teaser-edit-link.png)

* **連結** - 已套用至 Teaser 的連結。使用路徑瀏覽器來選取連結目標。
* **啟用行動號召** - 勾選後，會啟用行動號召的定義。清單中的第一個行動號召連結會用作其他 Teaser 元素的連結。

## 編輯對話框 {#edit-dialog}

Teaser 元件將影像轉譯委派給[影像元件](image-v1.md)。因此，內容作者可使用影像元件的[編輯對話框](image-v1.md#edit-dialog)來調整 Teaser 影像。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義內容作者在使用此元件時具備的 Teaser 選項。

### Teaser 索引標籤 {#teaser-tab}

![Teaser 元件的設計對話框](/help/assets/teaser-design.png)

* **行動號召**
   * **停用行動號召** - 對內容作者隱藏&#x200B;**行動號召**&#x200B;選項
* **元素**
   * **隱藏前置標題** - 對內容作者隱藏「**前置標題**」選項
   * **隱藏標題** - 對內容作者隱藏「**標題**」選項
      * 選取後，**標題類型**&#x200B;會隱藏
   * **隱藏說明** - 對內容作者隱藏「**說明**」選項
* **標題類型** - 定義 Teaser 標題所使用的 H 標記。
* **連結**
   * **不要連結影像** - 選取後，不會連結 Teaser 影像
   * **不要連結標題** - 選取後，不會連結 Teaser 標題
* **影像委派** - 資訊性顯示，指示 Teaser 要委派影像處理的元件。

### 樣式索引標籤 {#styles-tab}

Teaser 元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「Teaser 元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
