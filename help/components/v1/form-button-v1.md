---
title: 表單按鈕元件 (v1)
description: 核心元件表單隱藏元件允許在表單中包含隱藏欄位。
index: n
role: Architect, Developer, Admin, User
exl-id: 2c06a942-7ac5-4847-9d11-7bbcd0ea51bd
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '323'
ht-degree: 100%

---


# 表單按鈕元件 (v1) {#form-button-component-v}

利用核心元件表單按鈕元件，您可在表單中包含按鈕欄位以觸發動作。

## 用途 {#usage}

核心元件表單按鈕元件允許建立按鈕欄位，通常會觸發提交表單，其設計用於與[表單容器元件](form-container-v1.md)搭配使用。

按鈕屬性可由內容編輯者在[設定對話框](#configure-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

本文件說明表單按鈕元件 v1，最初由 AEM 6.3 搭配的核心元件 1.0.0 版導入。

下表列出表單按鈕元件 v1 的相容性。

| AEM 版本 | 表單按鈕元件 v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文件說明表單按鈕元件 v1。
>
>如需表單按鈕元件目前版本的詳細資訊，請參閱[表單按鈕元件](/help/components/forms/form-button.md)文件。

## 範例元件輸出 {#sample-component-output}

以下是從 [We.Retail](https://helpx.adobe.com/tw/experience-manager/6-4/sites/developing/using/we-retail.html) 中取得的範例。

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
>從核心元件匯出 JSON 需要核心元件 1.1.0 版。如需詳細資訊，請參閱[核心元件 v1 的相容性資訊](/help/versions.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義按鈕的參數。

![](/help/assets/chlimage_1-49.png)

* **類型**
   * **按鈕**
   * **提交**

* **標題** - 按鈕上顯示的文字
   * 若未提供，則預設為按鈕類型

* **名稱** - 與表單資料共同提交的按鈕名稱
* **值** - 與表單資料共同提交的按鈕值

## 設計對話框 {#design-dialog}

「表單按鈕」元件沒有設計對話框。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button)有關表單按鈕元件的最新技術文件。

您可以從 GitHub 下載完整的核心元件專案。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。
