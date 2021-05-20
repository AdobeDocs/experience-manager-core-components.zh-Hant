---
title: 核心元件的AMP支援
description: 核心元件支援AMP - Accelerated Mobile Pages
role: Architect, Developer, Administrator
exl-id: 1fd9b6b5-0e4d-48c7-8faa-42e0d4a6bbd0
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 1%

---

# 核心元件的AMP支援{#amp-support}

自核心元件的[發行版本2.11.0](/help/versions.md)起，已完全支援[AMP - Accelerated Mobile Pages](https://developers.google.com/amp) -。

本檔案概述如何支援AMP，以及如何為您的網站啟用AMP。 但如需完整的技術詳細資訊，請參閱[GitHub開發人員檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## 什麼是AMP?{#what-is-amp}

Accelerated Mobile Pages或AMP是開放原始碼架構，原本由Google設計，用來最佳化行動瀏覽頁面。 AMP頁面的載入速度通常比標準網頁快得多，可提供更好的行動體驗。

## 核心元件中的AMP {#amp-in-core-components}

核心元件中對AMP的支援可完全配置[。](#enabling-amp) AMP版頁面只能連同標準HTML版本一併提供，或完全不提供。

核心元件使用`amp`作為Sling選擇器來轉譯AMP頁面。 例如， `example.html`會呈現一般頁面，而`example.amp.html`會是AMP版本。

個別專案可決定是否使用AMP。 事實上，由於AMP和標準HTML頁面可同時傳送，專案只能在專案的特定頁面上選擇使用AMP。

## 專案{#getting-started}中的AMP支援快速入門

雖然AMP支援提供極大的彈性，但若要快速上手，只需幾個簡單的步驟：

1. 視需要安裝AMP支援擴充功能。
   * 若為AEM as aCloud Service專案，核心元件會自動提供擴充功能，且不需要安裝。
   * 針對內部部署和AMS專案，安裝核心元件時必須明確安裝擴充功能。
1. 安裝AMP擴充功能後，元件作者必須將元件超類型指向擴充功能中的超類型。
1. [在範本](#enabling-amp) 層級或您的個別頁面上啟用AMP支援。
1. [視需要部](#css-requirements) 署內建的CSS。

### 啟用{#enabling-amp}頁的AMP

若要為頁面啟用AMP，必須在[頁面政策中選取&#x200B;**AMP模式**。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-page-policy-template-author-developer)

![AMP頁策略選項](/help/assets/amp-policy.png)

* **無AMP**  — 頁面僅以標準HTML傳送。
* **配對AMP**  — 頁面會以AMP及HTML傳送。
* **僅限AMP**  — 頁面僅以AMP傳送。

頁面的AMP設定也可以在個別頁面的[頁面屬性](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)中覆寫。

![AMP頁面屬性](/help/assets/amp-page-properties.png)

* **從頁面範本繼承**  — 此為預設值，可從頁面範本的原則取用設定。
* **無AMP**  — 頁面僅以標準HTML傳送。
* **配對AMP**  — 頁面會以AMP及HTML傳送。
* **僅限AMP**  — 頁面僅以AMP傳送。

### CSS要求{#css-requirements}

將AMP與核心元件搭配使用時，主要差異在於AMP需要所有[CSS內嵌於`<head>`元素中並最佳化。](including-clientlibs.md#inlining)

為了支援此功能，我們使用自訂的頁面元件，只會為頁面上顯示的元件載入AMP專用的CSS。

>[!NOTE]
>
>由於AMP設計限制，Adobe不支援搭配您頁面的AMP版本使用回應式格線。

如需進一步需求和技術詳細資訊，請參閱[GitHub開發人員檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
