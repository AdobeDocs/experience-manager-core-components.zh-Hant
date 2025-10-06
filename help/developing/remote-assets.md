---
title: 支援遠端資產
description: 了解如何使用具有 OpenAPI 功能的 Dynamic Media 設定核心元件影像和 Teaser 元件以支援遠端資產。
role: Architect, Developer, Admin, User
exl-id: b462c1f3-a6c8-4a2a-abf4-d08ec82d4371
source-git-commit: 36ef19d5b29fe21f86309719d1e3f6588e31a93b
workflow-type: ht
source-wordcount: '465'
ht-degree: 100%

---


# 支援遠端資產 {#remote-assets-support}

了解如何使用具有 OpenAPI 功能的 Dynamic Media 設定核心元件影像和 Teaser 元件以支援遠端資產。

>[!NOTE]
>
>具有 OpenAPI 的 Dynamic Media 前稱為 Next Generation Dynamic Media。其功能與使用方式完全相同。

## 取得最新的 AEM 版本 {#latest}

若要使用具有 OpenAPI 的 Dynamic Media 以支援遠端資產，需要：

* AEM 6.5 SP 18+ 或 AEM as a Cloud Service
* 核心元件 2.23.2 版或更新版本

## 設定 HTTPS {#https}

通常建議使用 HTTPS 來執行您的所有生產 AEM 執行個體。不過，您的本機開發環境可能並未如此設定。不過，使用具有 OpenAPI 的 Dynamic Media 的遠端資產需要 HTTPS 才能運作。

[使用本指南](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/security/use-the-ssl-wizard.html?lang=zh-Hant)，在您需要使用遠端資產的任何環境 (包括開發環境) 中設定 HTTPS。

## 設定 OSGi {#osgi}

遠端資產的位置必須在 OSGi 設定中定義。依照以下方式設定 **Next Generation Dynamic Media 設定** OSGi 設定，將值取代為您的遠端資產環境值。

```text
imsClient="<ims-client-name>"
enabled=B"true"
imsOrg="<ims-org>@AdobeOrg"
repositoryId="<repo-id>.adobeaemcloud.com"
```

![Next Generation Dynamic Media 設定 OSGi 設定視窗](/help/assets/remote-assets-osgi.png)

如需有關如何設定 OSGi 的詳細資訊，請參閱下列檔案：

* 為 AEM as a Cloud Service [設定 Adobe Experience Manager as a Cloud Service 的 OSGi](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi.html?lang=zh-Hant)
* 為 AEM 6.5 [設定 OSGi](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/configuring/configuring-osgi.html?lang=zh-Hant)

## 驗證設定 {#verify}

現在您可以驗證使用具有 OpenAPI 的 Dynamic Media 的遠端資產功能是否正常運作。為此，您可以安裝 WKND 範例網站和核心元件。

* 需要[核心元件](https://github.com/adobe/aem-core-wcm-components/releases/download/core.wcm.components.reactor-2.23.2/core.wcm.components.all-2.23.2.zip) 2.23.2 版或更新版本。
* 需要 [WKND 範例網站](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-3.2.0/aem-guides-wknd.all-3.2.0-classic.zip) 3.2.0 版或更新版本。

安裝核心元件和 WKND 網站後，您即可在任何 WKND 頁面上測試此功能。

1. 使用 HTTPS 存取 AEM 執行個體。

1. 在頁面編輯器中開啟 WKND 示範頁面，例如 `https://<host>:<httpsPort>/editor.html/content/wknd/language-masters/en/magazine/arctic-surfing.html`

1. 將影像元件新增至頁面。

1. 在元件的「設定」對話框中，取消勾選&#x200B;**資產** 索引標籤上的&#x200B;**從頁面繼承精選影像**&#x200B;選項，然後按一下 **挑選**。

1. 如果設定正確，將會顯示包含&#x200B;**本機**&#x200B;和&#x200B;**遠端**&#x200B;選項的下拉式清單。選取&#x200B;**遠端**。

   ![影像選取的遠端和本機挑選選項](/help/assets/remote-asset-selection.png)

1. 將會開啟對話框，您必須驗證遠端服務。

1. 一旦通過驗證，將開啟遠端服務的資產瀏覽器。選取想要的資產，然後點選或按一下&#x200B;**選取**。

   ![選取遠端資產](/help/assets/remote-asset-picker.png)

遠端資產會新增至您的本機 AEM 頁面，且您已驗證此功能設定正確。

## 使用遠端資產 {#using}

設定後，您就可以使用核心元件 (例如[影像元件](/help/components/image.md)和 [Teaser 元件](/help/components/teaser.md)) 在選取資產的位置進行遠端資產選取。
