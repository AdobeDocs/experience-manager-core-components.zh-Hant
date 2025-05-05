---
title: 支援遠端Assets
description: 瞭解如何透過OpenAPI設定核心元件影像和Teaser元件，以支援使用Dynamic Media的遠端資產。
role: Architect, Developer, Admin, User
exl-id: b462c1f3-a6c8-4a2a-abf4-d08ec82d4371
source-git-commit: 36ef19d5b29fe21f86309719d1e3f6588e31a93b
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---


# 支援遠端Assets {#remote-assets-support}

瞭解如何透過OpenAPI設定核心元件影像和Teaser元件，以支援使用Dynamic Media的遠端資產。

>[!NOTE]
>
>Dynamic Media搭配OpenAPI先前稱為新一代Dynamic Media。 功能與使用方式相同。

## 取得最新的AEM版本 {#latest}

若要支援搭配OpenAPI使用Dynamic Media的遠端資產，需要：

* AEM 6.5 SP 18+或AEM as a Cloud Service
* 核心元件2.23.2版或更新版本

## 設定 HTTPS {#https}

通常建議使用HTTP來執行您的所有生產AEM執行個體。 不過，您的本機開發環境可能不會依此設定。 不過，使用Dynamic Media搭配OpenAPI的遠端資產需要HTTPS才能運作。

[使用本指南](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/security/use-the-ssl-wizard.html?lang=zh-Hant)設定HTTPS，無論您想使用遠端資產，包括開發環境。

## 設定OSGi {#osgi}

遠端資產的位置必須在OSGi設定中定義。 依照以下方式設定&#x200B;**新一代Dynamic Media設定** OSGi設定，將值取代為您遠端資產環境的值。

```text
imsClient="<ims-client-name>"
enabled=B"true"
imsOrg="<ims-org>@AdobeOrg"
repositoryId="<repo-id>.adobeaemcloud.com"
```

![新一代Dynamic Media設定OSGi設定視窗](/help/assets/remote-assets-osgi.png)

如需如何設定OSGi的詳細資訊，請參閱下列檔案：

* [為AEM as a Cloud Service設定Adobe Experience Manager as a Cloud Service的OSGi](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi.html?lang=zh-Hant)
* [為AEM 6.5設定OSGi](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/configuring/configuring-osgi.html?lang=zh-Hant)

## 驗證設定 {#verify}

現在您可以驗證搭配OpenAPI使用Dynamic Media的遠端資產功能是否正常運作。 若要這麼做，您可以安裝WKND範例網站和核心元件。

* 需要[核心元件](https://github.com/adobe/aem-core-wcm-components/releases/download/core.wcm.components.reactor-2.23.2/core.wcm.components.all-2.23.2.zip) 2.23.2版或更新版本。
* 需要[WKND範例網站](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-3.2.0/aem-guides-wknd.all-3.2.0-classic.zip)版本3.2.0或更新版本。

安裝核心元件和WKND網站後，您即可在任何WKND頁面上測試此功能。

1. 使用HTTPS存取AEM執行個體。

1. 在頁面編輯器中開啟WKND示範頁面，例如`https://<host>:<httpsPort>/editor.html/content/wknd/language-masters/en/magazine/arctic-surfing.html`

1. 將影像元件新增至頁面。

1. 在元件的「設定」對話方塊中，取消勾選&#x200B;**資產**&#x200B;索引標籤上的&#x200B;**從頁面**&#x200B;繼承精選影像，然後按一下&#x200B;**挑選**。

1. 如果組態正確，將會顯示包含選項&#x200B;**Local**&#x200B;和&#x200B;**Remote**&#x200B;的下拉式清單。 選取&#x200B;**遠端**。

   ![影像選取範圍的遠端和本機挑選選項](/help/assets/remote-asset-selection.png)

1. 將會開啟對話方塊，您必須驗證遠端服務。

1. 一旦通過驗證，將開啟遠端服務的資產瀏覽器。 選取想要的資產，然後點選或按一下&#x200B;**選取**。

   ![選取遠端資產](/help/assets/remote-asset-picker.png)

遠端資產會新增至您的本機AEM頁面，且您已驗證功能已正確設定。

## 使用遠端Assets {#using}

設定之後，可以選取遠端資產，您可在其中使用核心元件選取資產，例如[影像元件](/help/components/image.md)和[Teaser元件](/help/components/teaser.md)。
