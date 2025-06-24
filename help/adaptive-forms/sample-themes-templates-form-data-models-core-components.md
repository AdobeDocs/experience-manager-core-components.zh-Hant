---
title: 如何取得AEM Forms核心元件的範例主題和範本？
description: AEM Forms核心元件提供範例最適化表單主題、範本和表單資料模型。
solution: Experience Manager Forms
topic: Administration
role: Admin, User
level: Intermediate
exl-id: aef6e88b-dcae-4777-9893-9257d7702f43
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 1%

---

# 範例主題、範本和表單資料模型 {#sample-themes-templates-and-data-models}

[!DNL AEM Forms]核心元件提供現成的範例主題、範本和表單資料模型，以便快速建立多樣化的調適型表單。 這也有助於表單作者瞭解[最適化Forms核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html)的可擴充性、適應性和回應能力，以便輕鬆建立簡易的表單，同時與資料庫緊密連線。

參考內容套件中包含的範例主題、範本和表單資料模型包括：

| 範本 | 主題 | 表單資料模型 |
---------|----------|---------
| [空白](#Blank) | [畫布](#Canvas) | Microsoft® Dynamics 365 |
| [連絡我們](#Contact-Us) | [WKND](#WKND) | Salesforce |
| [連絡人詳細資料更新](#Contact-Details-Update) | [畫架](#Easel) |   |
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

參考範例主題可協助作者使用、定義及自訂表單的樣式，即使具備CSS基本知識的作者也可以視需要自訂主題。

**如何取得這些主題？**
您可以使用以下針對**AEM as a Cloud Service**&#x200B;環境提供的步驟來取得這些主題：

1. [啟用最適化表單核心元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html)
1. [將AEM Archetype 47專案或更新版本部署至您的環境](https://github.com/adobe/aem-project-archetype)


部署AEM Archetype時，您只能在表單中使用OOTB主題。若要根據您的需求自訂主題，[使用前端管道](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html)以部署主題。

>[!NOTE]
>
> * 主題不適用於&#x200B;**AEM 6.5**&#x200B;環境。

<!--

1. **AEM 6.5**

    1. [Enable Adaptive Form Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html)
    1. [Deploy an AEM Archetype 47 or later project to your environment](https://github.com/adobe/aem-project-archetype)


    When you deploy an AEM Archetype, you can only use the OOTB themes in your forms, To customize the themes as per your requirements, [Use the front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html) to deploy the themes.

-->


<!--

### Deploying an AEM Archetype 47 or later project to your environment {#using-archetype-to-deploy-themes}

You can get these themes by deploying an [AEM Archetype 47 or later](https://github.com/adobe/aem-project-archetype) to your **AEM Forms as a Cloud Service** or **AEM 6.5** Forms environment.

### Enable core components and use front-end pipeline to deploy themes {#use-front-end-pipeline-to-deploy-themes}

1. To get these themes on **Forms as a Cloud Service** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html) and use the [front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html) to deploy these themes.
    
1. To get these themes on **AEM 6.5 Forms** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html) and use the [Package Manager](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html) to deploy these themes.

[Learn to use and customize themes in AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html). 

[Learn to use and customize themes in AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html).

-->

**立即可用** [最適化表單核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html)主題為：

![OOTB主題](/help/adaptive-forms/assets/archetype-45-themes-1.png)

### 畫布 {#Canvas}

畫布布主題是表單的預設主題，並強調使用基本顏色、透明度與平面圖示。 在下方熒幕擷圖中，您可以看到畫布布佈景主題的外觀。

![畫布布主題](/help/adaptive-forms/assets/Safety-Inspection-Theme-Canvas.png)

### WKND {#WKND}

WKND主題包含生動、富有想象力且吸引人的設計，以展現您表單的時尚外觀。 此主題是以[WKND網站](https://wknd.site/us/en.html)的外觀和樣式為基礎，該網站是以[Adobe Experience Manager核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html)為基礎的旅遊和冒險網站組建。

![WKND佈景主題](/help/adaptive-forms/assets/Safety-Inspection-Form-Theme.png)


### 畫架 {#Easel}

畫框主題有助於建立吸引人且易於設定的表單外觀，而且會經過客製化，以簡化操作且方便使用。 畫架主題是以可攜式底座的概念為基礎，藝術家在製作畫作時可透過底座支援畫布。

![畫架佈景主題](/help/adaptive-forms/assets/Safety-Inspection-Theme-Easel.png)

### FSI （金融服務與保險） {#FSI}

FSI主題強調讓您的表單具有乾淨、實用的外觀。 套用FSI主題時，會套用淺藍色色調至您的表單，如影像所示。

![FSI佈景主題](/help/adaptive-forms/assets/fsi-theme-new1.png)


### 醫療保健 {#Healthcare}

Healthcare主題採用豐富而柔和的色調，強調表單中的標籤、面板、文字方塊和按鈕等元素。

![醫療保健佈景主題](/help/adaptive-forms/assets/healthcare-new-theme.png)


## 範例範本 {#Sample-templates}

範本會定義要在您的表單中復寫的初始表單結構、內容和動作，或是使用與您的表單類似的範本結構，例如，同意表單、權益登錄檔單等等。

**如何取得這些範本？**

您可以將[AEM Archetype 47或更新版本](https://github.com/adobe/aem-project-archetype)部署至您的&#x200B;**AEM Forms as a Cloud Service**&#x200B;環境或&#x200B;**AEM 6.5 Forms**&#x200B;環境，以取得這些範本。

<!--

>[!NOTE]
>
> * If you have [enabled core components and used front-end pipeline to deploy themes](#use-front-end-pipeline-to-deploy-themes), you need not to deploy an AEM Archetype.
> * You can find list of all OOTB templates when you create a form.

-->


**立即可用** [最適化表單核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html)範本為：

![參考範本](/help/adaptive-forms/assets/reference-templates-core-components.png)

<!--

### Basic {#Basic}

A basic template helps you quickly create an enrollment experience form. You can also use it to preview the functionality of [Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html). It provides a wizard layout for section-by-section presentation of data.

![Basic Template](/help/adaptive-forms/assets/Basic-template-desktop-view.png)

-->

### 空白 {#Blank}

空白畫布範本可用來從頭開始建立最適化表單結構、內容和規則。 空白範本中未預先納入任何表單元件。

![空白範本](/help/adaptive-forms/assets/Blank-temp-desktop-view.png)

### 聯絡我們 {#Contact-Us}

聯絡我們表單範本是用來建立表單，以促進網站訪客與表單管理員之間的通訊。 使用者可以透過表單提交查詢、意見回饋或支援請求。

![連絡我們範本](/help/adaptive-forms/assets/Contact-us-desktop-view.png)

### 連絡人詳細資料更新 {#Contact-Details-Update}

聯絡資料詳細資料更新範本可協助作者建立客戶地址和聯絡資料更新的表單。 此表單也可協助客戶更新與訂閱或權益相關的個人資訊，以確保順暢的通訊以及不間斷地存取服務或權益。

![連絡人詳細資料 — 更新](/help/adaptive-forms/assets/Contact-details-update.png)

### 同意表單 {#Consent-Form}

同意表單範本可用來建立表單，以從參與特定活動、研究研究、醫療程式或可能涉及其個人資訊或權利的任何情況的參與者取得法律檔案。 表單可確保透明度、保護參與者的權利，並清楚瞭解個人同意的內容。

![同意表單](/help/adaptive-forms/assets/Consent-form-desktop-view.png)

### 記錄服務要求 {#Log-Service-Request}

記錄服務要求範本可協助建立向服務提供者要求記錄特定記錄服務的表單。 此表單可作為一個正式請求，為事件、活動或資料記錄建立票證以用於監控或追蹤狀態。

![記錄服務要求範本](/help/adaptive-forms/assets/Log-service-request-desktop-view.png)


### 提供意見回饋 {#Give-Feedback}

提供意見回饋表單範本有助於建立表格，向其他人員或團隊提供具建設性的意見回饋。 表單有助於確保意見反應清晰、明確且可行，有助於促進開放溝通和改進。

![提供意見反應範本](/help/adaptive-forms/assets/Give-feedback-desktop-view.png)


### 福利註冊 {#Benefits-Enrollment}

福利登錄檔單範本可用來建立表單，以收集員工有關其偏好福利與保險選項的基本資訊。 它通常伴隨年度福利註冊期間。

![權益註冊範本](/help/adaptive-forms/assets/Benefits-enrollment-form-template.png)


### 員工福利彙總 {#Employee-Benefits-Summary}

員工福利摘要表單範本可用來建立表單，以收集有關個人福利的基本詳細資訊。 它有助於快速準確地評估涵蓋範圍，提供有效協助和支援的完整概觀。
![員工福利摘要](/help/adaptive-forms/assets/Employee-benefits-summary.png)


### 要求帳戶對帳單 {#Request-for-Account-Statement}

帳戶對帳單範本的請求可協助建立表單，以啟動取得準確且最新的客戶對帳單的程式。 對帳單提供財務交易、活動的詳細記錄，或使用此表單之客戶的其他相關資訊。

![帳戶陳述請求](/help/adaptive-forms/assets/Request-for-account-statment.png)

### 安全檢查 {#Safety-Inspection}

安全檢查表單範本可協助建立表單，以輸入安全工作環境的詳細資訊。 使用此表格進行定期檢查，即可識別潛在危險。 此表格涵蓋各種層面，例如緊急出口、防火安全、電氣安全、危險材料、個人防護裝置、工作站人體工學，以保障員工、訪客和客戶的安全與福祉。

![安全檢查表單](/help/adaptive-forms/assets/Safety-inspection-form.png)

### 品質控制檢查 {#Quality-Control-Inspection}

品質控制檢查表單範本可用來建立表單，以評估和記錄產品或專案的視覺外觀、尺寸、功能、檔案、測試結果以及整體品質。 它有助於識別缺陷、不符合項以及確保符合品質標準所需的更正動作。

![品質控制檢查](/help/adaptive-forms/assets/Quality-Control-Inspection.png)


### 購買要求 {#Purchase-Request}

採購請求表單範本可協助建立表單，以啟動採購程式，並允許員工正式要求購買其工作所需的商品或服務。 此表單會擷取必要的明細，例如料號摘要、數量、偏好的供應商（如果適用）、預算配置、採購理由、交貨資訊以及必要的核准。

![purchase-request-form](/help/adaptive-forms/assets/Purchase-request-form.png)

## 參考表單資料模型 {#reference-models}

建立以[核心元件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html)為基礎的最適化表單後，您可以將表單與資料庫Microsoft®Dynamics 365和Salesforce伺服器連線，以啟用業務工作流程。 例如：

* 在最適化表單提交時在Microsoft®Dynamics 365和Salesforce中寫入資料。
* 透過表單資料模型中定義的自訂實體在Microsoft®Dynamics 365和Salesforce中寫入資料，反之亦然。
* 查詢Microsoft®Dynamics 365和Salesforce伺服器以取得資料，並預先填入Adaptive Forms。
* 從Microsoft®Dynamics 365和Salesforce伺服器讀取資料。

您可以安裝[參考內容套件](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-forms-reference-content.ui.content-2.1.0.zip)，以取得下清單單資料模型：

* Microsoft® Dynamics 365
* Salesforce

如需使用這些模型的詳細資訊，請參閱[設定Microsoft®Dynamics 365和Salesforce雲端服務](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/configure-msdynamics-salesforce.html#configure-dynamics-cloud-service)
