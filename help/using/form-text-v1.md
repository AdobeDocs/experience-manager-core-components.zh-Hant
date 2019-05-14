---
title: 表單文字元件(v1)
seo-title: 表單文字元件(v1)
description: 'null'
seo-description: 核心元件表單文字元件允許輸入表單文字供提交。
uuid: 30123aa-57a8-4ed4-93cb-6a3d2edff9a7
content-type: 引用
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: bd4e9930-4d81-49ae-a3 d1-9a8740418
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# 表單文字元件(v1){#form-text-component-v}

核心元件表單文字元件允許輸入表單文字供提交。

## 使用狀況 {#usage}

表單文字元件允許提交不同類型的文字，並與 [表單容器元件搭配使用](form-container.md)。

文字驗證、標籤和說明訊息的類型可由 [設定對話方塊中的內容編輯器定義](form-text-v1.md#main-pars_title)。

## 版本與相容性 {#version-and-compatibility}

本文件說明Form Text Component v1of the Form Components with AEM6.3版的版本1.0.0。

下表列出表單文字元件v的相容性。

| AEM版本 | 表單文字元件v1 |
|--- |--- |
| 6.3 | 相容相容性 |
| 6.4 | 相容相容性 |

>[!CAUTION]
>
>本文件說明表單文字元件的v1。
>
>如需目前版本文字元件的詳細資訊，請參閱 [表單文字元件](form-text.md) 文件。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)業」的範例。

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
>從核心元件匯出JSON需要1.1.0版核心元件。如需詳細資訊，請參閱核心元件v [](versions.md#main-pars_title_236368006) 的相容性資訊。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義要輸入的文字類型，以及預設值和標籤。

### 主要功能 {#main}

![](assets/chlimage_1-23.png)

* **限制** -要輸入的文字類型，並驗證

   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數字**
   * **密碼**

* **文字行** -要顯示在文字區域中的行數(僅在 **「限制」** 設為 **「文字區域**」時顯示)

* **標籤** -將顯示為欄位的標籤
* **隱藏標籤無法顯示** -如果標籤僅供協助工具使用，而且不包含任何有關欄位的其他視覺資訊，則需要此標籤
* **元素名稱** -與表單資料一起提交的欄位名稱
* **值** -預先填入欄位的預設值

### 關於 {#about}

![](assets/chlimage_1-24.png)

* **說明訊息** -提示使用者在欄位中輸入的提示
* **顯示說明訊息做為預留位置** -在表單輸入空白且未聚焦時顯示說明訊息

### 限制 {#constraints}

![](assets/chlimage_1-25.png)

* **限制訊息**

   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 不顯示 **文字** 和 **文字區域** 限制類型

* **必要** -如果選取了使用者，必須先填入值，再送出表格
* **僅供讀取** -如果選取了使用者，則無法修改欄位的值

## 設計對話方塊 {#design-dialog}

「表單文字」元件沒有設計對話方塊。

## 技術細節 {#technical-details}

有關表單文字元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)。

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。
