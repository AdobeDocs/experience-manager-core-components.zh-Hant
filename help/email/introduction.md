---
title: 電子郵件核心元件簡介
description: 使用電子郵件核心元件的彈性，建立吸引人的電子郵件內容，並透過 Adobe Campaign 的強大功能進行傳遞。
role: Architect, Developer, Admin, User
exl-id: 0a411f28-bd6a-4bad-b473-6bc27c1d1055
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '376'
ht-degree: 100%

---


# 電子郵件核心元件簡介 {#email-core-components-introduction}

使用電子郵件核心元件的彈性，建立吸引人的電子郵件內容，並透過 Adobe Campaign 的強大功能進行傳遞。

## 概觀 {#overview}

電子郵件核心元件是以核心元件的相同強大基礎所建置。它們可讓您以簡易且彈性的拖放方式製作電子郵件內容，隨後可透過 Adobe Campaign 的強大功能傳遞給您的客群。

## 優點 {#benefits}

電子郵件是品牌體驗和客戶歷程的一部分。透過電子郵件核心元件，您的作者可在 AEM 中製作電子郵件內容，提供一致的品牌體驗，進而提升內容速度。

* 就像使用核心元件編寫頁面一樣，電子郵件核心元件可讓作者無需具備技術知識即可組合電子郵件，同時確保他們遵循品牌指南。
* 資產和內容重複使用的功能也鼓勵作者遵循品牌指南並最佳化內容建立流程。

## 功能 {#features}

* 核心電子郵件元件以[核心元件](/help/introduction.md)為基礎，因此也支援[可編輯的範本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)和[樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=zh-Hant)。
* 具備[十個電子郵件最佳化的立即可用元件](#components)可供編寫電子郵件內容。
* 歸功於大多數對話框欄位中插入了[Adobe Campaign 變數](campaign-variables.md)，核心電子郵件元件可提供進階個人化。
* 彈性的[分段元件](/help/email/components/segmentation.md)允許對您的內容進行進階分段。
* 核心電子郵件元件提供最佳的電子郵件易用 HTML 輸出，這要歸功於 [CSS 樣式內嵌器](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner:-Technical-documentation)、[HTML 屬性內嵌器](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner)和 [HTML 清理程式](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizing)。
* 您可以在 `/content` 以下的任何位置建立電子郵件內容。
* 電子郵件核心元件為[開放原始碼](https://github.com/adobe/aem-core-email-components)。

## 要求 {#requirements}

電子郵件核心元件有下列要求。

| AEM | Adobe Campaign | 核心元件 |
|---|---|---|
| AEM 6.5.14.0+<br>內部部署或 AMS | Adobe Campaign Classic<br>Adobe Campaign Standard | [版本 2.21.2](/help/versions.md)+ |

>[!NOTE]
>
>由於 AEM as a Cloud Service 不支援 Adobe Campaign 整合，因此 AEM as a Cloud Service 也不支援電子郵件核心元件。

## 電子郵件元件 {#components}

目前版本的電子郵件核心元件具備下列元件。

* [頁面](components/page.md)
* [容器](components/container.md)
* [標題](components/title.md)
* [文字](components/text.md)
* [影像](components/image.md)
* [按鈕](components/button.md)
* [Teaser](components/teaser.md)
* [體驗片段](components/experience-fragment.md)
* [內容片段](components/content-fragment.md)
* [細分](components/segmentation.md)

## 安裝及使用 {#installation-usage}

如需安裝電子郵件核心元件的詳細資訊，請參閱[使用電子郵件核心元件](using.md)文件。
