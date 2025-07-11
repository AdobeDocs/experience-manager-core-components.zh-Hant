---
title: 表單選項元件(v1)
description: 核心元件表單選項元件可讓您從各種格式的預先定義選項中進行選取。
index: n
role: Architect, Developer, Admin, User
exl-id: a5e8656b-eddd-48ec-876b-39bbaa70edf6
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 1%

---


# 表單選項元件(v1) {#form-options-component-v}

核心元件表單選項元件可讓您從各種格式的預先定義選項中進行選取。

## 使用情況 {#usage}

核心元件表單選項元件允許提交以多種不同方式呈現的不同型別的選項，並且旨在與[表單容器元件](form-container-v1.md)搭配使用。

選項、標籤和個別選項的呈現可由內容編輯者在[設定對話方塊](#configure-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

本檔案說明表單選項元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出表單選項元件v1的相容性。

| 元件版本 | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | 相容 | 相容 |
| v1 | 相容 | 相容 |

>[!CAUTION]
>
>本檔案說明表單選項元件v1。
>
>如需目前版本的表單選項元件的詳細資訊，請參閱[表單選項元件](/help/components/forms/form-options.md)檔案。

## 範例元件輸出 {#sample-component-output}

以下是從[We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html)中取得的範例。

### 螢幕擷圖 {#screenshot}

![](/help/assets/chlimage_1-89.png)

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
>從核心元件匯出JSON需要版本1.1.0的核心元件。 如需詳細資訊，請參閱核心元件v1[&#128279;](/help/versions.md)的相容性資訊。

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義應顯示的選項型別、標籤以及可用的選項。

![](/help/assets/chlimage_1-90.png)

* **型別**
如何顯示選項

   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **多重選取下拉式清單**

* **標題** — 將顯示為選項標籤的標題
* **名稱** — 與表單資料共同提交的欄位名稱
* **Source** — 定義選項的位置

   * **本機** — 已在元件中定義
      * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增值，**刪除**&#x200B;以移除值
      * **值** — 提交表單時選取此選項時儲存的值
      * **文字** — 表單上顯示的選項標籤
      * **作用中** — 表單載入時，選項會標示為已選取
      * **已停用** — 選項不可選取，但仍會顯示
      * **清單** - AEM中其他地方定義的靜態清單用於此選項
         * **清單** - AEM中靜態清單的路徑
            * 使用瀏覽按鈕來尋找清單資源
      * **資料來源** — 資料來源用於選項
         * **資料來源** — 資料來源的資源型別
* **說明訊息** — 使用者可在欄位中輸入的內容提示

## 設計對話方塊 {#design-dialog}

表單選項元件沒有設計對話方塊。

## 技術細節 {#technical-details}

您可以在GitHub[&#128279;](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options)上找到表單選項元件的最新技術檔案。

您可以從GitHub下載整個核心元件專案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。
