---
title: 表單隱藏元件(v1)
description: 核心元件表單隱藏元件允許顯示隱藏欄位。
index: n
role: Architect, Developer, Admin, User
exl-id: 8e30dac0-5b4b-4fc7-af99-5791c98c90bf
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 1%

---

# 表單隱藏元件(v1) {#form-hidden-component-v}

核心元件表單隱藏元件允許顯示隱藏欄位。

## 使用狀況 {#usage}

核心元件表單隱藏元件允許建立隱藏欄位，將有關當前頁面的資訊傳回AEM，並且與[表單容器元件](form-container-v1.md)一起使用。

欄位屬性可由[configure dialog](#configure-dialog)中的內容編輯器定義。

## 版本與相容性 {#version-and-compatibility}

本檔案說明表單隱藏元件v1，此元件最初於AEM 6.3的核心元件1.0.0版中推出。

下表列出了窗體隱藏元件v1的相容性。

| AEM版本 | 表單隱藏元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔介紹「表單隱藏元件」的v1。
>
>有關當前版本的表單隱藏元件的詳細資訊，請參閱[表單隱藏元件](/help/components/forms/form-hidden.md)文檔。

## 範例元件輸出 {#sample-component-output}

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
>從核心元件匯出JSON需使用1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md#release-history-and-compatibility)的[相容性資訊。

## 配置對話框 {#configure-dialog}

設定對話方塊可讓內容作者定義隱藏欄位的參數。

![](/help/assets/chlimage_1-26.png)

* **名稱**  — 隨表單資料提交的欄位名稱
* **值**  — 隨表單資料提交之欄位的值
* **識別碼**  — 該識別碼在頁面上應是唯一的，可用來將指令碼系結至此表單欄位

## 設計對話方塊 {#design-dialog}

「表單隱藏」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

如需表單隱藏元件[的最新技術檔案，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
