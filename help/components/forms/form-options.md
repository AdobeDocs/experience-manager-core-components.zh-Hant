---
title: 表單選項元件
description: 「核心元件表單」選項元件允許以各種格式從預定義選項中進行選擇。
role: Architect, Developer, Admin, User
exl-id: 8a74bd37-9b12-4fa6-bff2-53e337b16251
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# 表單選項元件 {#form-options-component}

「核心元件表單選項」元件允許以各種格式從預定義選項中進行選擇。

## 使用狀況 {#usage}

「核心元件表單選項」元件允許以多種不同方式提交不同類型的選項，並與 [窗體容器元件](form-container.md)。

選項、標籤和單個選項的演示可由中的內容編輯器定義 [配置對話框](#configure-dialog)。

## 版本和相容性 {#version-and-compatibility}

表單選項元件的當前版本為v2，該版本於2018年1月隨核心元件2.0.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |
| [v1](/help/components/v1/form-options-v1.md) | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗「表單選項」元件，並查看其配置選項示例以及HTML和JSON輸出，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_form_options)。

### 技術詳細資訊 {#technical-details}

有關表單選項元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_options_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

「配置」對話框允許內容作者定義應顯示的選項類型、標籤以及哪些選項可用。

![表單選項元件的編輯對話框](/help/assets/form-options-edit.png)

* **類型**  — 購股權之呈列方式
   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **複選下拉式清單**
* **標題**  — 將顯示為選項標籤的標題
* **名稱**  — 使用表單資料提交的欄位的名稱
* **源**  — 定義選項的位置
   * **本地**  — 在元件內定義
      * 點擊或按一下 **添加** 按鈕以添加值， **刪除** 刪除值
         * **值**  — 提交表單時選擇該選項時保存的值
         * **文本**  — 窗體上顯示的選項的標籤
         * **活動**  — 在載入表單時，選項被標籤為已選
         * **已禁用**  — 該選項不可選，但仍顯示
   * **清單**  — 在中其他位置定義的靜態AEM清單用於選項
      * **清單**  — 中靜態清單的路AEM徑
         * 使用「瀏覽」按鈕查找清單資源
   * **資料源**  — 資料源用於選項
      * **資料源**  — 資料源的資源類型
* **幫助消息**  — 提示用戶可在欄位中輸入的內容
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

## 設計對話框 {#design-dialog}

### 樣式頁籤 {#styles-tab}

表單選項元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
