---
title: 窗體隱藏元件(v1)
description: 「核心元件表單隱藏」元件允許顯示隱藏欄位。
index: n
role: Architect, Developer, Admin, User
exl-id: 8e30dac0-5b4b-4fc7-af99-5791c98c90bf
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 1%

---

# 窗體隱藏元件(v1) {#form-hidden-component-v}

「核心元件表單隱藏」元件允許顯示隱藏欄位。

## 使用狀況 {#usage}

核心元件表單隱藏元件允許建立隱藏欄位，將有關當前頁面的資訊傳回AEM，並與 [形式容器元件](form-container-v1.md)。

欄位屬性可由中的內容編輯器定義 [配置對話框](#configure-dialog)。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了表單隱藏元件的v1，最初是隨帶有6.3的核心元件1.0.0版一起引AEM入的。

下表列出了「表單隱藏元件」的v1的相容性。

| 版AEM本 | 窗體隱藏元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔介紹「表單隱藏元件」的v1。
>
>有關窗體隱藏元件當前版本的詳細資訊，請參閱 [窗體隱藏元件](/help/components/forms/form-hidden.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件導出JSON需要1.1.0版核心元件。 請參閱 [核心元件v1的相容性資訊](/help/versions.md#release-history-and-compatibility) 的子菜單。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義隱藏欄位的參數。

![](/help/assets/chlimage_1-26.png)

* **名稱**  — 與表單資料一起提交的欄位名稱
* **值**  — 與表單資料一起提交的欄位值
* **標識符**  — 標識符在頁面上應是唯一的，可用於將指令碼綁定到此表單域

## 設計對話框 {#design-dialog}

「表單隱藏」(Form Hidden)元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

有關表單隱藏元件的最新技術文檔 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)。

整個核心元件項目可從GitHub下載。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。
