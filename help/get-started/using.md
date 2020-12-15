---
title: 使用核心元件
description: 「若要在您自己的專案中啟動並執行核心元件，需執行三個步驟：下載和安裝、建立Proxy元件、載入核心樣式，以及允許範本上的元件。」
translation-type: tm+mt
source-git-commit: 10090b836397af3c9428f99bba72313263f34596
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 1%

---


# 使用核心元件{#using-core-components}

若要在您自己的專案中啟動並執行核心元件，有四個步驟，各自詳述於以下各節：

1. [下載和安裝](#download-and-install)
1. [建立代理元件](#create-proxy-components)
1. [載入核心樣式](#load-the-core-styles)
1. [啟用元件](#allow-the-components)

>[!NOTE]
>
>或者，如需如何從頭開始使用專案設定、核心元件、可編輯範本、用戶端程式庫和元件開發的更多指示，請參閱下列多部份教學課程：\
>[AEM Sites - WKND 教學課程快速入門](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

## 下載並安裝{#download-and-install}

核心元件背後的驅動力之一是靈活性。 更頻繁地推出新版核心元件，讓Adobe在提供新功能時更有彈性。 開發人員也可以靈活選擇將哪些元件整合至其專案，以及想要更新的頻率。

因此，在生產模式下（不含示例內容）啟動時，核心元件不是快速啟動的一部分。 因此，您的第一步是從GitHub[下載最新發行的內容套件，並將它安裝在AEM環境中。](https://github.com/adobe/aem-core-wcm-components/releases/latest)

有幾種方法可以自動化此程式，但要在實例上快速安裝內容包，最簡單的方法是使用「包管理器」;請參閱[安裝軟體包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages)。 此外，一旦您也將執行發佈例項，您就需要將該套件複製至發佈者；請參閱[複製軟體包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages)。

## 建立代理元件{#create-proxy-components}

由於[Proxy元件模式](/help/developing/guidelines.md#proxy-component-pattern)一節中說明的原因，核心元件不得直接從內容引用。 為避免此問題，它們都屬於隱藏的元件群組（`.core-wcm`或`.core-wcm-form`），因此無法直接顯示在編輯器中。

而必須建立網站特定的元件，以定義要顯示給頁面作者的元件名稱和群組，並將每個元件引用至核心元件作為其超類型。 這些網站特定元件有時稱為「proxy元件」，因為它們不需要包含任何元件，而且主要用來定義網站所用元件的版本。 但是，在自定義[核心元件](/help/developing/customizing.md)時，這些代理元件在標籤和邏輯定制中扮演了關鍵角色。

因此，對於每個想要用於網站的核心元件，您必須：

1. 在網站的元件資料夾中建立對應的代理元件。

   **示**
例在 `/apps/my-site/components` 建立類型的標題節點下  `cq:Component`

1. 使用super-type指向對應的核心元件版本。

   **ExampleAdd following**
屬性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定義元件的群組、標題和（可選）說明。 這些值是專案特定值，並指定元件對作者的公開方式。

   **示**
例添加以下屬性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例如，查看WKND站點](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml)的[title元件，這是以這種方式構建的代理元件的一個很好的示例。

## 載入核心樣式{#load-the-core-styles}

1. 如果尚未完成，請建立[用戶端資料庫](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)，其中包含您網站所需的所有CSS和JS檔案。
1. 在您網站的「用戶端程式庫」中，將相依性新增至可能需要的核心元件。 這是透過新增`embed`屬性來完成的。

   例如，要包含所有v1核心元件的客戶端庫，要添加的屬性為：

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

請確定您的Proxy元件和用戶端程式庫已部署至AEM環境，然後再移至下一節。

## 允許元件{#allow-the-components}

在[模板編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中執行以下步驟。

1. 在範本編輯器中，選取「版面容器」，並開啟其原則。
1. 在「允許的元件」清單中，選取先前建立的代理元件，這些元件應顯示在指派給這些元件的元件群組下。 完成後，請套用變更。
1. 或者，對於具有設計對話框的元件，可以預先配置它們。

就這樣！ 在從已編輯的範本建立的頁面中，您現在應該可以使用新建立的元件。

**閱讀下一節內容:**

* [自訂核心元件](/help/developing/customizing.md) -瞭解如何設定核心元件的樣式和自訂核心元件。
* [元件准則](/help/developing/guidelines.md) -瞭解核心元件的實作模式。
