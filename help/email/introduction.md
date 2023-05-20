---
title: 電子郵件核心元件簡介
description: 利用電子郵件核心元件的靈活性建立引人注目的電子郵件內容，並借助Adobe Campaign的強大功能提供。
role: Architect, Developer, Admin, User
exl-id: 0a411f28-bd6a-4bad-b473-6bc27c1d1055
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 5%

---


# 電子郵件核心元件簡介 {#email-core-components-introduction}

利用電子郵件核心元件的靈活性建立引人注目的電子郵件內容，並借助Adobe Campaign的強大功能提供。

## 概觀 {#overview}

電子郵件核心元件構建在核心元件的強大基礎之上。 它們支援簡單而靈活的電子郵件內容的拖放創作，然後利用Adobe Campaign的力量將這些內容交付給您的觀眾。

## 優點 {#benefits}

電子郵件是品牌體驗和客戶旅程的一部分。 使用電子郵件核心元件，您的作者可以從內部建立電子郵件內AEM容，從而提供一致品牌化的體驗，從而提高內容速度。

* 與使用核心元件創作頁面一樣，電子郵件核心元件允許作者在沒有技術知識的情況下匯編電子郵件，同時確保他們遵循品牌推廣准則。
* 重新使用資產和內容的功能還鼓勵作者遵循品牌指導原則並優化內容建立過程。

## 功能 {#features}

* 核心電子郵件元件基於 [核心元件、](/help/introduction.md) 因此也支援 [可編輯模板](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 和 [樣式系統。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)
* 有 [十個電子郵件優化的生產就緒型元件](#components) 來編寫電子郵件內容。
* 核心電子郵件元件通過插入 [Adobe Campaign變數](campaign-variables.md) 對話框。
* 柔性 [分段元件](/help/email/components/segmentation.md) 允許對內容進行高級分段。
* 核心電子郵件元件提供最佳的電子郵件友好HTML輸出，這要歸功於 [CSS樣式內線，](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner:-Technical-documentation) [HTML屬性內線，](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner) 和 [HTML消毒劑。](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizing)
* 您可以在以下任何位置建立電子郵件內容 `/content`。
* 電子郵件核心元件包括 [開源。](https://github.com/adobe/aem-core-email-components)

## 要求 {#requirements}

電子郵件核心元件具有以下要求。

| AEM | Adobe Campaign | 核心元件 |
|---|---|---|
| AEM6.5.14.0<br>內部或AMS。 | Adobe Campaign Classic<br>Adobe Campaign Standard | [2.21.2版](/help/versions.md)+ |

>[!NOTE]
>
>由於Adobe Campaign整合在as a Cloud Service中AEM不受支援，因此電子郵件核心元件在as a Cloud Service中同樣不AEM受支援。

## 電子郵件元件 {#components}

當前版本的電子郵件核心元件具有以下元件。

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

## 安裝和使用 {#installation-usage}

查看 [使用電子郵件核心元件](using.md) 文檔，瞭解有關安裝電子郵件核心元件的詳細資訊。
