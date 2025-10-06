---
title: 核心元件 AMP 支援
description: 核心元件支援 AMP - 加速行動頁面
role: Architect, Developer, Admin
exl-id: 1fd9b6b5-0e4d-48c7-8faa-42e0d4a6bbd0
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: ht
source-wordcount: '525'
ht-degree: 100%

---

# 核心元件 AMP 支援 {#amp-support}

截至核心元件 [2.11.0 版](/help/versions.md)，[AMP 加速行動頁面](https://developers.google.com/amp)已完全支援。

本文件概述 AMP 的支援方式以及如何為您的網站啟用。不過，如需完整的技術詳細資訊，請參閱[GitHub 開發人員文件。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## 什麼是 AMP？ {#what-is-amp}

加速行動頁面或 AMP 是開放原始碼框架，最初由 Google 設計，用於行動瀏覽頁面的最佳化。AMP 頁面的載入速度通常比標準網頁快得多，可提供更出色的行動體驗。

## 核心元件中的 AMP {#amp-in-core-components}

核心元件中的 AMP 支援[可完全設定。](#enabling-amp)AMP 版本的頁面可單獨提供、與標準 HTML 版本一起提供，或完全不提供。

核心元件使用 `amp` 作為 Sling 選擇器來轉譯 AMP 頁面。例如，`example.html` 會轉譯一般頁面，`example.amp.html` 則是 AMP 版本。

個別專案可決定是否利用 AMP。事實上，由於 AMP 和標準 HTML 頁面可以並行傳遞，因此專案可以只選擇在專案的某些頁面上使用 AMP。

## 開始使用專案中的 AMP 支援 {#getting-started}

雖然 AMP 支援提供極大的彈性，但只要幾個簡單的步驟，就能快速開始使用：

1. 安裝 AMP 支援擴充功能 (如有需要)。
   * 若為 AEM as a Cloud Service 專案，擴充功能會自動與核心元件一併提供，無需安裝。
   * 對於內部部署和 AMS 專案，安裝核心元件時必須明確安裝擴充功能。
1. 安裝 AMP 擴充功能後，元件作者必須將元件超類型指向擴充功能中的超類型。
1. 在範本層級或個別頁面上[啟用 AMP 支援](#enabling-amp)。
1. 根據需要[部署內嵌 CSS](#css-requirements)。

### 啟用頁面 AMP {#enabling-amp}

若要啟用頁面 AMP，必須在[頁面原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant#editing-a-template-page-policy-template-author-developer)中選取 **AMP 模式**。

![AMP 頁面原則選項](/help/assets/amp-policy.png)

* **無 AMP** - 僅以標準 HTML 傳遞頁面。
* **與 AMP 同步** - 頁面會以 AMP 及 HTML 形式傳遞。
* **僅限 AMP** - 僅以 AMP 傳遞頁面。

個別頁面的[頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=zh-Hant)也可以覆寫頁面的 AMP 設定。

![AMP 頁面屬性](/help/assets/amp-page-properties.png)

* **從頁面範本繼承** - 這是預設值，允許從頁面範本的原則中取得設定。
* **無 AMP** - 僅以標準 HTML 傳遞頁面。
* **與 AMP 同步** - 頁面會以 AMP 及 HTML 形式傳遞。
* **僅限 AMP** - 僅以 AMP 傳遞頁面。

### CSS 要求 {#css-requirements}

搭配核心元件使用 AMP 時，主要差異在於 AMP 要求在 `<head>` 元素中將所有 [CSS 內嵌](including-clientlibs.md#inlining)並進行最佳化。

為了支援此功能，使用自訂頁面元件，針對頁面上顯示的元件載入 AMP 專用的 CSS。

>[!NOTE]
>
>由於 AMP 設計限制，Adobe 不支援將回應式格線用於頁面的 AMP 版本。

如需進一步要求和技術詳細資訊，請參閱[GitHub 開發人員文件。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
