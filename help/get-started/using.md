---
title: 使用核心元件
description: 若要在自己的專案中啟動並執行核心元件，需要遵循三個步驟：下載並安裝、建立 proxy 元件、載入核心樣式並在範本上允許元件。
role: Architect, Developer, Admin, User
exl-id: ee2d25e4-e2b8-4ecc-a62c-f0066de2bf2d
source-git-commit: 8beae61676340e8aafaee469018d865ea7ed934e
workflow-type: ht
source-wordcount: '948'
ht-degree: 100%

---

# 使用核心元件{#using-core-components}

若要在自己的專案中啟動並執行核心元件，共有四個步驟，以下各節將分別詳細說明：

1. [下載並安裝](#download-and-install)
1. [建立 Proxy 元件](#create-proxy-components)
1. [載入核心樣式](#load-the-core-styles)
1. [啟用元件](#allow-the-components)

>[!TIP]
>
>如需有關如何從頭開始使用專案設定、核心元件、可編輯的範本、用戶端程式庫和元件開發的更廣泛說明，以下多部分教學課程可能會對您有所幫助：\
>[AEM Sites 快速入門 - WKND 教學課程](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!TIP]
>
>如果您使用[AEM 專案原型，](/help/developing/archetype/overview.md)核心元件會根據 Adobe 的最佳做法建議自動包含在您的專案中。

## 下載並安裝 {#download-and-install}

核心元件背後的驅動理念之一是彈性。更頻繁地發行新版本的核心元件，可讓 Adobe 更靈活地提供新功能。開發人員也因此可以靈活地選擇將哪些元件整合到其專案中，以及他們希望多久更新一次。這會導致 AEM 和核心元件出現各自的發佈流程。

因此，不論您是執行 AEM as a Cloud Service 還是內部部署，都會決定安裝步驟。

### AEM as a Cloud Service {#aemaacs}

無需動手！AEM as a Cloud Service 會自動隨最新版本的核心元件提供。正如 AEMaaCS 為您提供 AEM 的最新功能一樣，AEMaaCS 會自動為您更新核心元件的最新版本。

在 AEMaaCS 上使用核心元件時請謹記以下幾點：

* 核心元件包含在 `/libs` 中。
* 如果專案建置管道再次將核心元件包含為 `/apps` 的一部分，則會在記錄中產生警告，並且將忽略內嵌為專案一部分的版本。
   * 在即將發行的版本中，再次包含核心元件將導致管道建置失敗。
* 如果您的專案先前在 `/apps` 中包含核心元件，[您可能需要調整專案。](/help/developing/overview.md#via-aemaacs)
* 即使核心元件現在位於 `/libs`，也不建議在 `/apps` 中建立相同路徑的任何覆蓋。如果需要自訂元件的任何方面，則應改用 [Proxy 元件模式](/help/developing/guidelines.md#proxy-component-pattern)。
* 若要讓[目錄元件](/help/components/tableofcontents.md)呈現其內容，必須在 OSGi 中設定篩選器。
   * 如需詳細資訊，[請參閱該元件的 GitHub 文件](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1)。

### AEM 6.5 及更早版本 {#aem-65}

在生產模式 (沒有範例內容) 下啟動時，核心元件不是快速入門的一部分。因此，您的第一步是[從 GitHub 下載最新發行的內容套件](https://github.com/adobe/aem-core-wcm-components/releases/latest)，並安裝在您的 AEM 環境中。

有數種方法可以自動執行這項操作，但最簡單的方式是使用封裝管理程式在執行個體上快速安裝內容套件；請參閱[安裝套件](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages)。此外，一旦您也執行了發佈執行個體，您就需要將該套件複寫到發佈者；請參閱[複寫套件](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages)。

## 建立 Proxy 元件 {#create-proxy-components}

由於 [Proxy 元件模式](/help/developing/guidelines.md#proxy-component-pattern)區段中說明的原因，核心元件不可從內容中直接參照。為避免出現此情況，這些元件都屬於隱藏的元件群組 (`.core-wcm` 或 `.core-wcm-form`)，這將阻止它們直接顯示在編輯器中。

相反地，必須建立網站專用元件，這些元件會定義要向頁面作者顯示的所需元件名稱和群組，並將每個元件作為核心元件的超類型。這些網站專用元件有時稱為「Proxy 元件」，因為它們不需要包含任何內容，並且主要用於定義要用於網站的元件版本。不過，在自訂[核心元件](/help/developing/customizing.md)時，這些 Proxy 元件在標記與邏輯自訂方面扮演重要角色。

因此，對於需用於網站的每個核心元件，您必須：

1. 在網站的元件資料夾中建立對應的 Proxy 元件。

   **範例**
在 `/apps/my-site/components` 底下建立類型 `cq:Component` 的標題節點

1. 指向具有超類型的對應核心元件版本。

   **範例**
新增下列屬性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定義元件的群組、標題及說明 (選擇性)。這些值是專案專屬的值，並指定向作者公開元件的方式。

   **範例**
新增下列屬性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例如，檢視 [WKND 網站的標題元件](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml)，這是以這種方式建置的 Proxy 元件的好範例。

## 載入核心樣式 {#load-the-core-styles}

1. 如果尚未完成，請建立[用戶端程式庫](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)，其中包含您的網站所需的所有 CSS 和 JS 檔案。
1. 在網站的用戶端程式庫上，將相依性新增至所需的核心元件。這是透過新增 `embed` 屬性來完成的。

   例如，若要包含所有 v1 核心元件的用戶端程式庫，則要新增的屬性為：

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

在移至下一個區段之前，請確定您的 Proxy 元件和用戶端程式庫已部署到您的 AEM 環境。

## 允許元件 {#allow-the-components}

在[範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)中執行以下步驟。

1. 在「範本編輯器」中，選取「版面容器」，然後開啟其原則。
1. 在「允許的元件」清單中，選取先前建立的 Proxy 元件，這些元件應顯示在指定給它們的元件群組下。完成後，套用變更。
1. 或者，對於具有設計對話框的元件，可預先設定它們。

就是這樣！在從已編輯的範本所建立的頁面中，您現在應該能夠使用新建立的元件。

**閱讀後續章節：**

* [自訂核心元件](/help/developing/customizing.md) - 了解如何樣式化和自訂核心元件。
* [元件指導方針](/help/developing/guidelines.md) - 了解核心元件的實施模式。
