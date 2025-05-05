---
title: 核心元件版本
description: 核心元件會以發行版本發佈，其中可能包含相同核心元件的多個版本。 本檔案說明什麼是發行版本和版本，以及如何瞭解與核心元件和AEM的相容性。
role: Architect, Developer, Admin, User
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: 821530ce1958566f0a2c1fb88c5017572057f88f
workflow-type: tm+mt
source-wordcount: '3056'
ht-degree: 11%

---

# 核心元件版本 {#core-components-versions}

核心元件與[AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=zh-Hant)和[內部部署AEM](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html?lang=zh-Hant)安裝相容。

## 發行版本歷史記錄和相容性 {#release-history-and-compatibility}

核心元件的設計具有彈性，並與所有支援的AEM版本相容。 因此，元件的一個發行版本可以包含相同元件的多個版本。

下表說明核心元件發行版本的相容性，以及哪些發行版本中包含哪些元件版本。

### 發行記錄與需求 {#release-history-requirements}

下表內容為[可在GitHub上取得，並包含完整的發行版本詳細資料](https://github.com/adobe/aem-core-wcm-components/releases)，概述核心元件的發行版本及其與AEM發行版本和Java版本的相容性。

| 發行 | 描述 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  | Java | 發行日期 |
|---|---|---|---|---|---|---|---|
| [2.29.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.29.0) | 此發行版本新增了對在網站核心元件中製作預覽版資產的支援，並解決了許多錯誤修正。 | - | 6.5.21.0+ | 6.5 LTS GA | 持續 | 8， 11 | 2025年4月21日 |
| [2.28.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.28.0) | 此版本解決多項錯誤修正。 | - | 6.5.21.0+ | 6.5 LTS GA | 持續 | 8， 11 | 2025 年 3 月 17 日 |
| [2.27.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.27.0) | 此版本解決多項錯誤修正。 | - | 6.5.21.0+ | - | 持續 | 11 | 2024 年 9 月 10 日 |
| [2.26.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.26.0) | 此版本解決多項錯誤修正。 | - | 6.5.21.0+ | - | 持續 | 11 | 2024 年 7 月 31 日 |
| [2.25.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.25.4) | 此為修正部分IT故障的次要版本。 | - | 6.5.21.0+ | - | 持續 | 8， 11 | 2024 年 5 月 10 日 |
| [2.25.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.25.2) | 此為修正部分IT故障的次要版本。 | - | 6.5.21.0+ | - | 持續 | 8， 11 | 2024 年 5 月 9 日 |
| [2.25.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.25.0) | 此發行版本新增對Dynamic Media中的已命名智慧型裁切支援，包括效能和協助工具改進以及各種錯誤修正。 | - | 6.5.21.0+ | - | 持續 | 8， 11 | 2024 年 5 月 2 日 |
| [2.24.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.6) | 此修補程式發行版本包含資料層初始化的改良功能。 | - | 6.5.21.0+ | - | 持續 | 8， 11 | 2024年4月22日 |
| [2.24.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.4) | 此修補程式發行版本修正Sling模型初始化。 | - | 6.5.21.0+ | - | 持續 | 8， 11 | 2024年4月1日 |
| [2.24.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.2) | 此修補程式發行版本改善了整合測試的穩定性。 | - | 6.5.21.0+ | - | 持續 | 8， 11 | 2024 年 2 月 22 日 |
| [2.24.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.0) | 此發行版本新增了對Google Tag Manager Data Layer的支援，並包含各種錯誤修正。 | - | 6.5.21.0+ | - | 持續 | 8， 11 | 2024 年 2 月 14 日 |
| [2.23.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.23.4) | 此修補程式版本包含各種錯誤修正。 | - | 6.5.17.0+ | - | 持續 | 8， 11 | 2023 年 9 月 15 日 |
| [2.23.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.23.2) | 此修補程式已將遠端資產的Dynamic Media智慧型裁切新增至[影像](/help/components/image.md)和[Teaser元件](/help/components/teaser.md)，並修正了一些錯誤。 | - | 6.5.17.0+ | - | 持續 | 8， 11 | 2023 年 8 月 4 日 |
| [2.23.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.23.0) | 此發行版本新增對[新一代動態媒體遠端資產的支援。](/help/developing/remote-assets.md) | - | 6.5.17.0+ | - | 持續 | 8， 11 | 2023 年 6 月 6 日 |
| [2.22.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.12) | 此修補程式版本修正了兩個問題。 | - | 6.5.14.0+ | - | 持續 | 8， 11 | 2023 年 5 月 25 日 |
| [2.22.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.10) | 此修補程式版本修正了兩個回歸。 | - | 6.5.14.0+ | - | 持續 | 8， 11 | 2023 年 5 月 11 日 |
| [2.22.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.8) | 此修補程式版本復原了先前版本中意外移除的功能。 | - | 6.5.14.0+ | - | 持續 | 8， 11 | 2023 年 5 月 9 日 |
| [2.22.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.6) | 此修補程式發行版本修正[容器元件](/help/components/container.md)中的回歸。 | - | 6.5.14.0+ | - | 持續 | 8， 11 | 2023年4月21日 |
| [2.22.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.4) | 此修補程式發行版本修正[內容片段清單元件中的問題。](/help/components/content-fragment-list.md) | - | 6.5.14.0+ | - | 持續 | 8， 11 | 2023年4月5日 |
| [2.22.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.2) | 此維護發行版本旨在解決2.22.0中引入的兩個問題 | - | 6.5.14.0+ | - | 持續 | 8， 11 | 2023 年 3 月 31 日 |
| [2.22.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.0) | 此發行版本引入新版本的[List元件](/help/components/list.md)，並改善[Teaser](/help/components/teaser.md)以及[PDF檢視器](/help/components/pdf-viewer.md)和[輪播](/help/components/carousel.md)的更新 | - | 6.5.14.0+ | - | 持續 | 8， 11 | 2023 年 2 月 9 日 |
| [2.21.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.2) | 此修補程式發行版本修正[Teaser元件v1和v2的問題。](/help/components/teaser.md) | - | 6.5.13.0+ | - | 持續 | 8， 11 | 2022 年 9 月 12 日 |
| [2.21.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.0) | 此版本包含許多增強功能，包括發佈LinkHandler API、改進[影像元件](/help/components/image.md)和[資料層](/help/developing/data-layer/overview.md)，以及改進多面板元件。 | - | 6.5.13.0+ | - | 持續 | 8， 11 | 2022 年 9 月 12 日 |
| [2.20.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.8) | 此版本修正透過AdaptiveImageServlet傳送SVG影像的問題。 | - | 6.5.13.0+ | - | 持續 | 8， 11 | 2022 年 8 月 4 日 |
| [2.20.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.6) | 此修補程式版本修正了新[目錄元件的問題。](/help/components/tableofcontents.md) | - | 6.5.13.0+ | - | 持續 | 8， 11 | 2022 年 7 月 7 日 |
| [2.20.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.4) | 此修補程式版本修正了新[目錄元件的問題。](/help/components/tableofcontents.md) | - | 6.5.13.0+ | - | 持續 | 8， 11 | 2022 年 6 月 29 日 |
| [2.20.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.2) | 此修補程式發行版本修正了新AEMaaCS [網頁最佳化資產傳遞服務中的問題。](/help/developing/web-optimized-image-delivery.md) | - | 6.5.13.0+ | - | 持續 | 8， 11 | 2022 年 6 月 20 日 |
| [2.20.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.0) | 此版本新增新的[目錄元件](/help/components/tableofcontents.md)、新增對AEMaaCS [網頁最佳化資產傳遞服務](/help/developing/web-optimized-image-delivery.md)的支援，並包含錯誤修正。 | - | 6.5.13.0+ | - | 持續 | 8， 11 | 2022 年 6 月 9 日 |
| [2.19.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.19.0) | 此發行版本新增了[搜尋元件](/help/components/quick-search.md)的新版本、[按鈕元件](/help/components/button.md)的功能，以及許多協助工具改進和錯誤修正。 | - | 6.5.10.0+ | - | 持續 | 8， 11 | 2022年4月7日 |
| [2.18.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.8) | 此版本修正AEMaaCS的問題。 | - | 6.5.10.0+ | - | 持續 | 8， 11 | 2022 年 3 月 17 日 |
| [2.18.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.6) | 此為修補程式發行版本。 | - | 6.5.10.0+ | - | 持續 | 8， 11 | 2022 年 3 月 3 日 |
| [2.18.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.0) | 核心元件的這個主要發行版本，介紹了跨多個元件的新版本的新連結處理常式，以及許多協助工具改進和錯誤修正。 | - | 6.5.10.0+ * | - | 持續 | 8， 11 | 2022 年 2 月 16 日 |
| [2.17.14](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | 此為修補程式發行版本。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8， 11 | 2021 年 13 月 12 日 |
| [2.17.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | 此修補程式發行版本修正了先前發行版本引入的回歸。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8， 11 | 2021 年 10 月 1 日 |
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | 此修補程式增強了[List](/help/components/list.md)和[Navigation](/help/components/navigation.md)元件，以顯示重新導向目標的外部URL、啟用即將推出的[Teaser](/help/components/teaser.md)元件v2的頁面影像繼承以及包含其他錯誤修正。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8， 11 | 2021 年 8 月 31 日 |
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | 此修補程式發行版本此修補程式發行版本修正了先前引進的回溯不相容變更。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8， 11 | 2021 年 8 月 2 日 |
| [2.17.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.6) | 此修補程式發行版本新增對網頁網站地圖的支援，並包含各種協助工具改良。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8， 11 | 2021 年 7 月 29 日 |
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | 此修補程式發行版本包含無法搭配AEMaaCS使用的[資料層](/help/developing/data-layer/overview.md)的修正。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8， 11 | 2021 年 7 月 8 日 |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | 此發行版本包含許多支援連結處理常式功能的新元件版本的技術預覽，以及[頁面元件的精選影像功能的技術預覽。](/help/components/page.md)也包含數個錯誤修正。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8， 11 | 2021 年 6 月 16 日 |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | 此修補程式發行版本可修正新連結處理常式的問題。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2021 年 5 月 19 日 |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | 此修補程式發行版本主要修正新連結處理常式的問題，並新增增強功能以支援[PWA的多頁應用程式。](/help/components/page.md#pwa-support) | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2021 年 5 月 15 日 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | 此發行版本著重於改善協助工具，以及為現有元件引入新的連結處理常式。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2021年4月22日 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | 此修補程式發行版本主要修正[資料層](/help/developing/data-layer/overview.md)的回溯相容性問題，以及在某些情況下的IT測試失敗。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2021 年 3 月 16 日 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | 此發行版本包含對頁面元件[&#128279;](/help/components/page.md#pwa-support)中漸進式網頁應用程式(PWA)的支援，並支援[Adobe資料層2.0.0版。](/help/developing/data-layer/overview.md) | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2021 年 2 月 23 日 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | 此發行版本包含[內嵌元件](/help/components/embed.md)的新選項，並引入[頁面](/help/components/page.md)層級的Brand Slug，以及解決許多問題。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2021 年 2 月 9 日 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | 此修補程式發行版本解決在AEMaaCS上使用RTE時的問題 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2020 年 16 月 12 日 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | 此發行版本包含[影像元件的新Dynamic Media功能。](/help/components/image.md) | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2020 年 4 月 12 日 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | 這是2.12.0的修補程式版本，包含微幅修正。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2020 年 11 月 11 日 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | 這是2.12.0的修補版本，修正[影像元件](/help/components/image.md)中的重大錯誤。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2020 年 11 月 5 日 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | 此發行版本引入了[新的POST表單處理常式；](/help/components/forms/form-container.md#post-data)透過內容感知組態包含自訂CSS、JavaScript和中繼資料[標籤的功能；](/help/developing/including-clientlibs.md#context-aware-loading)以及`DataLayerBuilder`公用程式，以[簡化自訂元件中的資料層整合。](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2020 年 10 月 29 日 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | 此發行版本推出[AMP支援。](/help/developing/amp.md) | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2020 年 7 月 20 日 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | 此發行版本引入了[PDF Viewer元件。](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8， 11 | 2020 年 6 月 17 日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | 此發行版本啟用與[Adobe使用者端資料層](/help/developing/data-layer/overview.md)的整合，並引入[進度列元件。](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | - | 持續 | 8， 11 | 2020 年 5 月 29 日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此發行版本著重於修正及小幅增強功能。 | 6.4.4.0+ | 6.5.0.0+ | - | 持續 | 8， 11 | 2019 年 5 月 12 日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 此發行版本引進了新的[內嵌元件。](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | - | 持續 | 8， 11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此發行版本引進了新的[體驗片段元件。](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | - | 持續 | 8， 11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此發行版本引進了新的[Accordion，](/help/components/accordion.md) [按鈕，](/help/components/button.md) [容器，](/help/components/container.md)和[下載元件。](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | - | 持續 | 8， 11 | 2019 年 6 月 25 日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此發行版本引入了[內容片段清單元件。](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | - | 持續 | 8， 11 | 2019 年 5 月 7 日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此發行版本著重於[元件庫](https://aemcomponents.dev)的改良，但同時也包含[分隔符號元件](/help/components/separator.md)的一些功能增強。 | 6.4.2.0+ | 6.5.0.0+ | - | 持續 | 8 | 2019 年 3 月 14 日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此發行版本著重於[元件庫](https://aemcomponents.dev)，以及引入新的[分隔符號元件](/help/components/separator.md)，但同時也包含一些針對[影像元件](/help/components/image.md)的功能增強。 | 6.4.2.0+ | - | - | - | 8 | 2019 年 2 月 11 日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此發行版本主要針對錯誤修正，但也會包含一些[轉盤元件的功能增強。](/help/components/carousel.md) | 6.4.2.0+ | - | - | - | 8 | 2018 年 11 月 27 日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 此發行版本引入了[索引標籤元件](/help/components/tabs.md)和[轉盤元件](/help/components/carousel.md)，以及對[影像元件](/help/components/image.md) [頁面元件](/help/components/page.md)和[標題元件](/help/components/title.md)的改良和增強型追蹤。 | 6.4.2.0+ | — |  | - | 8 | 2018 年 10 月 16 日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 此發行版本引入了[Teaser元件](/help/components/teaser.md)，並改善[影像元件](/help/components/image.md)和許多錯誤修正。 | 6.4.2.0+ | — |  | - | 8 | 2018 年 7 月 13 日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 這是錯誤修正版本。 | 6.4.0.0+ | — |  | - | 8 | 2018 年 6 月 12 日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 此發行版本新增了底層改善、錯誤修正和小型改善，包括支援[影像元件中的影像翻轉。](/help/components/image.md) | 6.4.0.0+ | - | - | - | 8 | 2018年4月11日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 此發行版本主要針對底層改善、錯誤修正，以及對[影像元件、](/help/components/image.md) [頁面元件、](/help/components/page.md)和[內容片段元件](/help/components/content-fragment-component.md)的一些小幅度改善。 | 6.4.0.0+ | - | - | 8 | 2018 年 3 月 7 日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 此發行版本引入了[導覽元件](/help/components/navigation.md) [語言導覽元件](/help/components/language-navigation.md)和[快速搜尋元件](/help/components/quick-search.md)，並為所有元件實施了[樣式系統](/help/get-started/authoring.md#component-styling)。 | 6.4.0.0+ | - | - | - | 8 | 2018年1月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 此發行版本在所有元件上實作JSON匯出，並引入[內容片段元件。](/help/components/content-fragment-component.md) | 6.4.0.0+ | — |  | - | 8 | 2017 年 10 月 10 日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 此發行版本為[影像元件新增數個修正。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2017 年 8 月 4 日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 此發行版本新增[頁面元件](/help/components/page.md) [影像元件](/help/components/image.md)的修正，以及各種全域修正和改良。 | 6.4.0.0+ | — |  | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 此發行版本新增[影像元件](/help/components/image.md)中動畫GIF影像的修正。 | 6.4.0.0+ | - | - | - | 7 | 2017 年 3 月 22 日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心元件的初始發行版本。 | 6.4.0.0+ | - | - | - | 7 | 2017 年 3 月 20 日 |

>[!TIP]
>
>如同AEM，Adobe建議開發人員使用與其執行之AEM版本相容的[最新版本和核心元件](https://github.com/adobe/aem-core-wcm-components/releases/latest)版本，以受益於最新的修正和功能。

### 元件版本與發行版本 {#component-versions-and-releases}

下表詳細說明核心元件的哪些發行版本中包含哪些元件的哪些版本。

|  | 發行版本1.0.0 - 1.0.6 | 發行版本1.1.0 | 發行版本2.0.0 - 2.0.8 | 發行版本2.1.0 | 發行版本2.2.0 - 2.2.0 | 發行版本2.3.0 - 2.3.2 | 發行版本2.4.0 | 發行版本2.5.0 | 發行版本2.6.0 | 發行版本2.7.0 - 2.8.0 | 發行版本2.9.0 - 2.17.14 | 第2.18.0發行版本 | 第2.19.0發行版本 | 發行版本2.20.0 - 2.21.2 | 發行版本2.22.0+ |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **[Page](components/page.md)** | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2， v3 | v1， v2， v3 | v1， v2， v3 | v1， v2， v3 |
| **[標題](components/title.md)** | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2， v3 | v1， v2， v3 | v1， v2， v3 | v1， v2， v3 |
| **[影像](components/image.md)** | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2， v3 | v1， v2， v3 | v1， v2， v3 | v1， v2， v3 |
| **[清單](components/list.md)** | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2， v3 | v1， v2， v3 | v1， v2， v3 | v1， v2， v3， v4 |
| **[階層連結](components/breadcrumb.md)** | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2， v3 | v1， v2， v3 | v1， v2， v3 | v1， v2， v3 |
| **[社交媒體分享](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1，已棄用 | v1，已棄用 | v1，已棄用 | v1，已棄用 |
| **[來自容器](components/forms/form-container.md)** | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[表單文字](components/forms/form-text.md)** | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[表單選項](components/forms/form-options.md)** | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[已隱藏的表單](components/forms/form-hidden.md)** | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[表單按鈕](components/forms/form-button.md)** | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[內容片段](components/content-fragment-component.md)** |  | 沙箱 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[導覽](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[語言導覽](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[快速搜尋](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1， v2 | v1， v2 | v1， v2 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[索引標籤](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[傳送](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[分隔符號](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[內容片段清單](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[折疊式面板](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[按鈕](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[容器](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[下載](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[體驗片段](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[內嵌](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 | v1， v2 | v1， v2 | v1， v2 | v1， v2 |
| **[進度列](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[PDF檢視器](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[目錄](components/tableofcontents.md)** |  |  |  |  |  |  |  |  |  |  |  |  |  | v1 | v1 |

## 版本和發行版本 {#versions-and-releases}

核心元件是透過GitHub發佈。 這可讓Adobe更快新增功能至元件，也允許社群在AEM發行週期以外輸入內容。

核心元件可與已定義的AEM版本相容。 這表示一個AEM版本可支援核心元件的多個版本或發行版本。

### 版本 {#versions}

核心元件的主要反複專案為&#x200B;**版本**。 每個元件都有版本。 版本會以&#x200B;**v**&#x200B;加上非零的正整數表示，例如v1和v2。 只有進行了不向後相容的變更時，才會增加版本，這通常是引進新特性和功能的情況。

開發人員和管理員可以透過其資源型別路徑中的數字以及其實施的完全合格Java類別名稱，來識別核心元件的版本。 此版本編號代表[語意版本設定指南](https://semver.org/)所定義的主要版本。

如需核心元件版本的詳細資訊，請參閱核心元件的[開發人員檔案](developing/guidelines.md)。

### 發行版本 {#releases}

核心元件透過&#x200B;**發行版本**&#x200B;提供，而[代表GitHu上實際發佈的成品。](https://github.com/adobe/aem-core-wcm-components/releases)發行版本以格式`X.Y.Z`的小數表示，將所有核心元件收集在一起作為可遞送套件。

* **主要發行版本**&#x200B;引入全新的元件、對現有元件版本的改進以及標準錯誤修正。 這由發行版本編號中`X`元件的增加來表示。
* **次要發行版本**&#x200B;引入新元件、現有元件版本的新功能，以及錯誤修正。 這由發行版本編號中`Y`元件的增加來表示。
* **修補程式發行版本**&#x200B;只包含錯誤修正。 這由發行版本編號中`Z`元件的增加來表示。

>[!NOTE]
>
>發行版本可包含相同元件的多個版本。
>
>相同版本的元件可以出現在多個發行版本中。

## 核心元件支援 {#core-components-support}

核心元件是AEM不可或缺的一部分，並像在Quickstart中交付一樣，以相同的條款與條件受到支援。

就如同其他產品的功能，其生命週期結束的通則是:

* 移除元件前，將先公告該元件已被取代
* 最快將於公告後釋出的 AEM 版本中移除這些項目。

這可讓客戶在支援結束前，至少有一個版本的週期可移至新版本的元件。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

如需支援自訂元件的詳細資訊，請參閱[自訂核心元件](developing/customizing.md)頁面瞭解相關的核心元件版本。

## 基礎元件支援 {#foundation-component-support}

Adobe的開發重點已轉向核心元件，並將繼續新增新功能。

[幾乎所有的基礎元件已在AEM 6.5中棄用](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html?lang=zh-Hant)，未來只考慮修復基礎元件的重大錯誤。
