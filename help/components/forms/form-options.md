---
title: 表單選項元件
description: 核心元件表單選項元件可讓您從各種格式的預先定義選項中選取。
role: Architect, Developer, Admin, User
exl-id: 8a74bd37-9b12-4fa6-bff2-53e337b16251
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: ht
source-wordcount: '546'
ht-degree: 100%

---

# 表單選項元件 {#form-options-component}

「核心元件表單選項元件」可讓您從各種格式的預先定義選項中選取。

## 用途 {#usage}

「核心元件表單選項元件」允許提交以多種不同方式呈現的不同類型選項，其設計用於與[表單容器元件](form-container.md)搭配使用。

選項、標籤和個別選項的呈現方式可由內容編輯者在[設定對話框](#configure-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

「表單選項元件」的目前版本為 v2，此版本於 2018 年 1 月隨著「核心元件」2.0.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-options-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「表單選項元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_form_options_tw)」。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_form_options_v2_tw)有關「表單選項元件」的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義應呈現的選項類型、標籤以及可用的選項。

![表單選項元件的編輯對話框](/help/assets/form-options-edit.png)

* **類型** - 選項的呈現方式
   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **複選下拉式清單**
* **標題** - 將顯示為選項標籤的標題
* **名稱** - 與表單資料一起提交的欄位名稱
* **來源** - 定義選項的位置
   * **本機** - 已在元件內定義
      * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增值，點選或按一下&#x200B;**刪除**&#x200B;按鈕以移除值
         * **值** - 提交表單時，選取選項時所儲存的值
         * **文字** - 顯示於表單上的選項標籤
         * **作用中** - 載入表單時，該選項會標示為已選取
         * **已停用** - 該選項無法選取，但仍會顯示
   * **清單** - 將 AEM 中其他位置定義的靜態清單用於選項
      * **清單** - AEM 中靜態清單的路徑
         * 使用「瀏覽」按鈕來尋找清單資源
   * **資料來源** - 資料來源用於選項
      * **資料來源** - 資料來源的資源類型
* **說明訊息** - 提示使用者可輸入至該欄位的內容
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

## 設計對話框 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

「表單選項元件」支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
