---
title: 自訂核心元件
description: 核心元件實作數種模式，可輕鬆自訂，從簡單樣式到進階功能可重複使用。
role: 架構師、開發人員、管理員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '1109'
ht-degree: 2%

---


# 自訂核心元件{#customizing-core-components}

[核心元件](overview.md)實作了數種可輕鬆自訂的模式，從簡單樣式到進階功能可重複使用。

## 靈活的體系結構{#flexible-architecture}

核心元件從一開始就設計為靈活、可擴展。 檢視其架構的概觀，以瞭解可在何處進行自訂。

![核心元件架構](/help/assets/screen_shot_2018-12-07at093742.png)

* [設計對話](/help/get-started/authoring.md#edit-and-design-dialogs) 框定義作者可以在編輯對話框中執行或不能執行的操作。
* [編輯對](/help/get-started/authoring.md#edit-and-design-dialogs) 話方塊只顯示作者允許使用的選項。
* [Sling模型](#customizing-the-logic-of-a-core-component) 會驗證並準備檢視的內容（範本）。
* [Sling模型的結果](#customizing-the-logic-of-a-core-component) 可序列化為JSONSPA以用於使用案例。
* [HTL會轉譯](#customizing-the-markup) HTML伺服器端，以進行傳統伺服器端轉譯。
* [HTML輸出](#customizing-the-markup) 具有語義、可存取、搜尋引擎最佳化，而且樣式簡單。

所有核心元件都實施[Style System](#styling-the-components)。

## AEM 專案原型 {#aem-project-archetype}

[Project AEM  Archety會將最小的Adobe Experience Manager專案視為您自己專案的起點，包括自訂HTL元件與SlingModels的範例，以邏輯和正確實作核心元件與建議的proxy模式。](/help/developing/archetype/overview.md) 

## 自訂模式{#customization-patterns}

### 自定義對話框{#customizing-dialogs}

您可能需要自訂核心元件對話方塊中可用的設定選項，不論是[設計對話方塊或編輯對話方塊](/help/get-started/authoring.md)。

每個對話框都具有一致的節點結構。 建議將此結構複製在繼承元件中，以便[Sling Resource Merger](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html)和[Hide Conditions](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html)可用來隱藏、取代或重新排序原始對話方塊的區段。 要複製的結構定義為任何到頁籤項節點級別的結構。

要完全相容當前版本對對話框所做的任何更改，請務必不要接觸Tab項級別下的結構（隱藏、添加到、替換、重新排序等）。 而是透過`sling:hideResource`屬性隱藏父代的標籤項目（請參閱[ Sling Resource Merger Properties](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)），以及新增包含定製設定欄位的標籤項目。 `sling:orderBefore` 可用來重新排序索引標籤項目。

下面的對話框演示了建議的對話框結構，以及如何隱藏和替換繼承的頁籤，如上所述：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="https://www.jcp.org/jcr/1.0"
          xmlns:nt="https://www.jcp.org/jcr/nt/1.0"
          xmlns:granite="https://www.adobe.com/jcr/granite/1.0"
          jcr:primaryType="nt:unstructured">
    <content jcr:primaryType="nt:unstructured">
        <items jcr:primaryType="nt:unstructured">
            <tabs jcr:primaryType="nt:unstructured">
                <items jcr:primaryType="nt:unstructured">
                        <originalTab
                                jcr:primaryType="nt:unstructured"
                                sling:hideResource="true"/>
                        </originalTab>
                        <myTab
                               jcr:primaryType="nt:unstructured"
                               jcr:title="My Tab"
                               sling:resourceType="granite/ui/components/coral/foundation/container"/>
                               <!-- myTab content -->
                        </myTab>
                </items>
            </basic>
        </items>
    </content>
</jcr:root>
```

### 自訂核心元件{#customizing-the-logic-of-a-core-component}的邏輯

核心元件的Business邏輯是在Sling Models中實作。 此邏輯可透過使用Sling委派模式來擴充。

例如，標題核心元件使用所請求資源的`jcr:title`屬性來提供標題文本。 如果未定義`jcr:title`屬性，則會實作目前頁面標題的後援。 我們想要變更行為，以便始終顯示目前頁面的標題。

由於核心元件模型的實作是私有的，因此必須以委派模式加以擴充。

```java
@Model(adaptables = SlingHttpServletRequest.class,
       adapters = Title.class,
       resourceType = "myproject/components/pageHeadline")
public class PageHeadline implements Title {
    @ScriptVariable private Page currentPage;
    @Self @Via(type = ResourceSuperType.class)
    private Title title;
    @Override public String getText() {
        return currentPage.getTitle();
    }
    @Override public String getType() {
        return title.getType();
    }
}
```

如需委派模式的詳細資訊，請參閱核心元件GitHub Wiki文章[ Delegation Pattern for Sling Models](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)。

### 自定義標籤{#customizing-the-markup}

有時，進階樣式需要元件的不同標籤結構。

您可輕鬆將需要從核心元件修改的HTL檔案複製至proxy元件。

再舉核心階層連結元件的範例，若要自訂其標籤輸出，必須將`breadcrumb.html`檔案複製至具有指向核心階層連結元件之`sling:resourceSuperTypes`的網站特定元件。

### 設定元件{#styling-the-components}的樣式

第一種自訂形式是套用CSS樣式。

為了讓這更簡單，核心元件會轉譯語義標籤並遵循受[Bootstrap](https://getbootstrap.com/)啟發的標準命名慣例。 此外，為了輕鬆定位和命名個別元件的樣式，每個核心元件都會包裝在DIV元素中，並包含&quot; `cmp`&quot;和&quot; `cmp-<name>`&quot;類別。

例如，查看v1核心階層連結元件的HTL檔案：[breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，我們看到元素輸出的階層為`ol.breadcrumb > li.breadcrumb-item > a`。 因此，若要確定CSS規則只影響該元件的階層連結類別，所有規則都應以如下所示的名稱命名：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每個核心元件都採用AEM[樣式系統功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html)，可讓範本作者定義其他CSS類別名稱，頁面作者可套用至元件。 這允許為每個模板定義一個允許的元件樣式清單，以及其中一個樣式是否預設應用於該類型的所有元件。

## 自定義的升級相容性{#upgrade-compatibility-of-customizations}

有三種不同的升級方式：

* 升級版AEM本
* 將核心元件升級到新的次要版本
* 將核心元件升級到主要版本

通常，升AEM級至新版本不會影響核心元件或自訂，但元件版本也支援移轉至新AEM版本，且自訂不使用[已過時或移除](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)的API。

升級核心元件而不切換至較新的主要版本時，只要使用本頁所述的自訂模式，就不會影響自訂。

切換至較新的主要核心元件版本僅與內容結構相容，但自訂可能需要重新構圖。 將為每個元件版本發佈清除更改日誌，以突出顯示將影響本頁所述的自定義類型的更改。

## 支援自定義{#support-of-customizations}

與任何元AEM件一樣，在自訂方面有許多需注意的事項：

1. **切勿直接修改核心元件的程式碼。**

   這會使這些元件完全不受支援，並讓元件的未來更新變得十分痛苦。 請改用本頁所述的自訂方法。

1. **自訂代碼是您自己的責任。**

   我們的支援計畫不涵蓋自訂程式碼，而且報告的問題無法與[當做檔案記錄使用的Vanilla Core Components重制。](/help/get-started/using.md)

1. **觀看已過時和移除的功能。**

   將每個新AEM版本升級至後，請留意[已過時和已移除的功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)頁面，以確保所有使用的API仍為熱門。

另請參閱[核心元件支援](overview.md#core-component-support)部分。

**閱讀下一節內容:**

* [使用核心元件](/help/get-started/using.md) -在您自己的專案中啟動並執行核心元件。
* [元件准則](guidelines.md) -瞭解核心元件的實作模式。
