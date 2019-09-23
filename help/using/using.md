---
title: 使用核心元件
seo-title: 使用核心元件
description: 'null'
seo-description: 「若要在您自己的專案中啟動並執行核心元件，需執行三個步驟：下載和安裝、建立Proxy元件、載入核心樣式，以及允許範本上的元件。」
uuid: a1ef2acf-8226-4510-838b-f5fae196f9f1
contentOwner: 使用者
content-type: 引用
topic-tags: 開發
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新功能
discoiquuid: 1703a171-830c-477e-a34f-99caba841ec4
disttype: dist5
gnavtheme: 淺色
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1d725b6fc32112323e9939e8870922410a6c4f3

---


# 使用核心元件{#using-core-components}

若要在您自己的專案中啟 [動並執行核心元件](developing.md) ，有四個步驟，各自詳述於下列各節：

1. [下載和安裝](#download-and-install)
1. [建立代理元件](#create-proxy-components)
1. [載入核心樣式](#load-the-core-styles)
1. [啟用元件](#allow-the-components)

>[!NOTE]
>
>或者，如需如何從頭開始使用專案設定、核心元件、可編輯範本、用戶端程式庫和元件開發的更多指示，請參閱下列多部份教學課程：\
>[AEM Sites快速入門- WKND教學課程](wknd-tutorial.md)

## 下載和安裝 {#download-and-install}

核心元件背後的驅動力之一是靈活性。 更頻繁地推出新版核心元件，讓Adobe在提供新功能時更有彈性。 開發人員也可以靈活選擇將哪些元件整合至其專案，以及想要更新的頻率。

因此，在生產模式下（不含示例內容）啟動時，核心元件不是快速啟動的一部分。 因此，您的第一個步驟是 [從GitHub下載最新發行的內容套件](https://github.com/adobe/aem-core-wcm-components/releases/latest) ，並將它安裝在AEM環境中。

有幾種方法可以自動化此程式，但要在實例上快速安裝內容包，最簡單的方法是使用「包管理器」;請參 [閱安裝軟體包](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html)。 此外，一旦您也將執行發佈例項，您就需要將該套件複製至發佈者；請參 [閱複製包](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html)。

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:42:59.142-0400

Should we be promoting embedding the core-component package as an artifact in a customer application, reasoning as follows: 1) a customer application is required to leverage core components (at a minimum, proxy components must be defined) 2) a customer application must be updated to leverage new versions of core components (since it requires adjusting the sling:resourceSuperType to point at the new version of the component) It seems the only time theres an advantage to installing a release directly is if a bug-fix (non version-changing) release of core-components is cut, and it doesnt coincide with an application deployment. WDYT? For example, recommend doing this for ACS Commons which has a similar use-case (https://adobe-consulting-services.github.io/acs-aem-commons/pages/maven.html) We can of course keep the instructions for manually deploying, since some will want to do this, or the bug-fix use-case will appear.

 -->

## 建立代理元件 {#create-proxy-components}

基於「代理元件模式」 [部分中說明的原因](guidelines.md#proxy-component-pattern) ，不能直接從內容中引用核心元件。 為避免此問題，它們都屬於隱藏的元件群組( `.core-wcm` 或 `.core-wcm-form`)，這會防止它們直接出現在編輯器中。

而必須建立網站特定的元件，以定義要顯示給頁面作者的元件名稱和群組，並將每個元件引用至核心元件作為其超類型。 這些網站特定元件有時稱為「proxy元件」，因為它們不需要包含任何元件，而且主要用來定義網站所用元件的版本。 但是，在自訂核心元 [件時](customizing.md)，這些proxy元件對於標籤和邏輯自訂扮演了重要的角色。

因此，對於每個想要用於網站的核心元件，您必須：

1. 在網站的元件資料夾中建立對應的代理元件。

   **示例**&#x200B;在 `/apps/my-site/components` 建立類型的標題節點下 `cq:Component`

1. 使用super-type指向對應的核心元件版本。

   **範例**&#x200B;新增下列屬性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定義元件的群組、標題和（可選）說明。 這些值是專案特定值，並指定元件對作者的公開方式。

   **範例**&#x200B;新增下列屬性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例如，查看We. [Retail參考網站的標題元件](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/content/title/.content.xml)，這是以此方式建立之代理元件的好範例。

## 載入核心樣式 {#load-the-core-styles}

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:57:16.414-0400

Styles is odd in that most Core Components do not have CSS; very few even have structural CSS (breadcrumbs, list) It may be more apt to title this section: Load the Core JavaScript and CSS or Load the Core Client Libraries ?

 -->

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:41:37.115-0400

This section seems to cover the "sites" clientlibs for core components; Do we need a section for ensuring the editor clientlibs are loaded in the Page Editor? Pending: https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/issues/15

 -->

<!-- 

Comment Type: annotation
Last Modified By: cotescu
Last Modified Date: 2018-03-09T10:45:52.812-0500

Load the Core Client Libraries sounds way better

 -->

1. 如果尚未完成，請建立 [用戶端程式庫](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html) ，其中包含您網站所需的所有CSS和JS檔案。
1. 在您網站的「用戶端程式庫」中，將相依性新增至可能需要的核心元件。 這是透過新增屬性來 `embed` 完成。

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

## 允許元件 {#allow-the-components}

在模板編輯器中執行以 [下步驟](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)。

1. 在範本編輯器中，選取「版面容器」，並開啟其原則。
1. 在「允許的元件」清單中，選取先前建立的代理元件，這些元件應顯示在指派給這些元件的元件群組下。 完成後，請套用變更。
1. 或者，對於具有設計對話框的元件，可以預先配置它們。

就這樣！ 在從已編輯的範本建立的頁面中，您現在應該可以使用新建立的元件。

**閱讀下一頁：**

* [自訂核心元件](customizing.md) -瞭解如何設定核心元件的樣式和自訂核心元件。
* [元件准則](guidelines.md) -瞭解核心元件的實作模式。
