---
title: 表單容器元件(v1)
seo-title: 表單容器元件(v1)
description: 核心元件表單容器元件可讓您建立簡單的提交表單。
seo-description: 核心元件表單容器元件可讓您建立簡單的提交表單。
uuid: 075d83ed-de40-414e-a18f-46b3a857acba
content-type: 引用
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新功能
discoiquuid: 800c064e-2ad5-41f3-9cef-b025a55efd9
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Form Container Component (v1){#form-container-component-v}

核心元件表單容器元件可讓您建立簡單的提交表單。

## 使用狀況 {#usage}

表單容器元件支援簡單的WCM表單，並使用巢狀結構允許其他表單元件，以建立簡單資訊提交表單和功能。

使用設 [定對話方塊](form-container-v1.md#main-pars_title) ，內容編輯器可以定義提交表單觸發的類型、應將提交內容儲存在何處，以及是否應觸發工作流。 範本作者可使用設 [計對話方塊](form-container-v1.md#main-pars_title_1995166862) ，定義允許元件及其映射，類似範本編輯器中標準版面 [容器的設計對話方塊](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)。

## 版本與相容性 {#version-and-compatibility}

本檔案說明Form Container元件的v1，最初是隨AEM 6.3核心元件的1.0.0版一起推出。

下表列出表單容器元件v1的相容性。

| AEM版本 | 表單容器元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明表單容器元件的v1。
>
>如需表單容器元件目前版本的詳細資訊，請參閱表 [單容器元件檔案](form-container.md) 。

## 「設定」對話框 {#settings-dialog}

「設定」對話方塊可讓內容作者定義在提交元件時要執行的動作。

![](assets/chlimage_1.png)

根據選取的「 **動作類型**」，容器中的可用選項將會變更。 可用的操作類型包括：

* [郵件](form-container-v1.md#main-pars_title_966511656)
* [存放區內容](form-container-v1.md#main-pars_title_2065985840)
* [提交訂單](form-container-v1.md#main-pars_title_686874527)
* [更新訂單](form-container-v1.md#main-pars_title_410109286)

不論類型為何，都會有一 [般設定](form-container-v1.md#main-pars_title_375403046) ，適用於每個動作。

### 郵件 {#mail}

提交表單時，郵件動作類型會傳送電子郵件給指定的收件者。

![](assets/chlimage_1-1.png)

* **主旨** -提交表單時傳送的電子郵件主旨
* **寄件者** -在提交表單時傳送的電子郵件寄件者電子郵件地址
* **收件者** -在提交表單時收到電子郵件的收件者地址
   * 點選或按一下「 **新增** 」按鈕以新增其他位址
   * 點選或按一下「刪 **除** 」按鈕以移除電子郵件地址
* **CC** —— 收件者的地址，這些收件者會收到表單提交時傳送的電子郵件的碳副本
   * 點選或按一下「 **新增** 」按鈕以新增其他位址
   * 點選或按一下「刪 **除** 」按鈕以移除電子郵件地址

### 存放區內容 {#store-content}

提交表單時，表單的內容將儲存在指定的儲存庫位置。

![](assets/chlimage_1-2.png)

* **內容路徑** -內容存放庫路徑，已提交內容儲存在此路徑
* **檢視資料** -點選或按一下，將儲存的已提交資料檢視為JSON
* **開始工作流程** -設定在表單提交時，將儲存的內容當做裝載來啟動工作流程

### 提交訂單 {#submit-order}

提交表格後，將會提交訂單。

![](assets/chlimage_1-3.png)

### 更新訂單 {#update-order}

提交表單時，訂單將會更新。

![](assets/chlimage_1-4.png)

### 一般設定 {#general-settings}

無論選取的動作類型為何，都可以定義感謝頁面。

![](assets/chlimage_1-5.png)

在表單提交完成後，會將使用者重新導向至指定的頁面。

* 使用「選取對話方塊」，在AEM中選取資源。
* 如果感謝頁面不在AEM中，請指定絕對URL。 非絕對URL將會相對於AEM進行解譯。
* 留空可在提交後重新顯示表單。

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者為容器定義允許的元件及其對應，類似範本編輯器中標準版面 [容器的設計對話方塊](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)。

## 技術詳細資訊 {#technical-details}

有關表單容器元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。
