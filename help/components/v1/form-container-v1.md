---
title: 表單容器元件(v1)
description: 核心元件表單容器元件可讓您建立簡單的提交表單。
index: n
role: 架構師、開發人員、管理員、商業從業人員
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 2%

---


# 表單容器元件(v1){#form-container-component-v1}

核心元件表單容器元件可讓您建立簡單的提交表單。

## 使用狀況 {#usage}

表單容器元件支援簡單的WCM表單，並使用巢狀結構允許其他表單元件，以建立簡單資訊提交表單和功能。

使用[設定對話方塊](#settings-dialog)，內容編輯器可以定義提交表單觸發的動作類型、提交內容應儲存於何處，以及是否應觸發工作流程。 範本作者可使用[設計對話框](#design-dialog)來定義允許元件及其映射，類似於範本編輯器](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html)中[標準版面配置容器的設計對話框。

## 版本和相容性{#version-and-compatibility}

本檔案說明Form Container Component的v1，最初是隨6.3版核心元件1.0.0一起推出AEM的。

下表列出表單容器元件v1的相容性。

| 版AEM本 | 表單容器元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明表單容器元件的v1。
>
>如需表單容器元件目前版本的詳細資訊，請參閱[表單容器元件](/help/components/forms/form-container.md)檔案。

## 設定對話框{#settings-dialog}

「設定」對話方塊可讓內容作者定義在提交元件時要執行的動作。

![](/help/assets/chlimage_1.png)

視選取的&#x200B;**動作類型**&#x200B;而定，容器中的可用選項將會變更。 可用的操作類型包括：

* [郵件](#mail)
* [存放區內容](#store-content)
* [提交訂單](#submit-order)
* [更新訂單](#update-order)

無論類型如何，都有[一般設定](#general-settings)適用於每個動作。

### 郵件 {#mail}

提交表單時，郵件動作類型會傳送電子郵件給指定的收件者。

![](/help/assets/chlimage_1-1.png)

* **主旨** -提交表單時將傳送的電子郵件主旨
* **寄件者** -在提交表單時傳送的電子郵件寄件者電子郵件地址
* **收件人** -提交表單時收到電子郵件的收件人地址
   * 點選或按一下「新增&#x200B;****」按鈕以新增其他位址
   * 點選或按一下&#x200B;**Delete**&#x200B;按鈕以移除電子郵件地址
* **CC**  —— 收到表單提交時傳送之電子郵件碳副本的收件人地址
   * 點選或按一下「新增&#x200B;****」按鈕以新增其他位址
   * 點選或按一下&#x200B;**Delete**&#x200B;按鈕以移除電子郵件地址

### 存放區內容 {#store-content}

提交表單時，表單的內容將儲存在指定的儲存庫位置。

![](/help/assets/chlimage_1-2.png)

* **內容路徑** -內容儲存庫路徑，其中已提交內容儲存
* **檢視資料** -點選或按一下，將儲存的已提交資料檢視為JSON
* **開始工作流程** -設定在表單提交時，將儲存的內容當做裝載來啟動工作流程

### 提交訂單 {#submit-order}

提交表格後，將會提交訂單。

![](/help/assets/chlimage_1-3.png)

### 更新訂單 {#update-order}

提交表單時，訂單將會更新。

![](/help/assets/chlimage_1-4.png)

### 一般設定 {#general-settings}

無論選取的動作類型為何，都可以定義感謝頁面。

![](/help/assets/chlimage_1-5.png)

在表單提交完成後，會將使用者重新導向至指定的頁面。

* 使用「選擇」對話框在中選擇資源AEM。
* 如果感謝頁面未在AEM中，請指定絕對URL。 非絕對URL會相對於進行解AEM讀。
* 留空可在提交後重新顯示表單。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者為容器定義允許的元件及其對應，類似範本編輯器](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)中[標準版面容器的設計對話方塊。

## 技術詳細資訊{#technical-details}

有關表單容器元件[的最新技術檔案可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container)上找到。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
