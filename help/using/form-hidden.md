---
title: 表單隱藏元件
seo-title: 表單隱藏元件
description: 'null'
seo-description: 「核心元件表單隱藏」元件可顯示隱藏欄位。
uuid: 63a1b381-f45c-4241-b743-dea8abd45e11
contentOwner: 使用者
content-type: 引用
topic-tags: 核心元件
discoiquuid: 36e49035-7641-4bad-8a61-723060032903
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

「核心元件表單隱藏」元件可顯示隱藏欄位。

## 使用狀況 {#usage}

核心元件表單隱藏元件可讓您建立隱藏欄位，將目前頁面的相關資訊傳回AEM，並與表單容器元件一 [起使用](form-container.md)。

欄位屬性可由內容編輯器在「設定」對話方塊中 [定義](form-hidden.md)。

## 版本與相容性 {#version-and-compatibility}

目前的表單隱藏元件版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 相容 | 相容 | 相容 |
| [v1](form-hidden-v1.md) | 相容 | 相容 | 相容 |

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](versions.md)。

## 元件輸出示例 {#sample-component-output}

以下是 [We.Retail的範例](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

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

### 技術詳細資訊 {#technical-details}

有關「表單隱藏元件」的最新技 [術檔案，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義隱藏欄位的參數。

![](assets/chlimage_1-26.png)

* **名稱**&#x200B;隨表單資料提交的欄位名稱
* **值**&#x200B;與表單資料一起提交的欄位值
* **識別**&#x200B;碼識別碼在頁面上應是唯一的，可用來將指令碼系結至此表單欄位

由於「表單隱藏」元件通常沒有可見屬性，因此如果為幫助作者識別適當的「表單隱藏」元件而分配了「名稱」和「值 ******** 」欄位值，則編輯器中的元件佔位符將顯示這些值。

![](assets/screenshot_2018-10-19at094927.png)

## 設計對話框 {#design-dialog}

「表單隱藏」元件沒有設計對話框。