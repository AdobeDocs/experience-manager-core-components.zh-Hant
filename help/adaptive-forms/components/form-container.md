---
title: 適用性Forms核心元件 — 表單容器
description: 新增最適化表單至網頁。
role: Architect, Developer, Admin, User
source-git-commit: 7f680eac1da61b55f9d90db6c0842421d03ac1dc
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 1%

---


# 來自容器 {#form-container-adaptive-forms-core-component}

Forms可讓網站訪客透過提供有價值的資訊與網站互動，進而提高參與度和使用者滿意度。 Adobe Experience Manager(AEM)Sites中的適用性表單容器可讓網站擁有者輕鬆將表單新增至其頁面。 這可協助網站訪客與網站擁有者或組織之間的通訊，提供簡化的方式讓訪客提供意見反應、查詢及完成其他動作

## 使用狀況 {#reasons-to-use-forms-container}

表單可新增至網站的原因有幾個：

* **資料收集**:Forms可用於收集來自網站訪客的資料，以用於各種用途，例如市場研究、使用者行為分析等。

* **銷售機會開發**:表單可用來收集潛在客戶的資訊，例如姓名和電子郵件地址，以產生銷售機會，以利行銷。

* **電子商務**:Forms可用於線上購物，讓客戶可以透過網站下訂單和付款。

* **連絡人**:聯絡表格可讓網站訪客輕鬆與網站擁有者或組織聯絡。

* **調查和投票**:Forms可透過調查和投票，收集網站訪客的意見和意見。

* **事件註冊**:Forms可用於活動註冊，讓網站訪客可註冊參加活動或網路研討會。

* **訂閱**:Forms可用於網站訂閱，讓訪客可註冊電子報或其他一般通訊。

* **使用者驗證**:Forms可用於使用者驗證，讓網站訪客建立帳戶並登入以存取專屬內容或功能。

* **提高轉換率**:經過妥善設計的表單可讓使用者輕鬆完成所需的動作（例如購買產品或註冊服務），進而提高轉換率。


## 版本與相容性 {#version-and-compatibility}

適用性Forms容器核心元件已於2023年2月發行，其為核心元件2.0.4的一部分。下表顯示所有支援的版本、AEM相容性，以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容於<br>[版本2.0.4](/help/versions.md) 和 | 相容 | 相容 |

如需核心元件版本和版本的相關資訊，請參閱 [核心元件版本](/help/versions.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

取得適用性Forms容器核心元件的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 配置對話框 {#configure-dialog}

您可以透過「設定」對話方塊，輕鬆自訂訪客的表單容器體驗。 您也可以輕鬆定義表單容器選項，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本標籤](/help/adaptive-forms/assets/formcontainer_basictab.png)

* **預填服務**  — 此選項可讓使用者在呈現最適化表單時，選擇用於擷取資料的預填服務。 深入了解 [如何建立和設定預填服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=en#aem-forms-custom-prefill-service).

* **客戶端庫類別**  — 使用者可以根據適用性表單設定自訂JavaScript程式庫。 建議只保留程式庫中可重複使用的函式，這些函式依存於jquery和underscore.js協力廠商程式庫。

### 提交標籤 {#submission-tab}

![提交標籤](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

使用者可針對適用性表單提交設定不同的動作。
* **重新導向URL/路徑**  — 此選項可讓使用者為每個表單設定一個頁面，在提交最適化表單後，系統會將使用者重新導向至該頁面。 按一下這裡以取得 [如何配置重新導向頁面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html).

![顯示消息頁簽](/help/adaptive-forms/assets/formconatiner_showmessage.png)

* **顯示消息**  — 此選項可讓使用者新增在成功提交適用性表單時顯示的訊息。 預定義文本包含在對話框中，用戶可以修改它。 「顯示訊息」對話方塊支援RTF格式工具，讓使用者能將新增的文字格式化。

* **提交動作**  — 使用者按一下適用性表單上的「提交」按鈕時，會觸發「提交動作」。 使用者可從現成支援的下拉式清單中選取「提交動作」 。 了解如何 [在「提交」標籤中設定提交動作](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#supporting-custom-functions-in-validation-expressions-br).

## 設計對話方塊 {#design-dialog}



