---
title: 表單隱藏元件(v1)
description: 核心元件表單隱藏元件可顯示隱藏欄位。
index: n
role: Architect, Developer, Admin, User
exl-id: 8e30dac0-5b4b-4fc7-af99-5791c98c90bf
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 2%

---


# 表單隱藏元件(v1) {#form-hidden-component-v}

核心元件表單隱藏元件可顯示隱藏欄位。

## 使用情況 {#usage}

核心元件表單隱藏元件可建立隱藏欄位，以將目前頁面的相關資訊傳回AEM，並且此元件旨在與[表單容器元件](form-container-v1.md)搭配使用。

欄位屬性可由內容編輯者在[設定對話方塊](#configure-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

本檔案說明表單隱藏元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出表單隱藏元件v1的相容性。

| AEM 版本 | 表單隱藏元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明表單隱藏元件v1。
>
>如需目前版本的表單隱藏元件的詳細資訊，請參閱[表單隱藏元件](/help/components/forms/form-hidden.md)檔案。

## 範例元件輸出 {#sample-component-output}

以下是從[We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html)中取得的範例。

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
>從核心元件匯出JSON需要版本1.1.0的核心元件。 如需詳細資訊，請參閱核心元件v1[&#128279;](/help/versions.md#release-history-and-compatibility)的相容性資訊。

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義隱藏欄位的引數。

![](/help/assets/chlimage_1-26.png)

* **名稱** — 與表單資料共同提交的欄位名稱
* **值** — 與表單資料共同提交的欄位值
* **識別碼** — 識別碼在頁面上應該是唯一的，並且可用來將指令碼繫結到此表單欄位

## 設計對話方塊 {#design-dialog}

「表單隱藏」元件沒有「設計」對話方塊。

## 技術細節 {#technical-details}

您可以在GitHub[&#128279;](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)上找到有關表單隱藏元件的最新技術檔案。

您可以從GitHub下載整個核心元件專案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。
