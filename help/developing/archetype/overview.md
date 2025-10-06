---
title: AEM 專案原型
description: 了解 AEM 專案原型，其可作為以 AEM 為基礎的應用程式範本。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 5994133947ff697f7c866fe61598c58e37e77008
workflow-type: ht
source-wordcount: '527'
ht-degree: 100%

---


# AEM 專案原型 {#aem-project-archetype}

AEM 專案原型是一種 Maven 範本，其以最佳實務為基礎建立簡化的 Adobe Experience Manager (AEM) 專案，作為您網站的起點。本文件概述原型的優點和一般用法。您可以在原型 GitHub 存放庫中找到詳細的技術指示和文件。

>[!TIP]
>
>[在 GitHub 上可找到](https://github.com/adobe/aem-project-archetype)最新的 AEM 專案原型及相關技術文件。

{{traditional-aem}}

## 為何使用原型 {#why-use-the-archetype}

使用 AEM 專案原型，您只需操作一些按鍵即可建立以最佳實務為基礎的 AEM 專案。使用原型時，所有片段都已準備就緒，即便產生的專案規模精簡，它也實作了 AEM 的所有[主要功能](/help/developing/archetype/using.md#what-you-get)，您只需在其上建置並延伸。

當然，[成功的 AEM 專案](/help/developing/success.md)需仰賴許多元素，但使用 AEM 專案原型是堅實的基礎，強烈建議採用於任何 AEM 專案。

## 功能 {#features}

* **最佳實務：**&#x200B;使用 Adobe 的所有最新推薦實務來啟動您的網站。
* **低程式碼：**&#x200B;編輯您的範本、建立內容、部署您的 CSS，您的網站就可以上線了。
* **雲端就緒：**&#x200B;如有需要，請使用 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=zh-Hant) 在幾天內即可上線，並簡化擴充性和維護作業。
* **Dispatcher：**&#x200B;僅有具備可確保速度和安全性的[Dispatcher 設定](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=zh-Hant)，專案才算完整。
* **多網站：**&#x200B;如果需要，原型會產生[多語言和多區域設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html?lang=zh-Hant)的內容結構。
* **核心元件：**&#x200B;使用我們通用的[標準化元件集](/help/introduction.md)，作者幾乎能建立任何版面。
* **可編輯的範本：**&#x200B;組合出幾乎任何[無需程式碼的範本](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html?lang=zh-Hant)，並定義作者可編輯的內容。
* **回應式版面：**&#x200B;在範本或個別頁面上，為定義的中斷點[定義元素如何重排](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html?lang=zh-Hant) 。
* **頁首與頁尾：**&#x200B;使用[元件的本地化功能](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html?lang=zh-Hant)，無需程式碼即可完成組裝和本地化。
* **樣式系統：**&#x200B;允許作者為元件[套用不同的樣式](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html?lang=zh-Hant)，可避免建置自訂元件。
* **前端建置：**&#x200B;前端開發人員可以使用 Webpack、TypeScript 和 SASS [模擬 AEM 頁面和建置用戶端程式庫](front-end.md)。
* **WebApp 就緒：**&#x200B;針對使用 React 或 Angular 的網站，請使用 [SPA SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html?lang=zh-Hant) 保留[應用程式的情境式製作](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=zh-Hant)。
* **已啟用 Commerce：**&#x200B;適用於希望使用 [Commerce 核心元件](https://github.com/adobe/aem-core-cif-components)將 [AEM Commerce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html?lang=zh-Hant) 與商業解決方案 (例如 [Magento](https://magento.com/)) 整合的專案。
* **範例程式碼：**&#x200B;請檢視 HelloWorld 元件，以及範例模型、servlet、篩選器和排程器。
* **開放原始碼：**&#x200B;如果發現錯誤，請[協助我們](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md)改進！

## 延伸閱讀 {#further-reading}

* **[AEM 專案原型 GitHub](https://github.com/adobe/aem-project-archetype)** - 提供原型的完整使用方式和技術詳細資訊
* **[使用原型](using.md)** - 概述在專案中使用原型的方法及其產生的模組
* **[使用 AEM 專案原型的前端開發](front-end.md)** - 原型的前端模組使用方法
* **下列教學課程是以原型為基礎：**
   * **[WKND 網站](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hant)** - 了解如何啟動全新的網站。
   * **[WKND 單頁應用程式](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=zh-Hant)** - 了解如何建置 React 或 Angular Webapp (可在 AEM 中完整編寫)。
