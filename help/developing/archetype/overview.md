---
title: AEM 專案原型
description: 瞭解用作AEM型應用程式範本的AEM專案原型。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 8940285f4c5e5870b6a135dac674f06e4c1d8b5a
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 3%

---


# AEM 專案原型 {#aem-project-archetype}

AEM專案原型是Maven範本，可建立依最佳作法為基礎的最小Adobe Experience Manager (AEM)專案，作為您網站的起點。 本檔案概述原型的優點和一般用法。 您可以在原型GitHub存放庫中找到詳細的技術指示和檔案。

>[!TIP]
>
>在GitHub上可找到最新的AEM專案原型和相關技術檔案[。](https://github.com/adobe/aem-project-archetype)

## 為何使用原型 {#why-use-the-archetype}

使用AEM專案原型，您只需按幾下滑鼠，即可建立以最佳實務為基礎的AEM專案。 使用原型時，所有片段都已準備就緒，因此雖然產生的專案最小，但它已實作AEM的所有[主要功能](/help/developing/archetype/using.md#what-you-get)，因此您只需在其上建置並延伸。

當然，有許多元素進入[成功的AEM專案](/help/developing/success.md)，但使用AEM專案原型是堅實的基礎，強烈建議對任何AEM專案使用。

## 功能 {#features}

* **最佳實務：**&#x200B;使用Adobe所有最新建議實務Bootstrap您的網站。
* **低程式碼：**&#x200B;編輯您的範本、建立內容、部署您的CSS，您的網站就可以上線了。
* **雲端就緒：**&#x200B;如有需要，請使用[AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html)在幾天內上線，並簡化擴充性和維護作業。
* **Dispatcher：**&#x200B;專案僅已完成[Dispatcher組態](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html)，以確保速度和安全性。
* **多網站：**&#x200B;如果需要，原型會產生[多語言和多區域設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html)的內容結構。
* **核心元件：**&#x200B;作者可以使用我們通用的[標準化元件集](/help/introduction.md)來建立幾乎任何版面。
* **可編輯的範本：**&#x200B;組合幾乎任何[沒有程式碼範本](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，並定義作者可編輯的內容。
* **回應式配置：**&#x200B;在範本或個別頁面上，[為定義的中斷點定義元素如何重排](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html)。
* **頁首與頁尾：**&#x200B;使用元件的[本地化功能](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html)，組合併本地化不含程式碼的頁首與頁尾。
* **樣式系統：**&#x200B;允許作者[套用不同的樣式](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html)，避免建置自訂元件。
* **前端建置：**&#x200B;前端開發人員可以[使用Webpack、TypeScript和SASS模擬AEM頁面和建置使用者端資料庫](front-end.md)。
* **WebApp就緒：**&#x200B;針對使用React或Angular的網站，請使用[SPA SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html)保留[應用程式的內容內撰寫](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。
* **已啟用Commerce：**&#x200B;針對要將[AEM Commerce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html)與商業解決方案(例如[Magento](https://magento.com/))整合的專案，使用[Commerce核心元件](https://github.com/adobe/aem-core-cif-components)。
* **範常式式碼：**&#x200B;請檢視HelloWorld元件，以及範例模型、servlet、篩選器和排程器。
* **開放原始碼：**&#x200B;如果發現錯誤，請[協助您改進](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md)！

## 延伸閱讀 {#further-reading}

* **[AEM專案原型GitHub](https://github.com/adobe/aem-project-archetype)** — 如需原型的完整使用和技術詳細資訊
* **[使用Archetype](using.md)** — 如何在專案中使用原型及產生的模組概述
* **[使用AEM專案原型的前端開發](front-end.md)** — 如何使用原型的前端模組
* **下列教學課程是以原型為基礎：**
   * **[WKND網站](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** — 瞭解如何啟動全新的網站。
   * **[WKND Single Page App](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** — 瞭解如何建置React或Angular完全可在AEM中編寫的Web應用程式。
