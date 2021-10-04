---
title: 元件指引
description: 核心元件遵循與基礎元件截然不同的現代實作模式。
role: Architect, Developer, Admin
exl-id: e8c58fa5-c991-433c-8d38-575dacfc3433
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 元件指引 {#component-guidelines}

[核心元件](overview.md)遵循與基礎元件截然不同的現代實作模式。

本頁說明這些模式，以及何時可使用這些模式來建立您自己可授權的元件。 第一部分[一般元件模式](#general-component-patterns)適用於任何類型的元件，而第二部分[可重複使用的元件模式](#reusable-component-patterns)適用於打算在站點或項目之間重複使用的元件，例如核心元件。

## 一般元件模式 {#general-component-patterns}

不論元件是否專屬於單一專案，或元件是否打算在不同網站或專案間廣泛重複使用，建議使用任何類型的元件，都適用本節中的准則。

### 可設定元件 {#configurable-components}

元件可以與多種選項對話。 應運用此工具來讓元件具有彈性且可設定，並避免實作多個元件，這些元件大多是彼此不同的。

通常，如果線框或設計包含類似元素的變化，則這些變化不應作為不同的元件實施，而應作為一個元件實施，該元件具有可在變化之間選擇的選項。

若要進一步執行此步驟，如果元件在各個網站或項目之間重複使用，請參閱[預配置功能](#pre-configurable-capabilities)部分。

### 關注分離 {#separation-of-concerns}

將元件的邏輯（或模型）與標籤範本（或檢視）分開通常是個好做法。 有數種方式可達成此目的，但建議使用[Sling Models](https://sling.apache.org/documentation/bundles/models.html)來執行邏輯，並使用[HTML範本語言](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=zh-Hant)(HTL)來執行標籤，例如核心元件。

Sling模型是一組Java註解，可輕鬆從POJO存取所需的變數，因此可提供簡單、強大且有效的方式，為元件實作Java邏輯。

HTL的設計目的，是為了提供專為AEM量身打造的安全且簡單的範本語言。 它可以調用多種形式的邏輯，這使它非常靈活。

## 可重複使用的元件模式 {#reusable-component-patterns}

本節中的准則也適用於任何類型的元件，但對於打算在網站或專案間重複使用的元件（例如核心元件），這些准則最為合理。 因此，對於僅用於單一網站或專案的元件，可忽略這些准則。

### 可預先設定的功能 {#pre-configurable-capabilities}

除了頁面作者使用的編輯對話方塊外，元件也可以有範本作者預先設定的設計對話方塊。 [範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)允許設定所有這些預配置，稱為「Policys」。

為了盡可能使元件可重複使用，應為元件提供有意義的選項以進行預先配置。 這可讓您啟用或停用元件功能，以符合不同網站的特定需求。

### 代理元件模式 {#proxy-component-pattern}

由於每個內容資源都有一個`sling:resourceType`屬性，會參考元件來呈現，因此通常最好將這些屬性指向特定網站的元件，而不是指向由多個網站共用的元件。 如果某個網站需要某個元件的不同行為，這將提供更大的彈性，並避免內容重構，因為這樣就可以在特定網站的元件上完成此自訂，而不會影響其他網站。

不過，對於不要複製任何程式碼的專案特定元件，每個元件都應參考具有`sling:resourceSuperType`屬性的共用父元件。 這些專屬元件通常只指父元件，稱為「代理元件」。 如果代理元件完全繼承了功能，則它們可以是完全空的，或者它們可以重新定義元件的某些方面。

>[!TIP]
>
>如需如何建立Proxy元件的詳細資訊，請參閱[使用核心元件](/help/get-started/using.md#create-proxy-components)。

### 元件版本設定 {#component-versioning}

元件應隨著時間而保持完全相容，但有時需要進行無法相容的變更。 針對這些相反需求的一個解決方案是引入元件版本化，方法是在其資源類型路徑中添加數字，並在其實施的完全限定的Java類名稱中添加數字。 此版本號代表由[語義版本設定准則](https://semver.org/)定義的主要版本，該版本僅針對不向後相容的更改而遞增。

元件的下列方面發生不相容的變更，會產生新版本：

* Sling模型（遵循語義版本准則）
* HTL指令碼和範本
* HTML標籤和CSS選取器
* JSON表示法
* 對話方塊

如需詳細資訊，請參閱GitHub中的[版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies)檔案。

元件版本設定會建立對升級而言很重要的合約形式，因為它釐清可能需要重構某些項目的時間。 另請參閱[自定義項的升級相容性](customizing.md#upgrade-compatibility-of-customizations)部分，其中說明升級時需要考慮不同形式的自定義項。

為避免痛苦的內容移轉，切勿從內容資源直接指向版本化元件。 根據經驗，內容的`sling:resourceType`絕不得包含版本號，否則升級元件也需要重構內容。 避免此情況的最佳方式是遵循上述的[代理元件模式](#proxy-component-pattern)。

### 模型介面 {#model-interfaces}

此模式與HTL的`data-sly-use`指示相關，指向Java介面，而Sling模型實作也會將本身註冊至元件的資源類型。

結合上述的[代理元件模式](#proxy-component-pattern)後，這種雙綁定形式提供了以下良好的擴展點：

1. 網站可將Sling模型註冊至Proxy元件的資源類型，而無須考慮HTL檔案，這仍可指向介面，即可重新定義Sling模型的實作。
1. 網站可重新定義元件的HTL標籤，而無須考慮元件應指向的實作邏輯。

## 把它們放在一起 {#putting-it-all-together}

以標題核心元件為例，概述整個資源類型捆綁結構。 它說明了特定站點的代理元件如何解析元件版本設定，以避免內容資源包含任何版本號。 接著會顯示元件的`title.html` [ HTL](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html)檔案如何用於模型介面，而實作會透過[Sling Model](https://sling.apache.org/documentation/bundles/models.html)註解系結至元件的特定版本。

![資源綁定概述](/help/assets/chlimage_1-32.png)

以下是另一個概覽，不顯示實作POJO的詳細資訊，但顯示關聯的[範本和原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/components-templates/templates.html)如何被參考。

`cq:allowedTemplates`屬性會告訴哪些範本可用於網站，而`cq:template`則會告訴每個頁面的相關範本是什麼。 每個範本皆由下列三個部分組成：

* **structure**  — 包含將強制在每個頁面上顯示的資源，以及頁面作者無法刪除的資源，例如頁首和頁尾元件。
* **initial**  — 包含建立頁面時將複製到頁面的初始內容。
* **原則**  — 包含每個元件之對應至原則（元件的預先設定）。此映射允許策略在各模板之間重複使用，因此可以集中管理。

![模板和策略概述](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM 專案原型 {#aem-project-archetype}

[AEM專案原](/help/developing/archetype/overview.md) 型會將最簡化的Adobe Experience Manager專案視為您專案的起點，包括以SlingModels建立的自訂HTL元件範例，以運用建議的Proxy模式邏輯和正確實作核心元件。

**閱讀下一節內容:**

* [使用核心元件](/help/get-started/using.md)  — 在您自己的專案中開始使用核心元件。
* [自訂核心元件](customizing.md)  — 了解如何設定核心元件的樣式和自訂核心元件。
