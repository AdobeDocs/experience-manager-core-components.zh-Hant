---
title: 核心元件的AMP支援
description: 核心元件支援AMP — 加速行動頁面
role: Architect, Developer, Admin
exl-id: 1fd9b6b5-0e4d-48c7-8faa-42e0d4a6bbd0
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 0%

---

# 核心元件的AMP支援 {#amp-support}

截至 [版本2.11.0](/help/versions.md) 核心元件的、 [AMP — 行動頁面加速](https://developers.google.com/amp)  — 完全支援。

本檔案概述AMP的支援方式以及如何為您的網站啟用。 不過，如需完整技術細節，請參閱 [GitHub開發人員檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## 什麼是AMP？ {#what-is-amp}

Accelerated Mobile Pages或AMP是一個開放原始碼架構，最初由Google設計，用於最佳化頁面以進行行動瀏覽。 AMP頁面的載入速度通常比標準網頁快得多，提供更出色的行動體驗。

## 核心元件中的AMP {#amp-in-core-components}

核心元件支援AMP如下 [完全可設定。](#enabling-amp) AMP版本的頁面可單獨提供、與標準HTML版本一起提供，或根本不提供。

核心元件使用 `amp` 作為Sling選擇器以轉譯AMP頁面。 例如 `example.html` 會轉譯一般頁面，並且 `example.amp.html` 會是AMP版本。

個別專案可決定是否運用AMP。 事實上，由於AMP和標準HTML頁面可以並行傳送，因此專案可以選擇只在某些專案頁面上使用AMP。

## 開始使用專案中的AMP支援 {#getting-started}

雖然AMP支援提供極大的彈性，但快速開始使用AMP只需要幾個簡單步驟：

1. 視需要安裝AMP支援擴充功能。
   * 若為AEMas a Cloud Service專案，擴充功能會自動與核心元件搭配使用，不需安裝。
   * 對於內部部署和AMS專案，安裝核心元件時必須明確安裝擴充功能。
1. 安裝AMP擴充功能後，元件作者必須將元件超型別指向擴充功能中的超型別。
1. [啟用AMP支援](#enabling-amp) 在範本層級或您的個別頁面上。
1. [部署內嵌CSS](#css-requirements) 視需要。

### 為頁面啟用AMP {#enabling-amp}

若要為頁面啟用AMP，請 **AMP模式** 必須選取以下專案中的 [頁面原則。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-page-policy-template-author-developer)

![AMP頁面原則選項](/help/assets/amp-policy.png)

* **無AMP**  — 頁面僅以標準HTML傳送。
* **配對的AMP**  — 以AMP和HTML形式提供頁面。
* **僅AMP**  — 僅以AMP形式提供頁面。

頁面的AMP設定也可以在下列位置覆寫： [頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) 個別頁面時。

![AMP頁面屬性](/help/assets/amp-page-properties.png)

* **繼承自頁面範本**  — 這是預設值，可讓您從頁面範本的原則中取得設定。
* **無AMP**  — 頁面僅以標準HTML傳送。
* **配對的AMP**  — 以AMP和HTML形式提供頁面。
* **僅AMP**  — 僅以AMP形式提供頁面。

### CSS需求 {#css-requirements}

搭配核心元件使用AMP時，主要差異為AMP需要全部 [要內嵌的CSS](including-clientlibs.md#inlining) 在 `<head>` 元素和最佳化。

若要支援此功能，系統會使用自訂頁面元件，針對頁面上顯示的元件僅載入AMP專屬的CSS。

>[!NOTE]
>
>由於AMP設計限制，Adobe不支援將回應式格線用於頁面的AMP版本。

如需進一步需求和技術詳細資訊，請參閱 [GitHub開發人員檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
