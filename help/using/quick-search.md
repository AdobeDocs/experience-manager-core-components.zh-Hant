---
title: Quick Search Component
seo-title: Quick Search Component
description: 'null'
seo-description: The Quick Search Component provides search capabilities to a website and presents search results so that visitors can search the site and filter the results.
uuid: 1ba69be3-537e-4f20-9f17-b4b7174a8e88
content-type: 引用
topic-tags: 編寫
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 906a684d-5663-4497-bef3-37f13d5b46c7
disttype: dist5
gnavtheme: 淺色
groupsectionnavitems: 否
hidemerchandisingbar: 繼承
hidepromocomponent: 繼承
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# Quick Search Component{#quick-search-component}

The Quick Search Component provides search capabilities to a website and presents search results so that visitors can easily find matching content and view results.

## 使用狀況 {#usage}

The Quick Search component offers site visitors the ability to search for content, view the results in-place, and easily navigate to the matching pages. 當使用者捲動搜尋結果時，會動態擷取新結果。

The edit dialog allows the content author to define where in the content tree the search should start. [](#edit-dialog)使用設 [計對話框](#design-dialog)，範本作者可以設定內容樹中應開始搜尋的位置的預設值，以及最大結果集大小和最小搜尋詞長度。

## 版本與相容性 {#version-and-compatibility}

目前的快速搜尋元件版本為v1，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](versions.md)。

## 元件輸出示例 {#sample-component-output}

以下是 [We.Retail的範例](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

### 螢幕擷圖 {#screenshot}

![](assets/screen_shot_2018-01-19at094248.png)

### HTML {#html}

```
<section class="cmp-search" role="search" data-cmp-is="search" data-cmp-min-length="3" data-cmp-results-size="10">
    <form class="cmp-search__form" data-cmp-hook-search="form" method="get" action="/content/we-retail/us/en/equipment.searchresults.json/_jcr_content/root/responsivegrid/search" autocomplete="off">
        <div class="cmp-search__field">
            <i class="cmp-search__icon" data-cmp-hook-search="icon"></i>
            <span class="cmp-search__loading-indicator" data-cmp-hook-search="loadingIndicator"></span>
            <input class="cmp-search__input" data-cmp-hook-search="input" type="text" name="fulltext" placeholder="Search" role="combobox" aria-autocomplete="list" aria-haspopup="true" aria-invalid="false">
            <button class="cmp-search__clear" data-cmp-hook-search="clear">
                <i class="cmp-search__clear-icon"></i>
            </button>
        </div>
    </form>
    <div class="cmp-search__results" data-cmp-hook-search="results" role="listbox" aria-multiselectable="false"></div>
    
<script data-cmp-hook-search="itemTemplate" type="x-template">
    <a class="cmp-search__item" data-cmp-hook-search="item">
        <span class="cmp-search__item-title" data-cmp-hook-search="itemTitle"></span>
    </a>
</script>
</section>
```

### JSON {#json}

```
"search":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "relativePath":"/jcr:content/root/responsivegrid/search",
                     "resultsSize":10,
                     "searchTermMinimumLength":3,
                     ":type":"core/wcm/components/search/v1/search"
                  }
```

### 技術詳細資訊 {#technical-details}

>[!NOTE]
>
>保護搜尋元件或任何以AEM為基礎的應用程式不受DOS攻擊的影響，應該在更高的層級實作，例如使用 `mod_security` 在分派器上。

有關快速搜尋元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/search/v1/search)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## Edit Dialog {#edit-dialog}

編輯對話方塊可讓內容作者定義搜尋應在內容樹狀結構中的位置。

![](assets/screen_shot_2018-04-03at120132.png)

**搜索根** -從何處開始搜索的根頁。 「搜尋根」可以是Blueprint主版、語言主版或一般頁面。

## Design Dialog {#design-dialog}

Using the design dialog, the template author can set the default value for where in the content tree the search should begin as well as a maximum result set size and minimum search term length.The design dialog allows the template author to define which text formatting options are available to the content authors.

### Properties Tab {#properties-tab}

![](assets/screen_shot_2018-04-03at120028.png)

* **Search Root
The default value of search root when a content author places the Quick Search Component on a content page**
* **Results Size
The maximum number of results fetched by a search request**
* **搜尋詞最小長**&#x200B;度開始搜尋的搜尋詞最小長度

>[!NOTE]
>
>**結果大小****** 和搜尋詞最小長度只能在設計模式中設定，因此只能在範本層級設定，這表示內容作者無法修改這些值。

>[!CAUTION]
>
>**如果結果大小** 和搜 **** 尋詞最小長度分別設定為過高或過低，則可能會對效能產生影響。

### 樣式標籤 {#styles-tab}

「快速搜尋」元件支援AEM [Style系統](authoring.md#component-styling)。