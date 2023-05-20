---
title: 清單元件(v1)
description: 核心元件清單元件允許輕鬆建立動態清單和靜態清單。
index: n
role: Architect, Developer, Admin, User
exl-id: 510d059c-e60a-40aa-9032-66a901109f6e
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 4%

---

# 清單元件(v1) {#list-component-v}

核心元件清單元件允許輕鬆建立動態清單和靜態清單。

## 使用狀況 {#usage}

「清單元件」可用於建立子頁的動態清單或任意定義項的靜態清單。

可用清單類型和格式選項可由模板作者在 [設計對話框](#design-dialog)。 內容編輯器可以從可用清單類型中選擇以及如何格式化清單中的清單元素 [編輯對話框](#edit-dialog)。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了清單元件的v1，最初是隨帶有6.3的核心元件1.0.0版而引AEM入的。

下表列出了清單元件v1的相容性。

| 版AEM本 | 清單元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔描述了「清單元件」的v1。
>
>有關清單元件當前版本的詳細資訊，請參閱 [清單元件](/help/components/list.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件導出JSON需要1.1.0版核心元件。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 的子菜單。

## 編輯對話框 {#edit-dialog}

編輯對話框允許內容作者配置清單和清單元素。

### 清單設定 {#list-settings}

清單可以用不同的方式構建。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-list)
* [標記](#tags)

無論清單是如何構建的， [排序選項](#sort-options) 可以始終進行配置。

![](/help/assets/chlimage_1-38.png)

根據內容作者選擇構建清單的方式，其他配置選項將發生更改。

#### 子頁面 {#child-pages}

該清單可由當前頁面或其他頁面的子頁面生成。

![](/help/assets/chlimage_1-39.png)

* **父頁面**
   * 其子頁應生成清單的頁
   * 留空以使用當前頁
* **子深度**  — 應使用層次結構中下層的層數

#### 固定清單 {#fixed-list}

可以使用固定的項目清單生成清單。

![](/help/assets/chlimage_1-40.png)

點擊或按一下 **添加** 按鈕

* 輸入清單中項的文本或使用 **選擇對話框** 的子例AEM行。
* 使用拖動控制滑塊重新排列清單中的項目。
* 使用垃圾桶表徵圖刪除清單中的項目。

#### 搜尋 {#search-list}

可以使用內容搜索的結果來構建列AEM表。

![](/help/assets/chlimage_1-41.png)

* **搜索查詢**  — 運行全文搜索以生成清單元素的字串
* **搜索範圍**  — 應在何處運行搜索
   * 使用 **選擇對話框** 以選擇AEM
   * 如果留空，則使用當前頁

#### 標記 {#tags}

可以使用與特定位置下的某些標籤相匹配的頁面來構建清單。

![](/help/assets/chlimage_1-42.png)

* **父頁**  — 標籤匹配應從何處開始
   * 使用 **選擇對話框** 以選擇AEM
   * 如果留空，則使用當前頁
* **標籤**  — 應匹配哪些標籤
   * 使用 **瀏覽** 對話框，以選擇標籤
* **匹配**  — 定義哪些類型的匹配應限定清單中要包含的頁面
   * **任何標記**
   * **所有標記**

#### 排序選項 {#sort-options}

無論您選擇如何構建清單，總是可以定義某些排序選項。

![](/help/assets/chlimage_1-43.png)

* **排序依據**  — 元素的排序方式
   * **標題**
   * **上次修改日期**
* **排序順序**  — 訂購物料的順序
   * **升序**
   * **降序**
* **最大項**  — 清單中顯示的最大項目數。
   * 留空以返回所有項目。

### 項目設定 {#item-settings}

使用 **項設定** 頁籤。

![](/help/assets/chlimage_1-44.png)

* **連結項**
將項連結到相應頁
* **顯示說明**
顯示連結項的說明
* **顯示日期**
顯示連結項的修改日期

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者應允許的清單類型以及可用的項目設定。

### 清單設定 {#list-settings-1}

在 **清單設定** 頁籤中，可以定義日期格式以及元件中的內容作者應使用的清單類型。

![](/help/assets/chlimage_1-45.png)

* **日期格式**  — 用於顯示上次修改日期的格式
* **禁用子項**  — 禁用元件中的子清單類型
* **禁用靜態**  — 禁用元件中的靜態清單類型
* **禁用搜索**  — 禁用元件中的搜索清單類型
* **禁用標籤**  — 禁用元件中的標籤清單類型

### 項目設定 {#item-settings-1}

在 **項設定** 頁籤中，可以定義內容作者的元件中應提供的單個清單元素的格式選項。

![](/help/assets/chlimage_1-46.png)

* **連結項**  — 在中啟用「連結項目」選項 [編輯對話框](#edit-dialog)
* **顯示說明**  — 在中啟用「顯示說明」選項 [編輯對話框](#edit-dialog)
* **顯示日期**  — 在中啟用「顯示日期」選項 [編輯對話框](#edit-dialog)

## 技術詳細資訊 {#technical-details}

有關清單元件的最新技術文檔 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list)。

整個核心元件項目可從GitHub下載。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。
