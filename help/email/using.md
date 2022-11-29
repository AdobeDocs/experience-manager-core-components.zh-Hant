---
title: 使用電子郵件核心元件
description: 了解電子郵件核心元件的基本安裝、設定和使用方式。
role: Architect, Developer, Admin, User
exl-id: 0e79ca8f-eb0a-4519-b1e8-a9d3b0b99987
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 3%

---


# 使用電子郵件核心元件 {#using}

了解電子郵件核心元件的基本安裝、設定和使用方式。

## 安裝電子郵件核心元件 {#installation}

電子郵件核心元件可與AEM 6.5搭配使用。請參閱 [電子郵件核心元件簡介檔案的需求一節](introduction.md#requirements) 以取得更多資訊。

### 安裝核心元件 {#core-components}

電子郵件核心元件是以AEM核心元件為基礎而建置。 由於核心元件未隨AEM 6.5提供，因此您必須先安裝AEM核心元件，才能安裝電子郵件核心元件。

請參閱 [下載和安裝](/help/get-started/using.md#download-and-install) 使用核心元件一節，以取得如何安裝核心元件的詳細資訊。

### 安裝電子郵件核心元件 {#email-core-components}

在執行個體中安裝核心元件後，您也必須安裝電子郵件核心元件。 電子郵件核心元件尚不屬於AEM專案原型，因此您需要手動將其新增至專案。 請依照 [要安裝的電子郵件核心元件GitHub Wiki。](https://github.com/adobe/aem-core-email-components/wiki/Adding-to-Existing-Project)

如果您想要調整現有專案以使用電子郵件核心元件，可以依照這些相同指示操作。

## 設定 {#configuration}

安裝核心元件後，您應完成兩個重要的設定步驟。

### 設定Campaign {#configure-campaign}

您必須設定AEM-Adobe Campaign整合，這兩個解決方案才能通訊。

* 設定Adobe Campaign整合
   * Adobe Campaign Classic: [與Adobe Campaign Classic整合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html)
   * Adobe Campaign Standard: [與Adobe Campaign Standard整合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)
* [連結Adobe Campaign整合設定](/help/email/components/page.md#cloud-services-tab) 前往您將使用電子郵件核心元件的內容頁面

### 為電子郵件元件新增AEM資源類型篩選器 {#aem-resource-filter}

為了讓Adobe Campaign能夠根據電子郵件核心元件來轉譯電子郵件，必須在Campaign中調整篩選器。

1. 使用用戶端主控台以管理員身分登入Adobe Campaign。

1. 選擇 **工具** -> **瀏覽器** 的上界。

1. 在瀏覽器中，導覽至 **管理** -> **平台** -> **選項** 節點。

1. 選取 `AEMResourceTypeFilter` 選項。

1. 在 **值** 欄位，附加 `core/email/components/page/<v1>/page` 如果尚未存在。

   * 取代 `<v1>` 與最新版本的電子郵件核心元件 [頁面元件](/help/email/components/page.md) 例如 `v1`.
   * 請注意 **值** 欄位必須以逗號分隔。

1. 按一下「**儲存**」。

## 使用電子郵件核心元件 {#using-components}

安裝電子郵件元件並設定與Adobe Campaign的整合後，您就可以使用電子郵件元件在AEM中建立電子郵件內容，然後使用Adobe Campaign將該內容傳送給收件者。 以下是工作流程的概觀。

| 步驟 | 說明 | 解決方案 |
|---|---|---|
| 1 | 作者建立自由格式的資料夾階層結構，並以頁面形式傳送電子郵件內容。 | AEM |
| 2 | 使用 [範本編輯器，](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 作者會設定要在此頁面範本產生之所有電子郵件頁面之間共用的電子郵件標題和/或頁尾。 | AEM |
| 3 | 作者使用 [頁面編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/editing-content.html) 若要使用文字編輯器建立電子郵件內容，使用者可在其中挑選Adobe Campaign變數，並在收件者符合特定條件時，使用分段元件以條件式顯示資訊。 | AEM |
| 4 | 當電子郵件內容完成時， [工作流程已執行](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/workflows/overview.html) 來核准內容並傳送至Campaign。 | AEM |
| 5 | 會建立傳遞，定義收件者清單。 | 行銷活動 |
| 6 | 在AEM中建立的內容會選取作為傳送的內容。 | 行銷活動 |
| 7 | 內容會傳送給收件者，並以收件者的個人化資訊取代Adobe Campaign變數。 | 行銷活動 |

如需在AEM中建立電子郵件內容以及在Adobe Campaign中傳送的範例，請參閱下列資源。

* AEM 6.5: [協作使用Adobe Campaign Classic和Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)
