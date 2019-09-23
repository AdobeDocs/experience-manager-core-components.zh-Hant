---
title: 表單選項元件(v1)
seo-title: 表單選項元件(v1)
description: 'null'
seo-description: 核心元件表單選項元件允許從各種格式的預定義選項中進行選擇。
uuid: a22ed77c-c9f3-46f4-8afe-e478383c1251
content-type: 引用
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新功能
discoiquuid: e1975bfe-2bda-409a-998e-1ff4f9f23b94
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


# Form Options Component (v1){#form-options-component-v}

核心元件表單選項元件允許從各種格式的預定義選項中進行選擇。

## 使用狀況 {#usage}

核心元件表單選項元件允許以多種不同方式提交不同類型的選項，並與表單容器元件一 [起使用](form-container.md)。

選項、標籤和個別選項的呈現方式可由內容編輯器在「設定」對話方塊中 [定義](form-options-v1.md#main-pars_title)。

## 版本與相容性 {#version-and-compatibility}

本檔案說明Form Options元件的v1，最初是隨AEM 6.3核心元件的1.0.0版一起推出。

下表列出表單選項元件v1的相容性。

| 元件版本 | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | 相容 | 相容 |
| v1 | 相容 | 相容 |

>[!CAUTION]
>
>本檔案說明表單選項元件的v1。
>
>有關當前版本的表單選項元件的詳細資訊，請參 [閱表單選項元件文檔](form-options.md) 。

## 元件輸出示例 {#sample-component-output}

以下是 [We.Retail的範例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 螢幕擷圖 {#screenshot}

![](assets/chlimage_1-89.png)

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="cmp cmp-options aem-GridColumn aem-GridColumn--default--12">

    <fieldset class="form-group checkbox">
        <legend>What is your favorite type of toast?</legend>
        
        <div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="dry">
              Plain dry toast
            </label>
        </div>
<div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="french">
              French toast
            </label>
        </div>
<div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="texas">
              Texas toast
            </label>
        </div>

    </fieldset>
    
</div>
    
</form></div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "options": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/options",
                  "name": "toastTypes",
                  "jcr:title": "What is your favorite type of toast?",
                  "source": "local",
                  "type": "checkbox"
                }
              },
              ":itemsOrder": [
                "options"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>從核心元件匯出JSON需要1.1.0版的核心元件。 如需詳細 [資訊，請參閱核心元件v1的相容性資訊](versions.md#main-pars_title_236368006) 。

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者定義應顯示的選項類型、標籤，以及哪些選項可用。

![](assets/chlimage_1-90.png)

* **類**&#x200B;型選項的呈現方式

   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **複選下拉式清單**

* **Title** —— 將顯示為選項標籤的標題
* **Name** —— 隨表單資料提交的欄位名稱
* **源** -定義選項的位置

   * **Local** —— 在元件中定義
      * 點選或按一下「 **新增** 」按鈕以新增值， **「刪除** 」以移除值
      * **Value** —— 在提交表單時選擇該選項時保存的值
      * **Text** —— 表單上顯示的選項標籤
      * **活動** -當表單載入時，選項會標示為已選取
      * **停用** -選項無法選取，但仍顯示
      * **List** - AEM中其他位置定義的靜態清單會用於選項
         * **List** - AEM中靜態清單的路徑
            * 使用「瀏覽」按鈕查找清單資源
      * **資料來源** -使用資料來源做為選項
         * **資料源** -資料源的資源類型
* **說明訊息** -提示使用者可在欄位中輸入的內容

## 設計對話框 {#design-dialog}

「表單選項」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

有關表單選項元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。
