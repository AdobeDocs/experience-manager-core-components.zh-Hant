---
title: 使用核心元件編寫
description: 在AEM中，元件是構成所編寫頁面內容的結構元素 — 核心元件提供彈性且功能豐富的製作功能。
role: Architect, Developer, Admin, User
exl-id: 56e58303-a178-45ab-b59d-e374c9cf90cf
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 8%

---

# 使用核心元件製作

在 Adobe Experience Manager 中，元件是構成所編寫頁面內容的結構元素。

核心元件提供彈性且功能豐富的製作功能。 此 [WKND參考網站](https://wknd.site) 並說明如何使用核心元件來實作豐富的網站體驗。

若要體驗核心元件並查看其設定選項、HTML和JSON輸出範例，請造訪 [元件庫](https://adobe.com/go/aem_cmp_library).

如需在AEM專案上使用實作核心元件的更深入、以開發人員為導向的簡介，請參閱 [AEM專案原型](/help/developing/archetype/overview.md) 簽出 [WKND教學課程。](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hant)

>[!NOTE]
>
>[開發團隊必須先依照作者的環境整合核心元件](/help/get-started/using.md)，才能將其提供給您。整合後，可透過 [範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>核心元件 [需要AEM 6.4或更新版本](/help/versions.md) 需要使用 [可編輯的範本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html). 無法搭配傳統UI或靜態範本使用。

## 使用核心元件編寫 {#authoring-with-core-components}

身為作者，您會注意到核心元件的幾項優點，包括：

* 簡單易用，與 [頁面編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* 功能豐富，可容納許多使用案例，如 [WKND參考網站](https://wknd.site) 以及 [元件庫](https://adobe.com/go/aem_cmp_library)

* [可預先設定](#pre-configuring-core-components) 定義頁面作者可透過 [範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

* 內建 [協助工具准則](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

* 建置以支援 [回應式版面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* 建置以支援 [易本地化](localization.md)

元件可在 **元件** 頁面編輯器的側面板標籤 [編輯頁面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html).

元件會根據稱為元件群組的類別分組，以輕鬆組織和篩選元件。 元件組名稱隨元件一起顯示在 [元件瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html) 而且，也可以按組進行篩選，以便容易地找到正確的元件。

>[!NOTE]
>
>核心元件預設為隱藏群組的一部分，且在元件瀏覽器中不可見。
>
>將所需元件新增至可見群組，或自訂供作者使用。

## 預先設定核心元件 {#pre-configuring-core-components}

配置基礎元件是開發人員的工作。 不過，使用核心元件時，範本作者現在可以透過範本編輯器設定許多功能。

例如，如果影像元件不允許從檔案系統上傳影像，或者文本元件僅允許某些段落格式，則只需按一下即可啟用或禁用這些功能。

請參閱 [建立頁面範本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 以取得更多資訊。

### 編輯和設計對話框 {#edit-and-design-dialogs}

由於範本作者可預先設定核心元件，以定義範本中允許的選項，然後頁面作者進一步設定以定義實際頁面內容，因此每個元件在兩個不同的對話方塊中都可有選項。

|  | 說明 | 控制項 | 範例 |
|--- |--- |--- |--- |
| **編輯對話方塊** | 選項 **頁面作者** 可在正常頁面編輯期間修改放置的元件 | 元件顯示的內容，以及它最終如何出現在頁面上。 | 設定內容文字的格式，在頁面上旋轉影像 |
| **設計對話方塊** | 選項 **範本作者** 可在設定頁面範本時修改。 | 編輯元件時頁面作者有哪些可用選項 | 哪些文本格式選項可用，哪些影像就地選項可用 |

### 元件樣式 {#component-styling}

大部分核心元件的樣式可使用AEM樣式系統來定義。

* 範本作者可在該元件的「設計」對話方塊中，定義特定元件可用的樣式。
* 然後，內容作者就可以在新增元件和建立內容時選擇要套用的樣式。

如需詳細資訊，請參閱 [樣式系統](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html) 檔案。

## 開發人員資源 {#developer-resources}

請參閱 [開發核心元件](/help/developing/overview.md) 開發人員檔案，取得核心元件的技術資訊。
