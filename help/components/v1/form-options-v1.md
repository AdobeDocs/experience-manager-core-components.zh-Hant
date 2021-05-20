---
title: 表單選項元件(v1)
description: 核心元件表單選項元件允許以各種格式從預先定義的選項中進行選擇。
index: n
role: Architect, Developer, Administrator, Business Practitioner
exl-id: a5e8656b-eddd-48ec-876b-39bbaa70edf6
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 2%

---

# 表單選項元件(v1){#form-options-component-v}

核心元件表單選項元件允許以各種格式從預先定義的選項中進行選擇。

## 使用狀況 {#usage}

核心元件表單選項元件允許以多種不同方式呈現的不同類型選項的提交，並打算與[表單容器元件](form-container-v1.md)一起使用。

選項、標籤和單個選項的顯示可由[配置對話框](#configure-dialog)中的內容編輯器定義。

## 版本和相容性{#version-and-compatibility}

本檔案說明表單選項元件v1，最初是透過AEM 6.3推出的核心元件1.0.0版。

下表列出了「表單選項」元件的v1的相容性。

| 元件版本 | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | 相容 | 相容 |
| v1 | 相容 | 相容 |

>[!CAUTION]
>
>本文檔介紹「表單選項」元件的v1。
>
>有關當前版本的「表單選項」元件的詳細資訊，請參閱[「表單選項」元件](/help/components/forms/form-options.md)文檔。

## 元件輸出示例{#sample-component-output}

以下範例取自[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件匯出JSON需使用1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 配置對話框{#configure-dialog}

「設定」對話方塊可讓內容作者定義應呈現的選項類型、標籤，以及可用的選項。

![](/help/assets/chlimage_1-90.png)

* ****
類型選項的呈現方式

   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **複選下拉式清單**

* **Title**  — 將顯示為選項標籤的標題
* **名稱**  — 使用表單資料提交的欄位名稱
* **來源**  — 定義選項的位置

   * **本機**  — 在元件中定義
      * 點選或按一下&#x200B;**Add**&#x200B;按鈕以新增值，**Delete**&#x200B;以移除值
      * **值**  — 提交表單時選取該選項時儲存的值
      * **文字**  — 表單上顯示之選項的標籤
      * **作用中**  — 當表單載入時，選項會標示為已選取
      * **已停用**  — 無法選取選項，但仍顯示
      * **清單**  — 選項會使用AEM中其他位置定義的靜態清單
         * **清單**  - AEM中靜態清單的路徑
            * 使用Browse按鈕查找清單資源
      * **資料來源**  — 使用資料來源作為選項
         * **資料來源**  — 資料來源的資源類型
* **說明訊息**  — 可在欄位中輸入內容的使用者提示

## 設計對話框{#design-dialog}

「表單選項」元件沒有設計對話框。

## 技術詳細資訊{#technical-details}

如需表單選項元件[的最新技術檔案，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
