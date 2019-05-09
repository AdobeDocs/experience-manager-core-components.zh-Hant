---
title: 表單隱藏元件(v1)
seo-title: 表單隱藏元件(v1)
description: 核心元件表單隱藏元件允許顯示隱藏欄位。
seo-description: 核心元件表單隱藏元件允許顯示隱藏欄位。
uuid: f5005346-def5-4e1 f-8f93-e4 cfc67 a9329
content-type: 引用
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: d35f4e71-ec7 f-4128-9123-b997 dbb5 f0 cf
index: n
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 表單隱藏元件(v1){#form-hidden-component-v}

核心元件表單隱藏元件允許顯示隱藏欄位。

## 使用狀況 {#usage}

核心元件表單隱藏元件可讓您建立隱藏欄位，將目前頁面的相關資訊傳遞至AEM，並與 [表單容器元件一起使用](form-container.md)。

欄位屬性可由 [設定對話方塊中的內容編輯器定義](#configure-dialog)。

## 版本與相容性 {#version-and-compatibility}

本文件說明Form隱藏元件的v1，原始版本為AEM6.3的1.0.0版。

下表列出表單隱藏元件v的相容性。

| AEM版本 | 表單隱藏元件v1 |
|--- |--- |
| 6.3 | 相容相容性 |
| 6.4 | 相容相容性 |

>[!CAUTION]
>
>本文件說明表單隱藏元件的v1。
>
>如需目前版本「表單隱藏元件」的詳細資訊，請參閱 [「表單隱藏元件](form-hidden.md) 」文件。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)業」的範例。

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
 <form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
  <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
   <div class="visible aem-GridColumn aem-GridColumn--default--12">
    <input type="hidden" id="ghostToast" name="Invisible Toast" value="ghostToast">
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
                "hidden": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/hidden",
                  "name": "Invisible Toast",
                  "id": "ghostToast",
                  "value": "ghostToast"
                }
              },
              ":itemsOrder": [
                "hidden"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>從核心元件匯出JSON需要1.1.0版核心元件。如需詳細資訊，請參閱核心元件v [](versions.md#release-history-and-compatibility) 的相容性資訊。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義隱藏欄位的參數。

![](assets/chlimage_1-26.png)

* **名稱** -與表單資料一起提交的欄位名稱
* **值** -與表單資料一起提交的欄位值
* **識別碼** -識別碼應在頁面上唯一，並可用來系結指令碼至此表格欄位

## 設計對話方塊 {#design-dialog}

「表單隱藏」元件沒有設計對話方塊。

## 技術細節 {#technical-details}

有關表單隱藏元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)。

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。
