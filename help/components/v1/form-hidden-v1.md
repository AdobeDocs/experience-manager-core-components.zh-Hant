---
title: 表單隱藏元件 (v1)
description: 核心元件表單隱藏元件可顯示隱藏欄位。
index: n
role: Architect, Developer, Admin, User
exl-id: 8e30dac0-5b4b-4fc7-af99-5791c98c90bf
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '316'
ht-degree: 100%

---


# 表單隱藏元件 (v1) {#form-hidden-component-v}

核心元件表單隱藏元件可顯示隱藏欄位。

## 用途 {#usage}

核心元件表單隱藏元件可建立隱藏欄位，以將目前頁面的相關資訊傳回 AEM，其設計用於與[表單容器元件](form-container-v1.md)搭配使用。

欄位屬性可由內容編輯者在[設定對話框](#configure-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

本文件說明表單隱藏元件 v1，最初由 AEM 6.3 搭配的核心元件 1.0.0 版導入。

下表列出表單隱藏元件 v1 的相容性。

| AEM 版本 | 表單隱藏元件 v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文件說明表單隱藏元件 v1。
>
>如需表單隱藏元件目前版本的詳細資訊，請參閱[表單隱藏元件](/help/components/forms/form-hidden.md)文件。

## 範例元件輸出 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html) 中取得的範例。

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
>從核心元件匯出 JSON 需要核心元件 1.1.0 版。如需詳細資訊，請參閱[核心元件 v1 的相容性資訊](/help/versions.md#release-history-and-compatibility)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義隱藏欄位的參數。

![](/help/assets/chlimage_1-26.png)

* **名稱** - 與表單資料共同提交的欄位名稱
* **值** - 與表單資料共同提交的欄位值
* **識別碼** - 識別碼在頁面上應該要是唯一的，且可用於將指令碼繫結到此表單欄位

## 設計對話框 {#design-dialog}

「表單隱藏」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)有關表單隱藏元件的最新技術文件。

您可以從 GitHub 下載完整的核心元件專案。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。
