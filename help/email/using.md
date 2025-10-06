---
title: 使用電子郵件核心元件
description: 了解電子郵件核心元件的基本安裝、設定和使用。
role: Architect, Developer, Admin, User
exl-id: 0e79ca8f-eb0a-4519-b1e8-a9d3b0b99987
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '610'
ht-degree: 100%

---


# 使用電子郵件核心元件 {#using}

了解電子郵件核心元件的基本安裝、設定和使用。

## 安裝電子郵件核心元件 {#installation}

電子郵件核心元件可搭配 AEM 6.5 使用。如需詳細資訊，請參閱[「電子郵件核心元件簡介」文件的要求章節](introduction.md#requirements)。

### 安裝核心元件 {#core-components}

電子郵件核心元件以 AEM 核心元件為基礎。由於 AEM 6.5 未隨附核心元件，因此您必須先安裝 AEM 核心元件，才能安裝電子郵件核心元件。

如需有關如何安裝核心元件的詳細資訊，請參閱「使用核心元件」文件的[下載和安裝](/help/get-started/using.md#download-and-install) 一節。

### 安裝電子郵件核心元件 {#email-core-components}

在您的執行個體中安裝核心元件後，您也必須同樣安裝電子郵件核心元件。電子郵件核心元件尚未成為 AEM 專案原型的一部分，因此您需要手動將其新增到專案。請依照[電子郵件核心元件 GitHub wiki 文件所述進行安裝。](https://github.com/adobe/aem-core-email-components/wiki/Adding-to-Existing-Project)

如果您想要調整現有專案以使用電子郵件核心元件，可以依照這些相同的指示進行。

## 設定 {#configuration}

安裝核心元件後，您應完成兩個重要的設定步驟。

### 設定 Campaign {#configure-campaign}

您必須設定 AEM-Adobe Campaign 整合，兩個解決方案才能通訊。

* 設定您的 Adobe Campaign 整合
   * Adobe Campaign Classic：[與 Adobe Campaign Classic 整合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html)
   * Adobe Campaign Standard：[與 Adobe Campaign Standard 整合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)
* [將 Adobe Campaign 整合設定連結至](/help/email/components/page.md#cloud-services-tab)您將使用電子郵件核心元件的內容頁面

### 為電子郵件元件新增 AEM 資源類型篩選器 {#aem-resource-filter}

為了讓 Adobe Campaign 能夠根據電子郵件核心元件轉譯電子郵件，必須在 Campaign 中調整篩選器。

1. 使用用戶端主控台，以管理員身分登入 Adobe Campaign。

1. 從功能表列選取&#x200B;**工具** -> **總管**。

1. 在總管中，瀏覽至&#x200B;**管理** -> **平台** -> **選項**&#x200B;節點。

1. 從清單中選取 `AEMResourceTypeFilter` 選項。

1. 在&#x200B;**值**&#x200B;欄位中，請附加 `core/email/components/page/<v1>/page` (如尚未出現)。

   * 將 `<v1>` 取代為電子郵件核心元件[頁面元件](/help/email/components/page.md)的目前版本，例如 `v1`。
   * 請注意，**值**&#x200B;欄位中的值必須以逗號分隔。

1. 按一下&#x200B;**儲存**。

## 使用電子郵件核心元件 {#using-components}

安裝電子郵件元件並設定與 Adobe Campaign 的整合後，您就可以使用電子郵件元件在 AEM 中建立電子郵件內容，然後使用 Adobe Campaign 將該內容傳送給收件者。以下是工作流程的概觀。

| 步驟 | 說明 | 解決方案 |
|---|---|---|
| 1 | 作者會建立自由格式的階層式結構，將資料夾和電子郵件內容當做頁面。 | AEM |
| 2 | 使用[範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)，作者可設定電子郵件頁首及/或頁尾，該項設定將在此頁面範本產生的所有電子郵件頁面之間共用。 | AEM |
| 3 | 作者使用[頁面編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/editing-content.html)，透過文字編輯器建立電子郵件內容，他們可以在其中選取 Adobe Campaign 變數，並使用分段元件，在收件者符合特定條件時有條件地顯示資訊。 | AEM |
| 4 | 電子郵件內容完成時，會[執行工作流程](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/workflows/overview.html) ，以核准內容並傳送至 Campaign。 | AEM |
| 5 | 會建立傳遞，定義收件者清單。 | Campaign |
| 6 | 在 AEM 中建立的內容會選取為傳遞的內容。 | Campaign |
| 7 | 內容會傳送給收件者，以收件者的個人化資訊取代 Adobe Campaign 變數。 | Campaign |

如需在 AEM 中建立電子郵件內容以及在 Adobe Campaign 中傳遞的範例，請參閱下列資源。

* AEM 6.5：[使用 Adobe Campaign Classic 和 Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)
