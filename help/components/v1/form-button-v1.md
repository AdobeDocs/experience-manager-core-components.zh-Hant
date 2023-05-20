---
title: 窗體按鈕元件(v1)
description: 核心元件表單隱藏元件允許在表單中包含隱藏欄位。
index: n
role: Architect, Developer, Admin, User
exl-id: 2c06a942-7ac5-4847-9d11-7bbcd0ea51bd
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 2%

---

# 窗體按鈕元件(v1) {#form-button-component-v}

核心元件表單按鈕元件允許在表單中包含按鈕欄位以觸發操作。

## 使用狀況 {#usage}

核心元件表單按鈕元件允許建立按鈕欄位，通常用於觸發表單的提交，並與 [形式容器元件](form-container-v1.md)。

按鈕屬性可由中的內容編輯器定義 [配置對話框](#configure-dialog)。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了表單按鈕元件的v1，最初是隨帶有6.3的核心元件1.0.0版一起推出AEM的。

下表列出了表單按鈕元件v1的相容性。

| 版AEM本 | 窗體按鈕元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔介紹「表單按鈕元件」的v1。
>
>有關窗體按鈕元件的當前版本的詳細資訊，請參閱 [窗體按鈕元件](/help/components/forms/form-button.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>從核心元件導出JSON需要1.1.0版核心元件。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 的子菜單。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義按鈕的參數。

![](/help/assets/chlimage_1-49.png)

* **類型**
   * **按鈕**
   * **提交**

* **標題**  — 按鈕上顯示的文本
   * 如果未提供，則預設為按鈕類型

* **名稱**  — 按鈕的名稱，該按鈕與表單資料一起提交
* **值**  — 按鈕的值，該按鈕與表單資料一起提交

## 設計對話框 {#design-dialog}

「表單按鈕」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

有關表單按鈕元件的最新技術文檔 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button)。

整個核心元件項目可從GitHub下載。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。
