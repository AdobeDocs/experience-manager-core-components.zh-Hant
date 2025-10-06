---
title: 表單容器元件
description: 透過「核心元件表單容器元件」，可建立簡易的提交表單。
role: Architect, Developer, Admin, User
exl-id: 552f9dd5-6a3a-42d9-9969-e62a1f36e811
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: ht
source-wordcount: '914'
ht-degree: 100%

---

# 表單容器元件 {#form-container-component}

透過「核心元件表單容器元件」，可建立簡易的提交表單。

## 用途 {#usage}

表單容器元件支援簡易的 WCM 表單，並使用巢狀結構允許額外的表單元件，藉以建立易於使用的資料提交表單和功能。

使用[設定對話框](#configure-dialog) ，內容編輯者可定義表單提交所觸發的動作、應處理提交的 URL，以及是否應觸發工作流程。範本作者可以使用[設計對話框](#design-dialog)定義允許的元件及其對應，類似於[範本編輯器中標準版面容器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)的設計對話框。

>[!NOTE]
>
>核心元件表單容器元件僅支援使用核心元件表單元件 (按鈕、文字、隱藏等)。不支援在核心元件表單容器中使用[基礎元件](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html?lang=zh-Hant)表單元件 (反之亦然)。

## 版本和相容性 {#version-and-compatibility}

表單容器元件的目前版本為 v2，此版本於 2018 年 1 月隨著核心元件 2.0.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v2 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-container-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「表單容器元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_form_container_tw)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_form_container_v2_tw)有關表單容器元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義提交元件時所採取的動作。

容器內的可用選項會因所選取的&#x200B;**動作類型**&#x200B;而變更。可用的動作類型包括：

* [張貼表單資料](#post-data)
* [郵件](#mail)
* [存放區內容](#store-content)

不論類型為何，都有適用於每個動作的[一般設定](#general-settings)。

### 張貼表單資料 {#post-data}

提交表單時，張貼表單資料動作類型會將提交的資料以 JSON 形式，傳遞至第三方進行處理。

![表單容器元件編輯對話框中的張貼表單資料選項](/help/assets/form-container-edit-post.png)

* **端點** - 將處理資料的完整 HTTPS 服務
* **錯誤訊息** - 提交失敗時顯示的訊息

>[!TIP]
>系統管理員可以調整其他逾時選項，以處理轉寄的表單資料。[如需詳細資訊，請參閱 GitHub 上的技術文件。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/actions/rpc)

### 郵件 {#mail}

提交表單時，郵件動作類型將傳送電子郵件給指定的收件者。

![表單容器元件編輯對話框的郵件選項](/help/assets/form-container-edit-mail.png)

* **主旨** - 提交表單時，將傳送的電子郵件主旨
* **寄件者** - 提交表單時，將傳送的電子郵件的寄件者電子郵件地址
* **收件者** - 提交表單時，將接收電子郵件的收件者地址
   * 點選或按一下「**新增**」按鈕，以新增其他地址
   * 點選或按一下「**刪除**」按鈕，以移除電子郵件地址
* **副本** - 提交表單時，將接收所傳送之電子郵件副本的收件者地址
   * 點選或按一下「**新增**」按鈕，以新增其他地址
   * 點選或按一下「**刪除**」按鈕，以移除電子郵件地址

### 存放區內容 {#store-content}

提交表單時，表單的內容將儲存在指定的存放庫位置。

![表單容器編輯對話框中的存放區內容選項](/help/assets/form-container-edit-store.png)

* **內容路徑** - 提交的內容儲存所在的內容存放庫路徑
* **檢視資料** - 點選或按一下，檢視以 JSON 格式儲存的提交資料
* **啟動工作流程** - 設定在提交表單時，啟動將儲存內容作為承載的工作流程

>[!NOTE]
>
>為了簡化使用者資料的管理並強制分離關注點，通常不建議將使用者產生的內容儲存在存放庫中。
>
>改用[張貼表單資料](#post-data) 動作類型將使用者內容傳遞給專用服務提供者。

### 一般設定 {#general-settings}

無論選取的動作類型為何，您可以隨時定義感謝頁面。

![表單容器元件編輯對話框的一般選項](/help/assets/form-container-edit-general.png)

* **感謝頁面** - 完成表單提交後，系統會將使用者重新導向至指定頁面。
   * 使用「選取對話框」以在 AEM 中選取資源。
   * 如果感謝頁面不在 AEM 中，請指定絕對 URL。非絕對 URL 將解釋為相對於 AEM。
   * 留空以在提交後重新顯示表單。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

## 設計對話框 {#design-dialog}

設計對話框可讓範本作者為容器定義允許的元件及其對應，類似於[範本編輯器中標準版面容器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)的設計對話框。

### 樣式索引標籤 {#styles-tab}

表單容器元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
