---
title: 表單容器元件
description: 核心元件表單容器元件可讓您建立簡單的提交表單。
translation-type: tm+mt
source-git-commit: 95c0621f5423bfa515fe5e8b693e127ea56b4ae0

---


# 表單容器元件 {#form-container-component}

核心元件表單容器元件可讓您建立簡單的提交表單。

## 使用狀況 {#usage}

「容器元件」表單支援簡單的WCM表單，並使用巢狀結構允許額外的表單元件，以建立簡單資訊提交表單和功能。

使用「設 [定」對話方塊](#configure-dialog) ，內容編輯器可定義表單提交所觸發的動作、應儲存已提交內容的位置，以及是否應觸發工作流程。 範本作者可使用設計 [對話方塊](#design-dialog) ，定義允許的元件及其對應，類似範本編輯器中標準版面 [容器的設計對話方塊](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。

>[!NOTE]
>
>核心元件表單容器元件僅支援使用核心元件表單元件（按鈕、文字、隱藏等）。 不支 [援在核心元件](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) （或容器）內使用基礎元件（或反之）表單元件。

## 版本與相容性 {#version-and-compatibility}

目前的表單容器元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM 雲端服務 |
|--- |--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-container-v1.md) | 相容 | 相容 | 相容 | - |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗「表單容器元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](https://adobe.com/go/aem_cmp_library_form_container)。

## 技術詳細資訊 {#technical-details}

有關表單容器元件的最新技術文 [件可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_container_v2)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者定義在提交元件時要執行的動作。

![](/help/assets/screen_shot_2018-01-12at122046.png)

根據選取的「 **動作類型**」，容器中的可用選項將會變更。 可用的操作類型包括：

* [郵件](#mail)
* [存放區內容](#store-content)
* [提交訂單](#submit-order)
* [更新訂單](#update-order)

不論類型為何，都會有一 [般設定](#general-settings) ，適用於每個動作。

### 郵件 {#mail}

提交表單時，郵件動作類型會傳送電子郵件給指定的收件者。

![](/help/assets/screen_shot_2018-01-12at122554.png)

* **主旨**&#x200B;在提交表單時傳送的電子郵件主旨
* **寄件**&#x200B;者在提交表單時傳送的電子郵件寄件者電子郵件地址
* **收**&#x200B;件者在提交表單時會收到電子郵件的地址

   * 點選或按一下「 **新增** 」按鈕以新增其他位址
   * 點選或按一下「刪 **除** 」按鈕以移除電子郵件地址
* **CC**&#x200B;將收到表單提交時傳送之電子郵件之碳副本的收件人地址
   * 點選或按一下「 **新增** 」按鈕以新增其他位址
   * 點選或按一下「刪 **除** 」按鈕以移除電子郵件地址

### 存放區內容 {#store-content}

提交表單時，表單的內容將儲存在指定的儲存庫位置。

![](/help/assets/screen_shot_2018-01-12at122538.png)

* **內容路徑**&#x200B;內容存放庫路徑，其中已提交內容儲存
* **檢視資料**&#x200B;點選或按一下，將儲存的已提交資料檢視為JSON
* **啟動工作**&#x200B;流程設定在表單提交時，將儲存的內容當做裝載來啟動工作流程

### 提交訂單 {#submit-order}

提交表格後，將會提交訂單。

![](/help/assets/chlimage_1-3.png)

### 更新訂單 {#update-order}

提交表單時，訂單將會更新。

![](/help/assets/chlimage_1-4.png)

### 一般設定 {#general-settings}

無論選取的動作類型為何，都可以定義感謝頁面。

![](/help/assets/chlimage_1-5.png)

在表單提交完成後，會將使用者重新導向至指定的頁面。

* 使用「選取對話方塊」，在AEM中選取資源。
* 如果感謝頁面不在AEM中，請指定絕對URL。 非絕對URL將會相對於AEM進行解譯。
* 留空可在提交後重新顯示表單。

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者為容器定義允許的元件及其對應，類似範本編輯器中標準版面 [容器的設計對話方塊](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。
