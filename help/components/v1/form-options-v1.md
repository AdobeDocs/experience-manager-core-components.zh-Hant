---
title: 表單選項元件 (v1)
description: 核心元件表單選項元件可讓您從各種格式的預先定義選項中選取。
index: n
role: Architect, Developer, Admin, User
exl-id: a5e8656b-eddd-48ec-876b-39bbaa70edf6
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '459'
ht-degree: 100%

---


# 表單選項元件 (v1) {#form-options-component-v}

核心元件表單選項元件可讓您從各種格式的預先定義選項中選取。

## 用途 {#usage}

核心元件表單選項元件允許提交以多種不同方式呈現的各類型選項，其設計用於與[表單容器元件](form-container-v1.md)搭配使用。

選項、標籤和個別選項的呈現方式可由內容編輯者在[設定對話框](#configure-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

本文件說明表單選項元件 v1，最初由 AEM 6.3 搭配的核心元件 1.0.0 版導入。

下表列出表單選項元件 v1 的相容性。

| 元件版本 | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | 相容 | 相容 |
| v1 | 相容 | 相容 |

>[!CAUTION]
>
>本文件說明表單選項元件 v1。
>
>如需表單選項元件目前版本的詳細資訊，請參閱[表單選項元件](/help/components/forms/form-options.md)文件。

## 範例元件輸出 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html) 中取得的範例。

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
>從核心元件匯出 JSON 需要核心元件 1.1.0 版。如需詳細資訊，請參閱[核心元件 v1 的相容性資訊](/help/versions.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義應呈現的選項類型、標籤以及可用的選項。

![](/help/assets/chlimage_1-90.png)

* **類型**
選項的呈現方式

   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **複選下拉式清單**

* **標題** - 將顯示為選項標籤的標題
* **名稱** - 與表單資料一起提交的欄位名稱
* **來源** - 定義選項的位置

   * **本機** - - 定義於元件內部
      * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增值，點選或按一下&#x200B;**刪除**&#x200B;以移除值
      * **值** - 提交表單時，選取選項時所儲存的值
      * **文字** - 顯示於表單上的選項標籤
      * **作用中** - 載入表單時，該選項會標示為已選取
      * **已停用** - 該選項無法選取，但仍會顯示
      * **清單** - 將在 AEM 中其他位置定義的靜態清單用於選項
         * **清單** - AEM 中靜態清單的路徑
            * 使用「瀏覽」按鈕來尋找清單資源
      * **資料來源** - 資料來源用於選項
         * **資料來源** - 資料來源的資源類型
* **說明訊息** - 提示使用者可輸入至該欄位的內容

## 設計對話框 {#design-dialog}

「表單選項」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options)有關表單選項元件的最新技術文件。

您可以從 GitHub 下載完整的核心元件專案。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。
