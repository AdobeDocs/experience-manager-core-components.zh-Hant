---
title: 下載元件
description: 核心元件下載元件可在頁面上建立下載選項。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 48e7ade0-b849-4d1f-b836-51196e5ac507
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 1%

---

# 下載元件{#download-component}

核心元件下載元件可在頁面上建立下載選項。

## 使用狀況 {#usage}

核心元件下載元件可讓您在頁面上包含下載選項及其相關資產。

* 可在[配置對話框](#configure-dialog)中選擇下載選項的屬性。
* 可在[design對話方塊](#design-dialog)中定義下載元件的預設值。

## 版本和相容性{#version-and-compatibility}

目前的下載元件版本為v1，已於2019年6月隨核心元件2.5.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗下載元件以及查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_download)。

## 技術詳細資訊{#technical-details}

若需下載元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_download_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

「設定」對話方塊可讓內容作者定義下載項目，以及該項目的行為和顯示方式，供造訪頁面的訪客使用。

![下載元件編輯對話方塊的資產標籤](/help/assets/download-edit-asset.png)

### 資產標籤{#asset-tab}

選擇下載資產與[影像元件](image.md)的功能非常類似，同樣地會運用AEM DAM。

* **下載資產**
   * 從[資產瀏覽器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)拖放資產，或點選&#x200B;**browse**&#x200B;選項，從本機檔案系統上傳。
   * 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下「**編輯** 」，在資產編輯器中[管理資產](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)的轉譯。

### 屬性頁簽{#properties-tab}

![下載元件編輯對話框的屬性頁簽](/help/assets/download-edit-properties.png)

* **標題**  — 顯示為下載項目的標題
   * **從DAM資產取得標題**  — 選取此選項時，標題會自動填入DAM資產的標題。
* **說明**  — 顯示為下載項目的描述性子標題
   * **從DAM資產取得說明**  — 選取此選項時，說明會自動填入DAM資產的說明。
* **動作文字**  — 顯示為下載項目的動作文字
   * 從檔案系統上傳資產時，此欄位為必填欄位。
   * **內嵌顯示**  — 選取提供的動作時，文字 **** 會內嵌顯示。
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義使用下載元件的內容作者可用的選項。

### 屬性頁簽{#properties-tab-design}

![下載元件的設計對話框](/help/assets/download-design.png)

* **允許從檔案系統上傳**  — 允許內容作者從其本機檔案系統上傳資產作為下載資產。
   * 未選取預設值。
* **標題類型**  — 用於下載元件標題的HTML元素。
   * 如果未選取任何值，則預設值為H3。
* **顯示檔案大** 小 — 選取時，下載元件中會顯示資產的檔案大小。
   * 已選取預設值。
* **顯示檔案格式**  — 選取時，下載元件中會顯示資產的檔案格式。
   * 已選取預設值。
* **顯示檔案名稱**  — 選取時，下載元件中會顯示資產的檔案名稱。
   * 已選取預設值。

### 樣式標籤{#styles-tab}

影像元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
