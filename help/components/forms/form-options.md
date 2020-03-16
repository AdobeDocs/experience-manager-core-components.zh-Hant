---
title: 表單選項元件
description: 核心元件表單選項元件允許從各種格式的預定義選項中進行選擇。
translation-type: tm+mt
source-git-commit: 95c0621f5423bfa515fe5e8b693e127ea56b4ae0

---


# 表單選項元件 {#form-options-component}

核心元件表單選項元件允許從各種格式的預定義選項中進行選擇。

## 使用狀況 {#usage}

「核心元件表單選項」元件允許以多種不同方式提交不同類型的選項，並與「表單容器」元件一起 [使用](form-container.md)。

選項、標籤和個別選項的呈現方式可由內容編輯器在「設定」對話方塊中 [定義](#configure-dialog)。

## 版本與相容性 {#version-and-compatibility}

目前的表單選項元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM 雲端服務 |
|--- |--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-options-v1.md) | 相容 | 相容 | 相容 | - |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗「表單選項元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪「元件 [庫」](https://adobe.com/go/aem_cmp_library_form_options)。

### 技術詳細資訊 {#technical-details}

有關表單選項元件的最新技術文 [件可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_options_v2)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者定義應顯示的選項類型、標籤，以及哪些選項可用。

![](/help/assets/screen_shot_2018-01-12at113153.png)

* **類型** -選項的呈現方式
   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **複選下拉式清單**
* **Title**&#x200B;將顯示為選項標籤的標題
* **名稱**&#x200B;隨表單資料提交的欄位名稱
* **源**&#x200B;定義選項的位置
   * **Local** Defined within the component
      * 點選或按一下「 **新增** 」按鈕以新增值， **「刪除** 」以移除值
      * **值**&#x200B;當提交表單時，選取該選項時保存的值
      * **Text**&#x200B;表單上顯示的選項標籤
      * **活動**&#x200B;當表單載入時，選項會標示為已選取
      * **停用**&#x200B;此選項無法選取，但仍顯示
      * **清單** AEM中其他地方定義的靜態清單會用於選項
         * **清單** AEM中靜態清單的路徑
            * 使用「瀏覽」按鈕查找清單資源
      * **資料來源**&#x200B;資料來源用於選項
         * **資料源**&#x200B;資料源的資源類型
* **說明訊息**：使用者在欄位中可輸入內容的提示

## 設計對話框 {#design-dialog}

### 樣式標籤 {#styles-tab}

「表單選項」元件支援AEM [Style系統](/help/get-started/authoring.md#component-styling)。
