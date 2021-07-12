---
title: 表單文字元件(v1)
description: 核心元件表單文字元件可輸入表單文字以供提交。
index: n
role: Architect, Developer, Admin, User
exl-id: d6fbc596-cb42-4478-8a3c-aa5aead3be0a
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 7%

---

# 表單文字元件(v1) {#form-text-component-v}

核心元件表單文字元件可輸入表單文字以供提交。

## 使用狀況 {#usage}

表單文字元件允許提交不同類型的文本，並打算與[表單容器元件](form-container-v1.md)一起使用。

文本驗證、標籤和幫助消息的類型可由[配置對話框](#configure-dialog)中的內容編輯器定義。

## 版本與相容性 {#version-and-compatibility}

本檔案說明表單文字元件v1，此元件最初於AEM 6.3的核心元件1.0.0版中推出。

下表列出表單文本元件v1的相容性。

| AEM版本 | 表單文字元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔介紹「表單文本元件」的v1。
>
>有關當前版本的表單文本元件的詳細資訊，請參閱[表單文本元件](/help/components/forms/form-text.md)文檔。

## 範例元件輸出 {#sample-component-output}

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
>從核心元件匯出JSON需使用1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 配置對話框 {#configure-dialog}

設定對話方塊可讓內容作者定義要輸入的文字類型以及預設值和標籤。

### 主要 {#main}

![](/help/assets/chlimage_1-23.png)

* **限制**  — 要輸入並將根據驗證的文字類型

   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數量**
   * **密碼**

* **文本行**  — 要在文本區域中顯示的行數(僅當「約束」設 **** 定為「文本 **區域」**&#x200B;時顯示)

* **標籤**  — 將針對欄位顯示的標籤
* **隱藏標籤，使其不顯示**  — 如果標籤僅用於輔助功能目的，並且沒有傳遞任何有關該欄位的其他視覺資訊，則需要此標籤
* **元素名稱**  — 隨表單資料提交的欄位名稱
* **值**  — 預先填入欄位中的預設值

### 關於 {#about}

![](/help/assets/chlimage_1-24.png)

* **說明訊息**  — 提示使用者可在欄位中輸入的內容
* **將說明訊息顯示為預留位置**  — 在表單輸入為空且未聚焦時，在其內顯示說明訊息

### 限制 {#constraints}

![](/help/assets/chlimage_1-25.png)

* **限制訊息**

   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 未針對&#x200B;**Text**&#x200B;和&#x200B;**Text Area**&#x200B;約束類型顯示

* **必要**  — 如果選取此選項，則使用者必須先填入值，才能提交表單
* **設為唯讀**  — 如果選取，使用者無法修改欄位的值

## 設計對話方塊 {#design-dialog}

「表單文本」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

如需表單文字元件[的最新技術檔案，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
