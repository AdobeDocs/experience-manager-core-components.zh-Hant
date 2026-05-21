---
title: 使用核心元件編寫
description: 在 AEM 中，元件是構成所編寫頁面內容的結構元素。核心元件提供有彈性且功能豐富的編寫功能。
role: Developer, Admin, User
exl-id: 56e58303-a178-45ab-b59d-e374c9cf90cf
TQID: https://experienceleague.adobe.com/iLP4KD5kWkBaZ3b4c6Kos9ltFf1MBAZHPwN6wkcWrcY
product_v2:
  - id: c45915cf-e157-4af7-a80d-97b905bcb3a5
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: e2c1b6d3-bb7e-4fe8-8c72-f7b403298e91
subfeature_v2:
  - id: a6c0bfb4-91d0-4952-9c1d-c7f39e7705c4
  - id: f86a5563-8f73-4ec0-be7d-a1782604870a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
source-git-commit: 73aa5234ac63fa3be99feebce448bb6722513838
workflow-type: tm+mt
source-wordcount: 792
ht-degree: 100%

---

# 使用核心元件編寫

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。

核心元件提供有彈性且功能豐富的編寫功能。 [WKND 參考網站](https://wknd.site)及其說明如何使用核心元件可用於實施豐富的網站體驗。

若要體驗「核心元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_tw)」。

如需使用[ AEM 專案原型](/help/developing/archetype/overview.md)在 AEM 專案上實施核心元件的更深入、開發人員導向的簡介，請檢視[WKND 教學課程](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hant)。

>[!NOTE]
>
>[開發團隊必須先依照作者的環境整合核心元件](/help/get-started/using.md)，才能將其提供給您。 整合後，可透過[範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)使用及預先設定。

>[!CAUTION]
>
>核心元件[需要 AEM 6.4 或更新版本](/help/versions.md) ，而且需要使用[可編輯的範本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)。 它們無法搭配傳統 UI 使用，也無法搭配靜態範本使用。

## 使用核心元件編寫 {#authoring-with-core-components}

作為作者，您會注意到核心元件的幾項優點，包括：

* 簡單易用，並與[頁面編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant)適當整合

* 功能豐富的功能，可因應 [WKND 參考網站](https://wknd.site)以及[元件庫](https://adobe.com/go/aem_cmp_library_tw)中說明的許多使用案例

* [可預先設定](#pre-configuring-core-components)，以透過[範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)定義頁面作者可用的功能

* 建置於[協助工具指導方針](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html?lang=zh-Hant)

* 專為支援[回應式版面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html?lang=zh-Hant)而建置

* 專為支援[輕鬆本地化](localization.md)而建置

在[編輯頁面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant)時，元件可在頁面編輯器側面板的&#x200B;**元件**&#x200B;索引標籤上使用。

元件會根據稱為元件群組的類別分組，以輕鬆組織和篩選元件。 元件群組名稱會與元件一起顯示在[元件瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hant)中，也可以依群組篩選以輕鬆找到正確的元件。

>[!NOTE]
>
>核心元件預設為隱藏群組的一部分，且不會顯示在元件瀏覽器中。
>
>將所需元件新增至可見群組或自訂這些元件，以供作者使用。

## 預先設定核心元件 {#pre-configuring-core-components}

開發人員必須負責設定基礎元件。 不過，使用核心元件時，範本作者現在可以透過範本編輯器設定許多功能。

例如，如果影像元件不允許從檔案系統上傳影像，或如果文字元件僅允許特定段落格式，只要按一下即可啟用或停用這些功能。

如需詳細資訊，請參閱[建立頁面範本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)。

### 編輯和設計對話框 {#edit-and-design-dialogs}

由於範本作者可以預先設定核心元件，以定義範本中允許哪些選項，然後由頁面作者進一步設定以定義實際頁面內容，因此每個元件可以在兩個不同的對話框中有選項。

|  | 說明 | 控制內容 | 範例 |
|--- |--- |--- |--- |
| **編輯對話框** | **頁面作者** 在對置入的元件進行正常頁面編輯時可以修改的選項 | 元件顯示的內容以及最終顯示在頁面上的方式。 | 格式化內容文字，旋轉頁面上的影像 |
| **設計對話框** | 設定頁面範本時，**範本作者** 可以修改的選項。 | 頁面作者在編輯元件時可以使用的選項 | 哪些文字格式選項可用，哪些影像就地選項可用 |

### 元件樣式 {#component-styling}

大部分核心元件的樣式可使用 AEM 樣式系統定義。

* 範本作者可以在特定元件的「設計」對話框中，定義哪些樣式可供該元件使用。
* 然後，內容作者在新增元件和建立內容時，可以選擇要套用的樣式。

如需詳細資訊，請參閱[樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html?lang=zh-Hant) 文件。

## 開發人員資源 {#developer-resources}

如需有關核心元件的技術資訊，請參閱[開發核心元件](/help/developing/overview.md) 開發人員文件。
