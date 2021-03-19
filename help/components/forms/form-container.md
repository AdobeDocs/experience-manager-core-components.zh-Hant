---
title: 表單容器元件
description: 核心元件表單容器元件可讓您建立簡單的提交表單。
role: 架構師、開發人員、管理員、商業從業人員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---


# 表單容器元件{#form-container-component}

核心元件表單容器元件可讓您建立簡單的提交表單。

## 使用狀況 {#usage}

「容器元件」表單支援簡單的WCM表單，並使用巢狀結構允許額外的表單元件，以建立簡單資訊提交表單和功能。

使用[configure dialog](#configure-dialog)，內容編輯器可定義由表單提交觸發的動作、應處理提交的URl，以及是否應觸發工作流程。 範本作者可使用[設計對話方塊](#design-dialog)來定義允許的元件及其對應，類似範本編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中[標準版面容器的設計對話方塊。

>[!NOTE]
>
>核心元件表單容器元件僅支援使用核心元件表單元件（按鈕、文字、隱藏等）。 不支援在核心元件表單容器內使用[foundation元件](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html)表單元件（反之亦然）。

## 版本和相容性{#version-and-compatibility}

目前的表單容器元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-container-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗「表單容器元件」，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_form_container)。

## 技術詳細資訊{#technical-details}

有關表單容器元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_form_container_v2)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

「設定」對話方塊可讓內容作者定義在提交元件時要執行的動作。

視選取的&#x200B;**動作類型**&#x200B;而定，容器中的可用選項將會變更。 可用的操作類型包括：

* [貼文表單資料](#post-data)
* [郵件](#mail)
* [存放區內容](#store-content)

無論類型如何，都有[一般設定](#general-settings)適用於每個動作。

### 貼文表單資料{#post-data}

提交表單時，貼文表單資料動作類型會將提交的資料以JSON形式傳遞給第三方以進行處理。

![表單容器元件編輯對話方塊中的表單資料選項](/help/assets/form-container-edit-post.png)

* **端點** -將處理資料的完全合格HTTPS服務
* **錯誤訊息** -如果提交失敗，則顯示訊息

>[!TIP]
>系統管理員可以調整其他逾時選項，以處理轉送表單資料的處理。 [如需詳細資訊，請參閱GitHub的技術檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/actions/rpc)

### 郵件 {#mail}

提交表單時，郵件動作類型會傳送電子郵件給指定的收件者。

![表單容器元件編輯對話方塊中的郵件選項](/help/assets/form-container-edit-mail.png)

* **主旨** -提交表單時將傳送的電子郵件主旨
* **寄件者** -在提交表單時傳送的電子郵件寄件者電子郵件地址
* **收件人** -提交表單時收到電子郵件的收件人地址
   * 點選或按一下「新增&#x200B;****」按鈕以新增其他位址
   * 點選或按一下&#x200B;**Delete**&#x200B;按鈕以移除電子郵件地址
* **CC**  —— 收到表單提交時傳送之電子郵件碳副本的收件人地址
   * 點選或按一下「新增&#x200B;****」按鈕以新增其他位址
   * 點選或按一下&#x200B;**Delete**&#x200B;按鈕以移除電子郵件地址

### 存放區內容 {#store-content}

提交表單時，表單的內容將儲存在指定的儲存庫位置。

![在表單容器的編輯對話方塊中儲存內容選項](/help/assets/form-container-edit-store.png)

* **內容路徑** -內容儲存庫路徑，其中已提交內容儲存
* **檢視資料** -點選或按一下，將儲存的已提交資料檢視為JSON
* **開始工作流程** -設定在表單提交時，將儲存的內容當做裝載來啟動工作流程

>[!NOTE]
>
>為了簡化用戶資料的管理並強制分散關注點，通常不建議將用戶生成的內容儲存在儲存庫中。
>
>請改用[Post Form Data](#post-data)動作類型，將使用者內容傳遞給專屬服務供應商。

### 一般設定 {#general-settings}

無論選取的動作類型為何，都可以定義感謝頁面。

![表單容器元件編輯對話方塊中的一般選項](/help/assets/form-container-edit-general.png)

* **感謝頁面** -在表單提交完成後，將使用者重新導向至指定頁面。
   * 使用「選擇」對話框在中選擇資源AEM。
   * 如果感謝頁面未在AEM中，請指定絕對URL。 非絕對URL會相對於進行解AEM讀。
   * 留空可在提交後重新顯示表單。
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者為容器定義允許的元件及其對應，類似範本編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中[標準版面容器的設計對話方塊。

### 樣式標籤{#styles-tab}

表單容器元件AEM支援[樣式系統](/help/get-started/authoring.md#component-styling)。
