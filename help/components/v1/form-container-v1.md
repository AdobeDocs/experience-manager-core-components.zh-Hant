---
title: 窗體容器元件(v1)
description: 核心元件表單容器元件允許建立簡單提交表單。
index: n
role: Architect, Developer, Admin, User
exl-id: 1e34219f-fa82-494e-82e2-1b4d63d37fea
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 2%

---

# 窗體容器元件(v1) {#form-container-component-v1}

核心元件表單容器元件允許建立簡單提交表單。

## 使用狀況 {#usage}

表單容器元件支援簡單的WCM表單，並使用嵌套結構允許附加表單元件，從而實現了簡單資訊提交表單和功能的構建。

使用 [設定對話框](#settings-dialog) 內容編輯器可以定義何種類型的操作表單提交觸發器、應將提交的內容儲存在何處以及是否應觸發工作流。 模板作者可以使用 [設計對話框](#design-dialog) 定義允許元件及其映射，類似於 [模板編輯器中的標準佈局容器](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html)。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了表單容器元件的v1，最初是隨帶有6.3的核心元件1.0.0版一起引入AEM的。

下表列出了表單容器元件v1的相容性。

| 版AEM本 | 窗體容器元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本文檔介紹了表單容器元件的v1。
>
>有關窗體容器元件當前版本的詳細資訊，請參閱 [窗體容器元件](/help/components/forms/form-container.md) 的子菜單。

## 「設定」對話框 {#settings-dialog}

設定對話框允許內容作者定義在提交元件時採取的操作。

![](/help/assets/chlimage_1.png)

取決於所選 **操作類型**，容器中的可用選項將更改。 可用的操作類型有：

* [郵件](#mail)
* [存放區內容](#store-content)
* [提交訂單](#submit-order)
* [更新訂單](#update-order)

不管類型如何， [常規設定](#general-settings) 適用於每個操作。

### 郵件 {#mail}

提交表單後，郵件操作類型將向指定的收件人發送電子郵件。

![](/help/assets/chlimage_1-1.png)

* **主題**  — 將在表單提交時發送的電子郵件主題
* **從**  — 表單提交時將發送的電子郵件的發件人電子郵件地址
* **至**  — 提交表單時將接收電子郵件的收件人的地址
   * 點擊或按一下 **添加** 按鈕添加附加地址
   * 點擊或按一下 **刪除** 按鈕以刪除電子郵件地址
* **抄送**  — 在提交表單時收到電子郵件的碳副本的收件人地址
   * 點擊或按一下 **添加** 按鈕添加附加地址
   * 點擊或按一下 **刪除** 按鈕以刪除電子郵件地址

### 存放區內容 {#store-content}

提交表單後，表單的內容將儲存在指定的儲存庫位置。

![](/help/assets/chlimage_1-2.png)

* **內容路徑**  — 儲存已提交內容的內容儲存庫路徑
* **查看資料**  — 點擊或按一下以將儲存的已提交資料視為JSON
* **啟動工作流**  — 配置以在提交表單時將儲存的內容作為負載啟動工作流

### 提交訂單 {#submit-order}

提交表格後，將提交訂單。

![](/help/assets/chlimage_1-3.png)

### 更新訂單 {#update-order}

提交表單後，訂單將更新。

![](/help/assets/chlimage_1-4.png)

### 一般設定 {#general-settings}

無論選擇何種操作類型，都可以始終定義「感謝」頁。

![](/help/assets/chlimage_1-5.png)

在完成表單提交後，用戶將被重定向到指定的頁面。

* 使用「選擇」對話框在中選擇資AEM源。
* 如果感謝頁不在AEM中，請指定絕對URL。 非絕對URL將相對於進行解AEM釋。
* 留空以在提交後重新顯示表單。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者為容器定義允許的元件及其映射，類似於 [模板編輯器中的標準佈局容器](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)。

## 技術詳細資訊 {#technical-details}

有關表單容器元件的最新技術文檔 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container)。

整個核心元件項目可從GitHub下載。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。
