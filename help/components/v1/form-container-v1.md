---
title: 表單容器元件(v1)
description: 利用核心元件表單容器元件，可建立簡易提交表單。
index: n
role: Architect, Developer, Admin, User
exl-id: 1e34219f-fa82-494e-82e2-1b4d63d37fea
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---

# 表單容器元件(v1) {#form-container-component-v1}

利用核心元件表單容器元件，可建立簡易提交表單。

## 使用情況 {#usage}

「表單容器元件」可支援簡單的WCM表單，並使用巢狀結構來允許其他表單元件，藉以建置簡單的資訊提交表單和功能。

使用[設定對話方塊](#settings-dialog)，內容編輯者可以定義表單提交會觸發的動作型別、提交內容的儲存位置，以及是否應觸發工作流程。 範本作者可使用[設計對話方塊](#design-dialog)定義允許元件及其對應，類似於範本編輯器](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html)中[標準配置容器的設計對話方塊。

## 版本和相容性 {#version-and-compatibility}

本檔案說明表單容器元件v1，其最初隨附於AEM 6.3的核心元件1.0.0版引入。

下表列出表單容器元件v1的相容性。

| AEM 版本 | 表單容器元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明表單容器元件v1。
>
>如需目前版本的表單容器元件的詳細資訊，請參閱[表單容器元件](/help/components/forms/form-container.md)檔案。

## 設定對話方塊 {#settings-dialog}

設定對話方塊可讓內容作者定義在提交元件時所採取的動作。

![](/help/assets/chlimage_1.png)

根據選取的&#x200B;**動作型別**，容器內的可用選項將會變更。 可用的動作型別為：

* [郵件](#mail)
* [存放區內容](#store-content)
* [提交訂單](#submit-order)
* [更新訂單](#update-order)

無論型別為何，都有[一般設定](#general-settings)適用於每個動作。

### 郵件 {#mail}

提交表單時，郵件動作型別會傳送電子郵件給指定的收件者。

![](/help/assets/chlimage_1-1.png)

* **主旨** — 在提交表單時將傳送的電子郵件主旨
* **寄件者** — 在提交表單時將傳送之電子郵件的寄件者電子郵件地址
* **至** — 在提交表單時將收到電子郵件的收件者地址
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增其他地址
   * 點選或按一下&#x200B;**刪除**&#x200B;按鈕以移除電子郵件地址
* **副本** — 將接收在提交表單時傳送之電子郵件副本的收件者地址
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增其他地址
   * 點選或按一下&#x200B;**刪除**&#x200B;按鈕以移除電子郵件地址

### 存放區內容 {#store-content}

提交表單時，表單內容會儲存在指定的存放庫位置。

![](/help/assets/chlimage_1-2.png)

* **內容路徑** — 儲存所提交內容的內容存放庫路徑
* **檢視資料** — 點選或按一下以檢視以JSON格式儲存的提交資料
* **啟動工作流程** — 設定為在提交表單時啟動將儲存的內容作為承載的工作流程

### 提交訂單 {#submit-order}

在提交表單時，將會提交訂單。

![](/help/assets/chlimage_1-3.png)

### 更新訂單 {#update-order}

在提交表單時，將會更新訂單。

![](/help/assets/chlimage_1-4.png)

### 一般設定 {#general-settings}

無論選取的動作型別為何，您一律可以定義感謝頁面。

![](/help/assets/chlimage_1-5.png)

提交完表單後，系統會將使用者重新導向至指定的頁面。

* 使用「選取」對話方塊來選取AEM中的資源。
* 如果感謝頁面不在AEM中，請指定絕對URL。 非絕對URL將會解譯為相對於AEM。
* 留空可在提交後重新顯示表單。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者為容器定義允許的元件及其對應，類似於範本編輯器](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)中[標準配置容器的設計對話方塊。

## 技術細節 {#technical-details}

在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container)上可找到有關表單容器元件[的最新技術檔案。

您可以從GitHub下載整個核心元件專案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。
