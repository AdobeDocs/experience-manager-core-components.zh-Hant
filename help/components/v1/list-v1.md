---
title: 清單元件(v1)
description: 「核心元件清單元件」可讓您輕鬆建立動態和靜態清單。
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 清單元件(v1) {#list-component-v}

「核心元件清單元件」可讓您輕鬆建立動態和靜態清單。

## 使用狀況 {#usage}

「清單元件」可用來建立例如子頁面的動態清單或任意定義項目的靜態清單。

可用清單類型和格式選項可由模板作者在設計對話框中定 [義](#design-dialog)。 內容編輯器可以從可用的清單類型中選擇，以及如何在編輯對話框中格式化列 [表元素](#edit-dialog)。

## 版本與相容性 {#version-and-compatibility}

本檔案說明清單元件的v1，最初是隨AEM 6.3核心元件的1.0.0版一起推出。

下表列出了清單元件v1的相容性。

| AEM版本 | 清單元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明「清單元件」的v1。
>
>有關清單元件當前版本的詳細資訊，請參閱列 [表元件文檔](/help/components/list.md) 。

## 元件輸出示例 {#sample-component-output}

以下是 [We.Retail的範例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件匯出JSON需要1.1.0版的核心元件。 如需詳細 [資訊，請參閱核心元件v1的相容性資訊](/help/versions.md) 。

## Edit Dialog {#edit-dialog}

編輯對話框允許內容作者配置清單和清單元素。

### 清單設定 {#list-settings}

清單可以以不同的方式建立。

* [子頁面](#child-pages)
* [固定清單](#fixed-list)
* [搜尋](#search-list)
* [標記](#tags)

無論清單的建立方式為何，都有 [可隨時設定的排序選項](#sort-options) 。

![](/help/assets/chlimage_1-38.png)

視內容作者選擇如何建立清單而定，其他設定選項將會變更。

#### 子頁面 {#child-pages}

清單可由目前頁面或其他頁面的子頁面建立。

![](/help/assets/chlimage_1-39.png)

* **父頁面**
   * 其子頁面應該列出的頁面
   * 保留空白以使用目前頁面
* **子層深度** -應使用階層中向下的層數

#### Fixed List {#fixed-list}

清單可使用固定的項目清單來建立。

![](/help/assets/chlimage_1-40.png)

點選或按一下「 **新增** 」按鈕，將新項目插入清單。

* 在清單中輸入項目的文字，或使用「選 **取對話方** 」從AEM選擇項目。
* 使用拖動控制滑塊重新排列清單中的項目。
* 使用垃圾桶圖示來刪除清單中的項目。

#### 搜尋 {#search-list}

您可使用搜尋AEM內容的結果來建立清單。

![](/help/assets/chlimage_1-41.png)

* **Search query** —— 將執行全文搜尋以產生清單元素的字串
* **搜索範圍** -應在何處運行搜索
   * 使用「選 **取對話方** 」來選擇AEM中的位置
   * 如果保留空白，請使用目前頁面

#### 標記 {#tags}

清單可使用與特定位置下的特定標籤相符的頁面來建立。

![](/help/assets/chlimage_1-42.png)

* **上層頁面** -標籤符合的起始位置
   * 使用「選 **取對話方** 」來選擇AEM中的位置
   * 如果保留空白，請使用目前頁面
* **標籤** -哪些標籤應符合
   * 使用「瀏 **覽** 」對話框選擇標籤
* **Match** —— 定義哪些符合類型可限定要納入清單中的頁面
   * **任何標記**
   * **所有標記**

#### 排序選項 {#sort-options}

無論您選擇如何建立清單，都有某些排序選項可隨時定義。

![](/help/assets/chlimage_1-43.png)

* **排序依據** -元素的排序方式
   * **標題**
   * **上次修改日期**
* **排序順序** -項目的排序順序
   * **升序**
   * **降序**
* **最大項目** -清單中顯示的項目數上限。
   * 留空以傳回所有項目。

### 項目設定 {#item-settings}

使用「 **項目設定** 」標籤，可設定清單元素的格式。

![](/help/assets/chlimage_1-44.png)

* **連結項目**&#x200B;連結項目至對應頁面
* **顯示說明**&#x200B;顯示連結項目的說明
* **顯示日期**&#x200B;顯示連結項的修改日期

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者應允許的清單類型以及可用的項目設定。

### 清單設定 {#list-settings-1}

在「清 **單設定** 」索引標籤上，可以定義日期格式，以及內容作者應在元件中使用哪些類型的清單。

![](/help/assets/chlimage_1-45.png)

* **日期格式** -用於顯示上次修改日期的格式
* **禁用子項** -禁用元件中的子項清單類型
* **禁用靜態** -禁用元件中的靜態清單類型
* **禁用搜索** -禁用元件中的搜索清單類型
* **Disable Tags** - Disable tags list type in the component

### 項目設定 {#item-settings-1}

在「項 **目設定** 」標籤上，可定義內容作者的元件中應提供的個別清單元素的格式選項。

![](/help/assets/chlimage_1-46.png)

* **連結項目** -在編輯對話方塊中啟用連結 [項目選項](#edit-dialog)
* **顯示說明** -在編輯對話方塊中啟用顯示說 [明選項](#edit-dialog)
* **顯示日期** -在編輯對話方塊中啟用顯示日 [期選項](#edit-dialog)

## 技術詳細資訊 {#technical-details}

有關List Component的最新技術檔案 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。