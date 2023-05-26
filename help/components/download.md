---
title: 下載元件
description: 核心元件下載元件允許在頁面上建立下載選項。
role: Architect, Developer, Admin, User
exl-id: 48e7ade0-b849-4d1f-b836-51196e5ac507
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 1%

---

# 下載元件{#download-component}

核心元件下載元件允許在頁面上建立下載選項。

## 使用狀況 {#usage}

核心元件下載元件允許在頁面上包含下載選項及其相關資產。

* 下載選項的屬性可在 [設定對話方塊](#configure-dialog).
* 下載元件的預設值可在 [設計對話方塊](#design-dialog).

## 版本和相容性 {#version-and-compatibility}

下載元件的目前版本是v2，此版本隨2022年2月的核心元件2.18.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v2 | - | 相容 | 相容 |
| [v1](v1/download.md) | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗下載元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_download).

## 技術細節 {#technical-details}

有關下載元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_download_v2).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義下載專案，以及對於頁面的訪客它會如何表現和顯示。

![下載元件「編輯」對話方塊的「資產」索引標籤](/help/assets/download-edit-asset.png)

### 資產標籤 {#asset-tab}

選取的下載資產與 [影像元件](image.md) 且同樣運用AEM DAM。

* **下載資產**
   * 從拖放資產 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點選 **瀏覽** 從本機檔案系統上傳的選項。
   * 點選或按一下 **清除** 以取消選取目前選取的影像。
   * 點選或按一下 **編輯** 至 [管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 在資產編輯器中。

### 屬性標籤 {#properties-tab}

![下載元件「編輯」對話方塊的「屬性」標籤](/help/assets/download-edit-properties.png)

* **標題**  — 顯示為下載專案的標題
   * **從DAM資產取得標題**  — 選取後，標題會自動填入DAM資產的標題。
* **說明**  — 顯示為下載專案的描述性小標題
   * **從DAM資產取得說明**  — 選取後，說明會自動填入DAM資產的說明。
* **動作文字**  — 顯示為下載專案的動作文字
   * 從檔案系統上傳資產時，此欄位是必要的。
   * **顯示內嵌**  — 選取時，提供 **動作文字** 將顯示內嵌。
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 樣式索引標籤 {#styles-tab-edit}

![下載元件「編輯」對話方塊的「樣式」索引標籤](/help/assets/download-edit-styles.png)

下載元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling).

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的效果相同。

必須在以下位置為此元件設定樣式： [設計對話方塊](#design-dialog) 讓下拉式功能表可供使用。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些選項可供使用下載元件的內容作者使用。

### 屬性標籤 {#properties-tab-design}

![下載元件的「設計」對話方塊](/help/assets/download-design.png)

* **允許從檔案系統上傳**  — 允許內容作者從其本機檔案系統上傳資產作為下載資產。
   * 預設值為未選取。
* **標題型別**  — 用於下載元件標題的HTML元素。
   * 如果未選取任何值，預設值為H3。
* **顯示檔案大小**  — 選取時，資產的檔案大小將顯示在下載元件中。
   * 預設值已選取。
* **顯示檔案格式**  — 選取後，資產的檔案格式將顯示在下載元件中。
   * 預設值已選取。
* **顯示檔案名稱**  — 選取時，資產的檔案名稱將顯示在下載元件中。
   * 預設值已選取。

### 樣式索引標籤 {#styles-tab}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
