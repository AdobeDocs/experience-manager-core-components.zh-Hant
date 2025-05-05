---
title: 表單選項元件
description: 核心元件表單選項元件可讓您從各種格式的預先定義選項中進行選取。
role: Architect, Developer, Admin, User
exl-id: 8a74bd37-9b12-4fa6-bff2-53e337b16251
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---

# 表單選項元件 {#form-options-component}

核心元件表單選項元件可讓您從各種格式的預先定義選項中進行選取。

## 使用情況 {#usage}

核心元件表單選項元件允許提交以多種不同方式呈現的不同型別的選項，並且旨在與[表單容器元件](form-container.md)搭配使用。

選項、標籤和個別選項的呈現可由內容編輯者在[設定對話方塊](#configure-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

表單選項元件的目前版本是v2，此版本隨2018年1月的核心元件2.0.0版的發佈引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-options-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗表單選項元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_form_options_tw)。

### 技術細節 {#technical-details}

您可以在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_form_options_v2_tw)上找到表單選項元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義應顯示的選項型別、標籤以及可用的選項。

![表單選項元件的編輯對話方塊](/help/assets/form-options-edit.png)

* **型別** — 如何顯示選項
   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **多重選取下拉式清單**
* **標題** — 將顯示為選項標籤的標題
* **名稱** — 與表單資料共同提交的欄位名稱
* **Source** — 定義選項的位置
   * **本機** — 已在元件中定義
      * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增值，**刪除**&#x200B;以移除值
         * **值** — 提交表單時選取此選項時儲存的值
         * **文字** — 表單上顯示的選項標籤
         * **作用中** — 表單載入時，選項會標示為已選取
         * **已停用** — 選項不可選取，但仍會顯示
   * **清單** - AEM中其他地方定義的靜態清單用於選項
      * **清單** - AEM中靜態清單的路徑
         * 使用瀏覽按鈕來尋找清單資源
   * **資料來源** — 資料來源用於選項
      * **資料來源** — 資料來源的資源型別
* **說明訊息** — 使用者可在欄位中輸入的內容提示
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

## 設計對話方塊 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

表單選項元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
