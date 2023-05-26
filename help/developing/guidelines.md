---
title: 元件指引
description: 核心元件遵循的現代實作模式與基礎元件大為不同。
role: Architect, Developer, Admin
exl-id: e8c58fa5-c991-433c-8d38-575dacfc3433
source-git-commit: ee18626280f74a51a799f16d6bf3f5b0be9cd6b9
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 2%

---

# 元件指引 {#component-guidelines}

此 [核心元件](overview.md) 遵循與基礎元件截然不同的現代化實作模式。

此頁面說明這些模式，以及何時使用這些模式來建置您自己的可編寫元件。 第一節　 [一般元件模式](#general-component-patterns) 套用至任何種類的元件，而第二區段則 [可重複使用的元件模式](#reusable-component-patterns) 套用至要跨網站或專案重複使用的元件，例如執行個體的核心元件。

## 一般元件模式 {#general-component-patterns}

本節中的指南建議用於任何型別的元件，無論該元件是否特定於單一專案，或該元件是否要跨網站或專案廣泛地重複使用。

### 可設定的元件 {#configurable-components}

元件可以有包含各種選項的對話方塊。 應運用此工具，讓元件具備彈性且可設定，並避免實作多個主要是彼此變異的元件。

通常，如果線框或設計包含類似元素的變數，這些變數不應實作為不同的元件，而應實作為一個元件，並附上選項供您在變數之間選擇。

若要更進一步跨網站或專案重複使用元件，請參閱 [可預先設定的功能](#pre-configurable-capabilities) 區段。

### 關注點分離 {#separation-of-concerns}

將元件的邏輯（或模型）與標籤範本（或檢視）分開通常是好的做法。 有數種方法可以達成此目的，不過建議使用 [Sling模型](https://sling.apache.org/documentation/bundles/models.html) 邏輯和 [HTML範本語言](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=zh-Hant) (HTL)做為標籤，就像核心元件一樣。

Sling模型是一組Java註解，可輕鬆從POJO存取所需的變數，因此提供簡單、強大且有效率的方式，為元件實作Java邏輯。

HTL的設計初衷是針對AEM量身打造的一種安全且簡單的範本語言。 它可以呼叫多種形式的邏輯，因此非常靈活。

## 可重複使用的元件模式 {#reusable-component-patterns}

本節中的指引也可用於任何型別的元件，但對於打算跨網站或專案重複使用的元件（例如例項的核心元件）來說，這是最合理的指引。 因此，對於僅用於單一網站或專案的元件，可忽略這些准則。

### 可預先設定的功能 {#pre-configurable-capabilities}

除了頁面作者使用的編輯對話方塊之外，元件也可以有一個設計對話方塊，供範本作者預先設定。 此 [範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 允許設定這些稱為「原則」的預設定。

若要讓元件儘可能重複使用，應提供有意義的選項給元件，讓元件可預先設定。 這將允許啟用或停用元件的功能，以符合不同網站的特定需求。

### Proxy元件模式 {#proxy-component-pattern}

由於每個內容資源都有 `sling:resourceType` 參照要呈現元件的屬性，通常好的做法是讓這些屬性指向網站特定的元件，而不是指向由多個網站共用的元件。 這將提供更大的彈性，並可避免在某個網站需要元件的不同行為時進行內容重構，因為此自訂可在網站專用元件上實現，而不會影響其他網站。

不過，若是專案特定的元件不要複製任何程式碼，則每個元件都應使用來參照共用的父元件 `sling:resourceSuperType` 屬性。 這些通常只是參照父元件的專案特定元件稱為「Proxy元件」。 如果Proxy元件完全繼承了功能，則它們可以完全空白，或者它們可以重新定義元件的某些方面。

>[!TIP]
>
>請參閱 [使用核心元件](/help/get-started/using.md#create-proxy-components) 以取得有關如何建立Proxy元件的詳細資訊。

### 元件版本設定 {#component-versioning}

元件應隨時間推移保持完全相容，但有時必須進行無法保持相容的變更。 解決這些矛盾需求的解決方案之一，是在其資源型別路徑中新增數字，並在其實施的完全合格Java類別名稱中新增元件版本設定。 此版本編號代表下列定義的主要版本： [語意版本設定指南](https://semver.org/)，此變數只會隨著不向後相容的變更而遞增。

對下列元件進行不相容的變更，將會導致元件的新版本：

* Sling模型（遵循語意版本設定指南）
* htl指令碼和範本
* HTML標籤和CSS選取器
* JSON呈現
* 對話方塊

如需詳細資訊，請參閱 [版本設定原則](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) 檔案。

元件版本設定會建立對升級很重要的合約形式，因為它可釐清何時可能需要重構某些專案。 另請參閱區段 [升級自訂的相容性](customizing.md#upgrade-compatibility-of-customizations)，說明不同自訂形式升級時所需的考量事項。

為避免痛苦的內容移轉，切勿從內容資源直接指向版本化的元件。 根據經驗， `sling:resourceType` 的內容中絕不能有版本號碼，否則升級元件時也會要求重構內容。 避免此情況的最佳方式是遵循 [Proxy元件模式](#proxy-component-pattern) 如上所述。

### 模型介面 {#model-interfaces}

此模式與HTL有關 `data-sly-use` 指向Java介面的指示，而Sling模型實作也在將自身註冊到元件的資源型別。

當與 [Proxy元件模式](#proxy-component-pattern) 如上所述，這種形式的雙重繫結提供下列很好的擴充點：

1. 網站可以重新定義Sling模型的實作，方法是將其註冊到Proxy元件的資源型別，而不必考慮HTL檔案，它仍可以指向介面。
1. 網站可以重新定義元件的HTL標籤，而不用考慮它應該指向的實施邏輯。

## 整合所有內容 {#putting-it-all-together}

以下為整個資源型別繫結結構的概觀，以標題核心元件為例。 它說明網站特定的Proxy元件如何允許解析元件版本設定，以避免內容資源包含任何版本號碼。 然後它會顯示元件的 `title.html` [HTL](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=zh-Hant) 檔案會使用來建立模型介面，而實作會透過繫結至元件的特定版本 [Sling模型](https://sling.apache.org/documentation/bundles/models.html) 註解。

![資源繫結概觀](/help/assets/chlimage_1-32.png)

底下是另一個概觀，此概觀不會顯示實作POJO的詳細資訊，但會顯示如何關聯 [範本和原則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html) 已被引用。

此 `cq:allowedTemplates` 屬性說明哪些範本可用於網站，以及 `cq:template` 會說明每個頁面的關聯範本是什麼。 每個範本都由下列三個部分組成：

* **結構**  — 包含將在要呈現的每個頁面上強制執行，且頁面作者無法刪除的資源，例如頁首和頁尾元件。
* **初始**  — 包含建立頁面時複製到頁面的初始內容。
* **原則**  — 包含每個元件的原則對應，這是元件的預先設定。 此對應允許跨範本重複使用原則，因此可以集中管理。

![範本和原則概觀](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM 專案原型 {#aem-project-archetype}

[AEM專案原型](/help/developing/archetype/overview.md) 建立最簡化的Adobe Experience Manager專案作為您專案的開端，包括具有SlingModel的自訂HTL元件範例，用於核心元件的邏輯和正確實作以及建議的Proxy模式。

**閱讀後續章節：**

* [使用核心元件](/help/get-started/using.md)  — 在自己的專案中啟動並執行核心元件。
* [自訂核心元件](customizing.md)  — 瞭解如何樣式化和自訂核心元件。
