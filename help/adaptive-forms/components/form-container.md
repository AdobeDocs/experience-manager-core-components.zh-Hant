---
title: 自適應Forms核心元件 — 表單容器
description: 將自適應表單添加到網頁。
role: Architect, Developer, Admin, User
exl-id: 8df7f862-4d59-4c3f-88dd-f0c937081f4f
source-git-commit: 64536dc607c6e8da0b424b4a1502fa64ed8abbd0
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%

---

# 來自容器 {#form-container-adaptive-forms-core-component}

Forms公司通過提供有價值的資訊使網站訪問者能夠與網站進行互動，這可以提高用戶的參與度和用戶滿意度。 Adobe Experience Manager(AEM)站點中的自適應表單容器使網站所有者能夠輕鬆地將表單添加到其頁面中。 這通過為訪問者提供簡化的方式，以提供反饋、查詢和完成其他操作，幫助促進網站訪問者與網站所有者或組織之間的溝通

## 使用狀況 {#reasons-to-use-forms-container}

可以將表單添加到網站有以下幾個原因：

* **資料收集**:Forms可用於從網站訪問者收集各種資料，如市場研究、用戶行為分析等。

* **線索生成**:可以使用表單從潛在客戶收集資訊，以生成銷售和營銷工作的銷售線索。

* **電子商務**:Forms可以用於網上購物，讓顧客通過網站下訂單和付款。

* **聯繫人**:聯繫表允許網站訪問者輕鬆聯繫網站所有者或組織。

* **調查和民調**:Forms可以通過調查和調查收集網站訪問者的反饋和意見。

* **事件註冊**:Forms可用於活動註冊，允許網站訪問者註冊參加活動或網路研討會。

* **訂閱**:Forms可以用於網站訂閱，允許訪問者註冊新聞簡訊或其他常規通訊。

* **用戶驗證**:Forms可用於用戶驗證，允許網站訪問者建立帳戶並登錄以訪問獨家內容或功能。

* **提高轉換率**:精心設計的表格可以通過使用戶能夠容易地完成所需的動作來提高轉換率，例如購買產品或註冊服務。


## 版本和相容性 {#version-and-compatibility}

自適應Forms手風琴核心元件於2023年2月發佈，作為用於Cloud Service的核心元件2.0.4的一部分，以及用於Forms或更晚版本的核心元件1.1.12的核心元件6.5.16.0的一部分。 下面是一個表，其中顯示了所有支援的版本AEM、相容性以及指向相應文檔的連結：

| 元件版本 | AEM as a Cloud Service  | AEM6.5.16.0Forms |
|---|---|---|
| v1 | 相容<br>[發行版2.0.4](/help/adaptive-forms/version.md) 之後 | 相容<br>[發行版1.1.12](/help/adaptive-forms/version.md) 晚但小於2.0.0。 |

有關核心元件版本和版本的資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 的子菜單。
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

獲取有關自適應Forms集裝箱核心元件的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container)。 有關開發核心元件的詳細資訊，請查看 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

通過「配置」對話框，您可以輕鬆地為訪問者自定義表單容器體驗。 您還可以輕鬆定義表單容器選項，以獲得無縫的用戶體驗。

### 基本標籤 {#basic-tab}

![基本頁籤](/help/adaptive-forms/assets/formcontainer_basictab.png)

* **預填充服務**  — 此選項允許用戶在呈現自適應表單時選擇用於檢索資料的預填充服務。 瞭解有關 [如何建立和配置預填服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=en#aem-forms-custom-prefill-service)。

* **客戶端庫類別**  — 用戶可以按自適應表單配置自定義JavaScript庫。 建議只保留庫中的可重用函式，這些函式依賴於jquery和underloge.js第三方庫。

### 提交頁籤 {#submission-tab}

![「提交」頁籤](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

用戶可以為Adaptive Form提交配置不同的操作。

* **重定向URL/路徑**  — 此選項允許用戶為每個表單配置頁面，在提交自適應表單後，表單用戶將重定向到該頁面。 按一下這裡瞭解有關 [如何配置重定向頁面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html)。

![顯示消息頁籤](/help/adaptive-forms/assets/formconatiner_showmessage.png)

* **顯示消息**  — 此選項允許用戶添加在自適應表單成功提交時顯示的消息。 預定義文本包含在對話框中，用戶可以修改它。 「顯示消息」對話框支援富格文本格式設定工具，允許用戶對添加的文本進行格式化。

* **提交操作**  — 當用戶按一下自適應表單上的「提交」按鈕時，將觸發「提交操作」。 用戶可以從支援的下拉清單中選擇「提交操作」(Submit Actions)。 瞭解如何 [在「提交」頁籤中配置提交操作](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#supporting-custom-functions-in-validation-expressions-br)。
