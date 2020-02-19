---
title: 表單隱藏元件(v1)
description: 「核心元件表單隱藏」元件可顯示隱藏欄位。
index: n
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# Form Hidden Component (v1) {#form-hidden-component-v}

「核心元件表單隱藏」元件可顯示隱藏欄位。

## 使用狀況 {#usage}

核心元件表單隱藏元件可讓您建立隱藏欄位，將目前頁面的相關資訊傳回AEM，並與表單容器元件一 [起使用](form-container-v1.md)。

欄位屬性可由內容編輯器在「設定」對話方塊中 [定義](#configure-dialog)。

## 版本與相容性 {#version-and-compatibility}

本檔案說明Form Hidden Component的v1（最初隨AEM 6.3核心元件的1.0.0版推出）。

下表列出表單隱藏元件v1的相容性。

| AEM版本 | 表單隱藏元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明表單隱藏元件的v1。
>
>有關當前版本的「表單隱藏元件」的詳細資訊，請參閱「表 [單隱藏元件](/help/components/forms/form-hidden.md) 」文檔。

## 元件輸出示例 {#sample-component-output}

以下是 [We.Retail的範例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件匯出JSON需要1.1.0版的核心元件。 如需詳細 [資訊，請參閱核心元件v1的相容性資訊](/help/versions.md#release-history-and-compatibility) 。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義隱藏欄位的參數。

![](/help/assets/chlimage_1-26.png)

* **Name** —— 隨表單資料提交的欄位名稱
* **Value** —— 隨表單資料提交的欄位值
* **識別碼** -識別碼在頁面上應是唯一的，可用來將指令碼系結至此表單欄位

## 設計對話框 {#design-dialog}

「表單隱藏」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

有關「表單隱藏元件」的最新技 [術檔案，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。
