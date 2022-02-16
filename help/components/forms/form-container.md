---
title: 窗體容器元件
description: 核心元件表單容器元件允許建立簡單提交表單。
role: Architect, Developer, Admin, User
exl-id: 552f9dd5-6a3a-42d9-9969-e62a1f36e811
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 1%

---

# 窗體容器元件 {#form-container-component}

核心元件表單容器元件允許建立簡單提交表單。

## 使用狀況 {#usage}

表單容器元件支援簡單的WCM表單，並使用嵌套結構允許附加表單元件，從而實現簡單資訊提交表單和功能的構建。

使用 [配置對話框](#configure-dialog) 內容編輯器可以定義表單提交觸發的操作、應處理提交的URl以及是否應觸發工作流。 模板作者可以使用 [設計對話框](#design-dialog) 定義允許的元件及其映射，類似於 [模板編輯器中的標準佈局容器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)。

>[!NOTE]
>
>核心元件表單容器元件僅支援使用核心元件表單元件（按鈕、文本、隱藏等）。 使用 [基礎元件](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html) 不支援核心元件內的表單容器（反之亦然）。

## 版本和相容性 {#version-and-compatibility}

表單容器元件的當前版本為v2，該版本於2018年1月隨核心元件2.0.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |
| [v1](/help/components/v1/form-container-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗表單容器元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_form_container)。

## 技術詳細資訊 {#technical-details}

有關表單容器元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_container_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義在提交元件時採取的操作。

取決於所選 **操作類型**，容器中的可用選項將更改。 可用的操作類型有：

* [帖子表單資料](#post-data)
* [郵件](#mail)
* [存放區內容](#store-content)

不管類型如何， [常規設定](#general-settings) 適用於每個操作。

### 帖子表單資料 {#post-data}

提交表單時，過帳表單資料操作類型會將提交的資料作為JSON傳遞給第三方以進行處理。

![在表單容器元件的編輯對話框中發佈表單資料選項](/help/assets/form-container-edit-post.png)

* **端點**  — 將處理資料的完全限定的HTTPS服務
* **錯誤消息**  — 提交失敗時顯示的消息

>[!TIP]
>系統管理員可以調整其他超時選項以處理轉發表單資料的處理。 [有關詳細資訊，請參閱GitHub上的技術文檔。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/actions/rpc)

### 郵件 {#mail}

提交表單後，郵件操作類型將向指定的收件人發送電子郵件。

![表單容器元件的編輯對話框中的郵件選項](/help/assets/form-container-edit-mail.png)

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

![在窗體容器的編輯對話框中儲存內容選項](/help/assets/form-container-edit-store.png)

* **內容路徑**  — 儲存已提交內容的內容儲存庫路徑
* **查看資料**  — 點擊或按一下以將儲存的已提交資料視為JSON
* **啟動工作流**  — 配置以在提交表單時將儲存的內容作為負載啟動工作流

>[!NOTE]
>
>為了簡化用戶資料的管理並強制區分關注點，通常不建議在儲存庫中儲存用戶生成的內容。
>
>而使用 [帖子表單資料](#post-data) 將用戶內容傳遞給專用服務提供商的操作類型。

### 一般設定 {#general-settings}

無論選擇何種操作類型，都可以始終定義「感謝」頁。

![窗體容器元件編輯對話框中的常規選項](/help/assets/form-container-edit-general.png)

* **謝謝頁**  — 表單提交完成後，用戶將被重定向到指定的頁面。
   * 使用「選擇」對話框在中選擇資AEM源。
   * 如果感謝頁不在AEM中，請指定絕對URL。 非絕對URL將相對於進行解AEM釋。
   * 留空以在提交後重新顯示表單。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者為容器定義允許的元件及其映射，類似於 [模板編輯器中的標準佈局容器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)。

### 樣式頁籤 {#styles-tab}

表單容器元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
