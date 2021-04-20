---
title: 下載元件
description: 核心元件下載元件可讓您在頁面上建立下載選項。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 1%

---


# 下載元件{#download-component}

核心元件下載元件可讓您在頁面上建立下載選項。

## 使用狀況 {#usage}

核心元件下載元件可讓下載選項及其相關資產包含在頁面上。

* 可在[configure dialog](#configure-dialog)中選擇下載選項的屬性。
* 可在[design對話框](#design-dialog)中定義下載元件的預設值。

## 版本和相容性{#version-and-compatibility}

目前的下載元件版本為v1，此版本於2019年6月隨核心元件2.5.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗下載元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_download)。

## 技術詳細資訊{#technical-details}

有關下載元件[的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_download_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

「設定」對話方塊可讓內容作者定義下載項目，以及該項目的行為和顯示方式，讓頁面的訪客檢視。

![「下載元件」編輯對話方塊的「資產」標籤](/help/assets/download-edit-asset.png)

### 資產標籤{#asset-tab}

選擇下載資產與[影像元件](image.md)的功能非常相似，同樣也利用AEMDAM。

* **下載資產**
   * 從[資產瀏覽器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)拖放資產，或點選&#x200B;**browse**&#x200B;選項，從本機檔案系統上傳。
   * 點選或按一下&#x200B;**Clear**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下「編輯&#x200B;****」，在資產編輯器中管理資產](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)的轉譯。[

### 屬性頁籤{#properties-tab}

![下載元件編輯對話框的屬性頁籤](/help/assets/download-edit-properties.png)

* **標題** -顯示為下載項目的標題
   * **從DAM資產取得標題** -選取此選項時，標題會自動填入DAM資產的標題。
* **說明** -顯示為下載項目的描述性子標題
   * **從DAM資產取得說明** -選取此選項時，描述會自動填入DAM資產的說明。
* **動作文字** -顯示為下載項目的動作文字
   * 從檔案系統上傳資產時，此欄位為必填欄位。
   * **內嵌顯示** -選取提供的動作文字 **顯示** 內嵌時。
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義使用下載元件的內容作者可用的選項。

### 屬性頁籤{#properties-tab-design}

![下載元件的設計對話方塊](/help/assets/download-design.png)

* **允許從檔案系統上傳** -允許內容作者從其本機檔案系統上傳資產作為下載資產。
   * 未選取預設值。
* **標題類型** -用於下載元件標題的HTML元素。
   * 如果未選取任何值，則預設值為H3。
* **顯示檔案大小** -選取後，資產的檔案大小會顯示在下載元件中。
   * 選取預設值。
* **顯示檔案格式** -選中後，資產的檔案格式將顯示在下載元件中。
   * 選取預設值。
* **顯示檔案名** -選中後，資產的檔案名將顯示在下載元件中。
   * 選取預設值。

### 樣式標籤{#styles-tab}

映像元件支AEM持[樣式系統](/help/get-started/authoring.md#component-styling)。
