---
title: AMP對核心元件的支援
description: 核心元件支援AMP —— 加速行動頁面
translation-type: tm+mt
source-git-commit: 905096d909d4fbf624152ba3b5cbc1d80637245f
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---


# AMP對核心元件的支援 {#amp-support}

從2. [11.0版開始](/help/versions.md) ，完全支援 [AMP - Accelerated Mobile Pages](https://developers.google.com/amp) —— 核心元件。

本檔案概述如何支援AMP，以及如何為您的網站啟用AMP。 不過，如需完整的技術詳細資訊，請參閱 [GitHub開發人員檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## 什麼是AMP? {#what-is-amp}

Accelerated Mobile Pages或AMP是Google最初設計的開放原始碼架構，可最佳化行動瀏覽頁面。 AMP頁面的載入速度通常比標準網頁快得多，提供更佳的行動體驗。

## 核心元件中的AMP {#amp-in-core-components}

核心元件中對AMP的支援可完 [全配置。](#enabling-amp) AMP版的頁面可以與標準HTML版本一起獨享，或者完全不提供。

Core Components會使 `amp` 用做Sling選擇器來轉譯AMP頁面。 例如， `example.html` 將呈現正常頁面， `example.amp.html` 並將呈現AMP版本。

### 需求 {#requirements}

當搭配核心元件使用AMP時，主要的不同點是AMP要求所有CSS都內嵌在元素中， `<head>` 而且必須最佳化。

為支援此功能，會使用自訂的頁面元件，僅載入頁面上所顯示元件的AMP專用CSS。

如需進一步的需求和技術詳細資訊，請參閱 [GitHub開發人員檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

### 在核心元件中使用AMP {#using-amp}

個別專案可決定是否運用AMP。 事實上，由於AMP和標準HTML頁面可以並行傳送，因此專案可以選擇在專案的特定頁面上使用AMP。

### 安裝AMP支援 {#installing-amp}

由於AMP是可選的，因此它作為核心元件的擴展提供。

* 對於AEM做為Cloud Service專案，擴充功能會自動提供。
* 對於內部部署和AMS項目，在安裝核心元件時必須明確安裝擴展。

在安裝擴充功能後，元件作者必須將元件超類型指向擴充功能中的元件。

### 啟用頁面的AMP {#enabling-amp}

要為頁面啟用AMP，必 **須在頁面策略中選擇**[AMP模式。](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/templates.html#editingatemplatepagepolicies)

![AMP頁面策略選項](/help/assets/amp-policy.png)

* **無AMP** —— 頁面僅以標準HTML格式傳送。
* **配對AMP** —— 頁面以AMP和HTML格式傳送。
* **僅AMP** —— 頁面僅以AMP的形式傳送。

頁面的AMP設定也可以在個別頁面的「頁 [面屬性](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/authoring/editing-page-properties.html) 」中覆寫。

![AMP頁面屬性](/help/assets/amp-page-properties.png)

* **繼承自頁面模板** -這是預設值，允許從頁面模板的策略中獲取設定。
* **無AMP** —— 頁面僅以標準HTML格式傳送。
* **配對AMP** —— 頁面以AMP和HTML格式傳送。
* **僅AMP** —— 頁面僅以AMP的形式傳送。
