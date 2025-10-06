---
title: 表單容器元件 (v1)
description: 透過「核心元件表單容器元件」，可建立簡易的提交表單。
index: n
role: Architect, Developer, Admin, User
exl-id: 1e34219f-fa82-494e-82e2-1b4d63d37fea
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '609'
ht-degree: 100%

---


# 表單容器元件 (v1) {#form-container-component-v1}

透過「核心元件表單容器元件」，可建立簡易的提交表單。

## 用途 {#usage}

「表單容器元件」支援簡易的 WCM 表單，並使用巢狀結構允許額外的表單元件，藉以建立易於使用的資料提交表單和功能。

使用[設定對話框](#settings-dialog)，內容編輯者可定義表單提交所觸發的動作類型、提交內容的儲存位置，以及是否應觸發工作流程。範本作者可以使用[設計對話框](#design-dialog)定義允許的元件及其對應，類似於[範本編輯器中標準版面容器](https://helpx.adobe.com/tw/experience-manager/6-4/sites/authoring/using/templates.html)的設計對話框。

## 版本和相容性 {#version-and-compatibility}

本文件說明「表單容器元件」v1，最初由 AEM 6.3 搭配的核心元件 1.0.0 版導入。

下表列出「表單容器元件」v1 的相容性。

| AEM 版本 | 表單容器元件 v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文件說明「表單容器元件」v1。
>
>如需「表單容器元件」目前版本的詳細資訊，請參閱[表單容器元件](/help/components/forms/form-container.md)文件。

## 設定對話框 {#settings-dialog}

利用設定對話框，內容作者可以定義提交元件時所採取的動作。

![](/help/assets/chlimage_1.png)

容器內的可用選項會因所選取的&#x200B;**動作類型**&#x200B;而變更。可用的動作類型包括：

* [郵件](#mail)
* [存放區內容](#store-content)
* [提交訂單](#submit-order)
* [更新訂單](#update-order)

不論類型為何，都有適用於每個動作的[一般設定](#general-settings)。

### 郵件 {#mail}

提交表單時，郵件動作類型將傳送電子郵件給指定的收件者。

![](/help/assets/chlimage_1-1.png)

* **主旨** - 提交表單時，將傳送的電子郵件主旨
* **寄件者** - 提交表單時，將傳送的電子郵件的寄件者電子郵件地址
* **收件者** - 提交表單時，將接收電子郵件的收件者地址
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕，以新增其他地址
   * 點選或按一下&#x200B;**刪除**&#x200B;按鈕，以移除電子郵件地址
* **副本** - 提交表單時，將接收所傳送之電子郵件副本的收件者地址
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕，以新增其他地址
   * 點選或按一下&#x200B;**刪除**&#x200B;按鈕，以移除電子郵件地址

### 存放區內容 {#store-content}

提交表單時，表單的內容將儲存在指定的存放庫位置。

![](/help/assets/chlimage_1-2.png)

* **內容路徑** - 提交的內容儲存所在的內容存放庫路徑
* **檢視資料** - 點選或按一下，檢視以 JSON 格式儲存的提交資料
* **啟動工作流程** - 設定在提交表單時，啟動將儲存內容作為承載的工作流程

### 提交訂單 {#submit-order}

提交表單後，將會提交訂單。

![](/help/assets/chlimage_1-3.png)

### 更新訂單 {#update-order}

提交表單後，將會更新訂單。

![](/help/assets/chlimage_1-4.png)

### 一般設定 {#general-settings}

無論選取的動作類型為何，您可以隨時定義感謝頁面。

![](/help/assets/chlimage_1-5.png)

完成提交表單後，系統會將使用者重新導向至指定頁面。

* 使用「選取對話框」以在 AEM 中選取資源。
* 如果感謝頁面不在 AEM 中，請指定絕對 URL。非絕對 URL 將解釋為相對於 AEM。
* 留空以在提交後重新顯示表單。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可為容器定義允許的元件及其對應，類似於[範本編輯器中標準版面容器](https://helpx.adobe.com/tw/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)的設計對話框。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container)有關「表單容器元件」的最新技術文件。

您可以從 GitHub 下載完整的核心元件專案。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。
