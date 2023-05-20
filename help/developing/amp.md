---
title: AMP對核心元件的支援
description: 核心元件支援AMP — 加速移動頁
role: Architect, Developer, Admin
exl-id: 1fd9b6b5-0e4d-48c7-8faa-42e0d4a6bbd0
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 0%

---

# AMP對核心元件的支援 {#amp-support}

截至 [發行版2.11.0](/help/versions.md) 核心部件， [AMP — 加速的移動頁面](https://developers.google.com/amp)  — 完全支援。

本文檔概述了如何支援AMP以及如何為您的站點啟用它。 但是，有關完整的技術詳細資訊，請參閱 [GitHub開發人員文檔。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## 什麼是AMP? {#what-is-amp}

加速移動頁面或AMP是Google最初設計的一個開源框架，用於優化移動瀏覽頁面。 AMP頁面通常比標準網頁載入速度快得多，提供更好的移動體驗。

## 核心元件中的AMP {#amp-in-core-components}

支援核心元件中的AMP [完全可配置。](#enabling-amp) AMP版本的頁面可以與標準HTML版本一起單獨提供，或者根本不提供。

核心元件使用 `amp` 作為Sling選擇器來呈現AMP頁。 例如 `example.html` 將呈現正常頁面 `example.amp.html` 是AMP版本。

單個項目可以決定是否利用AMP。 事實上，由於AMP和標準HTML頁可以並行傳送，因此項目可以選擇只在項目的某些頁面上使用AMP。

## 項目中AMP支援入門 {#getting-started}

儘管AMP支援提供了極大的靈活性，但要快速開始使用它，只需要幾個簡單的步驟：

1. 如果需要，請安裝AMP支援擴展。
   * 對於AEMas a Cloud Service項目，核心元件可自動提供擴展，無需安裝。
   * 對於本地和AMS項目，安裝核心元件時必須顯式安裝擴展。
1. 安裝AMP擴展後，元件作者必須簡單地將元件超類型指向擴展中的超類型。
1. [啟用AMP支援](#enabling-amp) 在模板級別或各個頁面上。
1. [部署內聯CSS](#css-requirements) 按需要。

### 為頁面啟用AMP {#enabling-amp}

要為頁面啟用AMP，請 **AMP模式** 必須在 [頁面策略。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-page-policy-template-author-developer)

![AMP頁策略選項](/help/assets/amp-policy.png)

* **無AMP**  — 該頁僅作為標準HTML提供。
* **配對AMP**  — 該頁作為AMP和HTML提交。
* **僅AMP**  — 該頁僅作為AMP傳送。

頁面的AMP設定也可以在 [頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) 的子菜單。

![AMP頁屬性](/help/assets/amp-page-properties.png)

* **從頁面模板繼承**  — 這是預設值，允許從頁面模板的策略中獲取設定。
* **無AMP**  — 該頁僅作為標準HTML提供。
* **配對AMP**  — 該頁作為AMP和HTML提交。
* **僅AMP**  — 該頁僅作為AMP傳送。

### CSS要求 {#css-requirements}

將AMP與核心元件一起使用時，主要區別是AMP需要 [要內嵌的CSS](including-clientlibs.md#inlining) 的 `<head>` 元素和優化。

為支援此功能，使用自定義的頁面元件，該元件僅為頁面上存在的元件載入特定於AMP的CSS。

>[!NOTE]
>
>由於AMP設計限制，Adobe不支援將響應網格與頁面的AMP版本一起使用。

有關更多要求和技術詳細資訊，請參閱 [GitHub開發人員文檔。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
