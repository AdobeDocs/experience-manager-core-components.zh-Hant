---
title: 表單文字元件(v1)
description: 核心元件表單文字元件允許輸入表單文字以供提交。
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 7%

---


# 表單文字元件(v1){#form-text-component-v}

核心元件表單文字元件允許輸入表單文字以供提交。

## 使用狀況 {#usage}

表單文本元件允許提交不同類型的文本，並準備與[表單容器元件](form-container-v1.md)一起使用。

文本驗證、標籤和幫助消息的類型可由[configure dialog](#configure-dialog)中的內容編輯器定義。

## 版本和相容性{#version-and-compatibility}

本檔案說明Form Text元件的v1，最初是隨AEM 6.3核心元件的1.0.0版一起推出。

下表列出表單文字元件v1的相容性。

| AEM版本 | 表單文字元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明「表單文字元件」的v1。
>
>有關當前版本的表單文本元件的詳細資訊，請參閱[表單文本元件](/help/components/forms/form-text.md)文檔。

## 元件輸出示例{#sample-component-output}

以下範例取自[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 螢幕擷圖 {#screenshot}

![](/help/assets/chlimage_1-22.png)

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
 <form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
     <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
     <div class="cmp cmp-form-field aem-GridColumn aem-GridColumn--default--12">
   <div class="form-group">
       <label for="form-text-978484744">How many pieces of toast would you like?</label>
          <input type="number" id="form-text-978484744" name="pieces">
   </div>
  </div>
 </form>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "text": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/text",
                  "name": "piecesOfToast",
                  "jcr:title": "How many pieces of toast would you like?",
                  "type": "number",
                  "rows": "2"
                }
              },
              ":itemsOrder": [
                "text"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>從核心元件匯出JSON需要1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 配置對話框{#configure-dialog}

配置對話框允許內容作者定義要輸入的文本類型以及預設值和標籤。

### 主要 {#main}

![](/help/assets/chlimage_1-23.png)

* **約束** -要輸入和將驗證的文本類型

   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數量**
   * **密碼**

* **文本行** -要在文本區域中顯示的行數(僅在「約束」( **** Constraintis)設定為「文本區域」( **Text Area**)時顯示)

* **Label**  —— 將為欄位顯示的標籤
* **隱藏標籤不顯示** -如果標籤僅用於輔助功能用途，且不提供任何有關該欄位的其他視覺資訊，則需要此標籤
* **元素名稱** -隨表單資料提交的欄位名稱
* **值** -在欄位中預先填入的預設值

### 關於 {#about}

![](/help/assets/chlimage_1-24.png)

* **幫助消息** -提示用戶可在欄位中輸入的內容
* **將幫助消息顯示為預留位置** -在表單輸入內顯示幫助消息，當其為空且未聚焦

### 限制 {#constraints}

![](/help/assets/chlimage_1-25.png)

* **限制訊息**

   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * **Text**&#x200B;和&#x200B;**Text Area**&#x200B;約束類型未顯示

* **必要** -如果選取此選項，使用者必須先填入值，才能提交表格
* **只讀** -如果選中此選項，則用戶無法修改欄位的值

## 設計對話框{#design-dialog}

「表單文字」元件沒有設計對話方塊。

## 技術詳細資訊{#technical-details}

有關表單文字元件[的最新技術檔案可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)上找到。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
