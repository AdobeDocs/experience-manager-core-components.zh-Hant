---
title: 元件指引
description: 核心元件遵循與基礎元件截然不同的現代實施模式。
translation-type: tm+mt
source-git-commit: 2926c51c2ab97b50b9ec4942cd5415c15a1411b6
workflow-type: tm+mt
source-wordcount: '1259'
ht-degree: 1%

---


# 元件指引 {#component-guidelines}

[核心元件](overview.md)遵循與基礎元件截然不同的現代實施模式。

本頁說明這些模式，以及何時使用它們來建立您自己可授權的元件。 第一部分[一般元件模式](#general-component-patterns)適用於任何類型的元件，而第二部分[可重複使用元件模式](#reusable-component-patterns)則適用於打算跨網站或專案重複使用的元件，例如核心元件。

## 常規元件模式{#general-component-patterns}

本節中的准則建議用於任何類型的元件，不論元件是特定於單一專案，或是該元件應廣泛用於不同的網站或專案。

### 可配置元件{#configurable-components}

元件可以有各種選項的對話框。 應運用此功能，讓元件更具彈性和可設定性，並避免實作多種元件，這些元件大多是彼此不同的。

通常，如果線框或設計包含類似元素的變化，這些變化不應作為不同的元件實施，而應作為具有在變化之間選擇選項的元件。

若要更進一步，如果元件可跨網站或專案重複使用，請參閱[預先設定的功能](#pre-configurable-capabilities)一節。

### 關注事項分離{#separation-of-concerns}

將元件的邏輯（或模型）與標籤範本（或檢視）分開通常是個好做法。 有數種方法可達成此目的，但建議使用[Sling Models](https://sling.apache.org/documentation/bundles/models.html)來處理邏輯，並使用[HTML範本語言](https://docs.adobe.com/content/help/zh-Hant/experience-manager-htl/using/overview.html)(HTL)來處理標籤，就像核心元件也會做的。

Sling Models是一組Java註解，可輕鬆從POJO存取所需的變數，因此提供簡單、強大而有效率的方式，來建置元件的Java邏輯。

HTL的設計宗旨是提供安全且簡單的範本語言，專為AEM量身打造。 它可以叫用多種邏輯形式，使它非常靈活。

## 可重複使用的元件模式{#reusable-component-patterns}

本節中的准則也適用於任何類型的元件，但對於打算跨網站或專案重複使用的元件（例如核心元件），則最有意義。 因此，對於僅用於單一網站或專案的元件，可忽略這些准則。

### 預配置功能{#pre-configurable-capabilities}

除了頁面作者使用的編輯對話方塊外，元件也可以有範本作者的設計對話方塊，供範本作者預先設定。 [模板編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)允許設定所有這些預配置，這些配置稱為「策略」。

若要盡可能讓元件可重複使用，應為元件提供有意義的預先設定選項。 這可讓您啟用或停用元件的功能，以符合不同網站的特定需求。

### 代理元件模式{#proxy-component-pattern}

由於每個內容資源都有`sling:resourceType`屬性，可參照元件來呈現，因此通常最好將這些屬性指向特定網站的元件，而非指向由多個網站共用的元件。 如果某個網站需要不同的元件行為，這將提供更大的彈性並避免內容重構，因為此自訂可在特定網站的元件上完成，而不會影響其他網站。

但是，對於不要複製任何代碼的項目特定元件，它們應使用`sling:resourceSuperType`屬性參考共用父元件。 這些專案專用的元件通常僅指上層元件，稱為「proxy元件」。 如果代理元件完全繼承了該功能，則它們可以是完全空的，或者它們可以重新定義元件的某些方面。

### 元件版本控制{#component-versioning}

元件應隨著時間而保持完全相容，但有時必須進行無法相容的變更。 解決這些對立需求的一個解決方案是，在其資源類型路徑和其實施的完全限定Java類名中添加數字，以引入元件版本化。 此版本號代表由[語義版本控制准則](https://semver.org/)定義的主要版本，僅對不向後相容的更改進行增量。

對下列元件的不相容變更將產生新版本：

* Sling Models（依照語義版本准則）
* HTL指令碼和範本
* HTML標籤和CSS選擇器
* JSON表示法
* 對話方塊

如需詳細資訊，請參閱GitHub中的[版本控制政策](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies)檔案。

元件版本修訂會建立對升級而言很重要的合約形式，因為它釐清了何時可能需要重構某些項目。 另請參見[Upgrade Compatibility of Customizations](customizing.md#upgrade-compatibility-of-customizations)一節，該節將說明不同定制形式對升級的需求。

為避免痛苦的內容遷移，切勿直接指向內容資源的版本化元件。 根據經驗，`sling:resourceType`的內容不得包含版本號碼，或升級元件也需要重新構圖內容。 避免此情況的最佳方式是遵循上述的[Proxy元件模式](#proxy-component-pattern)。

### 型號介面{#model-interfaces}

此模式是關於HTL的`data-sly-use`指令，以指向Java介面，而Sling Model實作也會自行註冊至元件的資源類型。

結合上述的[Proxy元件模式](#proxy-component-pattern)時，這種雙重系結形式提供下列好的延伸點：

1. 網站可將Sling Model註冊至proxy元件的資源類型，以重新定義Sling Model的實作，而不需考慮HTL檔案，而HTL檔案仍可指向介面。
1. 網站可重新定義元件的HTL標籤，而不需考慮它應指向的實作邏輯。

## 將所有內容整合在一起{#putting-it-all-together}

以下是整個資源類型綁定結構的概述，以Title Core Component為例。 它說明了特定站點的代理元件如何解析元件版本，以避免內容資源包含任何版本號。 然後，它會顯示元件的`title.html` [HTL](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html)檔案如何用於模型介面，而實作則透過[Sling Model](https://sling.apache.org/documentation/bundles/models.html)註解系結至元件的特定版本。

![資源綁定概述](/help/assets/chlimage_1-32.png)

下面是另一個概述，它不顯示實施POJO的詳細資訊，但顯示關聯的[模板和策略](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html)如何被參考。

`cq:allowedTemplates`屬性會告訴哪些範本可用於網站，而`cq:template`則會告訴每個頁面相關範本的內容。 每個範本由下列三部分組成：

* **structure**  —— 包含將強制存在於每個頁面上的資源，且頁面作者無法刪除，例如頁首和頁尾元件。
* **initial**  —— 包含建立頁面時將複製到頁面的初始內容。
* **policies**  —— 包含每個元件的策略映射，該策略是元件的預配置。此映射允許策略跨模板重複使用，因此可以集中管理。

![範本與政策概觀](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM Project Archetype {#aem-project-archetype}

[AEM Project ](/help/developing/archetype/overview.md) Archetype會將最小的Adobe Experience Manager專案視為您自己專案的起點，包括使用SlingModels自訂HTL元件的範例，以邏輯和正確實作具有建議之proxy模式的核心元件。

**閱讀下一節內容:**

* [使用核心元件](/help/get-started/using.md) -在您自己的專案中啟動並執行核心元件。
* [自訂核心元件](customizing.md) -瞭解如何設定核心元件的樣式和自訂核心元件。
