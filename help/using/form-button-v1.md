---
title: 表單按鈕元件(v1)
seo-title: 表單按鈕元件(v1)
description: 'null'
seo-description: 核心元件表單隱藏元件可讓您將隱藏欄位加入表單中。
uuid: 0525e70f-294f-4d35-bc96-fc6 e4 ec225 e9
content-type: 引用
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: ea06acc0-38e2-4252-ac29-07332835b7 c4
disttype: dist5
gnavtheme: 淺色
groupsectionnavitems: 否
hidemerchandisingbar: 繼承
hidepromocomponent: 繼承
modalsize: 426x240
index: n
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 表單按鈕元件(v1){#form-button-component-v}

核心元件表單按鈕元件可讓您加入表單中的按鈕欄位，以觸發動作。

## 使用狀況 {#usage}

核心元件表單按鈕元件允許建立按鈕欄位，通常用來觸發表單提交，並與 [表單容器元件搭配使用](form-container.md)。

按鈕屬性可由 [設定對話方塊中的內容編輯器定義](form-button-v1.md#main-pars_title)。

## 版本與相容性 {#version-and-compatibility}

本文件說明Form Button元件的v1，原始版本為AEM6.3的1.0.0版。

下表列出表格按鈕元件的v相容性。

| AEM版本 | 表單按鈕元件v1 |
|--- |--- |
| 6.3 | 相容相容性 |
| 6.4 | 相容相容性 |

>[!CAUTION]
>
>本文件說明表格按鈕元件的v1。
>
>如需目前版本按鈕元件的詳細資訊，請參閱 [表單按鈕元件](form-button.md) 文件。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/chlimage_1-48.png)

### HTML {#html}

```
<div class="cmp cmp-button aem-GridColumn aem-GridColumn--default--12">
    <div class="cmp cmp-button">
        <button type="BUTTON" class="btn btn-action btn-primary" name="loveToast" value="ILoveToast">
            Click here if you love toast!
        </button>
    </div>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "button": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/button",
                  "name": "loveToast",
                  "jcr:title": "Click here if you love toast!",
                  "type": "submit",
                  "value": "ILoveToast"
                }
              },
              ":itemsOrder": [
                "button"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>從核心元件匯出JSON需要1.1.0版核心元件。如需詳細資訊，請參閱核心元件v [](versions.md#main-pars_title_236368006) 的相容性資訊。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義按鈕參數。

![](assets/chlimage_1-49.png)

* **類型**
   * **按鈕**
   * **提交**

* **標題** -顯示在按鈕上的文字
   * 如果未預設為按鈕類型，則無預設值

* **名稱** -按鈕的名稱，以表單資料提交
* **值** -按鈕的值，以表單資料提交

## 設計對話方塊 {#design-dialog}

表格按鈕元件沒有設計對話方塊。

## 技術細節 {#technical-details}

有關表單按鈕元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button)。

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。
