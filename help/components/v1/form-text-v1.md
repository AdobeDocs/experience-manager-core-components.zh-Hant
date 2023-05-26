---
title: 表單文字元件(v1)
description: 核心元件表單文字元件可讓您輸入表單文字以供提交。
index: n
role: Architect, Developer, Admin, User
exl-id: d6fbc596-cb42-4478-8a3c-aa5aead3be0a
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 7%

---

# 表單文字元件(v1) {#form-text-component-v}

核心元件表單文字元件可讓您輸入表單文字以供提交。

## 使用狀況 {#usage}

表單文字元件可用於提交不同型別的文字，並且旨在與 [表單容器元件](form-container-v1.md).

文字驗證的型別、標籤和說明訊息可由內容編輯者在 [設定對話方塊](#configure-dialog).

## 版本和相容性 {#version-and-compatibility}

本檔案說明表單文字元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出表單文字元件v1的相容性。

| AEM版本 | 表單文字元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明表單文字元件v1。
>
>如需目前版本的表單文字元件的詳細資訊，請參閱 [表單文字元件](/help/components/forms/form-text.md) 檔案。

## 範例元件輸出 {#sample-component-output}

以下是取自下列專案的範例： [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>從核心元件匯出JSON需要核心元件1.1.0版。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 以取得詳細資訊。

## 設定對話方塊 {#configure-dialog}

「設定」對話方塊可讓內容作者定義要輸入的文字型別，以及預設值和標籤。

### 主要 {#main}

![](/help/assets/chlimage_1-23.png)

* **限制**  — 要輸入並進行驗證的文字型別

   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數字**
   * **密碼**

* **文字行**  — 文字區域中要顯示的行數(僅在 **限制** 設為 **文字區域**)

* **標籤**  — 針對欄位顯示的標籤
* **隱藏標籤以避免顯示**  — 標籤僅用於協助工具目的，且不會提供欄位的任何其他視覺資訊時需要
* **元素名稱**  — 與表單資料共同提交的欄位名稱
* **值**  — 在欄位中預先填入的預設值

### 關於 {#about}

![](/help/assets/chlimage_1-24.png)

* **說明訊息**  — 向使用者提示可在欄位中輸入的內容
* **將說明訊息顯示為預留位置**  — 當表單輸入為空白且焦點不在其上時，在表單輸入中顯示說明訊息

### 限制 {#constraints}

![](/help/assets/chlimage_1-25.png)

* **限制訊息**

   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 未顯示於 **文字** 和 **文字區域** 限制型別

* **必填**  — 如果選取，使用者必須在提交表單之前填寫值
* **設為唯讀**  — 如果選取，使用者無法修改欄位的值

## 設計對話方塊 {#design-dialog}

表單文字元件沒有設計對話方塊。

## 技術細節 {#technical-details}

有關表單文字元件的最新技術檔案 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text).

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).
