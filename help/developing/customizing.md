---
title: 自訂核心元件
description: 核心元件實作多種模式，可讓您輕鬆自訂，從簡單的樣式設定到進階功能重複使用。
role: Architect, Developer, Admin
exl-id: ec4b918b-bc70-4d72-ba84-a24556aedb41
source-git-commit: bd688d422a072a9d5627c27817ac67f95829de4f
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 0%

---

# 自訂核心元件{#customizing-core-components}

[核心元件](overview.md)實作多種模式，從簡單的樣式到進階功能重複使用，都可以輕鬆自訂。

## 彈性的架構 {#flexible-architecture}

核心元件的設計從一開始就具備彈性及擴充性。 概略瞭解其架構便能瞭解可在何處進行自訂。

![核心元件架構](/help/assets/screen_shot_2018-12-07at093742.png)

* [設計對話方塊](/help/get-started/authoring.md#edit-and-design-dialogs)定義作者在編輯對話方塊中可以或不能做什麼。
* [編輯對話方塊](/help/get-started/authoring.md#edit-and-design-dialogs)只顯示作者可以使用的選項。
* [Sling模型](#customizing-the-logic-of-a-core-component)會驗證並準備檢視（範本）的內容。
* [對於SPA使用案例，Sling模型](#customizing-the-logic-of-a-core-component)的結果可序列化為JSON。
* [對於傳統的伺服器端轉譯，HTL會轉譯HTML](#customizing-the-markup)伺服器端。
* [HTML輸出](#customizing-the-markup)具有語意性、可存取、已最佳化搜尋引擎，且樣式簡易。

而且所有核心元件都實作[樣式系統](#styling-the-components)。

## AEM 專案原型 {#aem-project-archetype}

[AEM專案原型](/help/developing/archetype/overview.md)會建立最低限度的Adobe Experience Manager專案，作為您專案的開端，包括具有SlingModel的自訂HTL元件範例，適用於具有建議Proxy模式的核心元件的邏輯和正確實作。

## 自訂模式 {#customization-patterns}

### 自訂對話方塊 {#customizing-dialogs}

可能需要自訂核心元件對話方塊中可用的組態選項，無論是[設計對話方塊或編輯對話方塊](/help/get-started/authoring.md)。

每個對話方塊都有一致的節點結構。 建議在繼承元件中復寫此結構，以便使用[Sling Resource Merger](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html)和[隱藏條件](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html)來隱藏、取代或重新排序原始對話方塊的區段。 要復寫的結構定義為標籤專案節點層級的任何內容。

若要與對話方塊目前版本的任何變更完全相容，請勿觸及索引標籤專案層級下的結構（隱藏、新增至、取代、重新排序等），這點極為重要。 相反地，父系中的索引標籤專案應透過`sling:hideResource`屬性隱藏（請參閱[Sling資源合併屬性](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)），並且新增包含自訂設定欄位的新索引標籤專案。 必要時可使用`sling:orderBefore`重新排序索引標籤專案。

下列對話方塊示範建議的對話方塊結構，以及如何隱藏和取代上述繼承的索引標籤：

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
                        <myTab
                               jcr:primaryType="nt:unstructured"
                               jcr:title="My Tab"
                               sling:resourceType="granite/ui/components/coral/foundation/container">
                                  
                               <!-- myTab content -->
                                  
                        </myTab>
                </items>
            </tabs>
        </items>
    </content>
</jcr:root>
```

### 自訂核心元件的邏輯 {#customizing-the-logic-of-a-core-component}

在Sling模型中實作核心元件的商業邏輯。 可使用Sling委派模式來擴充此邏輯。

例如，標題核心元件使用請求資源的`jcr:title`屬性來提供標題文字。 如果未定義`jcr:title`屬性，則會實作目前頁面標題的遞補。 我們想要變更行為，以便一律顯示目前頁面的標題。

由於核心元件模型的實作是私人的，因此必須使用委派模式將其擴充。

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

### 自訂標籤 {#customizing-the-markup}

有時進階樣式需要元件的不同標籤結構。

將需要修改的HTL檔案從核心元件複製到[Proxy元件中，可輕鬆完成這項操作。](guidelines.md#proxy-component-pattern)

再次以核心階層連結元件為例，若要自訂其標籤輸出，必須將`breadcrumb.html`檔案複製到具有指向核心階層連結元件`sling:resourceSuperTypes`的網站特定元件中。

### 設定元件的樣式 {#styling-the-components}

自訂的第一個形式是套用CSS樣式。

為了輕鬆達成此目的，核心元件會轉譯語意標籤，並遵循由[Bootstrap](https://getbootstrap.com/)所激發的標準化命名慣例。 此外，為了輕鬆鎖定個別元件的樣式並為其建立名稱空間，每個核心元件都包裝在具有「`cmp`」和「`cmp-<name>`」類別的DIV元素中。

舉例來說，若檢視v1核心階層連結元件的HTL檔案： [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，我們發現元素輸出的階層為`ol.breadcrumb > li.breadcrumb-item > a`。 因此，為了確保CSS規則僅影響該元件的階層連結類別，所有規則都應採用名稱空間，如下所示：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每個核心元件都運用AEM [樣式系統功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html?lang=zh-Hant)，此功能可讓範本作者定義可由頁面作者套用至元件的其他CSS類別名稱。 這允許為每個範本定義一個允許的元件樣式清單，以及其中一個樣式是否預設應套用至該型別的所有元件。

## 升級自訂的相容性 {#upgrade-compatibility-of-customizations}

可能的升級有三種型別：

* 升級AEM版本
* 將核心元件升級至新的次要版本
* 將核心元件升級至主要版本

一般而言，將AEM升級至新版本不會影響核心元件或已完成的自訂，前提是元件的版本也支援正在移轉至的新AEM版本，且自訂功能不會使用[已棄用或已移除](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)的API。

升級核心元件而不切換至更新的主要版本應該不會影響自訂，前提是使用本頁所述的自訂模式。

切換至更新的主要核心元件版本只與內容結構相容，但自訂功能可能需要重構。 將針對每個元件版本發佈清楚的變更記錄，以強調會影響此頁面上描述的自訂型別之變更。

## 支援自訂 {#support-of-customizations}

和任何AEM元件一樣，關於自訂，有許多需要注意的事項：

1. **絕對不要直接修改核心元件的程式碼。**

   這將導致其完全不受支援，且使元件的未來更新成為一個痛苦的過程。 請改用本頁所述的自訂方法。

1. **自訂程式碼由您自行負責。**

   我們的支援計畫不會涵蓋自訂程式碼，且無法以[使用且記錄為](/help/get-started/using.md)的vanilla核心元件重現的回報問題不符合資格。

1. **觀看已過時和已移除的功能。**

   隨著每個新AEM版本的升級，請密切留意[已過時和已移除的功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)頁面，確保所有使用的API仍是常用的。

另請參閱[核心元件支援](overview.md#core-component-support)區段。

**閱讀後續章節：**

* [使用核心元件](/help/get-started/using.md) — 在您自己的專案中啟動並執行核心元件。
* [元件指導方針](guidelines.md) — 瞭解核心元件的實作模式。
