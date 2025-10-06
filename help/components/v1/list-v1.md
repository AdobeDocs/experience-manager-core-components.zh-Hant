---
title: 清單元件 (v1)
description: 核心元件清單元件可讓您輕鬆建立動態和靜態清單。
index: n
role: Architect, Developer, Admin, User
exl-id: 510d059c-e60a-40aa-9032-66a901109f6e
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '836'
ht-degree: 100%

---


# 清單元件 (v1) {#list-component-v}

核心元件清單元件可讓您輕鬆建立動態和靜態清單。

## 用途 {#usage}

清單元件可用於建立下層頁面的動態清單或任意定義項目的靜態清單。

範本作者可在[設計對話框](#design-dialog)中定義可用的清單類型和格式選項。內容編輯者可以在[編輯對話框](#edit-dialog)中，從可用的清單類型以及如何格式化清單元素中選取。

## 版本和相容性 {#version-and-compatibility}

本文件說明清單元件 v1，最初由 AEM 6.3 搭配的核心元件 1.0.0 版導入。

下表列出清單元件 v1 的相容性。

| AEM 版本 | 清單元件 v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文件說明清單元件 v1。
>
>如需清單元件目前版本的詳細資訊，請參閱[清單元件](/help/components/list.md)文件。

## 範例元件輸出 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html) 中取得的範例。

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
>從核心元件匯出 JSON 需要核心元件 1.1.0 版。如需詳細資訊，請參閱[核心元件 v1 的相容性資訊](/help/versions.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框可讓內容作者設定清單和清單元素。

### 清單設定 {#list-settings}

清單可透過不同方式建置。

* [下層頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-list)
* [標記](#tags)

無論清單的建置方式為何，都可隨時設定[排序選項](#sort-options)。

![](/help/assets/chlimage_1-38.png)

根據內容作者選擇建置清單的方式而定，其他設定選項將會變更。

#### 下層頁面 {#child-pages}

清單可由目前頁面或其他頁面的下層頁面建置。

![](/help/assets/chlimage_1-39.png)

* **上層頁面**
   * 其下層頁面應該產生清單的頁面
   * 留空將使用目前頁面
* **下層深度** - 要向下使用階層中的多少個層級

#### 固定清單 {#fixed-list}

清單可使用固定項目清單建立。

![](/help/assets/chlimage_1-40.png)

點選或按一下&#x200B;**新增**&#x200B;按鈕，將新項目插入清單。

* 在清單中輸入項目的文字，或使用&#x200B;**選取對話框**&#x200B;從 AEM 中選擇項目。
* 使用拖曳控點來重新排列清單中的項目。
* 使用垃圾桶圖示可刪除清單中的項目。

#### 搜尋 {#search-list}

清單可使用搜尋 AEM 內容的結果來建立。

![](/help/assets/chlimage_1-41.png)

* **搜尋查詢** - 執行全文搜尋以產生清單元素的字串
* **搜尋** - 應在何處執行搜尋
   * 使用&#x200B;**選取對話框**&#x200B;在 AEM 中選擇位置
   * 如果留空則使用目前頁面

#### 標記 {#tags}

清單可使用在特定位置下符合特定標記的頁面來建立。

![](/help/assets/chlimage_1-42.png)

* **上層頁面** - 應開始標記比對的位置
   * 使用&#x200B;**選取對話框**&#x200B;在 AEM 中選擇位置
   * 如果留空則使用目前頁面
* **標記** - 應該比對哪些標記
   * 使用&#x200B;**瀏覽**&#x200B;對話框來選取標記
* **符合** - 定義哪種類型的符合條件可使頁面列入清單
   * **任何標記**
   * **所有標記**

#### 排序選項 {#sort-options}

無論您選擇如何建置清單，都可隨時定義特定的排序選項。

![](/help/assets/chlimage_1-43.png)

* **排序依據** - 應該如何排序元素
   * **標題**
   * **上次修改日期**
* **排序順序** - 項目應排序的順序
   * **升序**
   * **降序**
* **最大項目** - 在清單中顯示的最大項目數。
   * 留空將傳回所有項目。

### 項目設定 {#item-settings}

使用&#x200B;**項目設定**&#x200B;索引標籤，可設定清單元素的格式。

![](/help/assets/chlimage_1-44.png)

* **連結項目**
連結項目至相應頁面
* **顯示說明**
顯示連結項目的說明
* **顯示日期**
顯示連結項目修改日期

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義應允許內容作者使用的清單類型，以及可用的項目設定。

### 清單設定 {#list-settings-1}

在&#x200B;**清單設定**&#x200B;索引標籤上，可以定義日期格式以及在元件中什麼類型的清單可供內容作者使用。

![](/help/assets/chlimage_1-45.png)

* **日期格式** - 用於顯示上次修改日期的格式
* **停用下層** - 停用元件中的下層清單類型
* **停用靜態** - 停用元件中的靜態清單類型
* **停用搜尋** - 停用元件中的搜尋清單類型
* **停用標記** - 停用元件中的標記清單類型

### 項目設定 {#item-settings-1}

在&#x200B;**項目設定**&#x200B;索引標籤上，可以定義在元件中可供內容作者使用的個別清單元素的格式選項。

![](/help/assets/chlimage_1-46.png)

* **連結項目** - 在[編輯對話框](#edit-dialog)中啟用連結項目選項
* **顯示說明** - 在[編輯對話框](#edit-dialog)中啟用顯示說明選項
* **顯示日期** - 在[編輯對話框](#edit-dialog)中啟用顯示日期選項

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list)有關清單元件的最新技術文件。

您可以從 GitHub 下載完整的核心元件專案。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。
