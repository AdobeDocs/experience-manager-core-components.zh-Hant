---
title: 自訂核心元件
description: 核心元件實作多種模式，可讓您輕鬆自訂，從簡單的樣式設定到進階功能重複使用。
role: Architect, Developer, Admin
exl-id: ec4b918b-bc70-4d72-ba84-a24556aedb41
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 1%

---

# 自訂核心元件{#customizing-core-components}

此 [核心元件](overview.md) 實作多種模式，從簡單的樣式設定到進階功能重複使用，讓您輕鬆自訂。

## 彈性的架構 {#flexible-architecture}

核心元件的設計從一開始就是為了靈活且可擴充。 概略瞭解其架構可揭示可在何處進行自訂。

![核心元件架構](/help/assets/screen_shot_2018-12-07at093742.png)

* [設計對話方塊](/help/get-started/authoring.md#edit-and-design-dialogs) 定義作者在「編輯」對話方塊中可以或無法執行的動作。
* [編輯對話方塊](/help/get-started/authoring.md#edit-and-design-dialogs) 僅向作者顯示他們可使用的選項。
* [Sling模型](#customizing-the-logic-of-a-core-component) 驗證並準備檢視（範本）的內容。
* [Sling模型的結果](#customizing-the-logic-of-a-core-component) 可針對SPA使用案例序列化為JSON。
* [HTL會轉譯HTML](#customizing-the-markup) 伺服器端用於傳統伺服器端轉譯。
* [HTML輸出](#customizing-the-markup) 語意化、可存取、最佳化搜尋引擎，且樣式簡易。

而所有核心元件都實作 [樣式系統](#styling-the-components).

## AEM 專案原型 {#aem-project-archetype}

[AEM專案原型](/help/developing/archetype/overview.md) 建立最小的Adobe Experience Manager專案作為您專案的開端，包括具有SlingModel的自訂HTL元件範例，用於核心元件的邏輯和正確實作具有建議的Proxy模式。

## 自訂模式 {#customization-patterns}

### 自訂對話方塊 {#customizing-dialogs}

您可能需要自訂核心元件對話方塊中可用的設定選項，無論是 [設計對話方塊或編輯對話方塊](/help/get-started/authoring.md).

每個對話方塊都有一致的節點結構。 建議在繼承元件中複製此結構，以便 [Sling資源合併](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) 和 [隱藏條件](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) 可用來隱藏、取代或重新排序原始對話方塊的區段。 要復寫的結構定義為標籤專案節點層級的任何內容。

若要與目前版本對話方塊上的任何變更完全相容，請勿觸及索引標籤專案層級之下的結構（隱藏、新增至、取代、重新排序等），這點非常重要。 反之，父系中的索引標籤專案應透過以下方式隱藏： `sling:hideResource` 屬性(請參閱 [Sling資源合併屬性](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html))，以及包含客制設定欄位的新標籤專案。 `sling:orderBefore` 必要時可用於重新排序索引標籤專案。

以下對話方塊示範建議的對話方塊結構，以及如何如上所述隱藏和取代繼承的索引標籤：

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

在Sling模型中實作核心元件的商業邏輯。 可以使用Sling委派模式來擴充此邏輯。

例如，標題核心元件會使用 `jcr:title` 提供標題文字之請求資源的屬性。 若否 `jcr:title` 屬性已定義，則會實作目前頁面標題的遞補。 我們想要變更行為，以便一律顯示目前頁面的標題。

由於核心元件模型的實作是私人的，因此必須使用委派模式來擴充它們。

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

如需委派模式的詳細資訊，請參閱核心元件GitHub Wiki文章 [Sling模型的委派模式](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models).

### 自訂標籤 {#customizing-the-markup}

有時進階樣式需要元件的不同標籤結構。

將需要修改的HTL檔案從核心元件複製到中，即可輕鬆完成這項操作 [proxy元件。](guidelines.md#proxy-component-pattern)

再次以核心階層連結元件為例，若要自訂其標籤輸出，請 `breadcrumb.html` 必須將檔案複製到具有 `sling:resourceSuperTypes` 這會指向核心階層連結元件。

### 設定元件樣式 {#styling-the-components}

自訂的第一個形式是套用CSS樣式。

為了輕鬆達成此目標，核心元件會轉譯語意標籤，並遵循由以下元素引發的標準化命名慣例： [Bootstrap](https://getbootstrap.com/). 此外，為了輕鬆鎖定個別元件的目標並為其命名樣式，每個核心元件都會包裝在具有「 `cmp`「和」 `cmp-<name>`&quot;類別。

例如，檢視v1核心階層連結元件的HTL檔案： [階層連結.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，我們會看到元素輸出的階層為 `ol.breadcrumb > li.breadcrumb-item > a`. 因此，為了確保CSS規則僅影響該元件的階層連結類別，所有規則都應命名為空間，如下所示：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每個核心元件都運用AEM [樣式系統特徵](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html) 可讓範本作者定義可由頁面作者套用至元件的其他CSS類別名稱。 這允許為每個範本定義允許的元件樣式清單，以及其中一個樣式是否預設應用於該型別的所有元件。

## 升級自訂的相容性 {#upgrade-compatibility-of-customizations}

可能有三種不同的升級型別：

* 升級AEM版本
* 將核心元件升級至新的次要版本
* 將核心元件升級至主要版本

一般而言，升級AEM至新版本不會影響核心元件或完成的自訂，前提是元件的版本也支援正在移轉至的新AEM版本，且自訂功能不會使用已移轉至的API [已棄用或已移除](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html).

升級核心元件而不切換到更新的主要版本應該不會影響自訂，只要使用此頁面上描述的自訂模式即可。

切換至核心元件的更新主要版本只與內容結構相容，但自訂功能可能需要重構。 將針對每個元件版本發佈清楚的變更記錄，以醒目顯示將影響本頁面上所述自訂型別的變更。

## 支援自訂 {#support-of-customizations}

和任何AEM元件一樣，關於自訂，有一些需要注意的事項：

1. **切勿直接修改核心元件的程式碼。**

   這將導致這些元件完全不受支援，且使元件未來的更新成為一個痛苦的過程。 請改用本頁所述的自訂方法。

1. **自訂程式碼由您自行負責。**

   我們的支援計畫不會涵蓋自訂程式碼，以及無法透過vanilla核心元件重現的已報告問題， [依檔案說明使用](/help/get-started/using.md) 不符合資格。

1. **觀看已過時和已移除的功能。**

   隨著每個新AEM版本的升級，請密切留意 [過時和移除的功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html) 頁面。

另請參閱 [核心元件支援](overview.md#core-component-support) 區段。

**閱讀後續章節：**

* [使用核心元件](/help/get-started/using.md)  — 在自己的專案中啟動並執行核心元件。
* [元件指導方針](guidelines.md)  — 瞭解核心元件的實作模式。
