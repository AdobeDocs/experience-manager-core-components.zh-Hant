---
title: 核心元件版本
description: 核心元件會以發行版本的形式發佈，其中可能包含同一核心元件的多個版本。本文件說明什麼是發行版本和版本，以及如何理解與核心元件和 AEM 的相容性。
role: Architect, Developer, Admin, User
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: 684bdb4168be00f02bb306dd7ab183e8c439b9e7
workflow-type: tm+mt
source-wordcount: '3110'
ht-degree: 99%

---

# 核心元件版本 {#core-components-versions}

核心元件與 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 和[內部部署 AEM](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html) 安裝相容。

## 發行版本歷史記錄與相容性 {#release-history-and-compatibility}

核心元件的設計具備靈活性，並與所有支援的 AEM 版本相容。因此，元件的發行版本可能包含同一元件的多個版本。

下表說明核心元件發行版本的相容性，以及各個發行版本所包含的元件版本。

### 發行版本歷史記錄與要求 {#release-history-requirements}

下表概述核心元件的發行版本，以及其與 AEM 發行版本和 Java 版本的相容性，其中內容[可在 GitHub 上取得，並包含完整發行版本的詳細資訊](https://github.com/adobe/aem-core-wcm-components/releases)。

| 發行版本 | 說明 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service | Java | 發行日期 |
|---|---|---|---|---|---|---|---|
| [2.30.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.30.2) | 此版本修正了與PDF檢視器相關的非本地化字串。 | - | 6.5.21.0+ | 6.5 LTS 正式發佈版 | 持續 | 8、11 | 2025 年 23 月 10 日 |
| [2.30.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.30.0) | 此版本處理數個資產和 Dynamic Media 的問題、釐清 LTS 支援的細節，並解決數個錯誤修正。 | - | 6.5.21.0+ | 6.5 LTS 正式發佈版 | 持續 | 8、11 | 2025 年 9 月 4 日 |
| [2.29.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.29.0) | 此發行版本新增支援在網站核心元件中製作資產的預覽版本，並解決數個錯誤修正。 | - | 6.5.21.0+ | 6.5 LTS 正式發佈版 | 持續 | 8、11 | 2025 年 4 月 21 日 |
| [2.28.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.28.0) | 此版本解決數個錯誤修正。 | - | 6.5.21.0+ | 6.5 LTS 正式發佈版 | 持續 | 8、11 | 2025 年 3 月 17 日 |
| [2.27.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.27.0) | 此版本解決數個錯誤修正。 | - | 6.5.21.0+ | - | 持續 | 11 | 2024 年 9 月 10 日 |
| [2.26.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.26.0) | 此版本解決數個錯誤修正。 | - | 6.5.21.0+ | - | 持續 | 11 | 2024 年 7 月 31 日 |
| [2.25.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.25.4) | 此為次要發行版本，修正部分 IT 故障。 | - | 6.5.21.0+ | - | 持續 | 8、11 | 2024 年 5 月 10 日 |
| [2.25.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.25.2) | 此為次要發行版本，修正部分 IT 故障。 | - | 6.5.21.0+ | - | 持續 | 8、11 | 2024 年 5 月 9 日 |
| [2.25.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.25.0) | 此發行版本新增支援「Dynamic Media」中預先定義的智慧裁切，包括效能和協助工具改良，以及多種錯誤修正。 | - | 6.5.21.0+ | - | 持續 | 8、11 | 2024 年 5 月 2 日 |
| [2.24.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.6) | 此修補程式發行版本包含資料層初始化改良。 | - | 6.5.21.0+ | - | 持續 | 8、11 | 2024 年 4 月 22 日 |
| [2.24.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.4) | 此修補程式發行版本修正 Sling 模型初始化。 | - | 6.5.21.0+ | - | 持續 | 8、11 | 2024 年 4 月 1 日 |
| [2.24.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.2) | 此修補程式發行版本改進整合測試的穩定性。 | - | 6.5.21.0+ | - | 持續 | 8、11 | 2024 年 2 月 22 日 |
| [2.24.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.0) | 此發行版本新增支援 Google Tag Manager 資料層，並包含多種錯誤修正。 | - | 6.5.21.0+ | - | 持續 | 8、11 | 2024 年 2 月 14 日 |
| [2.23.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.23.4) | 此修補程式發行版本包含多種錯誤修正。 | - | 6.5.17.0+ | - | 持續 | 8、11 | 2023 年 9 月 15 日 |
| [2.23.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.23.2) | 此修補程式將遠端資產的「Dynamic Media」智慧裁切新增至[影像](/help/components/image.md)和 [Teaser 元件](/help/components/teaser.md)，並修正多個錯誤。 | - | 6.5.17.0+ | - | 持續 | 8、11 | 2023 年 8 月 4 日 |
| [2.23.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.23.0) | 此發行版本新增支援 [Next Generation Dynamic Media 遠端資產](/help/developing/remote-assets.md)。 | - | 6.5.17.0+ | - | 持續 | 8、11 | 2023 年 6 月 6 日 |
| [2.22.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.12) | 此修補程式發行版本修正了兩個問題。 | - | 6.5.14.0+ | - | 持續 | 8、11 | 2023 年 5 月 25 日 |
| [2.22.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.10) | 此修補程式發行版本修正了兩個迴歸。 | - | 6.5.14.0+ | - | 持續 | 8、11 | 2023 年 5 月 11 日 |
| [2.22.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.8) | 此修補程式發行版本復原了先前版本中意外移除的功能。 | - | 6.5.14.0+ | - | 持續 | 8、11 | 2023 年 5 月 9 日 |
| [2.22.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.6) | 此修補程式發行版本修正[容器元件](/help/components/container.md)內的迴歸。 | - | 6.5.14.0+ | - | 持續 | 8、11 | 2023 年 4 月 21 日 |
| [2.22.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.4) | 此修補程式發行版本修正了[內容片段清單元件](/help/components/content-fragment-list.md)中的一個問題。 | - | 6.5.14.0+ | - | 持續 | 8、11 | 2023 年 4 月 5 日 |
| [2.22.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.2) | 此為維護發行版本，旨在解決 2.22.0 中導入的兩個問題 | - | 6.5.14.0+ | - | 持續 | 8、11 | 2023 年 3 月 31 日 |
| [2.22.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.0) | 此發行版本導入新版本的[清單元件](/help/components/list.md)，同時改善 [Teaser](/help/components/teaser.md)，並更新 [PDF 檢視器](/help/components/pdf-viewer.md)和[輪播](/help/components/carousel.md) | - | 6.5.14.0+ | - | 持續 | 8、11 | 2023 年 2 月 9 日 |
| [2.21.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.2) | 此修補程式發行版本修正 [Teaser 元件](/help/components/teaser.md) v1 和 v2 的問題。 | - | 6.5.13.0+ | - | 持續 | 8、11 | 2022 年 9 月 12 日 |
| [2.21.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.0) | 此發行版本包含多項增強功能，包括發佈 LinkHandler API、改良[影像元件](/help/components/image.md)和[資料層](/help/developing/data-layer/overview.md)，並改善多面板元件。 | - | 6.5.13.0+ | - | 持續 | 8、11 | 2022 年 9 月 12 日 |
| [2.20.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.8) | 此發行版本修正透過最適化影像 Servlet 傳遞 SVG 影像的問題。 | - | 6.5.13.0+ | - | 持續 | 8、11 | 2022 年 8 月 4 日 |
| [2.20.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.6) | 此修補程式發行版本修正了新的[目錄元件](/help/components/tableofcontents.md)的一個問題。 | - | 6.5.13.0+ | - | 持續 | 8、11 | 2022 年 7 月 7 日 |
| [2.20.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.4) | 此修補程式發行版本修正了新的[目錄元件](/help/components/tableofcontents.md)的一個問題。 | - | 6.5.13.0+ | - | 持續 | 8、11 | 2022 年 6 月 29 日 |
| [2.20.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.2) | 此修補程式發行版本修正了新的 AEMaaCS [網頁最佳化資產傳遞服務](/help/developing/web-optimized-image-delivery.md)中的一個問題。 | - | 6.5.13.0+ | - | 持續 | 8、11 | 2022 年 6 月 20 日 |
| [2.20.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.0) | 此發行版本新增新的[目錄元件](/help/components/tableofcontents.md)、新增支援 AEMaaCS [網路最佳化資產傳遞服務](/help/developing/web-optimized-image-delivery.md)，並包含錯誤修正。 | - | 6.5.13.0+ | - | 持續 | 8、11 | 2022 年 6 月 9 日 |
| [2.19.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.19.0) | 此發行版本新增[搜尋元件](/help/components/quick-search.md)的新版本、[按鈕元件](/help/components/button.md)功能，以及多項協助工具改良和錯誤修正。 | - | 6.5.10.0+ | - | 持續 | 8、11 | 2022 年 4 月 7 日 |
| [2.18.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.8) | 此發行版本修正 AEMaaCS 的一個問題。 | - | 6.5.10.0+ | - | 持續 | 8、11 | 2022 年 3 月 17 日 |
| [2.18.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.6) | 此為修補程式發行版本。 | - | 6.5.10.0+ | - | 持續 | 8、11 | 2022 年 3 月 3 日 |
| [2.18.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.0) | 此為核心元件的主要發行版本，導入跨多個元件新版本的新連結處理常式，以及多個協助工具改良和錯誤修正。 | - | 6.5.10.0+ * | - | 持續 | 8、11 | 2022 年 2 月 16 日 |
| [2.17.14](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | 此為修補程式發行版本。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8、11 | 2021 年 12 月 13 日 |
| [2.17.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | 此修補程式發行版本修正先前發行版本導入的迴歸。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8、11 | 2021 年 10 月 1 日 |
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | 此修補程式增強[清單](/help/components/list.md)和[導覽](/help/components/navigation.md)元件，以顯示重新導向目標的外部 URL、啟用即將推出的 [Teaser](/help/components/teaser.md) 元件 v2 版的頁面影像繼承，並包含其他錯誤修正。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8、11 | 2021 年 8 月 31 日 |
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | 此修補程式發行版本修正先前版本中與舊版不相容的變更。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8、11 | 2021 年 8 月 2 日 |
| [2.17.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.6) | 此修補程式發行版本新增支援網頁網站地圖，並包含各種協助工具改良。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8、11 | 2021 年 7 月 29 日 |
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | 此修補程式發行版本包含[資料層](/help/developing/data-layer/overview.md)無法搭配 AEMaaCS 使用的一個修正。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8、11 | 2021 年 7 月 8 日 |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | 此發行版本包含許多支援連結處理常式功能的新元件版本的技術預覽，以及[頁面元件的精選影像功能的技術預覽。](/help/components/page.md)也包含數個錯誤修正。 | 6.4.8.4+ | 6.5.6.0+ | - | 持續 | 8、11 | 2021 年 6 月 16 日 |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | 此修補程式發行版本修正了新連結處理常式的一個問題。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2021 年 5 月 19 日 |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | 此修補程式發行版本主要修正新連結處理常式的一個問題，並新增增強功能以支援 [PWA](/help/components/page.md#pwa-support) 的多頁應用程式。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2021 年 5 月 15 日 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | 此發行版本著重於改善協助工具，以及為現有元件導入新的連結處理常式。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2021 年 4 月 22 日 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | 此修補程式發行版本主要修正[資料層](/help/developing/data-layer/overview.md)的回溯相容性問題，以及在特定情況下的 IT 測試失敗。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2021 年 3 月 16 日 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | 此發行版本包含對[頁面元件的漸進式網頁應用程式 (PWA)](/help/components/page.md#pwa-support) 的支援，並支援 [Adobe 資料層](/help/developing/data-layer/overview.md) 2.0.0 版。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2021 年 2 月 23 日 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | 此發行版本包含[嵌入元件](/help/components/embed.md)的新選項，並導入[頁面](/help/components/page.md)層級的品牌概要，以及解決許多問題。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2021 年 2 月 9 日 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | 此修補程式發行版本解決在 AEMaaCS 上使用 RTE 時的一個問題 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2020 年 12 月 16 日 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | 此發行版本包含[影像元件](/help/components/image.md)的新 Dynamic Media 功能。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2020 年 12 月 4 日 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | 這是 2.12.0 的修補程式發行版本，包含微幅修正。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2020 年 11 月 11 日 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | 這是 2.12.0 的修補程式發行版本，修正[影像元件](/help/components/image.md)中的重大錯誤。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2020 年 11 月 5 日 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | 此發行版本導入[新的 POST 表單處理常式](/help/components/forms/form-container.md#post-data)、[透過內容感知設定](/help/developing/including-clientlibs.md#context-aware-loading)加入自訂 CSS 與 Javascript 和後設資料標籤、以及[簡化自訂元件中的資料層整合](/help/developing/data-layer/integrations.md#enabling-custom-components)的 `DataLayerBuilder` 公用程式。 | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2020 年 10 月 29 日 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | 此發行版本導入 [AMP 支援。](/help/developing/amp.md) | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2020 年 7 月 20 日 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | 此發行版本導入 [PDF 檢視器元件。](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | - | 持續 | 8、11 | 2020 年 6 月 17 日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | 此版本已啟用與 [Adobe Client Data Layer](/help/developing/data-layer/overview.md) 整合，並導入[進度列元件。](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | - | 持續 | 8、11 | 2020 年 5 月 29 日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此發行版本以修正為主，並包含小幅增強功能。 | 6.4.4.0+ | 6.5.0.0+ | - | 持續 | 8、11 | 2019 年 12 月 5 日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 此發行版本導入新的[嵌入元件。](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | - | 持續 | 8、11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此發行版本導入了新的[體驗片段元件。](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | - | 持續 | 8、11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此發行版本導入了新的[摺疊面板、](/help/components/accordion.md)[按鈕、](/help/components/button.md)[容器](/help/components/container.md)和[下載元件。](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | - | 持續 | 8、11 | 2019 年 6 月 25 日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此發行版本導入了[內容片段清單元件。](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | - | 持續 | 8、11 | 2019 年 5 月 7 日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此發行版本著重於[元件庫](https://aemcomponents.dev)的細部調整，但同時也包含[分隔符號元件](/help/components/separator.md)的一些功能增強。 | 6.4.2.0+ | 6.5.0.0+ | - | 持續 | 8 | 2019 年 3 月 14 日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此發行版本著重於[元件庫](https://aemcomponents.dev)，以及導入新的 [分隔符號元件](/help/components/separator.md)，但同時也包含一些針對[影像元件](/help/components/image.md)的功能增強。 | 6.4.2.0+ | - | - | - | 8 | 2019 年 2 月 11 日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此發行版本主要針對錯誤修正，但同時也包含一些[輪播元件](/help/components/carousel.md)的功能增強。 | 6.4.2.0+ | - | - | - | 8 | 2018 年 11 月 27 日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 此發行版本導入了[索引標籤元件](/help/components/tabs.md)和[輪播元件](/help/components/carousel.md)，以及對[影像元件、](/help/components/image.md)[頁面元件](/help/components/page.md)和[標題元件](/help/components/title.md)的改良和增強型追蹤。 | 6.4.2.0+ | -- |  | - | 8 | 2018 年 10 月 16 日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 此發行版本導入了 [Teaser 元件](/help/components/teaser.md)，並改善[影像元件](/help/components/image.md)和許多錯誤修正。 | 6.4.2.0+ | -- |  | - | 8 | 2018 年 7 月 13 日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 這是錯誤修正版本。 | 6.4.0.0+ | -- |  | - | 8 | 2018 年 6 月 12 日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 此發行版本新增了底層改善、錯誤修正和小型改善，包括支援[影像元件](/help/components/image.md)中的影像翻轉。 | 6.4.0.0+ | - | - | - | 8 | 2018 年 4 月 11 日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 此發行版本以底層改善和錯誤修正為主，以及對[影像元件、](/help/components/image.md)[頁面元件](/help/components/page.md)和[內容片段組件](/help/components/content-fragment-component.md)的一些小幅度改善。 | 6.4.0.0+ | - | - | 8 | 2018 年 3 月 7 日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 此發行版本導入了[導覽元件、](/help/components/navigation.md)[語言導覽元件](/help/components/language-navigation.md)和[快速搜尋元件](/help/components/quick-search.md)，並為所有元件實施[樣式系統](/help/get-started/authoring.md#component-styling)。 | 6.4.0.0+ | - | - | - | 8 | 2018 年 1 月 16 日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 此發行版本在所有元件上實施 JSON 匯出，並導入[內容片段元件。](/help/components/content-fragment-component.md) | 6.4.0.0+ | -- |  | - | 8 | 2017 年 10 月 10 日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 此發行版本新增[影像元件](/help/components/image.md)的數個修正。 | 6.4.0.0+ | - | - | 8 | 2017 年 8 月 4 日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 此發行版本新增[頁面元件、](/help/components/page.md)[影像元件](/help/components/image.md)的修正，以及各種全域修正和改良。 | 6.4.0.0+ | -- |  | - | 8 | 2017 年 4 月 26 日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 此發行版本新增[影像元件](/help/components/image.md)中動畫 GIF 影像的修正。 | 6.4.0.0+ | - | - | - | 7 | 2017 年 3 月 22 日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心元件的初始發行版本。 | 6.4.0.0+ | - | - | - | 7 | 2017 年 3 月 20 日 |

>[!TIP]
>
>如同 AEM，Adobe 建議開發人員使用與執行中之 AEM 版本相容的[核心元件最新發行版本和版本](https://github.com/adobe/aem-core-wcm-components/releases/latest)，以受益於最新的修正和功能。

### 元件版本和發行版本 {#component-versions-and-releases}

下表詳細說明各個核心元件發行版本所包含的元件版本。

|  | 發行版本 1.0.0 - 1.0.6 | 發行版本 1.1.0 | 發行版本 2.0.0 - 2.0.8 | 發行版本 2.1.0 | 發行版本 2.2.0-2.2.0 | 發行版本 2.3.0-2.3.2 | 發行版本 2.4.0 | 發行版本 2.5.0 | 發行版本 2.6.0 | 發行版本 2.7.0-2.8.0 | 發行版本 2.9.0-2.17.14 | 發行版本 2.18.0 | 發行版本 2.19.0 | 發行版本 2.20.0-2.21.2 | 發行版本 2.22.0+ |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **[頁面](components/page.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[標題](components/title.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[影像](components/image.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[清單](components/list.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3、v4 |
| **[階層連結](components/breadcrumb.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[社交媒體分享](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 (已棄用) | v1 (已棄用) | v1 (已棄用) | v1 (已棄用) |
| **[表單容器](components/forms/form-container.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[表單文字](components/forms/form-text.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[表單選項](components/forms/form-options.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[表單的隱藏項目](components/forms/form-hidden.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[表單按鈕](components/forms/form-button.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[內容片段](components/content-fragment-component.md)** |  | 沙箱 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[導覽](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[語言導覽](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[快速搜尋](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[索引標籤](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[輪播](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[分隔符號](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[內容片段清單](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[折疊面板](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[按鈕](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[容器](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[下載](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[體驗片段](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[嵌入](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[進度列](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[PDF 檢視器](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[目錄](components/tableofcontents.md)** |  |  |  |  |  |  |  |  |  |  |  |  |  | v1 | v1 |

## 版本和發行版本 {#versions-and-releases}

核心元件透過 GitHub 發佈。這可讓 Adobe 更快速地將功能新增至元件，同時也讓社群能在 AEM 的發行週期之外提供意見回饋。

核心元件會搭配相容的指定 AEM 版本一起提供。這表示單一 AEM 版本可支援核心元件的多個版本或發行版本。

### 版本 {#versions}

核心元件的主要疊代為&#x200B;**版本**。每個元件都有版本。版本會以 **v** 加上非零的正整數表示，例如 v1 和 v2。只有在進行與舊版不相容的變更時，版本才會遞增，這通常是導入新特性和功能的情況。

開發人員和管理員可透過其資源類型路徑中的數值，以及其實施的完整 Java 類別名稱，來識別核心元件的版本。依照[語義版本設定指導方針](https://semver.org/)中的定義，此版本號碼代表主要版本。

如需核心元件版本的進一步詳細資訊，請參閱[核心元件的開發人員文件](developing/guidelines.md)。

### 發行版本 {#releases}

核心元件透過&#x200B;**發行版本**&#x200B;提供，並[代表 GitHu 上實際發佈的成品。](https://github.com/adobe/aem-core-wcm-components/releases)發行版本以 `X.Y.Z` 的十進位數字格式表示，並將所有核心元件整合為可交付成果套件。

* **主要發行版本**&#x200B;會導入全新的元件、對現有元件版本的改良，以及標準錯誤修正。這會由發行版本編號中 `X` 部分的遞增來表示。
* **次要發行版本**&#x200B;會導入新的元件、現有元件版本的新功能，以及錯誤修正。這會由發行版本編號中 `Y` 部分的遞增來表示。
* **修補程式發行版本**&#x200B;僅包含錯誤修正。這會由發行版本編號中 `Z` 部分的遞增來表示。

>[!NOTE]
>
>發行版本可包含相同元件的多個版本。
>
>相同版本的元件可以出現在多個發行版本中。

## 核心元件支援 {#core-components-support}

核心元件是 AEM 不可或缺的一部分，並依照與 Quickstart 所提供相同的條款與條件給予支援。

就如同其他產品的功能，其生命週期結束的通則是:

* 移除元件前，將先公告該元件已被取代
* 最快將於公告後釋出的 AEM 版本中移除這些項目。

這可讓客戶在支援結束前，至少有一個版本的週期可移至新版本的元件。

每個元件的版本都清楚說明其支援的 AEM 版本。當停止支援 AEM 的單一版本時，核心元件對該 AEM 版本的支援也會停止。

如需支援自訂元件的詳細資訊，請參閱[自訂核心元件](developing/customizing.md)頁面瞭解相關的核心元件版本。

## 基礎元件支援 {#foundation-component-support}

Adobe 的開發重點已轉向核心元件，並將持續新增新功能。

[幾乎所有的基礎元件均已在 AEM 6.5 中棄用](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html)，未來僅考慮修正基礎元件的重大錯誤。
