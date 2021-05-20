---
title: 表單選項元件
description: 核心元件表單選項元件允許以各種格式從預先定義的選項中進行選擇。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 8a74bd37-9b12-4fa6-bff2-53e337b16251
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 2%

---

# 表單選項元件{#form-options-component}

核心元件表單選項元件允許以各種格式從預先定義的選項中進行選擇。

## 使用狀況 {#usage}

核心元件表單選項元件允許以多種不同方式呈現的不同類型選項的提交，並打算與[表單容器元件](form-container.md)一起使用。

選項、標籤和單個選項的顯示可由[配置對話框](#configure-dialog)中的內容編輯器定義。

## 版本和相容性{#version-and-compatibility}

目前的表單選項元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，本檔案已詳述。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-options-v1.md) | 相容 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗表單選項元件，並查看其設定選項的範例以及HTML和JSON輸出，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_form_options)。

### 技術詳細資訊{#technical-details}

如需表單選項元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_form_options_v2)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

「設定」對話方塊可讓內容作者定義應呈現的選項類型、標籤，以及可用的選項。

![表單選項元件的編輯對話框](/help/assets/form-options-edit.png)

* **類型**  — 如何呈現選項
   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **複選下拉式清單**
* **Title**  — 將顯示為選項標籤的標題
* **名稱**  — 使用表單資料提交的欄位名稱
* **來源**  — 定義選項的位置
   * **本機**  — 在元件中定義
      * 點選或按一下&#x200B;**Add**&#x200B;按鈕以新增值，**Delete**&#x200B;以移除值
         * **值**  — 提交表單時選取該選項時儲存的值
         * **文字**  — 表單上顯示之選項的標籤
         * **作用中**  — 當表單載入時，選項會標示為已選取
         * **已停用**  — 無法選取選項，但仍顯示
   * **清單**  — 選項會使用AEM中其他位置定義的靜態清單
      * **清單**  - AEM中靜態清單的路徑
         * 使用Browse按鈕查找清單資源
   * **資料來源**  — 使用資料來源作為選項
      * **資料來源**  — 資料來源的資源類型
* **說明訊息**  — 可在欄位中輸入內容的使用者提示
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

## 設計對話框{#design-dialog}

### 樣式標籤{#styles-tab}

表單選項元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
