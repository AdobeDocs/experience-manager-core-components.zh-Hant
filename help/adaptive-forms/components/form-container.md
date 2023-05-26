---
title: 最適化Forms核心元件 — 表單容器
description: 新增最適化表單至網頁。
role: Architect, Developer, Admin, User
exl-id: 8df7f862-4d59-4c3f-88dd-f0c937081f4f
source-git-commit: 64536dc607c6e8da0b424b4a1502fa64ed8abbd0
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%

---

# 來自容器 {#form-container-adaptive-forms-core-component}

Forms可提供寶貴資訊，讓網站訪客與網站互動，進而提高參與度和使用者滿意度。 Adobe Experience Manager (AEM) Sites中的調適型表單容器可讓網站擁有者輕鬆將表單新增至其頁面。 這有助於促進網站訪客與網站擁有者或組織之間的溝通，方法是為訪客提供簡化的方式來提供意見回饋、提出查詢並完成其他動作

## 使用狀況 {#reasons-to-use-forms-container}

可以將表單新增至網站的原因有幾個：

* **資料彙集**：Forms可用來從網站訪客收集資料，以進行各種用途，例如市場研究、使用者行為分析等。

* **銷售機會開發**：表單可用於從潛在客戶收集資訊（例如姓名和電子郵件地址），以產生銷售和行銷工作的潛在客戶。

* **電子商務**：Forms可用於線上購物，讓客戶透過網站下訂單及付款。

* **連絡人**：聯絡表單可讓網站訪客輕鬆聯絡網站擁有者或組織。

* **調查和投票**：Forms可用來透過調查和投票，從網站訪客收集意見反應和意見。

* **活動註冊**：Forms可用於事件註冊，讓網站訪客註冊活動或網路研討會。

* **訂閱**：Forms可用於網站訂閱，讓訪客註冊電子報或其他定期通訊。

* **使用者驗證**：Forms可用於使用者驗證，讓網站訪客建立帳戶並登入以存取專屬內容或功能。

* **提高轉換率**：設計良好的表單可讓使用者輕鬆完成所需的動作，例如購買產品或註冊服務，進而提高轉換率。


## 版本和相容性 {#version-and-compatibility}

Adaptive Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 和更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和更新版本，但低於2.0.0。 |

如需核心元件版本和發行版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在以下位置的技術檔案中取得最適化Forms容器核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以使用「設定」對話方塊輕鬆自訂訪客的表單容器體驗。 您也可以輕鬆定義表單容器選項，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/formcontainer_basictab.png)

* **預填服務**  — 此選項可讓使用者選擇預填服務，以便在轉譯最適化表單時擷取資料。 進一步瞭解 [如何建立和設定預填服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=en#aem-forms-custom-prefill-service).

* **使用者端資料庫類別**  — 使用者可以根據每個最適化表單設定自訂JavaScript程式庫。 建議僅將可重複使用的函式保留在程式庫中，因為它們相依於jquery和underscore.js協力廠商程式庫。

### 提交索引標籤 {#submission-tab}

![提交索引標籤](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

使用者可以為最適化表單提交設定不同的動作。

* **重新導向URL/路徑**  — 此選項可讓使用者為每個表單設定頁面，表單使用者在提交調適型表單後會重新導向至該頁面。 按一下這裡以取得更多關於 [如何設定重新導向頁面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html).

![顯示訊息標籤](/help/adaptive-forms/assets/formconatiner_showmessage.png)

* **顯示訊息**  — 此選項可讓使用者新增訊息，該訊息會在成功提交最適化表單時顯示。 預先定義的文字會包含在對話方塊中，且使用者可加以修改。 「顯示訊息」對話方塊支援RTF格式設定工具，可讓使用者設定新增文字的格式。

* **提交動作**  — 當使用者按一下最適化表單上的提交按鈕時，會觸發提交動作。 使用者可從下拉式清單中選取立即可用的支援提交動作。 瞭解如何 [在「提交」標籤中設定「提交」動作](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#supporting-custom-functions-in-validation-expressions-br).
