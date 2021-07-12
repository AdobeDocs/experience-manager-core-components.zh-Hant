---
title: 使用核心元件
description: 「若要在您自己的專案中開始使用核心元件，請依照下列三個步驟執行：下載並安裝、建立Proxy元件、載入核心樣式，以及允許範本上的元件。」
role: Architect, Developer, Admin, User
exl-id: ee2d25e4-e2b8-4ecc-a62c-f0066de2bf2d
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 2%

---

# 使用核心元件{#using-core-components}

若要在您自己的專案中開始使用核心元件，有四個步驟，請在以下各節中個別詳細說明：

1. [下載和安裝](#download-and-install)
1. [建立代理元件](#create-proxy-components)
1. [載入核心樣式](#load-the-core-styles)
1. [啟用元件](#allow-the-components)

>[!TIP]
>
>如需從頭開始使用專案設定、核心元件、可編輯範本、用戶端程式庫和元件開發的更多指示，下列多部分教學課程可能會受到關注：\
>[AEM Sites - WKND 教學課程快速入門](https://docs.adobe.com/content/help/zh-Hant/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!TIP]
>
>如果您使用[AEM專案原型，系統會根據Adobe的最佳實務建議，自動將核心元件納入您的專案中。](/help/developing/archetype/overview.md)

## 下載和安裝 {#download-and-install}

核心元件背後的驅動思想之一是靈活性。 更常推出新版核心元件，讓Adobe在提供新功能時更具彈性。 開發人員則可選擇將哪些元件整合至其專案中，以及想更新的頻率，因而可有彈性。 如此一來，AEM和核心元件就能分開發行程式。

因此，無論您是執行AEM as a Cloud Service還是內部部署，都會決定安裝步驟。

### AEM as a Cloud Service  {#aemaacs}

沒有步驟一！ AEM as aCloud Service會自動隨附最新版的核心元件。 就像AEM提供您最新的AemCass功能一樣，AEMaCS也會自動提供最新版的核心元件。

在AEMaaCS上使用核心元件時，請謹記以下幾點：

* 核心元件包含在`/libs`中。
* 如果專案建置管道再次包含核心元件作為`/apps`的一部分，則會在記錄中產生警告，且會忽略內嵌於專案中的版本。
   * 在即將發行的版本中，再次包含核心元件將會失敗管道建置。
* 如果您的專案先前在`/apps`中包含核心元件，則[您可能需要調整專案。](/help/developing/overview.md#via-aemaacs)
* 即使核心元件現在位於`/libs`中，也不建議在`/apps`中建立相同路徑的任何覆蓋。 [如果需要](/help/developing/guidelines.md#proxy-component-pattern) 自訂元件的任何方面，則應使用代理元件模式。

### AEM 6.5和之前版本 {#aem-65}

在生產模式中開始時（沒有範例內容），核心元件不是快速入門的一部分。 因此，您的第一步是從GitHub](https://github.com/adobe/aem-core-wcm-components/releases/latest)下載最新發行的內容套件，並安裝在您的AEM環境中。[

有幾種方法可以自動執行此操作，但在實例上快速安裝內容包的最簡單方法是使用包管理器；請參閱[安裝軟體包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages)。 此外，一旦您也有發佈執行個體在執行，就需要將該套件復寫至發佈者；請參閱[複製包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages)。

## 建立代理元件 {#create-proxy-components}

基於[代理元件模式](/help/developing/guidelines.md#proxy-component-pattern)區段中說明的原因，不得直接從內容參考核心元件。 為避免此情況，這些變數都屬於隱藏的元件群組（`.core-wcm`或`.core-wcm-form`），因此無法直接在編輯器中顯示。

而是必須建立網站特定元件，以定義要顯示給頁面作者的元件名稱和群組，並將每個元件參照核心元件作為其超類型。 這些網站特定元件有時稱為「代理元件」，因為它們不需要包含任何內容，且主要用於定義網站要使用的元件版本。 不過，自訂[核心元件](/help/developing/customizing.md)時，這些代理元件在標籤和邏輯自訂方面扮演著重要角色。

因此，針對每個想要用於網站的核心元件，您必須：

1. 在網站的元件資料夾中建立對應的代理元件。

   ****
範例在 `/apps/my-site/components` 建立類型的標題節點底下  `cq:Component`

1. 指向超類型對應的核心元件版本。

   ****
ExampleAdd下列屬性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定義元件的群組、標題和（可選）說明。 這些值是專案專用值，並指定元件向作者公開的方式。

   ****
範例新增下列屬性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例如，查看WKND站點](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml)的[標題元件，這是以這種方式構建的代理元件的好示例。

## 載入核心樣式 {#load-the-core-styles}

1. 若尚未完成，請建立[用戶端程式庫](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)，其中包含您網站所需的所有CSS和JS檔案。
1. 在網站的用戶端程式庫上，將相依性新增至可能需要的核心元件。 這可透過新增`embed`屬性來完成。

   例如，若要包含所有v1核心元件的用戶端程式庫，要新增的屬性為：

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

前往下一節，請確定您的Proxy元件和用戶端程式庫已部署至AEM環境。

## 允許元件 {#allow-the-components}

在[範本編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中執行下列步驟。

1. 在模板編輯器中，選擇佈局容器並開啟其策略。
1. 在「允許的元件」清單中，選擇以前建立的代理元件，該代理元件應顯示在分配給它們的元件組下。 完成後，套用變更。
1. （可選）對於具有設計對話框的元件，可以預先配置它們。

就這樣！ 在從已編輯的範本建立的頁面中，您現在應該可以使用新建立的元件。

**閱讀下一節內容:**

* [自訂核心元件](/help/developing/customizing.md)  — 了解如何設定核心元件的樣式和自訂核心元件。
* [元件准則](/help/developing/guidelines.md)  — 了解核心元件的實作模式。
