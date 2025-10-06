---
title: 表單文字元件 (v1)
description: 核心元件表單文字元件可讓您輸入表單文字以供提交。
index: n
role: Architect, Developer, Admin, User
exl-id: d6fbc596-cb42-4478-8a3c-aa5aead3be0a
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '472'
ht-degree: 100%

---


# 表單文字元件 (v1) {#form-text-component-v}

核心元件表單文字元件可讓您輸入表單文字以供提交。

## 用途 {#usage}

表單文字元件允許提交不同類型的文字，其設計用於與[表單容器元件](form-container-v1.md)搭配使用。

文字驗證類型、標籤和說明訊息可由內容編輯者在[設定對話框](#configure-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

本文件說明表單文字元件 v1，最初由 AEM 6.3 搭配的核心元件 1.0.0 版導入。

下表列出表單文字元件 v1 的相容性。

| AEM 版本 | 表單文字元件 v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文件說明表單文字元件 v1。
>
>如需表單文字元件目前版本的詳細資訊，請參閱[表單文字元件](/help/components/forms/form-text.md)文件。

## 範例元件輸出 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html) 中取得的範例。

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
>從核心元件匯出 JSON 需要核心元件 1.1.0 版。如需詳細資訊，請參閱[核心元件 v1 的相容性資訊](/help/versions.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義要輸入的文字類型，以及預設值和標籤。

### 主要 {#main}

![](/help/assets/chlimage_1-23.png)

* **限制** - 要輸入的文字類型，並據此進行驗證

   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數字**
   * **密碼**

* **文字行** - 要在文字區域中顯示的行數 (僅當&#x200B;**限制**&#x200B;設定為&#x200B;**文字區域**&#x200B;時才會顯示)

* **標籤** - 欄位上所顯示的標籤
* **隱藏標籤以避免顯示** - 標籤僅必須在協助工具用途時才需使用，不會提供欄位任何額外的可見資訊
* **元素名稱** - 與表單資料共同提交的欄位名稱
* **值** - 已預先填入欄位中的預設值

### 關於 {#about}

![](/help/assets/chlimage_1-24.png)

* **說明訊息** - 向使用者提示可輸入於欄位的內容
* **將說明訊息顯示為預留位置** - 當表單輸入為空白且焦點不在其上時，在表單輸入中顯示說明訊息

### 限制 {#constraints}

![](/help/assets/chlimage_1-25.png)

* **限制訊息**

   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 未針對&#x200B;**文字**&#x200B;和&#x200B;**文字區域**&#x200B;限制類型顯示

* **必要** - 如果選取，使用者必須在提交表單前填入值
* **設為唯讀** - 如果選取，使用者無法修改欄位的值

## 設計對話框 {#design-dialog}

「表單文字」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)有關表單文字元件的最新技術文件。

您可以從 GitHub 下載完整的核心元件專案。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。
