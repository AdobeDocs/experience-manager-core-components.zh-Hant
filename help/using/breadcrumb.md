---
title: 階層連結元件
seo-title: 階層連結元件
description: 'null'
seo-description: 核心元件階層連結元件是一個導覽元件，可根據頁面的內容階層中的位置建立連結的導覽路徑標示。
uuid: 13e858d5-24ad-4144-adc4-0fa1 ffd257 c1
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: dd237df-08b8-4deb-9881-66a1f0d65ef3
modalsize: 426x240
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# 階層連結元件{#breadcrumb-component}

核心元件階層連結元件是一個導覽元件，可根據頁面的內容階層中的位置建立連結的導覽路徑標示。

## 使用狀況 {#usage}

階層連結元件會顯示網站階層內目前頁面的位置，讓頁面訪客可從其目前位置導覽頁面階層。這通常會與頁首或頁尾整合。

可用選項，例如預設導覽層級，以及顯示目前頁面或隱藏頁面的能力，可由 [設計對話方塊中的範本作者定義](#design-dialog)。然後內容編輯器可選擇是否應顯示隱藏頁面，並在 [編輯對話方塊中顯示元件的實際導覽層級](#edit-dialog)。

## 版本與相容性 {#version-and-compatibility}

The current version of the Breadcrumb Component is v2，that which was be intenducated with the release2.0.0of the Core Components in18，and is described in this document.

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](breadcrumb-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/chlimage_1.png)

### HTML {#html}

```
<nav class="cmp-breadcrumb">
    <ol class="cmp-breadcrumb__list">
        <li class="cmp-breadcrumb__item">
            <a href="/content/we-retail/us.html" class="cmp-breadcrumb__item-link">
                United States
            </a>
        </li>
    
        <li class="cmp-breadcrumb__item">
            <a href="/content/we-retail/us/en.html" class="cmp-breadcrumb__item-link">
                English
            </a>
        </li>
    
        <li class="cmp-breadcrumb__item cmp-breadcrumb__item--active">
            
                Experience
            
        </li>
    </ol>
</nav>
```

### JSON {#json}

```
"breadcrumb":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "items":[  
                        {  
                           "page":{  
                              "path":"/content/we-retail/us",
                              "pageTitle":null,
                              "name":"us",
                              "description":null,
                              "title":"United States"
                           },
                           "active":false
                        },
                        {  
                           "page":{  
                              "path":"/content/we-retail/us/en",
                              "pageTitle":null,
                              "name":"en",
                              "description":null,
                              "title":"English"
                           },
                           "active":false
                        },
                        {  
                           "page":{  
                              "path":"/content/we-retail/us/en/experience",
                              "pageTitle":null,
                              "name":"experience",
                              "description":null,
                              "title":"Experience"
                           },
                           "active":true
                        }
                     ],
                     ":type":"weretail/components/content/breadcrumb"
                  }
```

>[!NOTE]
>
>從核心元件2.1.0版開始，階層連結元件支援 [schema.org微型資料](https://schema.org/BreadcrumbList)。

### 技術細節 {#technical-details}

有關階層連結元件的 [最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者抑制網站導覽路徑標示中隱藏和作用中頁面，以及應顯示階層中的深度。

![](assets/screen_shot_2018-01-12at124250.png)

* **導覽開始層級** -階層中的階層連結元件應該開始向下移至目前頁面。例如在我們的零售業：

   * 0開始於 `/content`

   * 1開始於 `/content/we-retail`
   * 開始於 `/content/we-retail/<country>`

* **顯示隱藏導覽項目** -顯示標示為隱藏在導覽路徑標示中的頁面(依預設不會顯示)
* **隱藏目前頁面**-抑制目前頁面中的目前頁面(依預設會顯示)

## 設計對話方塊 {#design-dialog}

The design dialog allows the template author to define what the default value are for the options tocre抑制hideo and active page in the breadcrumbs and should should should shown.

### 主標籤 {#main-tab}

![](assets/screen_shot_2018-01-12at124437.png)

* **導覽開始層級** -定義階層中階層連結元件在新增至頁面時應該開始至目前頁面的預設值。
* **顯示隱藏的導覽項目** -在頁面新增階層連結元件至頁面時，定義 **「顯示隱藏導覽項目** 」選項的預設值。

   * 它不會啓用或停用作者的選項。它只會設定預設值。

* **隱藏目前頁面**-在頁面新增階層連結元件至頁面時，定義 **「隱藏目前頁面** 」選項的預設值。

   * 它不會啓用或停用作者的選項。它只會設定預設值。

### 樣式標籤 {#styles-tab}

階層連結元件支援AEM [樣式系統](authoring.md#component-styling)。