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
>最新AEM專案原型和相關技術檔案 [在GitHub上可找到。](https://github.com/adobe/aem-project-archetype)

## 為何使用原型 {#why-use-the-archetype}

使用AEM專案原型，您只需按幾下滑鼠，即可建立以最佳實務為基礎的AEM專案。 使用原型時，所有片段都已準備就緒，因此雖然產生的專案最小，但已實施所有 [主要功能](/help/developing/archetype/using.md#what-you-get) AEM的URL編號，因此您只需要在上方建置並延伸。

當然，有許多元素可進入 [成功的AEM專案，](/help/developing/success.md) 但使用AEM專案原型是堅實的基礎，強烈建議用於任何AEM專案。

## 功能 {#features}

* **最佳實務：** 使用Adobe的所有最新建議作法Bootstrap您的網站。
* **低程式碼：** 編輯您的範本、建立內容、部署您的CSS，您的網站就可以上線了。
* **雲端就緒：** 如有需要，請使用 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 可在數天內上線，並簡化擴充性與維護作業。
* **Dispatcher：** 專案只有在符合以下條件時才完成： [Dispatcher設定](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html) 可確保速度和安全性。
* **多網站：** 如果需要，原型會產生 [多語言和多區域設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html).
* **核心元件：** 作者幾乎可以用我們的通用功能建立任何版面 [標準化元件集](/help/introduction.md).
* **可編輯的範本：** 組裝幾乎任何一個 [沒有程式碼的範本](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，並定義作者可編輯的內容。
* **回應式版面：** 在範本或個別頁面上， [定義元素重排的方式](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html) 用於定義的中斷點。
* **頁首與頁尾：** 組合併本地化它們，而不使用程式碼，使用 [元件的本地化功能](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html).
* **樣式系統：** 允許作者避免建置自訂元件 [套用不同的樣式](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html) 給他們。
* **前端建置：** 前端開發人員可以 [模擬AEM頁面並建置使用者端程式庫](front-end.md) Webpack、TypeScript和SASS的版本。
* **WebApp就緒：** 對於使用React或Angular的網站，請使用 [SPA SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html) 要保留 [應用程式的內容感知撰寫](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html).
* **Commerce已啟用：** 針對要整合的專案 [AEM商務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html) 使用商務解決方案，例如 [Magento](https://magento.com/) 使用 [Commerce核心元件](https://github.com/adobe/aem-core-cif-components).
* **範常式式碼：** 請檢視HelloWorld元件，以及範例模型、servlet、篩選器和排程器。
* **開放來源：** 如果事情未如預期般發展， [分配](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) 您的改良功能！

## 延伸閱讀 {#further-reading}

* **[AEM專案原型GitHub](https://github.com/adobe/aem-project-archetype)**  — 如需原型的完整使用和技術詳細資訊
* **[使用原型](using.md)**  — 概述如何在專案中使用原型和產生的模組
* **[使用AEM專案原型的前端開發](front-end.md)**  — 如何使用原型的前端模組
* **以下教學課程是根據原型：**
   * **[WKND網站](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**  — 瞭解如何啟動全新的網站。
   * **[WKND單頁應用程式](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)**  — 瞭解如何建立可完全在AEM中編寫的React或Angular網頁應用程式。
