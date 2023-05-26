---
title: 表單選項元件
description: 核心元件表單選項元件可讓您從各種格式的預先定義選項中進行選取。
role: Architect, Developer, Admin, User
exl-id: 8a74bd37-9b12-4fa6-bff2-53e337b16251
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# 表單選項元件 {#form-options-component}

「核心元件表單選項」元件可讓您從各種格式的預先定義選項中進行選取。

## 使用狀況 {#usage}

核心元件表單選項元件可讓您提交不同型別的選項（這些選項會以多種不同方式呈現），並且此元件旨在與 [表單容器元件](form-container.md).

選項、標籤和個別選項的呈現可由內容編輯者在 [設定對話方塊](#configure-dialog).

## 版本和相容性 {#version-and-compatibility}

表單選項元件的目前版本是v2，此版本隨2018年1月的核心元件2.0.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容於<br>[版本2.17.4](/help/versions.md) 和先前的 | 相容 | 相容 |
| [v1](/help/components/v1/form-options-v1.md) | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗表單選項元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_form_options).

### 技術細節 {#technical-details}

有關表單選項元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_options_v2).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

「設定」對話方塊可讓內容作者定義應顯示的選項型別、標籤以及可用的選項。

![表單選項元件的「編輯」對話方塊](/help/assets/form-options-edit.png)

* **型別**  — 如何顯示選項
   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **複選下拉式清單**
* **標題**  — 將顯示為選項標籤的標題
* **名稱**  — 與表單資料共同提交的欄位名稱
* **來源**  — 定義選項的位置
   * **本機**  — 在元件中定義
      * 點選或按一下 **新增** 按鈕以新增值， **刪除** 以移除值
         * **值**  — 提交表單時選取該選項時儲存的值
         * **文字**  — 表單上顯示之選項的標籤
         * **作用中**  — 表單載入時，選項會標籤為已選取
         * **已停用**  — 選項不可選取，但仍會顯示
   * **清單** - AEM中其他地方定義的靜態清單用於選項
      * **清單** - AEM中靜態清單的路徑
         * 使用瀏覽按鈕來尋找清單資源
   * **資料來源**  — 資料來源用於選項
      * **資料來源**  — 資料來源的資源型別
* **說明訊息**  — 使用者可在欄位中輸入的內容的提示
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

## 設計對話方塊 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

表單選項元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
