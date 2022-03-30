---
title: 元件指引
description: 核心元件遵循與基礎元件截然不同的現代實施模式。
role: Architect, Developer, Admin
exl-id: e8c58fa5-c991-433c-8d38-575dacfc3433
source-git-commit: ee18626280f74a51a799f16d6bf3f5b0be9cd6b9
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 2%

---

# 元件指引 {#component-guidelines}

的 [核心元件](overview.md) 遵循與基礎元件相去甚遠的現代實施模式。

本頁介紹這些模式，以及何時使用這些模式構建您自己的可授權元件。 第一部分 [常規元件模式](#general-component-patterns) 適用於任何類型的元件，而第二部分 [可重用元件模式](#reusable-component-patterns) 適用於要在站點或項目之間重複使用的元件，例如核心元件。

## 常規元件模式 {#general-component-patterns}

本節中的指導原則建議用於任何類型的元件，而不管該元件是否特定於單個項目，或該元件是否打算在站點或項目之間廣泛重複使用。

### 可配置元件 {#configurable-components}

元件可以與多種選項對話。 應利用這一點，使元件具有靈活性和可配置性，並避免實施多個大多是彼此差異的元件。

通常，如果線框或設計包含類似元素的變體，則這些變體不應作為不同的元件實現，而應作為具有在變體之間進行選擇的選項的一個元件來實現。

要進一步執行此步驟，如果元件在站點或項目之間重複使用，請參閱 [預配置功能](#pre-configurable-capabilities) 的子菜單。

### 關注事項的分離 {#separation-of-concerns}

將元件的邏輯（或模型）與標籤模板（或視圖）分離通常是一種好做法。 有幾種方法可實現此目標，但建議使用 [吊具模型](https://sling.apache.org/documentation/bundles/models.html) 邏輯和 [HTML模板語言](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=zh-Hant) (HTL)，與核心元件也一樣。

Sling Models是一組Java注釋，可輕鬆訪問POJO中所需的變數，因此為元件實現Java邏輯提供了簡單、強大和高效的方法。

HTL被設計為一種安全且簡單的模板語言，適合AEM使用。 它可以調用多種形式的邏輯，使它非常靈活。

## 可重用元件模式 {#reusable-component-patterns}

本節中的指南也可用於任何類型的元件，但對於希望在站點或項目之間重複使用的元件（例如核心元件），它們最有意義。 因此，對於僅在單個站點或項目上使用的元件，可以忽略這些准則。

### 預配置功能 {#pre-configurable-capabilities}

除了頁面作者使用的編輯對話框外，元件還可以有一個設計對話框，供模板作者預配置它們。 的 [模板編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 允許設定所有這些預配置，稱為「策略」。

要使元件盡可能可重複使用，應為它們提供有意義的預配置選項。 這將允許啟用或禁用元件的功能以滿足不同站點的特定需要。

### 代理元件模式 {#proxy-component-pattern}

因為每個內容資源都有 `sling:resourceType` 引用元件來呈現它的屬性，通常最好將這些屬性指向特定於站點的元件，而不是指向由多個站點共用的元件。 如果一個站點需要某個元件的不同行為，這將提供更大的靈活性並避免內容重構，因為此自定義可以在特定於站點的元件上實現，並且不會影響其他站點。

但是，對於項目特定的元件，如果不複製任何代碼，則它們應分別引用與 `sling:resourceSuperType` 屬性。 這些主要只指父元件的項目特定元件稱為「代理元件」。 如果代理元件完全繼承了該功能，則它們可以是完全空的，或者可以重新定義元件的某些方面。

>[!TIP]
>
>查看 [使用核心元件](/help/get-started/using.md#create-proxy-components) 以獲取有關如何建立代理元件的詳細資訊。

### 元件版本控制 {#component-versioning}

隨著時間的推移，元件應保持完全相容，但有時需要進行無法保持相容的更改。 解決這些相反需求的一個解決方案是引入元件版本化，方法是在其資源類型路徑中添加一個數字，並在其實現的完全限定的Java類名稱中添加數字。 此版本號表示由定義的主要版本 [語義版本指導](https://semver.org/)，僅對不向後相容的更改遞增。

對元件的以下方面進行不相容的更改將導致它們的新版本：

* Sling模型（遵循語義版本化准則）
* HTL指令碼和模板
* HTML標籤和CSS選擇器
* JSON表示法
* 對話方塊

有關詳細資訊，請參閱 [版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) 文檔。

元件版本控制建立一種對升級非常重要的合同形式，因為它澄清了何時可能需要重新計算某些內容。 另請參閱 [自定義項的升級相容性](customizing.md#upgrade-compatibility-of-customizations)，說明升級時需要採用不同形式的自定義。

為避免痛苦的內容遷移，切勿直接指向內容資源中版本控制的元件非常重要。 根據經驗， `sling:resourceType` 內容的版本號永遠不能包含，或升級元件將要求對內容進行重構。 避免這種情況的最佳方法是 [代理元件模式](#proxy-component-pattern) 如上所述。

### 模型介面 {#model-interfaces}

此模式與HTL `data-sly-use` 指令指向Java介面，而Sling Model實現也正在將自身註冊到元件的資源類型。

與 [代理元件模式](#proxy-component-pattern) 如上所述，這種雙綁定形式提供了以下好的擴展點：

1. 站點可以通過將Sling模型註冊到代理元件的資源類型來重新定義Sling模型的實現，而不必考慮HTL檔案，該檔案仍可指向介面。
1. 站點可以重新定義元件的HTL標籤，而無需考慮它應指向哪個實現邏輯。

## 把它們放在一起 {#putting-it-all-together}

以標題核心元件為例，下面是整個資源類型綁定結構的概述。 它說明了特定於站點的代理元件如何解決元件版本控制問題，以避免內容資源包含任何版本號。 然後，它顯示了元件 `title.html` [HTL](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html) 檔案用於模型介面，而實現通過 [吊具模型](https://sling.apache.org/documentation/bundles/models.html) 注釋。

![資源綁定概述](/help/assets/chlimage_1-32.png)

下面是另一個概述，它不顯示POJO實施的詳細資訊，但是顯示了與 [模板和策略](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html) 。

的 `cq:allowedTemplates` 屬性指明哪些模板可用於站點，以及 `cq:template` 告訴每個頁面關聯的模板是什麼。 每個模板由以下三部分組成：

* **結構**  — 包含將強制在每個頁面上顯示的資源，以及頁面作者將無法刪除的資源，例如頁眉和頁腳元件。
* **初始**  — 包含建立頁面時將複製到頁面的初始內容。
* **策略**  — 包含每個元件到策略的映射，策略是元件的預配置。 此映射允許策略跨模板重用，因此可以集中管理。

![模板和策略概述](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM 專案原型 {#aem-project-archetype}

[項AEM目原型](/help/developing/archetype/overview.md) 建立最小的Adobe Experience Manager項目作為您自己項目的起點，包括使用SlingModels定制HTL元件的示例，用於邏輯和使用推薦的代理模式正確實施核心元件。

**閱讀下一節內容:**

* [使用核心元件](/help/get-started/using.md)  — 在您自己的項目中啟動並運行核心元件。
* [定制核心元件](customizing.md)  — 學習如何設計和定制核心元件。
