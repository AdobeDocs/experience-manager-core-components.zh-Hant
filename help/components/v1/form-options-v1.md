---
title: 表單選項元件(v1)
description: 「核心元件表單」選項元件允許以各種格式從預定義選項中進行選擇。
index: n
role: Architect, Developer, Admin, User
exl-id: a5e8656b-eddd-48ec-876b-39bbaa70edf6
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 2%

---

# 表單選項元件(v1) {#form-options-component-v}

「核心元件表單」選項元件允許以各種格式從預定義選項中進行選擇。

## 使用狀況 {#usage}

核心元件表單選項元件允許以多種不同方式呈現的不同類型選項的提交，並且與 [形式容器元件](form-container-v1.md)。

選項、標籤和單個選項的演示可由中的內容編輯器定義 [配置對話框](#configure-dialog)。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了最初隨帶有6.3的核心元件1.0.0版而引入的表單選項元件的v1AEM。

下表列出了「表單選項」元件的v1相容性。

| 元件版本 | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | 相容 | 相容 |
| v1 | 相容 | 相容 |

>[!CAUTION]
>
>本文檔介紹「表單選項」元件的v1。
>
>有關表單選項元件當前版本的詳細資訊，請參閱 [表單選項元件](/help/components/forms/form-options.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件導出JSON需要1.1.0版核心元件。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 的子菜單。

## 配置對話框 {#configure-dialog}

「配置」對話框允許內容作者定義應顯示的選項類型、標籤以及哪些選項可用。

![](/help/assets/chlimage_1-90.png)

* **類型**
如何提供選項

   * **核取方塊**
   * **選項按鈕**
   * **下拉式清單**
   * **複選下拉式清單**

* **標題**  — 將顯示為選項標籤的標題
* **名稱**  — 使用表單資料提交的欄位的名稱
* **源**  — 定義選項的位置

   * **本地**  — 在元件內定義
      * 點擊或按一下 **添加** 按鈕以添加值， **刪除** 刪除值
      * **值**  — 提交表單時選擇該選項時保存的值
      * **文本**  — 窗體上顯示的選項的標籤
      * **活動**  — 在載入表單時，選項被標籤為已選
      * **已禁用**  — 該選項不可選，但仍顯示
      * **清單**  — 選項使用中其他位置AEM定義的靜態清單
         * **清單**  — 中靜態清單的路AEM徑
            * 使用「瀏覽」按鈕查找清單資源
      * **資料源**  — 資料源用於選項
         * **資料源**  — 資料源的資源類型
* **幫助消息**  — 提示用戶可在欄位中輸入的內容

## 設計對話框 {#design-dialog}

「表單選項」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

有關表單選項元件的最新技術文檔 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options)。

整個核心元件項目可從GitHub下載。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。
