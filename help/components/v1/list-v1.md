---
title: 清單元件(v1)
description: 核心元件清單元件可讓您輕鬆建立動態和靜態清單。
index: n
role: Architect, Developer, Admin, User
exl-id: 510d059c-e60a-40aa-9032-66a901109f6e
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 4%

---

# 清單元件(v1) {#list-component-v}

核心元件清單元件可讓您輕鬆建立動態和靜態清單。

## 使用狀況 {#usage}

例如，清單元件可用於建立子頁面的動態清單或任意定義專案的靜態清單。

可用的清單型別和格式設定選項可由範本作者在 [設計對話方塊](#design-dialog). 內容編輯器可以從可用的清單型別以及如何格式化中的清單元素 [編輯對話方塊](#edit-dialog).

## 版本和相容性 {#version-and-compatibility}

本檔案說明清單元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出List元件v1的相容性。

| AEM版本 | 清單元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明清單元件v1。
>
>如需目前版本的List元件的詳細資訊，請參閱 [清單元件](/help/components/list.md) 檔案。

## 範例元件輸出 {#sample-component-output}

以下是取自下列專案的範例： [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>從核心元件匯出JSON需要核心元件1.1.0版。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 以取得詳細資訊。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者設定清單和清單元素。

### 清單設定 {#list-settings}

清單可透過不同方式建立。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-list)
* [標記](#tags)

無論如何建立清單，都有 [排序選項](#sort-options) 隨時可以設定。

![](/help/assets/chlimage_1-38.png)

視內容作者選擇建立清單的方式而定，其他設定選項將會變更。

#### 子頁面 {#child-pages}

清單可由目前頁面的子頁面或其他頁面建立。

![](/help/assets/chlimage_1-39.png)

* **父頁面**
   * 其子頁面應產生清單的頁面
   * 留空將使用目前頁面
* **子項深度**  — 應該使用階層中向下的層級數

#### 固定清單 {#fixed-list}

清單可使用固定專案清單建立。

![](/help/assets/chlimage_1-40.png)

點選或按一下 **新增** 按鈕以將新專案插入至清單。

* 在清單中輸入專案的文字，或使用 **選擇對話方塊** 以從AEM選擇料號。
* 使用拖曳操作框來重新排列清單中的專案。
* 使用垃圾桶圖示可刪除清單中的專案。

#### 搜尋 {#search-list}

清單可使用搜尋AEM內容的結果來建立。

![](/help/assets/chlimage_1-41.png)

* **搜尋查詢**  — 執行全文檢索搜尋以產生清單元素的字串
* **搜尋範圍**  — 執行搜尋的位置
   * 使用 **選擇對話方塊** 以在AEM中選擇位置
   * 若保留為空白，則使用目前頁面

#### 標記 {#tags}

清單可使用在特定位置下符合特定標籤的頁面來建立。

![](/help/assets/chlimage_1-42.png)

* **上層頁面**  — 開始標籤比對的位置
   * 使用 **選擇對話方塊** 以在AEM中選擇位置
   * 若保留為空白，則使用目前頁面
* **標籤**  — 應該比對哪些標籤
   * 使用 **瀏覽** 對話方塊以選取標籤
* **符合**  — 定義用何種相符專案來限定要包含在清單中的頁面
   * **任何標記**
   * **所有標記**

#### 排序選項 {#sort-options}

無論您選擇如何建立清單，都可隨時定義特定的排序選項。

![](/help/assets/chlimage_1-43.png)

* **排序方式**  — 應該如何排序元素
   * **標題**
   * **上次修改日期**
* **排序順序**  — 專案應排序的順序
   * **升序**
   * **降序**
* **專案數量上限**  — 清單中顯示的最大專案數。
   * 留空將傳回所有專案。

### 項目設定 {#item-settings}

使用 **專案設定** 索引標籤中，可以設定清單元素的格式。

![](/help/assets/chlimage_1-44.png)

* **連結專案**
將專案連結至對應的頁面
* **顯示說明**
顯示連結專案的說明
* **顯示日期**
顯示連結專案的修改日期

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義允許內容作者使用的清單型別以及可用的專案設定。

### 清單設定 {#list-settings-1}

於 **清單設定** 索引標籤中，可以定義日期格式以及在元件中什麼型別的清單可供內容作者使用。

![](/help/assets/chlimage_1-45.png)

* **日期格式**  — 用於顯示上次修改日期的格式
* **停用子項**  — 停用元件中的子清單型別
* **停用靜態**  — 停用元件中的靜態清單型別
* **停用搜尋**  — 停用元件中的搜尋清單型別
* **停用標籤**  — 停用元件中的標籤清單型別

### 項目設定 {#item-settings-1}

於 **專案設定** 索引標籤上，可以定義在元件中可供內容作者使用的個別清單元素的格式選項。

![](/help/assets/chlimage_1-46.png)

* **連結專案**  — 在中啟用連結專案選項 [編輯對話方塊](#edit-dialog)
* **顯示說明**  — 啟用「 」中的「顯示說明」選項 [編輯對話方塊](#edit-dialog)
* **顯示日期**  — 啟用「 」中的「顯示日期」選項 [編輯對話方塊](#edit-dialog)

## 技術細節 {#technical-details}

有關清單元件的最新技術檔案 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list).

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).
