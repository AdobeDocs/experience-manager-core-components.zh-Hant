---
title: 元件指引
description: 核心元件遵循與基礎元件截然不同的實施模式。
role: Architect, Developer, Admin
exl-id: e8c58fa5-c991-433c-8d38-575dacfc3433
source-git-commit: 5994133947ff697f7c866fe61598c58e37e77008
workflow-type: ht
source-wordcount: '1225'
ht-degree: 100%

---

# 元件指引 {#component-guidelines}

[核心元件](overview.md)遵循與基礎元件截然不同的實施模式。

此頁面說明這些模式，以及何時使用這些模式來建置您自己的可編寫元件。第一節[一般元件模式](#general-component-patterns)適用於任何元件類型，而第二節[可重複使用的元件模式](#reusable-component-patterns)則適用於旨在跨網站或專案重複使用的元件，例如「核心元件」。

{{traditional-aem}}

## 一般元件模式 {#general-component-patterns}

此章節中的指導方針建議用於任何元件類型，無論該元件是否特定於單一專案，或該元件是否設計用於跨網站或專案廣泛重複使用。

### 可設定的元件 {#configurable-components}

元件可以具備包含各種選項的對話框。應充分利用此特性使元件具備靈活性且可設定性，並避免實施多個元件，這些元件大多是彼此的變化版本。

通常，如果透視效果或設計包含類似元素的變化版本，這些變化版本不應實施為不同的元件，而應實施為單一元件，並提供選項以供在變化版本之間選擇。

若要更進一步跨網站或專案重複使用元件，請參閱[可預先設定的功能](#pre-configurable-capabilities)章節。

### 關注點分離 {#separation-of-concerns}

將元件的邏輯 (或模型) 與標記範本 (或視圖) 分離通常是好的做法。有幾種方法可以達成此目的，不過建議的方法是使用 [Sling 模型](https://sling.apache.org/documentation/bundles/models.html)處理邏輯，並使用 [HTML 範本語言](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=zh-Hant) (HTL) 處理標記，就如同核心元件所採用的方式。

Sling 模型是一組 Java 註解，可從 POJO 輕鬆存取所需的變數，因此提供簡單、強大且有效率的方式來實施元件的 Java 邏輯。

HTL 設計為安全且簡易的範本語言，專為 AEM 量身打造。它可以呼叫許多形式的邏輯，因此具備高度靈活性。

## 可重複使用元件模式 {#reusable-component-patterns}

本章節中的指導方針也可用於任何元件類型，但對於旨在跨網站或專案重複使用的元件 (例如核心元件) 來說，更具參考價值。因此，對於僅用於單一網站或專案的元件，則可忽略這些指導方針。

### 可預先設定的功能 {#pre-configurable-capabilities}

除了頁面作者使用的編輯對話框之外，元件也可以具備設計對話框，以供範本作者預先設定。[範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)允許設定這些稱為「原則」的預先設定。

若要讓元件儘可能重複使用，應為元件提供有意義的選項，使其可預先設定。這可讓您啟用或停用元件功能，以符合不同網站的特定需求。

### Proxy 元件模式 {#proxy-component-pattern}

由於每個內容資源都具有 `sling:resourceType` 屬性會參照要將其轉譯的元件，理想的做法通常是讓這些屬性指向網站專用元件，而不是指向多個網站共用的元件。這樣可提供更大的彈性，並在單一網站需要元件的不同行為時避免內容重構，因為此類自訂可在網站專用元件上實現，而不會影響其他網站。

不過，為避免專案專用元件重複任何程式碼，每個元件都應透過 `sling:resourceSuperType` 屬性參照共用的上層元件。這些專案專用元件主要用來參照上層元件，稱為「Proxy 元件」。如果 Proxy 元件完全繼承該功能，則可以完全留空，或者可以重新定義元件的某些方面。

>[!TIP]
>
>如需有關如何建立 Proxy 元件的詳細資訊，請參閱[使用核心元件](/help/get-started/using.md#create-proxy-components)。

### 元件版本設定 {#component-versioning}

元件應隨時間推移保持完全相容性，然而有時又必須進行無法維持相容性的變更。針對這些矛盾需求，解決方案之一是導入元件版本設定，在其資源類型路徑中加入版本號碼，並在實施的完整 Java 類別名稱中標示版本號碼。此版本號碼代表[語義版本設定指導方針](https://semver.org/)所定義的主要版本，只有不回溯相容的變更才會遞增。

若元件在下列各方面進行不相容的變更，將會產生新版本的元件：

* Sling 模型 (遵循語義版本設定指導方針)
* HTL 指令碼和範本
* HTML 標記和 CSS 選取器
* JSON 表示法
* 對話框

如需詳細資訊，請參閱 GitHub 中的[版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies)文件。

元件版本設定會建立對升級很重要的合約形式，因其能夠明確指出何時可能需要重構。另請參閱[自訂項目的升級相容性](customizing.md#upgrade-compatibility-of-customizations)章節，其中解釋了不同形式的自訂項目在升級時需要考量哪些因素。

為了避免痛苦的內容移轉，切勿從內容資源直接指向已建立版本的元件。根據經驗法則，內容的 `sling:resourceType` 絕對不能有版本號碼，否則升級元件時也會要求重構內容。避免這種情況的最佳作法是遵循上述 [Proxy 元件模式](#proxy-component-pattern)。

### 模型介面 {#model-interfaces}

此模式是關於指向 Java 介面的 HTL `data-sly-use` 指令，而 Sling 模型實施也會同時將其自身註冊至元件的資源類型。

在與上述 [Proxy 元件模式](#proxy-component-pattern)結合時，這種雙重繫結的形式可提供下列良好的擴充點：

1. 網站可以重新定義 Sling 模型的實施，方法是將其註冊至 Proxy 元件的資源類型，無須考量 HTL 檔案，因該檔案仍可以指向介面。
1. 網站可以重新定義元件的 HTL 標記，而無須考慮其應指向哪個實施邏輯。

## 整合 {#putting-it-all-together}

以下為整個資源類型繫結結構的概觀，以「標題核心元件」為例。它說明網站專用 Proxy 元件如何允許解析元件版本設定，以避免內容資源包含任何版本號碼。接著它會顯示當實施透過 [Sling 模型](https://sling.apache.org/documentation/bundles/models.html)註解繫結至元件的特定版本時，元件的 `title.html` [HTL](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=zh-Hant) 檔案如何使用模型介面。

![資源繫結概觀](/help/assets/chlimage_1-32.png)

下方是另一個概觀，其中並未顯示實施 POJO 的詳細資料，但顯示如何參照關聯的[範本和原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html?lang=zh-Hant)。

`cq:allowedTemplates` 屬性指出哪些範本可以用於網站，而 `cq:template` 則指出每個頁面的關聯範本是什麼。每個範本皆由下列三個部分組成：

* **結構** - 包含每個頁面上強制呈現且頁面作者無法刪除資源，例如頁首和頁尾元件。
* **初始** - 包含建立頁面時將會複製到該頁面的初始內容。
* **原則** - 包含每個元件與原則的對應，這是元件的預先設定。此對應允許跨範本重複使用原則，從而可集中管理。

![範本和原則概觀](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM 專案原型 {#aem-project-archetype}

[AEM 專案原型](/help/developing/archetype/overview.md)會建立最精簡的 Adobe Experience Manager 專案，作為您專案的開端，包括具有 SlingModel 的自訂 HTL 元件範例，適用於具有建議 Proxy 模式的核心元件的邏輯和正確實施。

**閱讀後續章節：**

* [使用核心元件](/help/get-started/using.md) - 在您自己的專案中啟動並執行核心元件。
* [自訂核心元件](customizing.md) - 了解如何樣式化和自訂核心元件。
