---
title: 清單元件(v1)
description: 核心元件清單元件可讓您輕鬆建立動態和靜態清單。
index: n
role: Architect, Developer, Admin, User
exl-id: 510d059c-e60a-40aa-9032-66a901109f6e
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 3%

---


# 清單元件(v1) {#list-component-v}

核心元件清單元件可讓您輕鬆建立動態和靜態清單。

## 使用情況 {#usage}

例如，清單元件可用於建立子頁面的動態清單或任意定義專案的靜態清單。

範本作者可在[設計對話方塊](#design-dialog)中定義可用的清單型別和格式選項。 內容編輯者可以在[編輯對話方塊](#edit-dialog)中，從可用的清單型別以及如何格式化清單元素中選取。

## 版本和相容性 {#version-and-compatibility}

本檔案說明清單元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出清單元件v1的相容性。

| AEM 版本 | 清單元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明清單元件v1。
>
>如需目前版本的List元件的詳細資訊，請參閱[List元件](/help/components/list.md)檔案。

## 範例元件輸出 {#sample-component-output}

以下是從[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)中取得的範例。

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
>從核心元件匯出JSON需要版本1.1.0的核心元件。 如需詳細資訊，請參閱核心元件v1[&#128279;](/help/versions.md)的相容性資訊。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者設定清單和清單元素。

### 清單設定 {#list-settings}

清單可透過不同方式建立。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-list)
* [標記](#tags)

無論如何建立清單，一律可以設定[排序選項](#sort-options)。

![](/help/assets/chlimage_1-38.png)

視內容作者選擇建立清單的方式而定，其他設定選項將會變更。

#### 子頁面 {#child-pages}

清單可由目前頁面或其他頁面的子頁面建置。

![](/help/assets/chlimage_1-39.png)

* **父頁面**
   * 其子頁面應該產生清單的頁面
   * 留空將使用目前頁面
* **Child-Depth** — 應該使用階層中向下的層級

#### 固定清單 {#fixed-list}

清單可使用固定專案清單建立。

![](/help/assets/chlimage_1-40.png)

點選或按一下&#x200B;**新增**&#x200B;按鈕，將新專案插入清單。

* 在清單中輸入專案的文字，或使用&#x200B;**選取範圍對話方塊**&#x200B;從AEM中選擇專案。
* 使用拖曳控點來重新排列清單中的專案。
* 使用垃圾桶圖示可刪除清單中的專案。

#### 搜尋 {#search-list}

清單可使用搜尋AEM內容的結果來建立。

![](/help/assets/chlimage_1-41.png)

* **搜尋查詢** — 執行全文檢索搜尋以產生清單元素的字串
* **在**&#x200B;中搜尋 — 執行搜尋的位置
   * 使用&#x200B;**選取範圍對話方塊**&#x200B;在AEM中選擇位置
   * 如果留空則使用目前頁面

#### 標記 {#tags}

清單可使用在特定位置下符合特定標籤的頁面來建立。

![](/help/assets/chlimage_1-42.png)

* **父頁面** — 標籤比對應該開始的位置
   * 使用&#x200B;**選取範圍對話方塊**&#x200B;在AEM中選擇位置
   * 如果留空則使用目前頁面
* **標籤** — 應該比對哪些標籤
   * 使用&#x200B;**瀏覽**&#x200B;對話方塊來選取標籤
* **符合** — 定義應該以何種符合專案來限定清單中包含的頁面
   * **任何標籤**
   * **所有標籤**

#### 排序選項 {#sort-options}

無論您選擇如何建立清單，都可隨時定義特定的排序選項。

![](/help/assets/chlimage_1-43.png)

* **排序依據** — 應該如何排序專案
   * **標題**
   * **上次修改日期**
* **排序順序** — 專案應排序的順序
   * **遞增**
   * **降序**
* **最大專案數** — 清單中顯示的最大專案數。
   * 留空將傳回所有專案。

### 項目設定 {#item-settings}

使用&#x200B;**專案設定**&#x200B;索引標籤，可以設定清單元素的格式。

![](/help/assets/chlimage_1-44.png)

* **連結專案**
將專案連結至對應的頁面
* **顯示描述**
顯示連結專案的說明
* **顯示日期**
顯示連結專案的修改日期

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義允許內容作者使用的清單型別以及可用的專案設定。

### 清單設定 {#list-settings-1}

在&#x200B;**清單設定**&#x200B;索引標籤上，可以定義日期格式以及在元件中什麼型別的清單可供內容作者使用。

![](/help/assets/chlimage_1-45.png)

* **日期格式** — 用於顯示上次修改日期的格式
* **停用子項** — 停用元件中的子項清單型別
* **停用靜態** — 停用元件中的靜態清單型別
* **停用搜尋** — 停用元件中的搜尋清單型別
* **停用標籤** — 停用元件中的標籤清單型別

### 項目設定 {#item-settings-1}

在&#x200B;**專案設定**&#x200B;索引標籤上，可以定義在元件中可供內容作者使用的個別清單元素的格式選項。

![](/help/assets/chlimage_1-46.png)

* **連結專案** — 在[編輯對話方塊](#edit-dialog)中啟用連結專案選項
* **顯示說明** — 在[編輯對話方塊](#edit-dialog)中啟用[顯示說明]選項
* **顯示日期** — 在[編輯對話方塊](#edit-dialog)中啟用[顯示日期]選項

## 技術細節 {#technical-details}

在GitHub[&#128279;](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list)上可找到有關清單元件的最新技術檔案。

您可以從GitHub下載整個核心元件專案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。
