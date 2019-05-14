---
title: 表單文字元件
seo-title: 表單文字元件
description: 'null'
seo-description: 核心元件表單文字元件允許輸入表單文字供提交。
uuid: f2418d55-0b59-4c7c-a541-d12 dda4 db4 cf
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 3a970c4b-806b-4a0a-b6 b8-b3 dca4 e9 f136
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


# 表單文字元件{#form-text-component}

核心元件表單文字元件允許輸入表單文字供提交。

## 使用狀況 {#usage}

「表單文字」元件允許提交不同類型的文字，並與 [表單容器元件一起使用](form-container.md)。文字驗證、標籤和說明訊息的類型可由 [設定對話方塊中的內容編輯器定義](#configure-dialog)。

## 版本與相容性 {#version-and-compatibility}

目前版本的表單文字元件是v2，是從2018年月發行的版本2.0.0推出，並在本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |--- |
| v2 | 相容相容性 | 相容相容性 | 相容相容性 |
| [v1](form-text-v1.md) | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

以下是取自 [「我們零售](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)業」的範例。

### 螢幕擷圖 {#screenshot}

![](assets/chlimage_1-22.png)

### HTML {#html}

```
<div class="text aem-GridColumn aem-GridColumn--default--12">
   <div class="cmp-form-text">
      <label for="form-text-2146967">How many pieces of toast would you like?
      </label>
   <input class="cmp-form-text__text" type="number" id="form-text-2146967" name="pieces">
   </div>
</div>
```

### JSON {#json}

```
"text":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "id":"form-text-2146967",
                     "title":"How many pieces of toast would you like?",
                     "name":"pieces",
                     "value":"",
                     "helpMessage":"",
                     "type":"number",
                     "readOnly":false,
                     "required":false,
                     "requiredMessage":"",
                     "constraintMessage":"",
                     "rows":2,
                     "defaultValue":"",
                     ":type":"core/wcm/components/form/text/v2/text"
                  }
```

### 技術細節 {#technical-details}

有關表單文字元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義要輸入的文字類型，以及預設值和標籤。

### 主標籤 {#main-tab}

![](assets/chlimage_1-23.png)

* **限制要**輸入的文字類型，並驗證
   * **文字**
   * **文字區域**
   * **電子郵件**
   * **電話**
   * **日期**
   * **數字**
   * **密碼**
* **文字線條**要顯示在文字區域中的行數(僅在 **「限制」** 設為 **「文字區域**」時顯示)
* **Label**
the Label that will be displayed for the field
* **如果標籤僅供協助工具用途，而且不包含任何其他有關欄位的視覺化資訊，則隱藏標籤不會顯示**「需要」
* **元素名稱**：表單資料所提交欄位的名稱
* **值**預設值，在欄位中預先填入

### 關於標籤 {#about-tab}

![](assets/chlimage_1-24.png)

* **說明訊息** A提示使用者在欄位中輸入的內容
* **將說明訊息顯示為預留位置**，在表單輸入空白且未聚焦時顯示說明訊息

### 限制標籤 {#constraints-tab}

![](assets/chlimage_1-25.png)

* **限制訊息**
   * 如果值沒有驗證選取的類型，提交表單時訊息會顯示為工具提示
   * 不顯示 **文字** 和 **文字區域** 限制類型
* **必要**條件：如果使用者必須填寫值，才能提交表單
* **唯讀**時唯有選取使用者才能修改欄位值

## 設計對話方塊 {#design-dialog}

「表單文字」元件沒有設計對話方塊。