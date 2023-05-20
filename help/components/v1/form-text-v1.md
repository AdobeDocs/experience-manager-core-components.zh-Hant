---
title: 表單文本元件(v1)
description: 核心元件表單文本元件允許輸入表單文本以供提交。
index: n
role: Architect, Developer, Admin, User
exl-id: d6fbc596-cb42-4478-8a3c-aa5aead3be0a
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 7%

---

# 表單文本元件(v1) {#form-text-component-v}

核心元件表單文本元件允許輸入表單文本以供提交。

## 使用狀況 {#usage}

表單文本元件允許提交不同類型的文本，並將與 [形式容器元件](form-container-v1.md)。

文本驗證、標籤和幫助消息的類型可由內容編輯器在 [配置對話框](#configure-dialog)。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了表單文本元件的v1，最初是隨帶有6.3的核心元件1.0.0版一起引AEM入的。

下表列出了表單文本元件v1的相容性。

| 版AEM本 | 窗體文本元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔介紹「表單文本」元件的v1。
>
>有關窗體文本元件當前版本的詳細資訊，請參閱 [窗體文本元件](/help/components/forms/form-text.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件導出JSON需要1.1.0版核心元件。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 的子菜單。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義要輸入的文本類型以及預設值和標籤。

### 主要 {#main}

![](/help/assets/chlimage_1-23.png)

* **約束**  — 要輸入並將根據

   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數字**
   * **密碼**

* **文本行**  — 要在文本區域中顯示的行數(僅在 **約束** 設定為 **文本區域**)

* **標籤**  — 將為欄位顯示的標籤
* **隱藏標籤，使其不顯示**  — 如果僅出於輔助功能目的而需要標籤且不傳遞任何有關欄位的附加視覺資訊，則需要
* **元素名稱**  — 隨表單資料提交的欄位的名稱
* **值**  — 欄位中預填充的預設值

### 關於 {#about}

![](/help/assets/chlimage_1-24.png)

* **幫助消息**  — 向用戶提示可在欄位中輸入的內容
* **將幫助消息顯示為佔位符**  — 當表單輸入為空且未聚焦時，在表單輸入內顯示幫助消息

### 限制 {#constraints}

![](/help/assets/chlimage_1-25.png)

* **限制訊息**

   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 未顯示 **文本** 和 **文本區域** 約束類型

* **必需**  — 如果選中此選項，則用戶必須在提交表單之前填寫值
* **只讀**  — 如果選中，則用戶無法修改欄位的值

## 設計對話框 {#design-dialog}

「表單文本」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

有關表單文本元件的最新技術文檔 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)。

整個核心元件項目可從GitHub下載。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。
