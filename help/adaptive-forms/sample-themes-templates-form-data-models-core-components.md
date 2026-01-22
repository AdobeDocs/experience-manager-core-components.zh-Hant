---
title: 如何取得 AEM Forms 核心元件的範例主題和範本？
description: AEM Forms 核心元件提供自適應表單主題、範本和表單資料模型範例。
solution: Experience Manager Forms
topic: Administration
role: Admin, User
level: Intermediate
exl-id: aef6e88b-dcae-4777-9893-9257d7702f43
source-git-commit: 2be68aa708131486f7d89f33952153a7a90c3d0a
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 100%

---

# 範例主題、範本和表單資料模型 {#sample-themes-templates-and-data-models}

[!DNL AEM Forms] 核心元件提供現成的範例主題、範本和表單資料模型，以便快速建立多樣化的自適應表單。這也有助於表單作者了解[自適應表單核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hant)的可擴充性、適應性和回應能力，以便迅速建立簡易的表單，輕鬆打造複雜表單，同時可無縫連接至資料庫。

參考內容套件中包含的範例主題、範本和表單資料模型包括：

| 範本 | 主題 | 表單資料模型 |
---------|----------|---------
| [空白](#Blank) | [畫布](#Canvas) | Microsoft® Dynamics 365 |
| [聯絡我們](#Contact-Us) | [WKND](#WKND) | Salesforce |
| [聯絡詳細資訊更新](#Contact-Details-Update) | [畫架](#Easel) |   |
| [同意表單](#Consent-Form) | [FSI](#FSI) |  |
| [記錄服務要求](#Log-Service-Request) | [醫療保健](#Healthcare) |  |
| [提供意見回饋](#Give-Feedback) |  |  |
| [權益註冊](#Benefits-Enrollment) |  |   |
| [員工福利摘要](#Employee-Benefits-Summary) |   |   |
| [要求帳戶對帳單](#Request-for-Account-Statement) |   |   |
| [安全檢查表單](#Safety-Inspection) |   |   |
| [品質控制檢查](#Quality-Control-Inspection) |   |   |
| [購買要求](#Purchase-Request) |  |  |

{{traditional-aem}}

## 範例主題 {#Sample-Themes}

參考範例主題可協助作者使用、定義及自訂表單的樣式，即使具備 CSS 基本知識的作者也可以視需要自訂主題。

**如何取得這些主題？**
您可以使用以下針對 **AEM as a Cloud Service** 環境提供的步驟來取得這些主題：

<!-- 1. [Enable Adaptive Form Core Components](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html?lang=zh-Hant) -->
1. [將 AEM Archetype 47 專案或更新版本部署至您的環境](https://github.com/adobe/aem-project-archetype)


部署 AEM Archetype 時，您只能在表單中使用 OOTB 主題。若要根據您的需求自訂主題，[使用前端管道](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=zh-Hant)以部署主題。

>[!NOTE]
>
> * 主題不適用於 **AEM 6.5** 環境。

<!--

1. **AEM 6.5**

    1. [Enable Adaptive Form Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html?lang=zh-Hant)
    1. [Deploy an AEM Archetype 47 or later project to your environment](https://github.com/adobe/aem-project-archetype)


    When you deploy an AEM Archetype, you can only use the OOTB themes in your forms, To customize the themes as per your requirements, [Use the front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html?lang=zh-Hant) to deploy the themes.

-->


<!--

### Deploying an AEM Archetype 47 or later project to your environment {#using-archetype-to-deploy-themes}

You can get these themes by deploying an [AEM Archetype 47 or later](https://github.com/adobe/aem-project-archetype) to your **AEM Forms as a Cloud Service** or **AEM 6.5** Forms environment.

### Enable core components and use front-end pipeline to deploy themes {#use-front-end-pipeline-to-deploy-themes}

1. To get these themes on **Forms as a Cloud Service** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html?lang=zh-Hant) and use the [front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=zh-Hant) to deploy these themes.
    
1. To get these themes on **AEM 6.5 Forms** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html?lang=zh-Hant) and use the [Package Manager](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html?lang=zh-Hant) to deploy these themes.

[Learn to use and customize themes in AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=zh-Hant). 

[Learn to use and customize themes in AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html?lang=zh-Hant).

-->

**立即可用**[自適應表單核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hant)主題為：

![OOTB 主題](/help/adaptive-forms/assets/archetype-45-themes-1.png)

### 畫布 {#Canvas}

畫布主題是表單的預設主題，並強調使用基本顏色、透明度與平面圖示。在下面的螢幕擷圖中，您可以看到畫布主題的外觀。

![畫布主題](/help/adaptive-forms/assets/Safety-Inspection-Theme-Canvas.png)

### WKND {#WKND}

WKND 主題包含生動、富有想象力且吸引人的設計，以展現您表單的時尚外觀。此主題是以 [WKND 網站](https://wknd.site/us/en.html)的外觀和樣式為基礎，該網站是以 [Adobe Experience Manager 核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hant)為基礎的旅遊和冒險網站組建。

![WKND 主題](/help/adaptive-forms/assets/Safety-Inspection-Form-Theme.png)


### 畫架 {#Easel}

畫架主題有助於建立吸引人且易於設定的表單外觀，其設計經過客製化，以簡化操作且方便使用。畫架主題是以藝術家在繪畫時所使用的畫架為概念基礎，這種可攜式底座象徵在創作過程中為畫布提供穩固的支撐。

![畫架主題](/help/adaptive-forms/assets/Safety-Inspection-Theme-Easel.png)

### FSI (金融服務業和保險業) {#FSI}

FSI 主題強調讓您的表單具有乾淨、實用的外觀。套用 FSI 主題時，會套用淺藍色調至您的表單，如影像所示。

![FSI 主題](/help/adaptive-forms/assets/fsi-theme-new1.png)


### 醫療保健 {#Healthcare}

醫療保健主題採用豐潤的綠意色調，用於凸顯表單中的索引標籤、面板、文字方塊和按鈕等元素。

![醫療保健主題](/help/adaptive-forms/assets/healthcare-new-theme.png)


## 範例範本 {#Sample-templates}

範本會定義要在您的表單中複寫的初始表單結構、內容和動作，或是使用與您的表單類似的範本結構 (例如同意表單、權益登錄表單等等)。

**如何取得這些範本？**

您可以將 [AEM Archetype 47 或更新版本](https://github.com/adobe/aem-project-archetype)部署至您的 **AEM Forms as a Cloud Service** 環境或 **AEM 6.5 Forms** 環境，以取得這些範本。

<!--

>[!NOTE]
>
> * If you have [enabled core components and used front-end pipeline to deploy themes](#use-front-end-pipeline-to-deploy-themes), you need not to deploy an AEM Archetype.
> * You can find list of all OOTB templates when you create a form.

-->


**立即可用**[自適應表單核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hant)範本為：

![參考範本](/help/adaptive-forms/assets/reference-templates-core-components.png)

<!--

### Basic {#Basic}

A basic template helps you quickly create an enrollment experience form. You can also use it to preview the functionality of [Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hant). It provides a wizard layout for section-by-section presentation of data.

![Basic Template](/help/adaptive-forms/assets/Basic-template-desktop-view.png)

-->

### 空白 {#Blank}

空白畫布範本可用來從頭開始建立自適應表單結構、內容和規則。空白範本中未預先納入任何表單元件。

![空白範本](/help/adaptive-forms/assets/Blank-temp-desktop-view.png)

### 聯絡我們 {#Contact-Us}

聯絡我們表單範本是用來建立表單，以促進網站訪客與表單管理員之間的通訊。使用者可以透過表單提交查詢、意見回饋或支援請求。

![聯絡我們範本](/help/adaptive-forms/assets/Contact-us-desktop-view.png)

### 聯絡詳細資訊更新 {#Contact-Details-Update}

聯絡詳細資訊更新範本可協助作者建立客戶地址和聯絡資訊更新的表單。此表單也可協助客戶更新與訂閱或權益相關的個人資訊，以確保順暢的通訊以及服務或權益的存取不中斷。

![聯絡詳細資訊更新](/help/adaptive-forms/assets/Contact-details-update.png)

### 同意表單 {#Consent-Form}

同意表單範本可用來建立表單，以從參與特定活動、學術研究、醫療程序或可能涉及其個人資訊或權利的任何情況的參與者取得法律文件。表單可確保透明度、保護參與者的權利，並清楚瞭解個人同意的內容。

![同意表單](/help/adaptive-forms/assets/Consent-form-desktop-view.png)

### 記錄服務要求 {#Log-Service-Request}

記錄服務要求範本可協助建立向服務提供者要求記錄特定記錄服務的表單。此表單可作為一個正式請求，為事件、活動或資料記錄建立票證以用於監控或追蹤狀態。

![記錄服務要求範本](/help/adaptive-forms/assets/Log-service-request-desktop-view.png)


### 提供意見回饋 {#Give-Feedback}

提供意見回饋表單範本有助於建置表單，向其他人員或團隊提供具建設性的意見回饋。表單有助於確保意見反應清晰、明確且可行，有助於促進開放溝通和改進。

![提供意見回饋範本](/help/adaptive-forms/assets/Give-feedback-desktop-view.png)


### 權益註冊 {#Benefits-Enrollment}

權益註冊表單範本可用來建立表單，以收集員工有關其偏好福利與保障選項的基本資訊。此表單通常配合年度福利註冊期間使用。

![權益註冊範本](/help/adaptive-forms/assets/Benefits-enrollment-form-template.png)


### 員工福利摘要 {#Employee-Benefits-Summary}

員工福利摘要表單範本可用來建立表單，以收集有關個人福利的基本詳細資訊。有助於快速準確地評估保障範圍，提供有效率的協助和支援的完整概觀。
![員工福利摘要](/help/adaptive-forms/assets/Employee-benefits-summary.png)


### 要求帳戶對帳單 {#Request-for-Account-Statement}

要求帳戶對帳單範本可協助建立表單，以啟動取得準確且最新的客戶對帳單的流程。對帳單提供財務交易、活動的詳細記錄，或使用此表單之客戶的其他相關資訊。

![要求帳戶對帳單](/help/adaptive-forms/assets/Request-for-account-statment.png)

### 安全檢查 {#Safety-Inspection}

安全檢查表單範本可協助建立表單，以輸入安全工作環境的詳細資訊。使用此表單進行定期檢查，即可識別潛在危險。此表單涵蓋各種層面，例如緊急出口、防火安全、電氣安全、危險物質、個人防護裝備、工作站人體工學等，以保障員工、訪客和客戶的安全與福祉。

![安全檢查表單](/help/adaptive-forms/assets/Safety-inspection-form.png)

### 品質控制檢查 {#Quality-Control-Inspection}

品質控制檢查表單範本可用來建立表單，以評估和記錄產品或項目的視覺外觀、尺寸、功能、文件、測試結果以及整體品質。有助於識別缺陷、不合規項目以及確保符合品質標準所需的更正動作。

![品質控制檢查](/help/adaptive-forms/assets/Quality-Control-Inspection.png)


### 購買要求 {#Purchase-Request}

購買要求表單範本可協助建立表單，以啟動採購流程，並允許員工正式要求購買其工作所需的商品或服務。此表單會擷取必要的項目說明，例如品項描述、數量、偏好的供應商 (如果適用)、預算配置、採購理由、交貨資訊以及必要的核准。

![購買要求表單](/help/adaptive-forms/assets/Purchase-request-form.png)

## 參考表單資料模型 {#reference-models}

建立以[核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hant)為基礎的自適應表單後，您可以將表單與資料庫 Microsoft® Dynamics 365 和 Salesforce 伺服器連接，以啟用業務工作流程。例如：

* 於自適應表單提交時在 Microsoft® Dynamics 365 和 Salesforce 中寫入資料。
* 透過表單資料模型中定義的自訂實體在 Microsoft®Dynamics 365 和 Salesforce 中寫入資料，反之亦然。
* 查詢 Microsoft®Dynamics 365 和 Salesforce 伺服器以取得資料，並預先填入自適應表單。
* 從 Microsoft®Dynamics 365 和 Salesforce 伺服器讀取資料。

您可以安裝[參考內容套件](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-forms-reference-content.ui.content-2.1.0.zip)，以取得以下表單資料模型：

* Microsoft® Dynamics 365
* Salesforce

如需使用這些模型的詳細資訊，請參閱[設定 Microsoft® Dynamics 365 和 Salesforce 雲端服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/configure-msdynamics-salesforce.html?lang=zh-Hant#configure-dynamics-cloud-service)
