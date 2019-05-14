---
title: 表單隱藏元件
seo-title: 表單隱藏元件
description: 'null'
seo-description: 核心元件表單隱藏元件允許顯示隱藏欄位。
uuid: 63a1b381-f45 c-4241-b743-depd45 e11
contentOwner: 使用者
content-type: 引用
topic-tags: 核心元件
discoiquuid: 36e49035-7641-4bad-8a61-72306003293
disttype: dist5
gnavtheme: 淺色
groupsectionnavitems: 否
hidemerchandisingbar: 繼承
hidepromocomponent: 繼承
modalsize: 426x240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# 表單隱藏元件{#form-hidden-component}

核心元件表單隱藏元件允許顯示隱藏欄位。

## 使用狀況 {#usage}

核心元件表單隱藏元件可讓您建立隱藏欄位，將目前頁面的相關資訊傳遞至AEM，並與 [表單容器元件一起使用](form-container.md)。

欄位屬性可由 [設定對話方塊中的內容編輯器定義](form-hidden.md)。

## 版本與相容性 {#version-and-compatibility}

目前版本的「表單隱藏元件」是v2，它是在2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](form-hidden-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)業」的範例。

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

### 技術細節 {#technical-details}

有關表單隱藏元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義隱藏欄位的參數。

![](assets/chlimage_1-26.png)

* **名稱**使用表單資料提交的欄位名稱
* **值：**與表單資料一起提交的欄位值
* **識別碼**識別碼在頁面上應唯一，並可用來系結指令碼至此表格欄位

由於「表單隱藏」元件通常沒有可見屬性，因此在編輯器中，元件的預留位置位置會顯示 **「名稱** 」和 **「值** 」欄位值(如果指派的話)，以協助作者識別適當的「表單隱藏」元件。

![](assets/screenshot_2018-10-19at094927.png)

## 設計對話方塊 {#design-dialog}

「表單隱藏」元件沒有設計對話方塊。