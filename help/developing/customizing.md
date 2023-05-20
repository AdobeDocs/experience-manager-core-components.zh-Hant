---
title: 自訂核心元件
description: 核心元件實施了幾種模式，從簡單的造型到高級功能的重用，這些模式允許輕鬆定制。
role: Architect, Developer, Admin
exl-id: ec4b918b-bc70-4d72-ba84-a24556aedb41
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 1%

---

# 自訂核心元件{#customizing-core-components}

的 [核心元件](overview.md) 實施多種模式，從簡單的樣式到高級功能的重用，都可輕鬆實現定制。

## 靈活的體系結構 {#flexible-architecture}

核心元件從一開始就設計為靈活和可擴展。 查看其體系結構的概述，可以在何處進行自定義。

![核心元件體系結構](/help/assets/screen_shot_2018-12-07at093742.png)

* [設計對話框](/help/get-started/authoring.md#edit-and-design-dialogs) 定義作者在編輯對話框中可以或不能執行的操作。
* [編輯對話框](/help/get-started/authoring.md#edit-and-design-dialogs) 僅顯示作者允許使用的選項。
* [Sling模型](#customizing-the-logic-of-a-core-component) 驗證並準備視圖（模板）的內容。
* [Sling模型的結果](#customizing-the-logic-of-a-core-component) 可序列化到JSONSPA以用例。
* [HTL呈現HTML](#customizing-the-markup) 伺服器端，用於傳統的伺服器端呈現。
* [HTML輸出](#customizing-the-markup) 語義、易訪問、搜索引擎已優化，且易於使用。

所有核心元件都 [樣式系統](#styling-the-components)。

## AEM 專案原型 {#aem-project-archetype}

[項AEM目原型](/help/developing/archetype/overview.md) 建立最小的Adobe Experience Manager項目作為您自己項目的起點，包括一個帶SlingModels的自定義HTL元件示例，用於邏輯和使用推薦的代理模式正確實施核心元件。

## 自定義模式 {#customization-patterns}

### 自定義對話框 {#customizing-dialogs}

可能需要定制核心元件對話框中可用的配置選項 [設計對話框或編輯對話框](/help/get-started/authoring.md)。

每個對話框都具有一致的節點結構。 建議在繼承元件中複製此結構，以便 [Sling資源合併](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) 和 [隱藏條件](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) 可用於隱藏、替換或重新排序原始對話框的節。 要複製的結構定義為直至頁籤項目節點級別的任何內容。

要與對對話框當前版本所做的任何更改完全相容，非常重要的是，不要觸碰頁籤項級別下的結構（隱藏、添加到、替換、重新排序等）。 相反，應通過 `sling:hideResource` 屬性(請參見 [Sling資源合併屬性](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html))，以及添加的包含定製配置欄位的新頁籤項。 `sling:orderBefore` 可用於重新排序頁籤項（如果需要）。

下面的對話框演示了建議的對話框結構以及如何隱藏和替換繼承的頁籤，如上所述：

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

### 定制核心元件的邏輯 {#customizing-the-logic-of-a-core-component}

核心元件的業務邏輯在Sling模型中實現。 該邏輯可通過使用Sling委託模式來擴展。

例如，標題核心元件使用 `jcr:title` 請求資源的屬性，以提供標題文本。 否 `jcr:title` 定義屬性，實現對當前頁標題的回退。 我們要更改行為，以便始終顯示當前頁面的標題。

由於核心元件模型的實施是私有的，因此必須使用委託模式進行擴展。

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

有關委派模式的詳細資訊，請參閱核心元件GitHub Wiki文章 [吊具模型委託模式](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)。

### 自定義標籤 {#customizing-the-markup}

有時，高級樣式需要元件的不同標籤結構。

通過將需要修改的HTL檔案從核心元件複製到 [代理元件。](guidelines.md#proxy-component-pattern)

再次以核心Breadcrumb元件的示例為例，要自定義其標籤輸出， `breadcrumb.html` 檔案必須複製到具有 `sling:resourceSuperTypes` 指向核心Breacrumb元件。

### 設定元件的樣式 {#styling-the-components}

第一種定制形式是應用CSS樣式。

為了簡化此過程，核心元件會呈現語義標籤並遵循受 [Bootstrap](https://getbootstrap.com/)。 此外，為了輕鬆確定各個元件的樣式並命名其空間，每個核心元件都包裝在帶有「 」的DIV元素中 `cmp`&quot;和&quot; `cmp-<name>`類。

例如，查看v1核心Breadcrumb元件的HTL檔案： [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，我們看到元素輸出的層次 `ol.breadcrumb > li.breadcrumb-item > a`。 因此，要確保CSS規則僅影響該元件的breadcrumb類，所有規則應按如下所示命名：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每個核心元件都利用 [樣式系統功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html) 允許模板作者定義可由頁面作者應用於元件的其他CSS類名。 這允許為每個模板定義允許的元件樣式清單，以及預設情況下是否應將其中一種樣式應用於此類的所有元件。

## 自定義項的升級相容性 {#upgrade-compatibility-of-customizations}

可以進行三種不同的升級：

* 升級版AEM本
* 將核心元件升級到新的次版本
* 將核心元件升級到主版本

通常，AEM升級到新版本不會影響核心元件或完成的自定義，前提是元件的版本還支援要遷移到的新AEM版本，且自定義不使用已遷移的API [已棄用或刪除](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)。

升級核心元件而不切換到較新的主版本不應影響定制，只要使用此頁上描述的定製模式。

切換到較新的主要核心元件版本僅與內容結構相容，但可能需要重新構造自定義。 將為每個元件版本發佈清除更改日誌，以突出顯示將影響此頁中描述的自定義類型的更改。

## 支援自定義 {#support-of-customizations}

與任何組AEM件一樣，在自定義方面有許多需要注意的事項：

1. **切勿直接修改核心元件的代碼。**

   這將使這些元件完全不受支援，並使將來對元件的更新成為一個痛苦的過程。 而是使用此頁上介紹的自定義方法。

1. **自定義代碼是您自己的責任。**

   我們的支援計畫不涵蓋自定義代碼，並報告了無法使用以下香草核心元件複製的問題 [已記錄](/help/get-started/using.md) 不合格。

1. **監視已棄用和已刪除的功能。**

   將每個AEM新版本升級到時，通過關注 [已棄用和已刪除的功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html) 的子菜單。

另請參閱 [核心元件支援](overview.md#core-component-support) 的子菜單。

**閱讀後續章節：**

* [使用核心元件](/help/get-started/using.md)  — 在您自己的項目中啟動並運行核心元件。
* [元件指南](guidelines.md)  — 瞭解核心元件的實施模式。
