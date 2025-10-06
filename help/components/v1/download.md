---
title: 下載元件 (v1)
description: 核心元件下載元件允許在頁面上建立下載選項。
role: Architect, Developer, Admin, User
exl-id: ebd63522-218d-4784-bea0-1627c64f5230
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '621'
ht-degree: 100%

---


# 下載元件 (v1) {#download-component}

核心元件下載元件允許在頁面上建立下載選項。

## 用途 {#usage}

核心元件下載元件允許在頁面上包含下載選項及其相關資產。

* 可在[設定對話框](#configure-dialog)中選取下載選項的屬性。
* 可在[設計對話框](#design-dialog)中定義下載元件的預設值。

## 版本和相容性 {#version-and-compatibility}

本文件說明下載元件 v1，最初於 2019 年 6 月隨著核心元件 2.5.0 版發行導入。

>[!CAUTION]
>
>本文件說明下載元件 v1。
>
>如需下載元件目前版本的詳細資訊，請參閱[下載元件](/help/components/download.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「下載元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_download_tw)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_download_v1_tw)有關下載元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義下載項目，以及其對頁面訪客的行為與顯示方式。

![下載元件編輯對話框的資產索引標籤](/help/assets/download-edit-asset.png)

### 資產索引標籤 {#asset-tab}

下載資產的選取與[影像元件](image-v1.md)的功能非常類似，也同樣運用 AEM 的 DAM。

* **下載資產**
   * 從[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hant)拖曳資產，或點選&#x200B;**瀏覽**&#x200B;選項，以從本機檔案系統上傳。
   * 點選或按一下&#x200B;**「清除」**，取消選取目前選取的影像。
   * 點選或按一下&#x200B;**編輯**，以在 Asset Editor 中[管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=zh-Hant)。

### 屬性索引標籤 {#properties-tab}

![下載元件編輯對話框的屬性索引標籤](/help/assets/download-edit-properties.png)

* **標題** - 顯示為下載項目標題
   * **從 DAM 資產取得標題** - 選取後，標題會自動填入 DAM 資產的標題。
* **說明** - 顯示為下載項目的說明性副標題
   * **從 DAM 資產取得說明** - 選取後，說明會自動填入 DAM 資產的說明。
* **動作文字** - 顯示為下載項目的動作文字
   * 從檔案系統上傳資產時，此欄位為必填欄位。
   * **顯示內嵌** - 選取後，提供的&#x200B;**動作文字**&#x200B;將顯示內嵌。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可為使用下載元件的內容作者定義可用選項。

### 屬性索引標籤 {#properties-tab-design}

![下載元件的設計對話框](/help/assets/download-design.png)

* **允許從檔案系統上傳** - 允許內容作者從其本機檔案系統上傳資產作為下載資產。
   * 預設值為未選取。
* **標題類型** - HTML 元素用作下載元件標題。
   * 如果未選取任何值，預設值為 H3。
* **顯示檔案大小** - 選取後，資產的檔案大小將顯示在下載元件中。
   * 預設值已選取。
* **顯示檔案格式** - 選取後，資產的檔案格式將顯示在下載元件中。
   * 預設值已選取。
* **顯示檔案名稱** - 選取後，資產的檔案名稱將顯示在下載元件中。
   * 預設值已選取。

### 樣式索引標籤 {#styles-tab}

影像元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
