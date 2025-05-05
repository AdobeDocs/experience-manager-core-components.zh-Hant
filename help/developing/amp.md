---
title: 核心元件的AMP支援
description: 核心元件支援AMP — 加速行動頁面
role: Architect, Developer, Admin
exl-id: 1fd9b6b5-0e4d-48c7-8faa-42e0d4a6bbd0
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# 核心元件的AMP支援 {#amp-support}

自[核心元件發行版本2.11.0](/help/versions.md)起，[AMP - Accelerated Mobile Pages](https://developers.google.com/amp) — 已完全支援。

本檔案概述AMP的支援方式以及如何為您的網站啟用。 不過，如需完整的技術詳細資訊，請參閱[GitHub開發人員檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## 什麼是AMP？ {#what-is-amp}

Accelerated Mobile Pages或AMP是開放原始碼架構，最初由Google設計，用於最佳化頁面以進行行動瀏覽。 AMP頁面的載入速度通常比標準網頁快得多，可提供更出色的行動體驗。

## 核心元件中的AMP {#amp-in-core-components}

核心元件中的AMP支援[可完全設定。](#enabling-amp) AMP版本的頁面可單獨提供、與標準HTML版本一起提供，或完全不提供。

核心元件使用`amp`作為Sling選擇器來轉譯AMP頁面。 例如，`example.html`會轉譯一般頁面，`example.amp.html`會是AMP版本。

個別專案可決定是否利用AMP。 事實上，由於AMP和標準HTML頁面可以並行傳送，因此專案可以只選擇在專案的某些頁面上使用AMP。

## 開始使用專案中的AMP支援 {#getting-started}

雖然AMP支援提供極大的彈性，但只要幾個簡單的步驟，就能快速開始使用：

1. 安裝AMP支援擴充功能（如有需要）。
   * 若為AEM as a Cloud Service專案，擴充功能會自動與核心元件搭配使用，無需安裝。
   * 對於內部部署和AMS專案，安裝核心元件時必須明確安裝擴充功能。
1. 安裝AMP擴充功能後，元件作者必須將元件超型別指向擴充功能中的超型別。
1. 在範本層級或個別頁面上[啟用AMP支援](#enabling-amp)。
1. [視需要部署內嵌CSS](#css-requirements)。

### 為頁面啟用AMP {#enabling-amp}

若要啟用頁面的AMP，必須在[頁面原則中選取&#x200B;**AMP模式**。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant#editing-a-template-page-policy-template-author-developer)

![AMP頁面原則選項](/help/assets/amp-policy.png)

* **無AMP** — 僅以標準HTML傳送頁面。
* **配對的AMP** — 頁面會以AMP及HTML形式傳送。
* **僅AMP** — 僅以AMP傳送頁面。

個別頁面的[頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=zh-Hant)也可以覆寫頁面的AMP設定。

![AMP頁面屬性](/help/assets/amp-page-properties.png)

* **從頁面範本繼承** — 這是預設值，允許從頁面範本的原則中取得設定。
* **無AMP** — 僅以標準HTML傳送頁面。
* **配對的AMP** — 頁面會以AMP及HTML形式傳送。
* **僅AMP** — 僅以AMP傳送頁面。

### CSS需求 {#css-requirements}

搭配核心元件使用AMP時，主要差異在於AMP要求在`<head>`元素中將所有[CSS內嵌](including-clientlibs.md#inlining)並進行最佳化。

為了支援此功能，使用自訂頁面元件，針對頁面上顯示的元件載入特定於AMP的CSS。

>[!NOTE]
>
>由於AMP設計限制，Adobe不支援將回應式格線用於頁面的AMP版本。

如需進一步需求和技術詳細資訊，請參閱[GitHub開發人員檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
