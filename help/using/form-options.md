---
title: 表單選項元件
seo-title: 表單選項元件
description: 核心元件表單選項元件可讓您從預先定義的選項中選擇各種格式。
seo-description: 核心元件表單選項元件可讓您從預先定義的選項中選擇各種格式。
uuid: 7e8714df-75d1-4bb0-b1 ee-b7 c7450 d806 a
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 42289c2b-1671-463a-ac1 d-457aa9 aefa2 a
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 表單選項元件{#form-options-component}

核心元件表單選項元件可讓您從預先定義的選項中選擇各種格式。

## 使用狀況 {#usage}

核心元件表單選項元件允許提交不同類型的選項，並用於 [與表單容器元件搭配使用](form-container.md)。

選項、標籤和個別選項的呈現方式可由 [設定對話方塊](#configure-dialog)中的內容編輯器定義。

## 版本與相容性 {#version-and-compatibility}

目前版本的表單選項元件是v2，是從2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](form-options-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/screen_shot_2018-01-12at113648.png)

### HTML {#html}

```
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="cmp-form aem-Grid aem-Grid--12 aem-Grid--default--12">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-66464844" name="hidden">

</div>
<div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-858231075" name="hidden">

</div>
<div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-862566768" name="hidden">

</div>
<div class="container responsivegrid aem-GridColumn aem-GridColumn--default--12">

    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container/container">
    
    <div class="options aem-GridColumn aem-GridColumn--default--12">

    <fieldset class="cmp-form-options">
        
            <legend class="cmp-form-options__legend">What is your favorite type of toast?</legend>
            <label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="dryToast">
                Plain dry toast
            </label>
<label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="frenchToast">
                French Toast
            </label>
<label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="texasToast">
                Texas Toast
            </label>

    </fieldset>

</div>

</div></form>
```

### JSON {#json}

```
"container":{  
                           "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                           "columnCount":12,
                           "gridClassNames":"aem-Grid aem-Grid--12 aem-Grid--default--12",
                           ":items":{  
                              "options_816658469":{  
                                 "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                                 "id":"form-options-269951232",
                                 "title":"What is your favorite type of toast?",
                                 "name":"favToast",
                                 "type":"RADIO",
                                 "items":[  
                                    {  
                                       "value":"dryToast",
                                       "text":"Plain dry toast",
                                       "selected":false,
                                       "disabled":false
                                    },
                                    {  
                                       "value":"frenchToast",
                                       "text":"French Toast",
                                       "selected":false,
                                       "disabled":false
                                    },
                                    {  
                                       "value":"texasToast",
                                       "text":"Texas Toast",
                                       "selected":false,
                                       "disabled":false
                                    }
                                 ],
                                 ":type":"core/wcm/sandbox/components/form/options/v2/options"
                              }
                           },
                           ":itemsOrder":[  
                              "options_816658469"
                           ],
                           ":type":"core/wcm/sandbox/components/form/container/v2/container"
                        }
```

### 技術細節 {#technical-details}

有關表單選項元件的 [最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義應該顯示的選項類型、標籤以及可用選項。

![](assets/screen_shot_2018-01-12at113153.png)

* **類型** -如何顯示選項
   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **複選下拉式清單**
* **標題**將顯示為選項標籤的標題
* **名稱**表單資料提交欄位的名稱
* **來源**定義選項
   * **本機**定義的本機定義
      * 點選或按一下「 **新增** 」按鈕可新增值， **刪除** 以移除值
      * **值**當表單提交時選取該選項時所儲存的值
      * **文字**顯示表單上顯示的選項
      * **活動：**當表單載入時，選項會標示為
      * **停用**：無法選取選項但仍顯示
      * **清單：**在AEM其他位置定義的靜態清單用於選項
         * **列出** AEM中靜態清單的路徑
            * 使用「瀏覽」按鈕尋找清單資源
      * **資料來源** A資料來源用於選項
         * **資料來源的資料來源**資源類型
* **說明訊息**：使用者在欄位中輸入的提示訊息

## 設計對話方塊 {#design-dialog}

### 樣式標籤 {#styles-tab}

表單選項元件支援AEM [樣式系統](authoring.md#component-styling)。