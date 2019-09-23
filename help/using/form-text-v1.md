---
title: 表單文字元件(v1)
seo-title: 表單文字元件(v1)
description: 'null'
seo-description: 核心元件表單文字元件允許輸入表單文字以供提交。
uuid: 30123aba-57a8-4ed4-93cb-6a3d2edff9a7
content-type: 引用
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新功能
discoiquuid: bd4e9930-4d81-49ae-a3d1-9a8740418dae
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Form Text Component (v1){#form-text-component-v}

核心元件表單文字元件允許輸入表單文字以供提交。

## 使用狀況 {#usage}

表單文字元件允許提交不同類型的文字，並與表單容器元件一 [起使用](form-container.md)。

文字驗證、標籤和說明訊息的類型可由內容編輯器在「設定」對話方塊中 [定義](form-text-v1.md#main-pars_title)。

## 版本與相容性 {#version-and-compatibility}

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
>有關當前版本的表單文本元件的詳細資訊，請參 [閱表單文本元件文檔](form-text.md) 。

## 元件輸出示例 {#sample-component-output}

以下是 [We.Retail的範例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 螢幕擷圖 {#screenshot}

![](assets/chlimage_1-22.png)

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
>從核心元件匯出JSON需要1.1.0版的核心元件。 如需詳細 [資訊，請參閱核心元件v1的相容性資訊](versions.md#main-pars_title_236368006) 。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義要輸入的文本類型以及預設值和標籤。

### Main {#main}

![](assets/chlimage_1-23.png)

* **約束** -要輸入並將驗證的文本類型

   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數字**
   * **密碼**

* **文本行** -要在文本區域中顯示的行數(僅當「約束」( **Constraint** )設定為「文本區域」( **Text Area**)時顯示)

* **Label** —將為欄位顯示的標籤
* **隱藏標籤不顯示** -如果標籤僅用於協助工具用途且不提供任何其他有關該欄位的視覺資訊，則需要此標籤
* **元素名稱** -隨表單資料提交的欄位名稱
* **Value** —— 在欄位中預先填入的預設值

### 關於 {#about}

![](assets/chlimage_1-24.png)

* **說明訊息** -提示使用者在欄位中可輸入的內容
* **將幫助消息顯示為預留位置** -在表單輸入內顯示幫助消息時，其為空白且未聚焦

### 限制 {#constraints}

![](assets/chlimage_1-25.png)

* **限制訊息**

   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 不顯示文本 **和文本** 區 **域約束類型**

* **必要** -如果選取此選項，使用者必須先填入值，才能提交表格
* **只讀** -如果選中此選項，用戶無法修改欄位的值

## 設計對話框 {#design-dialog}

「表單文字」元件沒有設計對話方塊。

## 技術詳細資訊 {#technical-details}

有關表單文字元件的最新技術 [檔案可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。
