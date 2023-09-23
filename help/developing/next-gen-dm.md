---
title: 新一代Dynamic Media支援
description: 瞭解如何設定核心元件影像和Teaser元件以支援遠端新一代Dynamic Media資產。
role: Architect, Developer, Admin, User
source-git-commit: 9b8930c2e268f52a1377906725db9a05a089e233
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 1%

---


# 新一代Dynamic Media支援 {#next-gen-dm-support}

瞭解如何設定核心元件影像和Teaser元件以支援遠端新一代Dynamic Media資產。

## 取得最新的AEM版本 {#latest}

支援新一代Dynamic Media遠端資產需要：

* AEM 6.5 SP 18+或AEMas a Cloud Service
* 核心元件2.23.2版或更新版本

## 設定 HTTPS {#https}

通常建議使用HTTP來執行您的所有生產AEM執行個體。 不過，您的本機開發環境可能不會依此設定。 不過，新一代Dynamic Media遠端資產需要HTTPS才能運作。

[使用本指南](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/security/use-the-ssl-wizard.html) 可設定HTTPS以在您想要使用遠端資產的地方使用，包括開發環境。

## 設定OSGi {#osgi}

遠端資產的位置必須在OSGi設定中定義。 設定 **新一代Dynamic Media設定** OSGi設定如下，將值取代為遠端資產環境的值。

```text
imsClient="<ims-client-name>"
enabled=B"true"
imsOrg="<ims-org>@AdobeOrg"
repositoryId="<repo-id>.adobeaemcloud.com"
```

![新一代Dynamic Media設定OSGi設定視窗](/help/assets/remote-assets-osgi.png)

如需如何設定OSGi的詳細資訊，請參閱下列檔案：

* [為Adobe Experience Manager as a Cloud Service設定OSGi](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi.html) 適用於AEMas a Cloud Service
* [設定OSGi](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/configuring/configuring-osgi.html) 適用於AEM 6.5的

## 驗證設定 {#verify}

現在您可以驗證新一代Dynamic Media遠端資產功能是否正常運作。 若要這麼做，您可以安裝WKND範例網站和核心元件。

* [核心元件](https://github.com/adobe/aem-core-wcm-components/releases/download/core.wcm.components.reactor-2.23.2/core.wcm.components.all-2.23.2.zip) 需要2.23.2版或更新版本。
* [WKND範例網站](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-3.2.0/aem-guides-wknd.all-3.2.0-classic.zip) 需要版本3.2.0或更新版本。

安裝核心元件和WKND網站後，您即可在任何WKND頁面上測試此功能。

1. 使用HTTPS存取AEM執行個體。

1. 在頁面編輯器中開啟WKND示範頁面，例如 `https://<host>:<httpsPort>/editor.html/content/wknd/language-masters/en/magazine/arctic-surfing.html`

1. 將影像元件新增至頁面。

1. 在元件的「設定」對話方塊中，取消核取選項 **從頁面繼承精選影像** 於 **資產** 標籤並按一下 **選取**.

1. 如果設定正確，將會顯示包含選項的下拉式清單 **本機** 和 **遠端**. 選取 **遠端**.

   ![影像選取的遠端和本機挑選選項](/help/assets/remote-asset-selection.png)

1. 將會開啟對話方塊，您必須驗證遠端服務。

1. 一旦通過驗證，將開啟遠端服務的資產瀏覽器。 選取所需的資產，然後點選或按一下 **選取**.

   ![選取遠端資產](/help/assets/remote-asset-picker.png)

遠端資產會新增至您的本機AEM頁面，且您已驗證功能已正確設定。

## 使用遠端資產 {#using}

設定之後，您可以選取遠端資產，其中您可以使用核心元件選取資產，例如 [影像元件](/help/components/image.md) 和 [Teaser元件。](/help/components/teaser.md)
