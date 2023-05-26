---
title: 電子郵件核心元件簡介
description: 使用電子郵件核心元件的彈性，建立引人入勝的電子郵件內容，並透過Adobe Campaign的強大功能提供。
role: Architect, Developer, Admin, User
exl-id: 0a411f28-bd6a-4bad-b473-6bc27c1d1055
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 5%

---


# 電子郵件核心元件簡介 {#email-core-components-introduction}

使用電子郵件核心元件的彈性，建立引人入勝的電子郵件內容，並透過Adobe Campaign的強大功能提供。

## 概觀 {#overview}

電子郵件核心元件建置在與核心元件相同的強大基礎之上。 它們可讓您以拖放方式輕鬆撰寫電子郵件內容，然後利用Adobe Campaign的強大功能將其傳送給您的對象。

## 優點 {#benefits}

電子郵件是品牌體驗和客戶歷程的一部分。 透過電子郵件核心元件，您的作者可以在AEM中製作電子郵件內容，提供一致的品牌體驗，從而提高內容速度。

* 就像使用核心元件編寫頁面一樣，電子郵件核心元件可讓作者在沒有技術知識的情況下組裝電子郵件，同時確保他們遵循品牌指南。
* 重複使用資產和內容的功能也鼓勵作者遵循品牌指南並最佳化內容建立流程。

## 功能 {#features}

* 核心電子郵件元件是根據 [核心元件、](/help/introduction.md) 因此也支援 [可編輯的範本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 和 [樣式系統。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)
* 有 [十個電子郵件最佳化的生產就緒元件](#components) 以撰寫電子郵件內容。
* 核心電子郵件元件提供進階的個人化功能，這要歸功於以下專案的插入： [Adobe Campaign變數](campaign-variables.md) 在大部分對話方塊欄位上。
* 彈性 [分段元件](/help/email/components/segmentation.md) 可讓您對內容進行進階分段。
* 核心電子郵件元件提供最佳的電子郵件易用HTML輸出，這要歸功於 [CSS樣式內嵌器、](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner:-Technical-documentation) [HTML屬性內嵌程式、](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner) 和 [HTML洗手液。](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizing)
* 您可以在下列任何位置建立電子郵件內容 `/content`.
* 電子郵件核心元件包括 [開放原始碼。](https://github.com/adobe/aem-core-email-components)

## 要求 {#requirements}

電子郵件核心元件具有下列需求。

| AEM | Adobe Campaign | 核心元件 |
|---|---|---|
| AEM 6.5.14.0+<br>內部部署或AMS | Adobe Campaign Classic<br>Adobe Campaign Standard | [第2.21.2發行版本](/help/versions.md)+ |

>[!NOTE]
>
>由於AEMas a Cloud Service不支援Adobe Campaign整合，因此AEMas a Cloud Service也不支援電子郵件核心元件。

## 電子郵件元件 {#components}

目前版本的電子郵件核心元件包含下列元件。

* [Page](components/page.md)
* [容器](components/container.md)
* [標題](components/title.md)
* [文字](components/text.md)
* [影像](components/image.md)
* [按鈕](components/button.md)
* [Teaser](components/teaser.md)
* [體驗片段](components/experience-fragment.md)
* [內容片段](components/content-fragment.md)
* [Segmentation](components/segmentation.md)

## 安裝及使用 {#installation-usage}

請參閱 [使用電子郵件核心元件](using.md) 有關安裝電子郵件核心元件的詳細資訊，請參閱檔案。
