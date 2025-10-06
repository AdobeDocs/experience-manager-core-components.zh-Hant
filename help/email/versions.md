---
title: 核心電子郵件元件版本
description: 核心電子郵件元件會以發行版本的形式發佈。
role: Architect, Developer, Admin, User
exl-id: 9733659a-641c-4a98-8d10-84e93e0e0a5d
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '444'
ht-degree: 100%

---


# 核心電子郵件元件版本 {#core-components-versions}

電子郵件核心元件的目前發行版本為 1.3.0，與 AEM 6.5 相容，適用於內部部署或 AMS。

如需有關要求和安裝的詳細資訊，請分別參閱「電子郵件核心元件簡介」文件的[要求章節](/help/email/introduction.md#requirements)和「使用電子郵件核心元件」文件的[安裝章節](/help/email/using.md#installing-the-email-core-components)。

## 發行版本歷史記錄與相容性 {#release-history-and-compatibility}

電子郵件核心元件設計為具備彈性，並與所有支援的 AEM 版本相容。[在 GitHub 上可找到電子郵件核心元件版本歷史記錄的完整詳細資訊。](https://github.com/adobe/aem-core-email-components/releases)但是，下表提供「電子郵件核心元件」的版本概觀，及其與 AEM 發行版本和 Java 版本的相容性。

| 發行版本 | 說明 | AEM 6.5 | AEM 6.5 LTS | 核心元件 | Java | 發行日期 |
|---|---|---|---|---|---|---|
| [1.3.0](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.3.0) | 此發行版本更新內嵌的 Jsoup 程式庫。 | 6.5.14.0+ | - | [2.21.2+](/help/versions.md) | 8、11 | 2024 年 6 月 28 日 |
| [1.2.2](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.2.2) | 此維護發行版本修正選擇器篩選、解決 `SelectorParseException`，並修復其他錯誤。 | 6.5.14.0+ | - | [2.21.2+](/help/versions.md) | 8、11 | 2023 年 5 月 24 日 |
| [1.2.0](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.2.0) | 此發行版本導入 Selenium e2e 測試，並包含許多錯誤修正。 | 6.5.14.0+ | - | [2.21.2+](/help/versions.md) | 8、11 | 2022 年 11 月 29 日 |
| [1.0.0](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.0.0) | 首次公開發行版本，請參閱發行說明以取得詳細資訊 | 6.5.14.0+ | - | [2.21.2+](/help/versions.md) | 8、11 | 2022 年 11 月 29 日 |
| [0.18.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.18.0) | 修正 | 6.5.13.0+ |  |  | 8、11 | 2022 年 9 月 30 日 |
| [0.17.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.17.0) | 修正 | 6.5.13.0+ |  |  | 8、11 | 2022 年 9 月 27 日 |
| [0.16.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.16.0) | 修正 | 6.5.13.0+ |  |  | 8、11 | 2022 年 9 月 14 日 |
| [0.14.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.14.0) | 修正 iOS 上 Outlook 的媒體查詢 | 6.5.13.0+ |  |  | 8、11 | 2022 年 8 月 8 日 |
| [0.13.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.13.0) | 包裝函式 DIV 效能修正，修正 RTF 文字的處理連結 | 6.5.13.0+ |  |  | 8、11 | 2022 年 7 月 27 日 |
| [0.11.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.11.0) | 細分元件、HTML 內嵌器、修正的自訂區段支援 | 6.5.13.0+ |  |  | 8、11 | 2022 年 7 月 6 日 |
| [0.10.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.10.0) | 為頁面元件欄設定啟用頁面原則、更新細分元件、改善程式碼涵蓋範圍 | 6.5.13.0+ |  |  | 8、11 | 2022 年 6 月 15 日 |
| [0.9.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.9.0) | 標題和容器元件的修正和更新 | 6.5.13.0+ |  |  | 8、11 | 2022 年 6 月 1 日 |
| [0.8.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.8.0) | 新增 Teaser 元件、修正和程式碼涵蓋範圍改善 | 6.5.13.0+ |  |  | 8、11 | 2022 年 5 月 19 日 |
| [0.7.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.7.0) | 修正 | 6.5.13.0+ |  |  | 8、11 | 2022 年 5 月 4 日 |
| [0.6.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.6.0) | 新增標題、按鈕和體驗片段元件，新增 ContextHub 支援 | 6.5.13.0+ |  |  | 8、11 | 2022 年 4 月 20 日 |
| [0.5.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.5.0) | 新增樣式內嵌器和內容片段元件 | 6.5.13.0+ |  |  | 8、11 | 2022 年 4 月 7 日 |
| [0.4.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.4.0) | 新增 URL 外部器、個人化和細分元件 | 6.5.13.0+ |  |  | 8、11 | 2022 年 3 月 23 日 |
| [0.3.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.3.0) | 新增文字和容器元件，新增編寫 UI、修正 | 6.5.13.0+ |  |  | 8、11 | 2022 年 3 月 9 日 |
| [0.2.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.2.0) | 頁面元件和各種 POC 的初始預發行版本 | 6.5.13.0+ |  |  | 8、11 | 2022 年 2 月 24 日 |
