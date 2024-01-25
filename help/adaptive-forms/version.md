---
title: AEM Forms核心元件版本
description: AEM核心元件會以發行版本發佈，發行版本可能包含相同核心元件的多個版本。 本檔案說明什麼是發行版本和版本，以及如何瞭解與核心元件和AEM的相容性。
role: Architect, Developer, Admin, User
exl-id: 8146a5b1-acf6-4b54-ad6b-6e1747a137f6
source-git-commit: 5ba402a0f781f73fe7eb5afc9b4beb47ba28851e
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 4%

---

# 核心元件版本 {#core-components-versions}

目前版本的核心元件2.0.10相容於 [AEMas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 而核心元件1.1.12版相容於 [AEM 6.5 Form內部部署和AMS](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html) 安裝。

## AEM作為Cloud Service版本記錄 {#aem-as-cs-version-history}

下表列出與AEMas a Cloud Service相容的核心元件發行版本，這些版本位於 [GitHub及其版本的完整詳細資訊](https://github.com/adobe/aem-core-forms-components/releases).

| 發行 | 說明 | AEM as a Cloud Service  | Java™ | 發行日期 |
|---|---|---|---|---|
| [2.0.76](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.76) | 在此版本中，條款與條件元件的樣式標籤和自訂屬性標籤已修正。 此發行版本也修正了單選按鈕元件，以儲存第一次點按的布林值。 | 持續 | 8， 11 | 2023年11月15日 |
| [2.0.74](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.74) | 此版本會針對AEM Forms中的提交動作更新提交錯誤。 | 持續 | 8， 11 | 2023年11月15日 |
| [2.0.70](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.70) | 此發行版本新增了處理表單容器中網站頁面語言的支援。 | 持續 | 8， 11 | 2023年11月10 |
| [2.0.64](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.64) | 支援RTF文字作為Radio/checkbox元件的標籤。 在此發行版本中，也新增了對Switch元件的支援。 此發行版本也包含條款與條件元件的修正。 | 持續 | 8， 11 | 2023年11月6日 |
| [2.0.62](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.62) | 在此版本中，新增了對條款與條件元件的支援。 此外，核心元件中也新增了限定名稱支援。 | 持續 | 8， 11 | 2023 年 10 月 16 日 |
| [2.0.60](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.60) | 此發行版本包含與自訂屬性功能、精靈和日期選擇器元件相關的修正。 | 持續 | 8， 11 | 2023年9月12日 |
| [2.0.56](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.56) | 在此版本中，新增了所有核心元件的自訂屬性支援。 | 持續 | 8， 11 | 2023年9月12日 |
| [2.0.54](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.54) | 此發行版本修正了與日期選擇器元件本地化相關的問題。 | 持續 | 8， 11 | 2023年8月30日 |
| [2.0.52](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.52) | 支援在最適化表單中使用核取方塊元件。 | 持續 | 8， 11 | 2023年8月25日 |
| [2.0.50](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.50) | 在此版本中新增對最適化表單中表單片段的支援。 | 持續 | 8， 11 | 2023年8月4日 |
| [2.0.48](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.48) | 此版本中的主要改善與Lighthouse效能有關。 | 持續 | 8， 11 | 2023年7月25日 |
| [2.0.42](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.42) | 此版本整合了程式設計端的改良功能。 | 持續 | 8， 11 | 2023年7月18日 |
| [2.0.38](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.38) | 此發行版本改進了協助工具功能。 | 持續 | 8， 11 | 2023年7月17日 |
| [2.0.36](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.36) | 在此版本中，您可以使用規則編輯器的Invoke Service來使用自訂錯誤處理常式。 | 持續 | 8， 11 | 2023年7月3日 |
| [2.0.34](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.34) | 新增預設錯誤訊息的本地化支援，以及可重複元件的新增/移除按鈕。 | 持續 | 8， 11 | 2023年6月28日 |
| [2.0.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.32) | 此版本新增最適化Forms的驗證碼支援。 | 持續 | 8， 11 | 2023年6月15日 |
| [2.0.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.26) | 支援在AEM Sites上新增最適化表單。 | 持續 | 8， 11 | 2023年6月7日 |
| [2.0.18](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.18) | 在此版本中，支援摺疊式功能表元件的重複性。 也將新元件新增為垂直索引標籤。 | 持續 | 8， 11 | 2023年6月5日 |
| [2.0.10](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.10) | 在這個版本中，Sites的編輯器開始支援最適化表單容器元件。 | 持續 | 8， 11 | 2023 年 3 月 17 日 |
| [2.0.8](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.8) | 此發行版本中介紹了精靈元件的重複功能。 | 持續 | 8， 11 | 2023 年 3 月 03 日 |
| [2.0.6](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | 此發行版本引進了多種數值輸入核心元件格式。 | 持續 | 8， 11 | 2023年2月8日 |
| [2.0.4](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | 此發行版本將介紹AEMas a Cloud Service的核心元件支援。 | 持續 | 8， 11 | 2023年1月30日 |

## AEM 6.5 Forms版本記錄 {#aem-as-form-version-history}

下表列出與AEM 6.5 Form內部部署和AMS相容的核心元件發行版本，可從以下網址取得： [GitHub及其版本的完整詳細資訊](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12).

| 發行 | 說明 | AEM 6.4 | AEM 6.5 | Java™ | 發行日期 |
|---|---|---|---|---|---|
| [1.1.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.32) | 此版本更新了AEM Service Pack 6.5.18.0的套件資訊資訊。 | - | 6.5.16.0+ | 8， 11 | 2023 年 10 月 15 日 |
| [1.1.28](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.28) | 支援RTF文字作為Radio/checkbox元件的標籤。 此發行版本也包含對條款與條件元件和交換器元件的支援。 | - | 6.5.16.0+ | 8， 11 | 2023 年 10 月 15 日 |
| [1.1.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.26) | 在此版本中，新增了對最適化表單和表單片段的核取方塊元件的支援。 其中也包括改善燈塔效能。 此版本也包含使用規則編輯器的Invoke Service的自訂錯誤處理常式。 | - | 6.5.16.0+ | 8， 11 | 2023 年 10 月 15 日 |
| [1.1.24](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.24) | 新增預設錯誤訊息的本地化支援，以及可重複元件的新增/移除按鈕。 此外，也新增最適化Forms中recaptcha的支援。 | - | 6.5.16.0+ | 8， 11 | 2023年6月29日 |
| [1.1.22](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.22) | 支援在AEM Sites上新增最適化表單。 在精靈和垂直標籤元件的編輯對話方塊中新增專案標籤。 | - | 6.5.16.0+ | 8， 11 | 2023年6月7日 |
| [1.1.12](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12) | 此發行版本中介紹了對AEM Forms內部部署和AMS的核心元件支援。 | - | 6.5.16.0+ | 8， 11 | 2023年2月8日 |

## 另請參閱 {#see-also}

{{see-also}}