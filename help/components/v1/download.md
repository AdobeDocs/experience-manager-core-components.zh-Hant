---
title: 下載元件(v1)
description: 核心元件下載元件允許在頁面上建立下載選項。
role: Architect, Developer, Admin, User
exl-id: ebd63522-218d-4784-bea0-1627c64f5230
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# 下載元件(v1) {#download-component}

核心元件下載元件允許在頁面上建立下載選項。

## 使用情況 {#usage}

核心元件下載元件允許在頁面上包含下載選項及其相關資產。

* 可在[設定對話方塊](#configure-dialog)中選取下載選項的內容。
* 可在[設計對話方塊](#design-dialog)中定義下載元件的預設值。

## 版本和相容性 {#version-and-compatibility}

本檔案說明下載元件v1，此版本隨2019年6月的核心元件發行版本2.5.0的發佈引入。

>[!CAUTION]
>
>本檔案說明下載元件v1。
>
>如需目前版本的下載元件的詳細資訊，請參閱[下載元件](/help/components/download.md)檔案。

## 範例元件輸出 {#sample-component-output}

若要體驗下載元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_download_tw)。

## 技術細節 {#technical-details}

在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_download_v1_tw)上可找到有關下載元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義下載專案，以及對於頁面的訪客它會如何表現和顯示。

下載元件之編輯對話方塊的![資產標籤](/help/assets/download-edit-asset.png)

### 資產標籤 {#asset-tab}

選取的下載資產與[影像元件](image-v1.md)的功能非常類似，也同樣運用AEM的DAM。

* **下載資產**
   * 從[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hant)拖放資產，或點選&#x200B;**瀏覽**&#x200B;選項，以從本機檔案系統上傳。
   * 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下&#x200B;**編輯**&#x200B;以[在資產編輯器中管理資產](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=zh-Hant)的轉譯。

### 屬性標籤 {#properties-tab}

下載元件之編輯對話方塊的![屬性標籤](/help/assets/download-edit-properties.png)

* **標題** — 顯示為下載專案的標題
   * **從DAM資產取得標題** — 選取時，標題會自動填入DAM資產的標題。
* **描述** — 顯示為下載專案的描述性子標題
   * **從DAM資產取得說明** — 選取時，說明會自動填入DAM資產的說明。
* **動作文字** — 顯示為下載專案的動作文字
   * 從檔案系統上傳資產時，此欄位為必填欄位。
   * **顯示內嵌** — 選取時，提供的&#x200B;**動作文字**&#x200B;將顯示內嵌。
* **ID** — 此選項可控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些選項可供使用下載元件的內容作者使用。

### 屬性標籤 {#properties-tab-design}

下載元件![&#128279;](/help/assets/download-design.png)的設計對話方塊

* **允許從檔案系統上傳** — 允許內容作者從其本機檔案系統上傳資產作為下載資產。
   * 預設值為未選取。
* **標題型別** — 用於下載元件標題的HTML元素。
   * 如果未選取任何值，預設值為H3。
* **顯示檔案大小** — 選取時，資產的檔案大小將顯示在下載元件中。
   * 預設值已選取。
* **顯示檔案格式** — 選取時，資產的檔案格式將顯示在下載元件中。
   * 預設值已選取。
* **顯示檔案名稱** — 選取時，資產的檔案名稱將顯示在下載元件中。
   * 預設值已選取。

### 樣式索引標籤 {#styles-tab}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
