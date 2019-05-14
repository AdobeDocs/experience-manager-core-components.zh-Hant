---
title: 表單按鈕元件
seo-title: 表單按鈕元件
description: 'null'
seo-description: 核心元件表單隱藏元件可讓您將隱藏欄位加入表單中。
uuid: 22c53cd0-d0 bc-4e5 d-89f3-5ac4 f61 a9100
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: a6e2974a-243f-40ab-903c-c7 d3 e8615 bcc
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


# 表單按鈕元件{#form-button-component}

核心元件表單按鈕元件允許加入按鈕在頁面上觸發動作。

## 使用狀況 {#usage}

核心元件表單按鈕元件允許建立按鈕欄位，通常用來觸發表單提交，並與 [表單容器元件搭配使用](form-container.md)。

按鈕屬性可由 [設定對話方塊中的內容編輯器定義](form-button.md)。

## 版本與相容性 {#version-and-compatibility}

目前版本的表格按鈕元件是v2，是從2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](form-button-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/screen_shot_2018-01-12at120021.png)

### HTML {#html}

```
<div class="container responsivegrid aem-GridColumn aem-GridColumn--default--12">
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="cmp-form aem-Grid aem-Grid--12 aem-Grid--default--12">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="button aem-GridColumn aem-GridColumn--default--12">
<button type="BUTTON" class="cmp-form-button" name="loveToast" value="ILoveToast">Click here if you love toast!</button>
</div>

</form>
</div>
```

### JSON {#json}

```
"button":{  
                           "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                           ":type":"core/wcm/sandbox/components/form/button/v2/button",
                           "name":"loveToast",
                           "jcr:title":"Click here if you love toast!",
                           "type":"button",
                           "value":"ILoveToast"
                        }
```

### 技術細節 {#technical-details}

有關表單按鈕元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義按鈕參數。

### 屬性索引標籤 {#properties-tab}

![](assets/screen_shot_2018-01-12at120433.png)

* **類型**

   * **按鈕**
   * **提交**

* **標題** -顯示在按鈕上的文字

   * 如果未預設為按鈕類型，則無預設值

* **名稱** -按鈕的名稱，以表單資料提交
* **值** -按鈕的值，以表單資料提交

## 設計對話方塊 {#design-dialog}

### 樣式標籤 {#styles-tab}

表單按鈕元件支援AEM [樣式系統](authoring.md#component-styling)。