---
title: 表單按鈕元件(v1)
description: 核心元件表單隱藏元件允許在表單中包含隱藏欄位。
index: n
role: Architect, Developer, Admin, User
exl-id: 2c06a942-7ac5-4847-9d11-7bbcd0ea51bd
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 2%

---

# 表單按鈕元件(v1) {#form-button-component-v}

核心元件表單按鈕元件可在表單中納入按鈕欄位，以觸發動作。

## 使用狀況 {#usage}

核心元件表單按鈕元件允許建立按鈕欄位，通常用於觸發表單提交，並與[表單容器元件](form-container-v1.md)一起使用。

按鈕屬性可由[configure dialog](#configure-dialog)中的內容編輯器定義。

## 版本與相容性 {#version-and-compatibility}

本檔案說明表單按鈕元件v1，此元件最初於AEM 6.3的核心元件1.0.0版中推出。

下表列出「表單按鈕元件」v1的相容性。

| AEM版本 | 表單按鈕元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明「表單按鈕元件」的v1。
>
>有關當前版本的「表單按鈕元件」的詳細資訊，請參閱[表單按鈕元件](/help/components/forms/form-button.md)文檔。

## 範例元件輸出 {#sample-component-output}

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
>從核心元件匯出JSON需使用1.1.0版的核心元件。 如需詳細資訊，請參閱核心元件v1](/help/versions.md)的[相容性資訊。

## 配置對話框 {#configure-dialog}

設定對話方塊可讓內容作者定義按鈕的參數。

![](/help/assets/chlimage_1-49.png)

* **類型**
   * **按鈕**
   * **提交**

* **標題**  — 按鈕上顯示的文字
   * 如果未提供，則預設為按鈕類型

* **名稱**  — 隨表單資料提交的按鈕名稱
* **值**  — 隨表單資料提交的按鈕值

## 設計對話方塊 {#design-dialog}

「表單按鈕」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

如需表單按鈕元件[的最新技術檔案，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
