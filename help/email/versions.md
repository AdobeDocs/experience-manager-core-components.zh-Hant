---
title: 核心電子郵件元件版本
description: 核心電子郵件元件會以發行版本發佈。
role: Architect, Developer, Admin, User
exl-id: 9733659a-641c-4a98-8d10-84e93e0e0a5d
source-git-commit: 91cf78d4c6622bbdec5ac7d22954c9c081c839d2
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 13%

---


# 核心電子郵件元件版本 {#core-components-versions}

電子郵件核心元件的目前版本為1.3.0，與內部部署和AMS的AEM 6.5相容。

如需有關需求和安裝的詳細資訊，請參閱「電子郵件核心元件簡介」檔案的[需求區段](/help/email/introduction.md#requirements)和「使用電子郵件核心元件」檔案的[安裝區段](/help/email/using.md#installing-the-email-core-components)。

## 發行版本歷史記錄和相容性 {#release-history-and-compatibility}

電子郵件核心元件的設計具有彈性，並與所有支援的AEM版本相容。 您可以在GitHub上找到電子郵件核心元件[版本記錄的完整詳細資料。](https://github.com/adobe/aem-core-email-components/releases)但是，下表提供電子郵件核心元件的版本概觀，及其與AEM版本和Java版本的相容性。

| 發行 | 描述 | AEM 6.5 | AEM 6.5 LTS | 核心元件 | Java | 發行日期 |
|---|---|---|---|---|---|---|
| [1.3.0](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.3.0) | 此版本更新了內嵌的Jsoup程式庫。 | 6.5.14.0+ | - | [2.21.2+](/help/versions.md) | 8， 11 | 2024 年 6 月 28 日 |
| [1.2.2](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.2.2) | 此維護發行修正了選擇器篩選、解決了`SelectorParseException`並修正了其他錯誤。 | 6.5.14.0+ | - | [2.21.2+](/help/versions.md) | 8， 11 | 2023 年 5 月 24 日 |
| [1.2.0](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.2.0) | 此發行版本引入了Selenium e2e測試，並包含許多錯誤修正。 | 6.5.14.0+ | - | [2.21.2+](/help/versions.md) | 8， 11 | 2022 年 11 月 29 日 |
| [1.0.0](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.0.0) | 首次公開發行，請參閱發行說明以取得詳細資訊 | 6.5.14.0+ | - | [2.21.2+](/help/versions.md) | 8， 11 | 2022 年 11 月 29 日 |
| [0.18.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.18.0) | 修正 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 9 月 30 日 |
| [0.17.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.17.0) | 修正 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 9 月 27 日 |
| [0.16.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.16.0) | 修正 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 9 月 14 日 |
| [0.14.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.14.0) | 修正iOS上Outlook的媒體查詢 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 8 月 8 日 |
| [0.13.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.13.0) | 包裝函式DIV效能修正，修正RTF文字的處理連結 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 7 月 27 日 |
| [0.11.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.11.0) | 區段元件、HTML內嵌器、修正的自訂區段支援 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 7 月 6 日 |
| [0.10.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.10.0) | 為頁面元件欄設定啟用頁面原則、更新分段元件、改善程式碼涵蓋範圍 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 6 月 15 日 |
| [0.9.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.9.0) | 標題和容器元件的修正和更新 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 6 月 1 日 |
| [0.8.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.8.0) | 新增Teaser元件、修正和程式碼涵蓋範圍改善 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 5 月 19 日 |
| [0.7.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.7.0) | 修正 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 5 月 4 日 |
| [0.6.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.6.0) | 新增標題、按鈕和體驗片段元件，新增ContextHub支援 | 6.5.13.0+ |  |  | 8， 11 | 2022年4月20日 |
| [0.5.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.5.0) | 新增樣式內嵌和內容片段元件 | 6.5.13.0+ |  |  | 8， 11 | 2022年4月7日 |
| [0.4.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.4.0) | 新增URL外部化程式、個人化和分段元件 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 3 月 23 日 |
| [0.3.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.3.0) | 新增文字和容器元件，新增編寫UI、修正 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 3 月 9 日 |
| [0.2.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.2.0) | 頁面元件和各種POC的初始發行說明 | 6.5.13.0+ |  |  | 8， 11 | 2022 年 2 月 24 日 |
