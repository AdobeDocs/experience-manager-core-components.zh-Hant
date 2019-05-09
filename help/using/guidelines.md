---
title: 元件准則
seo-title: 元件准則
description: 核心元件遵循與基礎元件截然不同的現代化實作模式。
seo-description: 核心元件遵循與基礎元件截然不同的現代化實作模式。
uuid: b1daea89-da3 c-454f-8ab5-d75 a19412954
contentOwner: 使用者
content-type: 引用
topic-tags: 開發
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 170dba8f-a2 ed-442e-a56 e-126b338 c36 e
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 元件准則 {#component-guidelines}

[核心元件](developing.md) 遵循與基礎元件截然不同的現代化實作模式。

此頁面說明這些模式，以及使用它們來建立您自己的授權元件。第一節 [一般元件模式](guidelines.md) 適用於任何種類的元件，而第二個區域 [可重復使用的元件模式](guidelines.md) 適用於希望跨網站或專案重復使用的元件，例如核心元件。

## 一般元件模式 {#general-component-patterns}

建議針對任何類型的元件使用本節中的准則，無論元件是屬於單一專案，還是要在網站或專案中廣泛重復使用元件。

### 可設定的元件 {#configurable-components}

元件可以具有各種選項的對話方塊。應運用這項功能，讓元件靈活靈活，並避免實作大部分彼此變化的元件。

通常，如果線框或設計包含類似元素的變化，這些變化不應實作為不同的元件，而是一個包含選項的元件，可選擇各種變化。

若要進一步瞭解，如果跨網站或專案重復使用元件，請參閱 [「預先設定的功能](#pre-configurable-capabilities) 」區段。

### 分離顧慮 {#separation-of-concerns}

將元件的邏輯(或模型)與標記範本(或檢視)分開，通常是很好的做法。有幾種方法可達成此目標，但建議使用的 [是邏輯](https://sling.apache.org/documentation/bundles/models.html) 和 [HTML範本語言](https://helpx.adobe.com/experience-manager/htl/using/overview.html) (HTL)的Sling模型，例如核心元件亦然。

Sling Model是一組Java註解，可輕鬆存取POJO所需的變數，因此提供簡單、強大且方便的方式來建置元件的Java邏輯。

HTL是專為AEM量身打造的安全且簡單的範本語言。它可以呼叫許多形式的邏輯，使它非常有彈性。

## 可重復使用的元件模式 {#reusable-component-patterns}

本節中的准則適用於任何類型的元件，但對於希望跨網站或專案重復使用的元件，例如核心元件，它們最有意義。因此，只能忽略僅用於單一網站或專案的元件。

### 預先設定的功能 {#pre-configurable-capabilities}

除了頁面作者所使用的編輯對話方塊外，元件也可以有設計對話方塊，讓範本作者預先進行預先設定。[範本編輯器](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) 允許設定所有這些預先設定，稱為「原則」。

若要讓元件盡可能重復使用，應提供有意義的選項進行預先設定。這將允許啓用或停用元件的功能，以符合不同網站的特定需求。

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:49:04.584-0400

Unclear how I can add my own capability toggle (for example, if i extend a component and want to toggle that extended functionality ... )

 -->

### Proxy元件模式 {#proxy-component-pattern}

由於每個內容資源都有參照元件的 `sling:resourceType` 屬性，因此通常建議將這些屬性指向網站特定元件，而不是指向多個網站共用的元件。如果某個網站需要不同的元件行為，因此可提供更大的彈性並避免內容重構，因為此自訂隨後可在網站特定元件上達成，而不會影響其他網站。

但是，如果專案專用的元件不要複製任何程式碼，則他們應參照共用父元件與 `sling:resourceSuperType` 屬性。這些專案特有的元件主要是指父元件，稱為「proxy元件」。如果Proxy元件完全繼承功能，或者可以重新定義元件的某些方面，則可以完全空白。

### 元件版本管理 {#component-versioning}

元件必須持續相容於時間，但有時無法維持不相容的變更。面對這些反對需求的一個解決之道，就是在其資源類型路徑中新增一個數字，並在其實施的完全合格Java類別名稱中加入數字。此版本號碼代表一個主要版本， [由語義版本修訂指引](https://semver.org/)定義，僅針對不相容的變更增加。

不相容地變更元件的下列層面將會產生新版本：

* Sling Model(遵循語義版本指引)
* HTL指令碼與範本
* HTML Markup和CSS選擇器
* JSON表示法
* 對話方塊

如需詳細資訊，請參閱GitHub中 [的版本修訂政策](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) 文件。

元件版本修訂建立了一種對升級很重要的合約形式，因為在某些情況下可能需要重新重構。另請參閱 [「自訂](customizing.md#upgrade-compatibility-of-customizations)相容性的升級相容性」，說明不同自訂表單的升級需求。

為避免內容移轉困難，切勿直接指向內容資源的版本化元件。作為縮圖規則，內容中 `sling:resourceType` 的內容絕對不一定有版本編號，或者升級元件也需要重構內容。避免此問題的最佳方式是遵循上述 [的Proxy元件模式](#proxy-component-pattern) 。

### 模型介面 {#model-interfaces}

此模式是關於HTL `data-sly-use` 的指示，指向Java介面，而Sling Model實作也會註冊至元件的資源類型。

結合上述 [Proxy元件模式](#proxy-component-pattern) 時，這種雙重系結提供的雙連繫結提供了下列優點：

1. 網站可以將Sling模型的實作重新定義為proxy元件的資源類型，而不需考慮HTL檔案，這個問題仍然可以指向介面。
1. 網站可以重新定義元件的HTL標記，而不需考慮該元件應指向哪個實作邏輯。

## 將一切整合 {#putting-it-all-together}

以下是整個資源類型系結結構的概述，以「標題核心元件」為例。它說明網站特定Proxy元件如何允許解決元件版本修訂，以避免內容資源包含任何版本號碼。接著，它會顯示元件 `title.html`[的HTL](https://helpx.adobe.com/experience-manager/htl/using/overview.html) 檔案如何用於模型介面，而建置Binds則會透過 [Sling Model](https://sling.apache.org/documentation/bundles/models.html) 附註來系結至元件的特定版本。

![資源系結概述](assets/chlimage_1-32.png)

以下是另一個概述，無法顯示實施POJO的詳細資訊，但揭示了相關 [範本和原則](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/page-templates-editable.html) 的參照方式。

`cq:allowedTemplates` 屬性會告訴您哪些範本可用於網站， `cq:template` 並告知每個頁面相關範本的內容。每個範本都有下列三個部分：

* **結構**包含在每個頁面上強制顯示的資源，而且頁面作者無法刪除，例如頁面頁首和頁尾元件。
* **初始**包含初始內容，會在建立頁面時重復。
* **原則**包含每個元件對應至原則的對應，這是元件的預先設定。此對應可讓您跨範本重復使用原則，並因此進行集中管理。

![範本與政策概述](assets/screen_shot_2018-12-07at093102.png)

**下一步閱讀：**

* [使用核心元件](using.md) -在您自己的專案中啓動並執行核心元件。
* [自訂核心元件](customizing.md) -瞭解如何樣式和自訂核心元件。
