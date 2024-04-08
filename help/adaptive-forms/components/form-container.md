---
title: 最適化Forms核心元件 — 表單容器
description: 將最適化表單新增至網頁。
role: Architect, Developer, Admin, User
exl-id: 03c4cf7c-51d6-4850-a566-1c0514d52dab
source-git-commit: e4274194026c3370b52be17171776847374a86b5
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 2%

---

# 表單容器 {#form-container-adaptive-forms-core-component}

Forms可提供寶貴資訊，讓網站訪客與網站互動，進而提高參與度和使用者滿意度。 Adobe Experience Manager (AEM) Sites中的最適化表單容器可讓網站擁有者輕鬆將表單新增至其頁面。 這有助於促進網站訪客與網站擁有者或組織之間的溝通，透過提供簡化的方式讓訪客提供意見回饋、提出查詢並完成其他動作

## 使用情況 {#reasons-to-use-forms-container}

可以將表單新增至網站的原因有幾個：
- **資料彙集**：Forms可用來從網站訪客收集資料，以進行各種用途，例如市場研究、使用者行為分析等。

- **銷售機會開發**：表單可用來從潛在客戶收集資訊，例如姓名和電子郵件地址，以針對銷售和行銷工作產生潛在客戶。

- **電子商務**：Forms可用於線上購物，讓客戶透過網站下訂單及付款。

- **連絡人**：聯絡表單可讓網站訪客輕鬆聯絡網站擁有者或組織。

- **調查和投票**：Forms可用來透過調查和投票，從網站訪客收集意見反應和意見。

- **活動註冊**：Forms可用於事件註冊，讓網站訪客註冊活動或網路研討會。

- **訂閱**：Forms可用於網站訂閱，讓訪客註冊電子報或其他定期通訊。

- **使用者驗證**：Forms可用於使用者驗證，可讓網站訪客建立帳戶並登入以存取專屬內容或功能。

- **提高轉換率**：設計良好的表單可讓使用者輕鬆完成所需的動作，例如購買產品或註冊服務，進而提高轉換率。


## 版本和相容性 {#version-and-compatibility}

最適化Forms摺疊式功能表核心元件於2023年2月發行，屬於AEM 6.5.16.0 Forms或更新版本適用的Cloud Service核心元件2.0.4和核心元件1.1.12的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  | AEM 6.5.16.0 Forms或更新版本 |
|---|---|---|
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 及更新版本 | 相容於<br>[第1.1.12發行版本](/help/adaptive-forms/version.md) 和較新版本，但小於2.0.0。 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術細節 {#technical-details}

在的技術檔案中取得最適化Forms容器核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的表單容器體驗。 您也可以輕鬆定義表單容器選項，以提供順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/formcontainer_basictab.png)

- **標題**  — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。

- **預填服務**  — 此選項可讓使用者選擇預填服務，以便在最適化表單轉譯時擷取資料。 進一步瞭解 [如何建立及設定預填服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=en#aem-forms-custom-prefill-service).

- **使用者端資料庫類別**  — 使用者可以根據每個最適化表單設定自訂JavaScript程式庫。 建議僅將可重複使用的函式保留在程式庫中，這些函式需依賴jquery和underscore.js協力廠商程式庫。
有時，如果有 **複雜驗證規則**，則確切的驗證指令碼會位於自訂函式中，且使用者會從欄位驗證運算式呼叫這些自訂函式。 AEM若要在執行伺服器端驗證時讓此自訂函式館為已知且可用，表單使用者可在 **[!UICONTROL 基本]** 最適化表單容器屬性的索引標籤，如下所示。

使用者可以根據每個最適化表單設定customJavaScript程式庫。 程式庫中只會保留可重複使用的函數，這些函數與 jquery 和 underscore.js 第三方程式庫有相依性。

### 資料模型標籤 {#data-model-tab}

![提交索引標籤](/help/adaptive-forms/assets/formcontainer_fdmtab.png)

您可以使用表單資料模型將表單連線至資料來源，以根據使用者動作傳送及接收資料。 您也可以將表單連線至JSON結構描述，以預先定義的格式接收提交的資料。 根據需求，將您的表單連結至JSON結構描述或表單資料模型：
- 建立JSON結構描述並上傳至您的環境
- 建立表單資料模型

### 提交索引標籤 {#submission-tab}

使用者可以為最適化表單提交設定不同的動作。

- **重新導向URL/路徑**  — 此選項可讓使用者為每個表單設定頁面，表單使用者在提交調適型表單後會重新導向至該頁面。 按一下這裡以取得更多關於 [如何設定重新導向頁面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html).

![提交索引標籤](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

- **顯示訊息**  — 此選項可讓使用者新增訊息，該訊息會在成功提交最適化表單時顯示。 預先定義的文字會包含在對話方塊中，且使用者可加以修改。 「顯示訊息」對話方塊支援RTF格式工具，可讓使用者格式化新增的文字。

![顯示訊息標籤](/help/adaptive-forms/assets/formconatiner_showmessage.png)

- **提交動作**  — 當使用者按一下最適化表單上的提交按鈕時，就會觸發提交動作。 使用者可從下拉式清單中選取立即可用的支援提交動作。 瞭解如何 [在提交索引標籤中設定提交動作](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#supporting-custom-functions-in-validation-expressions-br).

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理表單容器元件的CSS樣式。

### 允許的元件標籤 {#allowed-components-tab}

![設計對話方塊允許的元件索引標籤](/help/adaptive-forms/assets/formcontainer-allowedcomponents.png)

此 **允許的元件** 索引標籤可讓範本編輯器設定元件，這些元件可在最適化Forms編輯器中作為面板的專案新增。

### 預設元件標籤 {#default-components-tab}

![「設計」對話方塊預設元件索引標籤](/help/adaptive-forms/assets/formcontainer-defaultcomponents.png)

此 **預設元件** 索引標籤可讓範本編輯器指定在調適型Forms編輯器中，預設顯示為表單容器元件專案的元件。

### 回應式設定標籤 {#responsive-tab}

![設計對話方塊回應式設定索引標籤](/help/adaptive-forms/assets/formcontainer-responsivestyle.png)

此 **回應式設定** 索引標籤可讓範本編輯器在調適型Forms編輯器中指定表單容器元件內格線的欄數。

### 樣式索引標籤 {#styles-tab}

最適化Forms檔案附件核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/formcontainer-styletab.png)

- **預設CSS類別**：您可以為最適化Forms表單容器核心元件提供預設CSS類別。

- **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性標籤

![自訂屬性對話方塊](/help/adaptive-forms/assets/formcontainer-custompropertiestab.png)

自訂屬性可讓您使用表單範本，將自訂屬性（索引鍵/值組）與最適化表單核心元件建立關聯。 自訂屬性會反映在元件Headless轉譯的properties區段中。 它可讓您建立根據自訂屬性值調整的動態表單行為。 例如，開發人員可以為行動、桌上型電腦或Web平台設計各種無頭Forms元件的轉譯，大幅提升各種裝置的使用者體驗。

- **群組名稱**：您可以提供名稱來識別自訂屬性群組。 您可以新增、刪除或重新排列多個自訂屬性群組。 新增自訂屬性群組後，您可以看到下列選項：

   - **索引鍵值配對**：您可以按一下「 」，新增多個自訂屬性名稱和自訂屬性值 **新增** 按鈕來設定每個自訂屬性群組。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳，以重新排列自訂屬性名稱和自訂屬性值的順序。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}