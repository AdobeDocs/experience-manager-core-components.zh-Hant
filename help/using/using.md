---
title: 使用核心元件
seo-title: 使用核心元件
description: 'null'
seo-description: 「若要在您自己的專案中使用核心元件啓動並執行，有三個步驟：下載並安裝、建立Proxy元件、載入核心樣式，並允許元件上的元件」。
uuid: a ef2acf-8226-4510-838b-f5 fe196 f9 f1
contentOwner: 使用者
content-type: 引用
topic-tags: 開發
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: 1703a171-830c-477e-a34 f-99caba841 ec4
disttype: dist5
gnavtheme: 淺色
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 使用核心元件{#using-core-components}

若要在您自己專案中使用 [核心元件](developing.md) 啓動並執行，有四個步驟，這些步驟分別詳細說明如下：

1. [下載和安裝](#download-and-install)
1. [建立Proxy元件](#create-proxy-components)
1. [載入核心樣式](#load-the-core-styles)
1. [啓用元件](#allow-the-components)

>[!NOTE]
>
>或者，如需有關如何從頭開始使用專案設定、可編輯的範本、用戶端資料庫和元件開發的詳細指示，以下多部分教學課程可能會有興趣：\
>[AEM Sites快速入門- WKND教學課程](wknd-tutorial.md)

## 下載和安裝 {#download-and-install}

核心元件背後的一個驅動概念就是彈性。更常發行新版的核心元件，讓Adobe更有彈性地提供新功能。開發人員可以靈活彈性地選擇要整合到專案中的元件，以及他們想要更新的頻率。

因此，核心元件不是開始於生產模式時快速啓動的一部分(沒有範例內容)。因此，您的第一個步驟是 [從GitHub下載最新發行的內容套件，](https://github.com/adobe/aem-core-wcm-components/releases/latest) 並將它安裝在您的AEM環境中。

有幾種方式可自動化這項作業，但在執行個體上，最簡單的方式就是使用「封裝管理員」，將內容封裝快速安裝；請參閱 [安裝套件](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html)。此外，當您也有執行個體執行時，您將需要複製該封裝至發行者；請參閱 [複製套件](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html)。

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:42:59.142-0400

Should we be promoting embedding the core-component package as an artifact in a customer application, reasoning as follows: 1) a customer application is required to leverage core components (at a minimum, proxy components must be defined) 2) a customer application must be updated to leverage new versions of core components (since it requires adjusting the sling:resourceSuperType to point at the new version of the component) It seems the only time theres an advantage to installing a release directly is if a bug-fix (non version-changing) release of core-components is cut, and it doesnt coincide with an application deployment. WDYT? For example, recommend doing this for ACS Commons which has a similar use-case (https://adobe-consulting-services.github.io/acs-aem-commons/pages/maven.html) We can of course keep the instructions for manually deploying, since some will want to do this, or the bug-fix use-case will appear.

 -->

## 建立Proxy元件 {#create-proxy-components}

基於 [「Proxy元件模式](guidelines.md#proxy-component-pattern) 」區段中說明的原因，不能直接從內容參考核心元件。為避免這些問題，這些全都屬於隱藏的元件群組( `.core-wcm` 或 `.core-wcm-form`)，因此無法直接在編輯器中顯示。

而必須建立網站特定元件，以定義要顯示給頁面作者的元件名稱和群組，並將每個元件參照為其超級類型的核心元件。這些網站特定元件有時稱為「proxy元件」，因為它們不需要包含任何項目，也不需要大部分的服務來定義要用於網站的元件版本。不過，自訂 [核心元件](customizing.md)時，這些Proxy元件會扮演標記和邏輯自訂的重要角色。

因此，對於想要用於網站的每個核心元件，您必須：

1. 在網站元件資料夾中建立對應的Proxy元件。

   **範例**下方 `/apps/my-site/components` 建立標題節點 `cq:Component`

1. 使用super-type指向對應的核心元件版本。

   **範例**新增下列屬性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定義元件的群組、標題和選擇性描述。這些值是專案特有的，並說明元件對作者的公開方式。

   **範例**新增下列屬性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例如，查看We. Retail參考網站的 [標題元件，這是](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/content/title/.content.xml)以該方式建立的代理元件的好範例。

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

1. 如果尚未完成，請建立 [「用戶端庫](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html) 」，其中包含您的網站所需的所有CSS和JS檔案。
1. 在您網站的用戶端庫中，新增可能需要的核心元件相依性。這是透過新增 `embed` 屬性來完成。

   例如，若要納入所有v核心元件的「用戶端庫」，要新增的屬性如下：

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

請確定您的Proxy元件和用戶端程式庫已部署到您的AEM環境，然後移至下一節。

## 允許元件 {#allow-the-components}

下列步驟通常是在 [範本編輯器中完成](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)，不過，您可以在「設計」模式中完成這項工作：

1. 在範本編輯器(或設計模式)中，選取版面容器(或parsys)，然後開啓其原則(或設計組態)。
1. 在允許元件的清單中，選取先前建立的Proxy元件，該元件應該顯示在指派給他們的元件群組底下。完成後，請套用變更。
1. 或者，對於具有設計對話方塊的元件，可以預先設定。

就是在編輯過的範本中，您現在應該能夠使用新建立的元件。

**下一步閱讀：**

* [自訂核心元件](customizing.md) -瞭解如何樣式和自訂核心元件。
* [元件准則](guidelines.md) -瞭解核心元件的實施模式。
