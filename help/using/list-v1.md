---
title: 清單元件(v1)
seo-title: 清單元件(v1)
description: 'null'
seo-description: 核心元件清單元件可讓您輕鬆建立動態和靜態清單。
uuid: 06658c9d-cff2-4bfe-b425-d980 d1181908
content-type: 引用
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 7c130cc-83ff-464d-b58 f-d581 f4365 dbd
disttype: dist5
gnavtheme: 淺色
groupsectionnavitems: 否
hidemerchandisingbar: 繼承
hidepromocomponent: 繼承
modalsize: 426x240
noindex: 'true'
index: n
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# 清單元件(v1){#list-component-v}

核心元件清單元件可讓您輕鬆建立動態和靜態清單。

## 使用狀況 {#usage}

清單元件可用來建立子頁面的動態清單或任意定義項目的靜態清單。

可用清單類型和格式選項可由 [設計對話方塊中的範本作者定義](list-v1.md#main-pars_title_1995166862)。內容編輯器可以從可用的清單類型中選取，以及如何在 [編輯對話方塊中格式化清單元素](list-v1.md#main-pars_title)。

## 版本與相容性 {#version-and-compatibility}

本文件說明清單元件的v1，原始版本為AEM6.3的1.0.0版核心元件。

下表列出清單元件v的相容性。

| AEM版本 | 清單元件v1 |
|--- |--- |
| 6.3 | 相容相容性 |
| 6.4 | 相容相容性 |

>[!CAUTION]
>
>本文件說明清單元件的v1。
>
>如需目前版本清單元件的詳細資訊，請參閱 [清單元件](list.md) 文件。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/chlimage_1-47.png)

### HTML {#html}

```
<div class="cmp cmp-list aem-GridColumn aem-GridColumn--default--12">

<ul>
    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/arctic-surfing-in-lofoten.html">
            <span class="cmp-list--item-title">Arctic Surfing In Lofoten</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/summit-success-in-the-himalayas.html">
            <span class="cmp-list--item-title">Summit Success in the Himalayas</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/climbing-on-kalymnos-island--greece.html">
            <span class="cmp-list--item-title">Climbing on Kalymnos Island, Greece</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/running-at-the-great-wall-marathon.html">
            <span class="cmp-list--item-title">Running at the Great Wall Marathon</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/skiing-deep-powder-in-siberia.html">
            <span class="cmp-list--item-title">Skiing deep powder in Siberia</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/climbing-in-the-massif-du-mont-blanc.html">
            <span class="cmp-list--item-title">Climbing in the Massif du Mont Blanc</span>
            
        </a>
        
    </article>
</li>
</ul>

</div>
```

### JSON {#json}

```
"articles_list": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/articleslist",
              "tagsMatch": "any",
              "displayAs": "teaser",
              "feedEnabled": "true",
              "listFrom": "children",
              "limit": "0",
              "orderBy": "cq:lastModified",
              "pageMax": "0"
            }
```

>[!NOTE]
>
>從核心元件匯出JSON需要1.1.0版核心元件。如需詳細資訊，請參閱核心元件v [](versions.md#main-pars_title_236368006) 的相容性資訊。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者設定清單和清單元素。

### 清單設定 {#list-settings}

清單可以以不同的方式建立。

* [子頁面](list-v1.md#main-pars_title_1861279796)
* [固定清單](list-v1.md#main-pars_title_1227896889)
* [搜尋](list-v1.md#main-pars_title_1224003560)
* [標記](list-v1.md#main-pars_title_700759533)

不論清單是如何建立的，都有 [可隨時設定的「排序選項](list-v1.md#main-pars_title_1568376452) 」。

![](assets/chlimage_1-38.png)

視內容作者選擇要如何建立清單而定，其他設定選項將會變更。

#### 子頁面 {#child-pages}

可建立目前頁面或其他頁面的子頁面。

![](assets/chlimage_1-39.png)

* **父頁面**
   * 子系頁面應製作清單的頁面
   * 保留空白以使用目前頁面
* **子深度** -階層中應使用多少層級

#### 固定清單 {#fixed-list}

您可以使用固定清單來建立清單。

![](assets/chlimage_1-40.png)

點選或按一下「 **新增** 」按鈕，將新項目嵌入清單中。

* 輸入清單中項目的文字，或使用 **「選擇對話方塊** 」從AEM選擇項目。
* 使用拖曳控制點重新排列清單中的項目。
* 使用垃圾筒圖示可刪除清單中的項目。

#### 搜尋 {#search}

您可以使用搜尋AEM內容的搜尋結果來建立清單。

![](assets/chlimage_1-41.png)

* **搜尋查詢** -將執行全文搜尋的字串，以產生清單元素
* **搜尋-** 應執行搜尋的位置
   * 使用 **「選取對話方塊** 」選擇AEM中的位置
   * 如果留空，請使用目前頁面

#### 標記 {#tags}

您可以使用符合特定位置標記的頁面來建立清單。

![](assets/chlimage_1-42.png)

* **上層頁面** -標籤符合應該開始的位置
   * 使用 **「選取對話方塊** 」選擇AEM中的位置
   * 如果留空，請使用目前頁面
* **標記** -應符合哪些標籤
   * 使用 **「瀏覽** 」對話方塊選取標記
* **符合** -定義哪種符合應符合清單中要包含的頁面
   * **任何標記**
   * **所有標記**

#### 排序選項 {#sort-options}

無論您選擇如何建立清單，都有一些可隨時定義的排序選項。

![](assets/chlimage_1-43.png)

* **訂購-** 如何訂購元素
   * **標題**
   * **上次修改日期**
* **排序順序** -應訂購項目的順序
   * **升序**
   * **降序**
* **最大項目** -清單中顯示的最大項目數。
   * 保留空白以傳回所有項目。

### 項目設定 {#item-settings}

使用 **「項目設定** 」標籤，可以設定清單元素的格式。

![](assets/chlimage_1-44.png)

* **連結項目**連結項目至對應頁面
* **顯示說明**顯示連結項目的說明
* **顯示連結項目的日期**顯示修改日期

## 設計對話方塊 {#design-dialog}

此設計對話方塊可讓範本作者定義應允許的清單類型，以及可用項目設定。

### 清單設定 {#list-settings-1}

在 **「清單設定** 」標籤上，可以定義日期格式，以及元件中應該提供何種清單類型給內容作者。

![](assets/chlimage_1-45.png)

* **日期格式** -用於顯示上次修改日期的格式
* **停用子項** -停用元件中的子清單類型
* **停用靜態** -停用元件中的靜態清單類型
* **停用搜尋** -停用元件中的搜尋清單類型
* **停用標記** -停用元件中的標籤清單類型

### 項目設定 {#item-settings-1}

在 **「項目設定** 」標籤上，可以定義內容作者的元件中應該提供的個別清單元素格式選項。

![](assets/chlimage_1-46.png)

* **編輯對話方塊中的連結項目** -啓用連結 [項目選項](list-v1.md#main-pars_title_550499279)
* **在編輯對話方塊中顯示說明** -啓用顯示 [說明選項](list-v1.md#main-pars_title_550499279)
* **在編輯對話方塊中顯示日期** -啓用顯示 [日期選項](list-v1.md#main-pars_title_550499279)

## 技術細節 {#technical-details}

有關List Component [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list)。

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。
