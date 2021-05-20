---
title: 清單元件(v1)
description: 核心元件清單元件可輕鬆建立動態及靜態清單。
index: n
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 510d059c-e60a-40aa-9032-66a901109f6e
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 4%

---

# 清單元件(v1){#list-component-v}

核心元件清單元件可輕鬆建立動態及靜態清單。

## 使用狀況 {#usage}

清單元件可用於建立子頁的動態清單或任意定義項的靜態清單。

可用清單類型和格式選項可由範本作者在[設計對話方塊](#design-dialog)中定義。 內容編輯器可以從可用的清單類型中選擇，以及如何在[edit對話框](#edit-dialog)中格式化清單元素。

## 版本和相容性{#version-and-compatibility}

本檔案說明清單元件的v1，此元件最初於AEM 6.3的核心元件1.0.0版中推出。

下表列出清單元件v1的相容性。

| AEM版本 | 清單元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔介紹清單元件的v1。
>
>有關清單元件當前版本的詳細資訊，請參閱[清單元件](/help/components/list.md)文檔。

## 元件輸出示例{#sample-component-output}

以下範例取自[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 螢幕擷圖 {#screenshot}

![](/help/assets/chlimage_1-47.png)

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
>從核心元件匯出JSON需使用1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者設定清單和清單元素。

### 清單設定 {#list-settings}

清單可以以不同的方式建置。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-list)
* [標記](#tags)

無論清單是如何建立的，都有[排序選項](#sort-options)可以始終配置。

![](/help/assets/chlimage_1-38.png)

視內容作者選擇如何建立清單而定，其他設定選項將會變更。

#### 子頁面 {#child-pages}

清單可由目前頁面或其他頁面的子頁面建立。

![](/help/assets/chlimage_1-39.png)

* **父頁面**
   * 應建立其子頁清單的頁
   * 留空即可使用目前頁面
* **子深度**  — 應使用階層中向下多少個層級

#### 固定清單{#fixed-list}

可使用固定的項目清單來建立清單。

![](/help/assets/chlimage_1-40.png)

點選或按一下&#x200B;**Add**&#x200B;按鈕，將新項目插入清單。

* 在清單中輸入項的文本，或使用&#x200B;**選擇對話框**&#x200B;從AEM中選擇項。
* 使用拖動控點重新排列清單中的項目。
* 使用垃圾桶圖示來刪除清單中的項目。

#### 搜尋 {#search-list}

可使用搜尋AEM內容的結果來建立清單。

![](/help/assets/chlimage_1-41.png)

* **搜尋查詢**  — 將執行全文搜尋以產生清單元素的字串
* **在** 中搜尋 — 該執行搜尋的位置
   * 使用&#x200B;**選擇對話框**&#x200B;選擇AEM中的位置
   * 留空時，請使用目前頁面

#### 標記 {#tags}

清單可以使用在特定位置下符合特定標籤的頁面來建立。

![](/help/assets/chlimage_1-42.png)

* **上層頁面**  — 應開始進行標籤比對的位置
   * 使用&#x200B;**選擇對話框**&#x200B;選擇AEM中的位置
   * 留空時，請使用目前頁面
* **標籤**  — 應符合的標籤
   * 使用&#x200B;**Browse**&#x200B;對話方塊來選取標籤
* **符合**  — 定義哪些符合類型應該會讓頁面符合清單中的資格
   * **任何標記**
   * **所有標記**

#### 排序選項{#sort-options}

無論您選擇以何種方式建立清單，都有可一律定義的特定排序選項。

![](/help/assets/chlimage_1-43.png)

* **排序依據**  — 應如何排序元素
   * **標題**
   * **上次修改日期**
* **排序順序**  — 應排序項目的順序
   * **升序**
   * **降序**
* **項目數上限**  — 清單中顯示的項目數上限。
   * 保留為空以傳回所有項目。

### 項目設定 {#item-settings}

使用&#x200B;**Item Settings**&#x200B;頁簽，可以配置清單元素的格式。

![](/help/assets/chlimage_1-44.png)

* **連結**
項目連結項目至對應的頁面
* **顯示**
說明顯示連結項目的說明
* **顯示**
連結項目的DateShow修改日期

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義內容作者應允許的清單類型以及可用的項目設定。

### 清單設定 {#list-settings-1}

在&#x200B;**清單設定**&#x200B;標籤中，可定義日期格式，以及內容作者可在元件中使用哪些類型的清單。

![](/help/assets/chlimage_1-45.png)

* **日期格式**  — 用於顯示上次修改日期的格式
* **禁用子項**  — 禁用元件中的子項清單類型
* **停用靜態**  — 停用元件中的靜態清單類型
* **停用搜尋**  — 停用元件中的搜尋清單類型
* **停用標籤**  — 在元件中停用標籤清單類型

### 項目設定 {#item-settings-1}

在&#x200B;**項目設定**&#x200B;標籤中，可以定義內容作者應在元件中可用的個別清單元素的格式選項。

![](/help/assets/chlimage_1-46.png)

* **連結項目**  — 在編輯對話方塊中啟用連結 [項目選項](#edit-dialog)
* **顯示說明**  — 在編輯對話方塊中啟用顯示說 [明選項](#edit-dialog)
* **顯示日期**  — 在編輯對話方塊中啟用顯示 [日期選項](#edit-dialog)

## 技術詳細資訊{#technical-details}

如需清單元件[的最新技術檔案，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
