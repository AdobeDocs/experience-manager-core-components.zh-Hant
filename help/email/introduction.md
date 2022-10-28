---
title: 電子郵件核心元件簡介
description: 使用電子郵件核心元件的彈性建立引人入勝的電子郵件內容，並透過Adobe Campaign的強大功能提供。
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 4%

---


# 電子郵件核心元件簡介 {#email-core-components-introduction}

使用電子郵件核心元件的彈性建立引人入勝的電子郵件內容，並透過Adobe Campaign的強大功能提供。

## 總覽 {#overview}

電子郵件核心元件是以核心元件的相同強大基礎所建立。 它們可讓您以簡單、有彈性的拖放方式製作電子郵件內容，然後透過Adobe Campaign的強大功能將內容傳送給您的對象。

## 優點 {#benefits}

電子郵件是品牌體驗和客戶歷程的一部分。 透過電子郵件核心元件，您的作者可以從AEM內製作電子郵件內容，提供品牌一致的體驗，進而提升內容速度。

* 如同使用核心元件製作頁面，電子郵件核心元件可讓作者在不具備技術知識的情況下組合電子郵件，同時確保遵循品牌准則。
* 重複使用資產和內容的功能也鼓勵作者遵循品牌准則，並最佳化內容建立程式。

## 功能 {#features}

* 核心電子郵件元件以 [核心元件、](/help/introduction.md) 因此也支援 [可編輯的範本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 和 [樣式系統。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)
* 有 [10個電子郵件最佳化的生產就緒元件](#components) 來製作電子郵件內容。
* 由於在大部分的對話方塊欄位中插入Adobe Campaign變數，核心電子郵件元件可提供進階個人化。
* 彈性的細分元件可讓您對內容進行進階細分。
* 核心電子郵件元件可提供最佳的電子郵件友好HTML輸出，此功能 [CSS樣式內嵌，](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner) [HTML屬性內線，](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner) 和 [HTML消毒劑。](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizer)
* 您可以在下方任意位置建立電子郵件內容 `/content`.
* 電子郵件核心元件包括 [開放原始碼。](https://github.com/adobe/aem-core-email-components)

## 要求 {#requirements}

電子郵件核心元件有下列需求。

| AEM | Adobe Campaign | 核心元件 |
|---|---|---|
| AEM 6.5.x.y（內部部署或AMS） | Adobe Campaign Classic vX<br>或<br>Adobe Campaign Standard | [第x版](/help/versions.md) 或更高 |

>[!NOTE]
>
>由於AEMas a Cloud Service不支援Adobe Campaign整合，因此電子郵件核心元件同樣不支援AEMas a Cloud Service。

## 電子郵件元件 {#components}

目前版本的電子郵件核心元件具有下列元件。

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

## 安裝與使用 {#installation-usage}

請參閱 [使用電子郵件核心元件](using.md) 有關安裝電子郵件核心元件的詳細資訊檔案。
