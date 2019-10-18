---
title: 自訂核心元件
seo-title: 自訂核心元件
description: 核心元件實作數種模式，可輕鬆自訂，從簡單樣式到進階功能可重複使用。
seo-description: AEM核心元件會建置數種可輕鬆自訂的模式，從簡單的樣式到進階功能可重複使用。
uuid: 38d22b85-4867-4716-817a-10ee2f8de6f5
contentOwner: 使用者
content-type: 參考
topic-tags: 開發
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 3c9e0ade-1ce0-4e34-ae04-8da63f9b6c4f
translation-type: tm+mt
source-git-commit: 683b4f4705c226275439a408423cbf1b23bea66f

---


# 自訂核心元件{#customizing-core-components}

核心元 [件實作數種模式](developing.md) ，可讓您輕鬆自訂，從簡單的樣式到進階功能可重複使用。

## 靈活的架構 {#flexible-architecture}

核心元件從一開始就設計為靈活、可擴展。 檢視其架構的概觀，以瞭解可在何處進行自訂。

![核心元件架構](assets/screen_shot_2018-12-07at093742.png)

* [設計對話框](authoring.md#edit-and-design-dialogs) ，定義作者可以在編輯對話框中執行或無法執行的操作。
* [編輯對話框](authoring.md#edit-and-design-dialogs) ，僅顯示作者允許使用的選項。
* [Sling模型](#customizing-the-logic-of-a-core-component) 會驗證並準備檢視的內容（範本）。
* [Sling模型的結果可序列化](#customizing-the-logic-of-a-core-component) ，以用於SPA使用案例的JSON。
* [HTL會轉譯HTML伺服器端](#customizing-the-markup) ，以用於傳統伺服器端轉譯。
* [HTML輸出具有語義](#customizing-the-markup) 、可存取、搜尋引擎最佳化，而且樣式簡單。

所有核心元件都實作 [Style System](customizing.md)。

## AEM Project Archetype {#aem-project-archetype}

[AEM Project Archetype會為您自己的專案建立最小的Adobe Experience Manager專案，包括使用SlingModels自訂HTL元件的Helloworld範例，以邏輯和正確實作具有建議之proxy模式的核心元件。](overview.md)

## 自訂模式 {#customization-patterns}

### 自訂對話方塊 {#customizing-dialogs}

可能需要自定義核心元件對話框中可用的配置選項，無論是「設計對話框」 [還是「編輯對話框」](authoring.md)。

每個對話框都具有一致的節點結構。 建議將此結構複製在繼承元件中，以便 [Sling Resource Merger](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) and [Hide Conditions](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) (Sling Resource Mergare and Hide Conditions)可用來隱藏、取代或重新排序原始對話方塊的區段。 要複製的結構定義為任何到頁籤項節點級別的結構。

要完全相容當前版本對對話框所做的任何更改，請務必不要接觸Tab項級別下的結構（隱藏、添加到、替換、重新排序等）。 相反地，父代的標籤項目應該透過屬性隱藏 `sling:hideResource` (請參閱 [Sling Resource Merger Properties](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html))，而新增的標籤項目則包含定製設定欄位。 `sling:orderBefore` 可用來重新排序索引標籤項目。

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

### 自訂核心元件的邏輯 {#customizing-the-logic-of-a-core-component}

核心元件的Business邏輯是在Sling Models中實作。 此邏輯可透過使用Sling委派模式來擴充。

例如，標題核心元件使用所請 `jcr:title` 求資源的屬性來提供標題文本。 如果未 `jcr:title` 定義屬性，則會實作目前頁面標題的後援。 我們想要變更行為，以便始終顯示目前頁面的標題。

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

如需委派模式的詳細資訊，請參閱核心元件GitHub wiki文章 [Delegation Pattern for Sling Models](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)。

### 自定義標籤 {#customizing-the-markup}

有時，進階樣式需要元件的不同標籤結構。

您可輕鬆將需要從核心元件修改的HTL檔案複製至proxy元件。

再舉核心階層連結元件的範例，若要自訂其標籤輸出， `breadcrumb.html` 檔案必須複製至具有指向核心階層連結元件的網站 `sling:resourceSuperTypes` 特定元件中。

### 設定元件的樣式 {#styling-the-components}

第一種自訂形式是套用CSS樣式。

為了輕鬆完成，核心元件會轉換語義標籤，並遵循受 [Bootstrap啟發的標準命名慣例](https://getbootstrap.com/)。 此外，為了輕鬆定位和命名個別元件的樣式，每個核心元件都會封裝在具有" `cmp`"和" `cmp-<name>`"類的DIV元素中。

例如，查看v1核心階層連結元件的HTL檔案： [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，我們看到元素輸出的階層 `ol.breadcrumb > li.breadcrumb-item > a`。 因此，若要確定CSS規則只影響該元件的階層連結類別，所有規則都應以如下所示的名稱命名：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每個核心元件都運用AEM [Style System](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) （AEM樣式系統）功能，讓範本作者定義其他CSS類別名稱，頁面作者可套用至元件。 這允許為每個模板定義一個允許的元件樣式清單，以及其中一個樣式是否預設應用於該類型的所有元件。

## 定製的升級相容性 {#upgrade-compatibility-of-customizations}

有三種不同的升級方式：

* 升級AEM版本
* 將核心元件升級到新的次要版本
* 將核心元件升級到主要版本

一般而言，將AEM升級至新版本不會影響核心元件或自訂作業，但元件版本也支援要移轉至的新AEM版本，且自訂作業不會使用已過時或移除 [的API](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html)。

升級核心元件而不切換至較新的主要版本時，只要使用本頁所述的自訂模式，就不會影響自訂。

切換至較新的主要核心元件版本僅與內容結構相容，但自訂可能需要重新構圖。 將為每個元件版本發佈清除更改日誌，以突出顯示將影響本頁所述的定製類型的更改。

## 支援自訂 {#support-of-customizations}

和任何AEM元件一樣，在自訂設定方面有許多需要注意的事項：

1. **切勿直接修改核心元件的程式碼。**

   這會使這些元件完全不受支援，並讓元件的未來更新變得十分痛苦。 請改用本頁所述的自訂方法。

1. **自訂代碼是您自己的責任。**

   我們的支援計畫不涵蓋自訂程式碼，所回報的問題無法與檔案所述的Vanilla Core Components [一起重制](using.md) ，將無法符合資格。

1. **觀看已過時和移除的功能。**

   在將每個新AEM版本升級至時，請留意「已過時和已移除的功能」頁面，以確保所有使用的API仍 [為熱門](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html) 。

另請參閱核 [心元件支援](developing.md#core-component-support) 。

**閱讀下一節內容:**

* [使用核心元件](using.md) -在您自己的專案中使用核心元件進行啟動和執行。
* [元件准則](guidelines.md) -瞭解核心元件的實作模式。
