---
title: 表單按鈕元件(v1)
description: 利用核心元件表單隱藏元件，可在表單中包含隱藏欄位。
index: n
role: Architect, Developer, Admin, User
exl-id: 2c06a942-7ac5-4847-9d11-7bbcd0ea51bd
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 2%

---

# 表單按鈕元件(v1) {#form-button-component-v}

利用核心元件表單按鈕元件，可在表單中包含按鈕欄位來觸發動作。

## 使用狀況 {#usage}

核心元件表單按鈕元件可建立按鈕欄位，通常用於觸發表單提交，並且旨在與搭配使用 [表單容器元件](form-container-v1.md).

按鈕屬性可由內容編輯器在 [設定對話方塊](#configure-dialog).

## 版本和相容性 {#version-and-compatibility}

本檔案說明表單按鈕元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出表單按鈕元件v1的相容性。

| AEM版本 | 表單按鈕元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明表單按鈕元件v1。
>
>如需目前版本的表單按鈕元件的詳細資訊，請參閱 [表單按鈕元件](/help/components/forms/form-button.md) 檔案。

## 範例元件輸出 {#sample-component-output}

以下是取自下列專案的範例： [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>從核心元件匯出JSON需要核心元件1.1.0版。 請參閱 [核心元件v1的相容性資訊](/help/versions.md) 以取得詳細資訊。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義按鈕的引數。

![](/help/assets/chlimage_1-49.png)

* **類型**
   * **按鈕**
   * **提交**

* **標題**  — 按鈕上顯示的文字
   * 如果未提供，則預設為按鈕型別

* **名稱**  — 與表單資料共同提交的按鈕名稱
* **值**  — 與表單資料共同提交的按鈕值

## 設計對話方塊 {#design-dialog}

表單按鈕元件沒有設計對話方塊。

## 技術細節 {#technical-details}

有關表單按鈕元件的最新技術檔案 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button).

您可以從GitHub下載整個核心元件專案。

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).
