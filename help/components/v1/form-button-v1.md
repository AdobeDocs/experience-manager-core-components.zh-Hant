---
title: 表單按鈕元件(v1)
description: 核心元件表單隱藏元件允許在表單中包含隱藏欄位。
index: n
role: 架構師、開發人員、管理員、商業從業人員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---


# 表單按鈕元件(v1){#form-button-component-v}

核心元件表單按鈕元件允許在表單中包含按鈕欄位以觸發操作。

## 使用狀況 {#usage}

核心元件表單按鈕元件允許建立按鈕欄位，通常用於觸發表單的提交，並與[表單容器元件](form-container-v1.md)一起使用。

按鈕屬性可由[configure dialog](#configure-dialog)中的內容編輯器定義。

## 版本和相容性{#version-and-compatibility}

本檔案說明Form Button元件的v1，此元件最初是隨6.3版核心元件的1.0.0版一起AEM推出。

下表列出表單按鈕元件v1的相容性。

| 版AEM本 | 表單按鈕元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明「表單按鈕元件」的v1。
>
>有關當前版本的「表單按鈕元件」的詳細資訊，請參閱[表單按鈕元件](/help/components/forms/form-button.md)文檔。

## 元件輸出示例{#sample-component-output}

以下範例取自[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 螢幕擷圖 {#screenshot}

![](/help/assets/chlimage_1-48.png)

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
>從核心元件匯出JSON需要1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 配置對話框{#configure-dialog}

配置對話框允許內容作者定義按鈕的參數。

![](/help/assets/chlimage_1-49.png)

* **類型**
   * **按鈕**
   * **提交**

* **Title**  —— 按鈕上顯示的文字
   * 如果沒有提供，則預設為按鈕類型

* **名稱** -按鈕的名稱，隨表單資料提交
* **Value**  —— 隨表單資料提交的按鈕值

## 設計對話框{#design-dialog}

「表單按鈕」元件沒有設計對話方塊。

## 技術詳細資訊{#technical-details}

有關表單按鈕元件[的最新技術檔案可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button)上找到。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
