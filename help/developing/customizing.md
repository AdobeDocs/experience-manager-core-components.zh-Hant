---
title: 自訂核心元件
description: 核心元件實作多種模式，可輕鬆自訂，從簡單的樣式到進階功能可重複使用。
role: Architect, Developer, Admin
exl-id: ec4b918b-bc70-4d72-ba84-a24556aedb41
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 1%

---

# 自訂核心元件{#customizing-core-components}

[核心元件](overview.md)實作了數種允許輕鬆自訂的模式，從簡單的樣式到進階功能重複使用。

## 靈活的體系結構 {#flexible-architecture}

核心元件從一開始就設計為靈活且可擴充。 檢視其架構的概觀，便可顯示可在何處進行自訂。

![核心元件架構](/help/assets/screen_shot_2018-12-07at093742.png)

* [設計對](/help/get-started/authoring.md#edit-and-design-dialogs) 話方塊定義作者可在編輯對話方塊中或無法執行的操作。
* [編輯對](/help/get-started/authoring.md#edit-and-design-dialogs) 話方塊只顯示作者可使用的選項。
* [Sling模](#customizing-the-logic-of-a-core-component) 型會驗證並準備檢視的內容（範本）。
* [SPA使用案例](#customizing-the-logic-of-a-core-component) 可將Sling模型的結果序列化為JSON。
* [HTL會轉譯HTML](#customizing-the-markup) 伺服器端，以利傳統伺服器端轉譯。
* [HTML會](#customizing-the-markup) 輸出語意、可存取、搜尋引擎已最佳化，且易於設定樣式。

所有核心元件都實現[樣式系統](#styling-the-components)。

## AEM 專案原型 {#aem-project-archetype}

[AEM專案原](/help/developing/archetype/overview.md) 型會將最簡化的Adobe Experience Manager專案視為您專案的起點，包括以SlingModels建立的自訂HTL元件範例，以邏輯和正確實作核心元件並搭配建議的Proxy模式。

## 自訂模式 {#customization-patterns}

### 自訂對話方塊 {#customizing-dialogs}

可能需要自定義核心元件對話框中可用的配置選項，無論是[設計對話框或編輯對話框](/help/get-started/authoring.md)。

每個對話方塊都有一致的節點結構。 建議在繼承元件中複製此結構，以便[Sling Resource Merger](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html)和[Hide Conditions](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html)可用來隱藏、替換或重新排序原始對話方塊的區段。 要複製的結構定義為直至索引標籤項目節點層級的任何項目。

要完全相容當前版本上對對話框所做的任何更改，請務必不要接觸頁簽項目級別下的結構（隱藏、添加、替換、重新排序等）。 相反地，父項的索引標籤項目應透過`sling:hideResource`屬性（請參閱[ Sling Resource Merger Properties](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)）隱藏，並新增包含定製配置欄位的新索引標籤項目。 `sling:orderBefore` 可以視需要重新排序索引標籤項目。

以下對話方塊示範建議的對話方塊結構，以及如何依上述方式隱藏和取代繼承的標籤：

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

核心元件的商業邏輯是在Sling模型中實作。 此邏輯可使用Sling委派模式來擴充。

例如，標題核心元件使用請求資源的`jcr:title`屬性來提供標題文本。 若未定義`jcr:title`屬性，則會實作目前頁面標題的後援。 我們想要變更行為，以一律顯示目前頁面的標題。

由於核心元件模型的實作為私人模型，因此必須以委派模式加以擴充。

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

如需委派模式的詳細資訊，請參閱核心元件GitHub Wiki文章[Sling模型的委派模式](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)。

### 自定義標籤 {#customizing-the-markup}

有時，進階樣式需要元件的不同標籤結構。

將需要修改的HTL檔案從核心元件複製到[代理元件中，即可輕鬆完成此操作。](guidelines.md#proxy-component-pattern)

再以核心階層連結元件的範例為例，若要自訂其標籤輸出，必須將`breadcrumb.html`檔案複製至具有指向核心階層連結元件之`sling:resourceSuperTypes`的網站特定元件。

### 元件的樣式 {#styling-the-components}

第一種自訂形式是套用CSS樣式。

為了簡化操作，核心元件會轉譯語義標籤，並遵循受[Bootstrap](https://getbootstrap.com/)啟發的標準化命名慣例。 此外，為了輕鬆定位和命名個別元件的樣式，每個核心元件都包裝在具有「`cmp`」和「`cmp-<name>`」類別的DIV元素中。

例如，查看v1核心階層連結元件的HTL檔案：[breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，我們發現元素輸出的階層為`ol.breadcrumb > li.breadcrumb-item > a`。 因此，為了確定CSS規則只影響該元件的階層連結類別，所有規則的命名方式皆應如下所示：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每個核心元件都利用AEM [樣式系統功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html)，該功能允許範本作者定義可由頁面作者套用至元件的其他CSS類別名稱。 這可為每個範本定義允許的元件樣式清單，以及其中一個預設應套用至該類型的所有元件。

## 自定義項的升級相容性 {#upgrade-compatibility-of-customizations}

有三種不同的升級方式：

* 升級AEM版本
* 將核心元件升級至新的次要版本
* 將核心元件升級至主要版本

一般而言，將AEM升級至新版本不會影響核心元件或完成的自訂，前提是元件的版本也支援要移轉至的新AEM版本，且自訂不使用已[遭取代或移除的API](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)。

升級核心元件而不切換至較新的主要版本，只要使用本頁所述的自訂模式，就不應影響自訂。

切換至較新的主要核心元件版本僅與內容結構相容，但可能需要重構自訂內容。 系統會針對每個元件版本發佈清除變更記錄，以反白標示會影響本頁面所述自訂類型的變更。

## 支援自訂 {#support-of-customizations}

與任何AEM元件一樣，有許多關於自訂的事項需要注意：

1. **請勿直接修改核心元件的程式碼。**

   這會使這些元件完全不受支援，並讓未來元件的更新過程充滿痛苦。 請改用本頁所述的自訂方法。

1. **自訂程式碼由您自行負責。**

   我們的支援計畫不涵蓋自訂程式碼，且以[作為記錄檔案的Vanilla核心元件無法重制的回報問題將不符合資格。](/help/get-started/using.md)

1. **觀看過時和移除的功能。**

   將每個新AEM版本升級至後，請留意[已過時和已移除的功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)頁面，以確保所有使用的API仍為熱門版。

另請參閱[核心元件支援](overview.md#core-component-support)一節。

**閱讀下一節內容:**

* [使用核心元件](/help/get-started/using.md)  — 在您自己的專案中開始使用核心元件。
* [元件准則](guidelines.md)  — 了解核心元件的實作模式。
