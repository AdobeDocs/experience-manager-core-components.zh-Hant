---
title: 表單隱藏元件(v1)
description: 「核心元件表單隱藏」元件可顯示隱藏欄位。
index: n
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 1%

---


# 表單隱藏元件(v1){#form-hidden-component-v}

「核心元件表單隱藏」元件可顯示隱藏欄位。

## 使用狀況 {#usage}

核心元件表單隱藏元件允許建立隱藏欄位，將有關當前頁的資訊傳回AEM，並與[表單容器元件](form-container-v1.md)一起使用。

欄位屬性可由[configure dialog](#configure-dialog)中的內容編輯器定義。

## 版本和相容性{#version-and-compatibility}

本檔案說明第1版的表單隱藏元件(最初是隨6.3版核心元件1.0.0推出AEM)。

下表列出表單隱藏元件v1的相容性。

| 版AEM本 | 表單隱藏元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明表單隱藏元件的v1。
>
>有關當前版本的表單隱藏元件的詳細資訊，請參閱[表單隱藏元件](/help/components/forms/form-hidden.md)文檔。

## 元件輸出示例{#sample-component-output}

以下範例取自[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件匯出JSON需要1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md#release-history-and-compatibility)的[相容性資訊。

## 配置對話框{#configure-dialog}

配置對話框允許內容作者定義隱藏欄位的參數。

![](/help/assets/chlimage_1-26.png)

* **名稱** -隨表單資料提交的欄位名稱
* **值** -隨表單資料提交的欄位值
* **識別碼** -識別碼在頁面上應是唯一的，可用來將指令碼系結至此表單欄位

## 設計對話框{#design-dialog}

「表單隱藏」元件沒有設計對話框。

## 技術詳細資訊{#technical-details}

有關表單隱藏元件[的最新技術檔案可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)上找到。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
