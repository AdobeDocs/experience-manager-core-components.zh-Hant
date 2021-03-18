---
title: AMP對核心元件的支援
description: 核心元件支援AMP —— 加速行動頁面
role: 架構師、開發人員、管理員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 1%

---


# AMP對核心元件{#amp-support}的支援

從核心元件的[版本2.11.0](/help/versions.md)開始，完全支援[AMP - Accelerated Mobile Pages](https://developers.google.com/amp) -。

本檔案概述如何支援AMP，以及如何為您的網站啟用AMP。 但是，如需完整的技術詳細資訊，請參閱[GitHub開發人員檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## 什麼是AMP?{#what-is-amp}

Accelerated Mobile Pages或AMP是Google最初設計的開放原始碼架構，可最佳化行動瀏覽頁面。 AMP頁面的載入速度通常比標準網頁快得多，提供更佳的行動體驗。

## 核心元件{#amp-in-core-components}中的AMP

核心元件中對AMP的支援是完全可配置的。[](#enabling-amp) AMP版的頁面可以與標準HTML版本一起獨享，或者完全不提供。

Core Components使用`amp`做為Sling選擇器來轉譯AMP頁面。 例如，`example.html`將呈現正常頁面，而`example.amp.html`將是AMP版本。

個別專案可決定是否運用AMP。 事實上，由於AMP和標準HTML頁面可以並行傳送，因此專案可以選擇在專案的特定頁面上使用AMP。

## 在您的項目{#getting-started}中開始使用AMP支援

雖然AMP支援提供許多彈性，但快速上手只需幾個簡單步驟：

1. 如有需要，請安裝AMP支援擴充功能。
   * 對於AEMCloud Service項目，核心元件將自動提供擴展，無需安裝。
   * 對於內部部署和AMS項目，在安裝核心元件時必須明確安裝擴展。
1. 在安裝AMP擴展後，元件作者只需將元件超級類型指向擴展中的那些類型。
1. [啟用范](#enabling-amp) 本層級或個別頁面的AMP支援。
1. [視需要部](#css-requirements) 署內嵌的CSS。

### 為{#enabling-amp}頁啟用AMP

要為頁啟用AMP,**AMP模式**&#x200B;必須在[頁策略中選擇。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-page-policy-template-author-developer)

![AMP頁策略選項](/help/assets/amp-policy.png)

* **無AMP** -頁面僅以標準HTML格式傳送。
* **配對AMP** -頁面以AMP和HTML格式傳送。
* **僅AMP** -頁面僅以AMP形式傳送。

頁面的AMP設定也可以在個別頁面的[頁面屬性](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)中覆寫。

![AMP頁面屬性](/help/assets/amp-page-properties.png)

* **繼承自頁面模板** -這是預設值，允許從頁面模板的策略中獲取設定。
* **無AMP** -頁面僅以標準HTML格式傳送。
* **配對AMP** -頁面以AMP和HTML格式傳送。
* **僅AMP** -頁面僅以AMP形式傳送。

### CSS需求{#css-requirements}

當將AMP與核心元件搭配使用時，主要差異在於AMP要求所有[CSS都內嵌在`<head>`元素中，並最佳化。](including-clientlibs.md#inlining)

為支援此功能，會使用自訂的頁面元件，僅載入頁面上所顯示元件的AMP專用CSS。

>[!NOTE]
>
>由於AMP設計限制，Adobe不支援將Responsive Grid與您頁面的AMP版本搭配使用。

如需詳細需求和技術詳細資訊，請參閱[GitHub開發人員檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
