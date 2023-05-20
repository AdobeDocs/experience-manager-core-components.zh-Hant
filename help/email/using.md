---
title: 使用電子郵件核心元件
description: 瞭解電子郵件核心元件的基本安裝、配置和使用情況。
role: Architect, Developer, Admin, User
exl-id: 0e79ca8f-eb0a-4519-b1e8-a9d3b0b99987
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 3%

---


# 使用電子郵件核心元件 {#using}

瞭解電子郵件核心元件的基本安裝、配置和使用情況。

## 安裝電子郵件核心元件 {#installation}

電子郵件核心元件可與AEM6.5一起使用。查看 [電子郵件核心元件簡介文檔的「要求」部分](introduction.md#requirements) 的子菜單。

### 安裝核心元件 {#core-components}

電子郵件核心元件構建在核AEM心元件上。 由於核心元件未隨附AEM6.5，因此在安裝電子郵件核心AEM元件之前，必須先安裝核心元件。

請參閱一節 [下載並安裝](/help/get-started/using.md#download-and-install) 中「使用核心元件」一節，瞭解有關如何安裝核心元件的詳細資訊。

### 安裝電子郵件核心元件 {#email-core-components}

在實例中安裝核心元件後，您必須同樣安裝電子郵件核心元件。 「電子郵件核心元件」尚不是「項AEM目原型」的一部分，因此您需要將它們手動添加到項目中。 請遵循中的文檔 [要安裝的電子郵件核心元件GitHub Wiki。](https://github.com/adobe/aem-core-email-components/wiki/Adding-to-Existing-Project)

如果您希望調整現有項目以使用電子郵件核心元件，可以按照這些說明進行操作。

## 設定 {#configuration}

安裝核心元件後，應完成兩個重要的配置步驟。

### 配置市場活動 {#configure-campaign}

您必須設定AEM-Adobe Campaign整合才能使兩個解決方案通信。

* 配置您的Adobe Campaign整合
   * Adobe Campaign Classic: [與Adobe Campaign Classic整合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html)
   * Adobe Campaign Standard: [與Adobe Campaign Standard整合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)
* [連結Adobe Campaign整合配置](/help/email/components/page.md#cloud-services-tab) 到內容頁面，您將在其中使用電子郵件核心元件

### 為電AEM子郵件元件添加資源類型篩選器 {#aem-resource-filter}

為了使Adobe Campaign能夠根據電子郵件核心元件呈現電子郵件，必須在市場活動中調整篩選器。

1. 使用客戶端控制台以管理員身份登錄Adobe Campaign。

1. 選擇 **工具** -> **瀏覽器** 的上界。

1. 在瀏覽器中，導航到 **管理** -> **平台** -> **選項** 的下界。

1. 選擇 `AEMResourceTypeFilter` 的子菜單。

1. 在 **值** 欄位，追加 `core/email/components/page/<v1>/page` 的子菜單。

   * 替換 `<v1>` 與當前版本的電子郵件核心元件 [頁面元件](/help/email/components/page.md) 例如 `v1`。
   * 請注意， **值** 欄位必須以逗號分隔。

1. 按一下「**儲存**」。

## 使用電子郵件核心元件 {#using-components}

安裝電子郵件元件並配置與Adobe Campaign的整合後，您可以使用電子郵件元件在中建立電子郵件內容AEM，然後使用Adobe Campaign將該內容發送給收件人。 以下是工作流的概述。

| 步驟 | 說明 | 解決方案 |
|---|---|---|
| 1 | 作者建立資料夾和電子郵件內容作為頁面的自由格式分層結構。 | AEM |
| 2 | 使用 [模板編輯器，](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 作者配置了將在此頁面模板生成的所有電子郵件頁面之間共用的電子郵件頁眉和/或頁腳。 | AEM |
| 3 | 作者使用 [頁面編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/editing-content.html) 使用文本編輯器建立電子郵件內容，在文本編輯器中，他們可以選擇Adobe Campaign變數並使用分段元件在收件人滿足特定條件時有條件地顯示資訊。 | AEM |
| 4 | 電子郵件內容完成後， [工作流正在運行](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/workflows/overview.html) 以批准內容併發送到市場活動。 | AEM |
| 5 | 建立傳遞，定義收件人清單。 | 行銷活動 |
| 6 | 在中建立的AEM內容被選作傳送的內容。 | 行銷活動 |
| 7 | 內容被發送給收件人，用收件人的個性化資訊替換Adobe Campaign變數。 | 行銷活動 |

有關在Adobe Campaign中建立電子郵件內容AEM和在中傳遞電子郵件內容的示例，請參閱以下資源。

* AEM 6.5: [與Adobe Campaign Classic和Adobe Campaign Standard合作](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)
