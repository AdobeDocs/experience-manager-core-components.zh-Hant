---
title: 自訂核心元件
seo-title: 自訂核心元件
description: 核心元件建置幾種樣式，可輕鬆自訂，從簡單樣式到進階功能重復使用。
seo-description: AEM核心元件建置幾種樣式，可輕鬆自訂，從簡單樣式到進階功能重復使用。
uuid: 38d22b85-4867-4716-817a-10ee2f8de6f5
contentOwner: 使用者
content-type: 引用
topic-tags: 開發
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 3c9e0d-1ce0-4e34-ae04-8da63 f9 b6 c4 f
translation-type: tm+mt
source-git-commit: 62643e5bd49ab006230f65004bb9374822dcc017

---


# 自訂核心元件{#customizing-core-components}

[核心元件](developing.md) 建置幾種樣式，可輕鬆自訂，從簡單樣式到進階功能重復使用。

## 有彈性的架構 {#flexible-architecture}

核心元件從一開始就是彈性且可擴充性的。檢視其架構概述，可顯示可進行自訂的位置。

![核心元件架構](assets/screen_shot_2018-12-07at093742.png)

* [設計對話方塊](authoring.md#edit-and-design-dialogs) 定義作者可以或無法在編輯對話方塊中執行的動作。
* [編輯對話方塊](authoring.md#edit-and-design-dialogs) 只會顯示作者可使用的選項。
* [Sling模型](#customizing-the-logic-of-a-core-component) 會驗證並準備檢視(範本)的內容。
* [Sling模型](#customizing-the-logic-of-a-core-component) 的結果可序列化SPSON使用案例。
* [HTL會將HTML](#customizing-the-markup) 演算為傳統伺服器端演算。
* [HTML輸出](#customizing-the-markup) 為語義、可存取、搜尋引擎最佳化，而且易於樣式。

所有核心元件都實作 [樣式系統](customizing.md)。

## 自訂模式 {#customization-patterns}

### 自訂對話方塊 {#customizing-dialogs}

您可能需要自訂核心元件對話方塊中可用的組態選項，包括 [「設計對話方塊」或「編輯對話方塊](authoring.md)」。

每個對話方塊都有一致的節點結構。建議您在繼承元件中複製此結構，以便 [使用Sling Resource合併](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) 和 [隱藏條件](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) 隱藏、取代或重新排序原始對話方塊的區段。複製的結構定義為定位項目節點層級的任何項目。

為完全相容於目前版本上對對話方塊所做的任何變更，請務必不要在標籤項目層級下建立結構(隱藏、新增到、取代、重新排序等)。不過，父項的標籤項目應透過 `sling:hideResource` 屬性隱藏(請參閱 [Sling Resource合併屬性](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html))，以及新增包含設定欄位欄位的新標籤項目。`sling:orderBefore` 可用來重新排序標籤項目。

以下對話方塊顯示建議的對話方塊結構，以及如何隱藏和取代繼承的標籤：

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:43:20.265-0400

Should we provide guidance on how to name their CSS classes, etc. to align to component re-usability best-practices? We tout that we follow bootstrap css naming, should we be counseling customers to align similarly? .cmp- 
<component name="">
  -- 
 <element>
   - 
  <element descriptor="">
    ? 
  </element> 
 </element> 
</component>

 -->

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

### 自訂核心元件邏輯 {#customizing-the-logic-of-a-core-component}

核心元件的商業邏輯已建置於Sling模型中。您可以使用Sling委派模式來擴充此邏輯。

例如，標題核心元件使用請求資源 `jcr:title` 的屬性來提供標題文字。如果未 `jcr:title` 定義屬性，則會實作目前頁面標題的備援。我們想要變更行為，讓目前頁面的標題永遠顯示。

由於核心元件的實作是私人的，因此必須以委派模式擴充。

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

如需有關委派模式的詳細資訊，請參閱核心元件GitHub Wiki文章 [「Sling Models的委派模式](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)」。

### 自訂標記 {#customizing-the-markup}

有時進階樣式需要元件的不同標記結構。

您可以複製需要從核心元件修改到Proxy元件的HTL檔案，輕鬆完成這項工作。

再次執行核心階層連結元件的範例，若要自訂其標記輸出， `breadcrumb.html` 則必須將檔案複製到網站專用的元件中，該元件 `sling:resourceSuperTypes` 指向核心階層連結元件。

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:43:20.265-0400

Should we provide guidance on how to name their CSS classes, etc. to align to component re-usability best-practices? We tout that we follow bootstrap css naming, should we be counseling customers to align similarly? .cmp- 
<component name="">
  -- 
 <element>
   - 
  <element descriptor="">
    ? 
  </element> 
 </element> 
</component>

 -->

### 設定元件樣式 {#styling-the-components}

第一種自訂方式是套用CSS樣式。

為方便這麼做，核心元件會轉換語義標記，並遵循 [由Bootstrap啓發的標準化命名慣例](https://getbootstrap.com/)。此外，若要輕鬆定位和命名個別元件的樣式，每個核心元件都以「 `cmp`」和類別包裝在DIV元素 `cmp-<name>`中。

例如，查看v核心階層連結元件的HTL檔案： [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，我們會看到元素輸出的階層 `ol.breadcrumb > li.breadcrumb-item > a`。為了確保CSS規則只會影響該元件的階層連結類別，所有規則都應是名稱空間，如下所示：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每個核心元件都運用「AEM [Style System」功能](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) ，讓範本作者定義其他可由頁面作者套用至元件的CSS類別名稱。這可讓每個範本定義允許的元件樣式清單，以及其中是否應預設套用至該類型的所有元件。

## 自訂的升級相容性 {#upgrade-compatibility-of-customizations}

有種不同的升級方式：

* 升級AEM版本
* 將核心元件升級至新的次要版本
* 將核心元件升級至主要版本

一般而言，將AEM升級為新版本不會影響核心元件或完成自訂，前提是元件的版本也支援正在移轉的新AEM版本，而且自訂不會使用 [已停用或移除](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html)的API。

只要使用本頁所述的自訂模式，升級核心元件而不會切換至較新的版本不不會影響自訂。

切換至較新版本的核心元件只能與內容結構相容，但自訂可能需要重構。將會針對每個元件版本發佈清除變更記錄，以強調將影響此頁面上所述自訂種類的變更。

## 支援自訂 {#support-of-customizations}

與任何AEM元件一樣，您也可以注意關於自訂的一些事項：

1. **切勿直接修改核心元件的程式碼。**

   這會使它們完全不受支援，並讓未來元件的更新過程變得很困難。請改用本頁所述的自訂方法。

1. **自訂程式碼是您自己的責任。**

   我們的支援計劃不涵蓋自訂程式碼，而無法以明文規定 [的Vanilla](using.md) Core Components重新產生的問題無法取得。

1. **觀看已過時並移除功能。**

   每個新的AEM版本升級後，只要留意 [已過時和已移除的功能](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html) 頁面，即可確保所有使用的API仍保持主題。

另請參閱 [核心元件支援](developing.md#core-component-support) 區段。

**下一步閱讀：**

* [使用核心元件](using.md) -在您自己的專案中啓動並執行核心元件。
* [元件准則](guidelines.md) -瞭解核心元件的實施模式。
