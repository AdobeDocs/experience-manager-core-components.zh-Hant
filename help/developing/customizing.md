---
title: 自訂核心元件
description: 核心元件實施多種模式，從簡單的樣式到進階功能重複使用，都可以輕鬆自訂。
role: Architect, Developer, Admin
exl-id: ec4b918b-bc70-4d72-ba84-a24556aedb41
source-git-commit: 5994133947ff697f7c866fe61598c58e37e77008
workflow-type: ht
source-wordcount: '1041'
ht-degree: 100%

---

# 自訂核心元件{#customizing-core-components}

[核心元件](overview.md)實施多種模式，從簡單的樣式到進階功能重複使用，都可以輕鬆自訂。

{{traditional-aem}}

## 彈性的架構 {#flexible-architecture}

核心元件的設計從一開始就具備彈性及擴充性。概略了解其架構，便能了解可在何處進行自訂。

![核心元件架構](/help/assets/screen_shot_2018-12-07at093742.png)

* [設計對話框](/help/get-started/authoring.md#edit-and-design-dialogs)定義作者在編輯對話框中可執行或不可執行的操作。
* [編輯對話框](/help/get-started/authoring.md#edit-and-design-dialogs)只向作者顯示可以使用的選項。
* [Sling 模型](#customizing-the-logic-of-a-core-component)會驗證並準備檢視 (範本) 的內容。
* [Sling 模型的結果](#customizing-the-logic-of-a-core-component)可序列化為 JSON 以供作 SPA 使用案例。
* 針對傳統的伺服器端轉譯，[HTL 會轉譯 HTML](#customizing-the-markup) 伺服器端。
* [HTML 輸出](#customizing-the-markup)具有語義化、易存取、搜尋引擎最佳化等特性，且樣式簡易。

而且所有核心元件都實施[樣式系統](#styling-the-components)。

## AEM 專案原型 {#aem-project-archetype}

[AEM 專案原型](/help/developing/archetype/overview.md)會建立最精簡的 Adobe Experience Manager 專案，作為您專案的開端，包括具有 SlingModel 的自訂 HTL 元件範例，適用於具有建議 Proxy 模式的核心元件的邏輯和正確實施。

## 自訂模式 {#customization-patterns}

### 自訂對話框 {#customizing-dialogs}

無論是[設計對話框或編輯對話框](/help/get-started/authoring.md)，可能會需要自訂核心元件對話框中可用的設定選項。

每個對話框都有一致的節點結構。建議在繼承元件中複寫此結構，以便使用 [Sling Resource Merger](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) 和[隱藏條件](https://helpx.adobe.com/tw/experience-manager/6-5/sites/developing/using/hide-conditions.html)來隱藏、取代或重新排序原始對話框的區段。要複寫的結構定義為索引標籤項目節點層級的任何內容。

若要與對話框目前版本的任何變更完全相容，請勿觸及索引標籤項目層級下的結構 (隱藏、新增至、取代、重新排序等)，這點極為重要。相反地，上層中的索引標籤項目應透過 `sling:hideResource` 屬性隱藏 (請參閱 [Sling 資源合併屬性](https://helpx.adobe.com/tw/experience-manager/6-5/sites/developing/using/sling-resource-merger.html))，並且新增包含自訂設定欄位的新索引標籤項目。`sling:orderBefore` 於必要時可用於重新排序索引標籤項目。

下列對話框示範建議的對話框結構，以及如何隱藏和取代上述繼承的索引標籤：

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

在 Sling 模型中會實施核心元件的商業邏輯。此邏輯可利用 Sling 委派模式進行擴充。

例如，標題核心元件使用請求資源的 `jcr:title` 屬性來提供標題文字。如果未定義 `jcr:title` 屬性，則會實施目前頁面標題的遞補。我們想要變更此行為，以便一律顯示目前頁面的標題。

由於核心元件模型的實施是私人的，因此必須透過委派模式進行擴充。

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

如需委派模式的詳細資訊，請參閱核心元件 GitHub Wiki 文章 [Sling 模型的委派模式](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)。

### 自訂標記 {#customizing-the-markup}

有時進階樣式需要元件採用不同的標記結構。

將需要修改的 HTL 檔案從核心元件複製到 [Proxy 元件](guidelines.md#proxy-component-pattern)中，即可輕鬆完成這項操作。

再次以核心階層連結元件為例，若要自訂其標記輸出，必須將 `breadcrumb.html` 檔案複製到具有指向核心階層連結元件的 `sling:resourceSuperTypes` 的網站專用元件中。

### 設定元件樣式 {#styling-the-components}

自訂的第一個形式是套用 CSS 樣式。

為了輕鬆達成此目標，核心元件會轉譯語義標記，並遵循源自 [Bootstrap](https://getbootstrap.com/) 的標準化命名慣例。此外，為了輕鬆鎖定個別元件的樣式並為其建立命名空間，每個核心元件都包裝在具有「`cmp`」和「`cmp-<name>`」類別的 DIV 元素中。

舉例來說，若檢視 v1 核心階層連結元件的 HTL 檔案：[breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，我們發現元素輸出的階層為 `ol.breadcrumb > li.breadcrumb-item > a`。因此，為了確保 CSS 規則僅影響該元件的階層連結類別，所有規則都應採用命名空間，如下所示：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每個核心元件都利用 AEM [樣式系統功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html) ，此功能可讓範本作者定義可由頁面作者套用至元件的其他 CSS 類別名稱。這允許為每個範本定義一個允許的元件樣式清單，以及其中一個樣式是否應預設套用至該類型的所有元件。

## 升級自訂的相容性 {#upgrade-compatibility-of-customizations}

可能的升級有三種類型：

* 升級 AEM 版本
* 將核心元件升級至新的次要版本
* 將核心元件升級至主要版本

一般而言，將 AEM 升級至新版本不會影響核心元件或已完成的自訂，前提是元件的版本也支援正在移轉至的新 AEM 版本，且自訂功能未使用[已棄用或已移除](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)的 API。

只要使用本頁所述的自訂模式，在不切換至新版主要版本的情況下升級核心元件，通常不會影響自訂功能。

切換至新版主要版本的主要核心元件版本只與內容結構相容，但自訂功能可能需要重構。將針對每個元件版本發佈清楚的變更記錄，以強調會影響此頁面上描述的自訂類型之變更。

## 支援自訂 {#support-of-customizations}

與任何 AEM 元件一樣，針對自訂功能需留意以下幾點：

1. **絕對不要直接修改核心元件的程式碼。**

   這將導致其完全不受支援，未來的元件更新作業也將變得相當棘手。請改用本頁所述的自訂方法。

1. **自訂程式碼由您自行負責。**

   我們的支援計畫不涵蓋自訂程式碼，且回報的問題若無法在[依文件所述使用](/help/get-started/using.md) 的原始核心元件上重現，則不在支援範圍內。

1. **留意已棄用和已移除的功能。**

   隨著每個 AEM 新版本的升級，請密切留意[已棄用和已移除的功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)頁面，確保所有使用的 API 仍是常用的。

另請參閱[核心元件支援](overview.md#core-component-support) 章節。

**閱讀後續章節：**

* [使用核心元件](/help/get-started/using.md) - 在您自己的專案中啟動並執行核心元件。
* [元件指導方針](guidelines.md) - 了解核心元件的實施模式。
