---
title: 使用核心元件
description: 「若要在自己的專案中啟動並執行核心元件，有三個步驟要執行：下載和安裝、建立Proxy元件、載入核心樣式，以及在範本上允許元件。」
role: Architect, Developer, Admin, User
exl-id: ee2d25e4-e2b8-4ecc-a62c-f0066de2bf2d
source-git-commit: 8beae61676340e8aafaee469018d865ea7ed934e
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 2%

---

# 使用核心元件{#using-core-components}

若要在自己的專案中啟動並執行核心元件，有三個步驟，以下各節將分別詳述：

1. [下載並安裝](#download-and-install)
1. [建立Proxy元件](#create-proxy-components)
1. [載入核心樣式](#load-the-core-styles)
1. [啟用元件](#allow-the-components)

>[!TIP]
>
>如需如何從頭開始使用專案設定、核心元件、可編輯範本、使用者端程式庫和元件開發的更廣泛說明，以下多部分教學課程可能會有幫助：\
>[AEM Sites - WKND 教學課程快速入門](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hant)

>[!TIP]
>
>如果您使用 [AEM專案原型，](/help/developing/archetype/overview.md) 核心元件會根據Adobe的最佳實務建議自動納入您的專案。

## 下載並安裝 {#download-and-install}

核心元件背後的驅動理念之一是彈性。 更頻繁地發行新版本的核心元件，可讓Adobe更靈活地交付新功能。 反過來，開發人員可以靈活地選擇將哪些元件整合到其專案中，以及希望多久更新一次。 這會導致AEM和核心元件的個別發行程式。

因此，執行AEM as a Cloud Service或內部部署會決定安裝步驟。

### AEM as a Cloud Service  {#aemaacs}

沒有第一步！ AEMas a Cloud Service會自動隨最新版本的核心元件提供。 正如AEMaaCS為您提供AEM的最新功能一樣，AEMaaCS會自動讓您使用最新版本的核心元件。

在AEMaaCS上使用核心元件時，請謹記以下幾點：

* 核心元件包含在 `/libs`.
* 如果專案建置管道再次包含核心元件作為的一部分，則會在記錄中產生警告 `/apps` 和將忽略專案中內嵌的版本。
   * 在即將發行的版本中，再次包含核心元件將導致管道建置失敗。
* 如果您的專案先前已將核心元件納入 `/apps`， [您可能需要調整專案。](/help/developing/overview.md#via-aemaacs)
* 即使核心元件現在位於 `/libs`，不建議在中建立相同路徑的任何覆蓋 `/apps`. [Proxy元件模式](/help/developing/guidelines.md#proxy-component-pattern) 如果需要自訂元件的任何方面，則應改用。
* 為了 [目錄元件](/help/components/tableofcontents.md) 若要呈現其內容，需要在OSGi中設定篩選器。
   * [請參閱元件的GitHub檔案](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1) 以取得詳細資訊。

### AEM 6.5和舊版 {#aem-65}

在生產模式（沒有範例內容）下啟動時，核心元件不是快速入門的一部分。 因此，您的第一步是 [從GitHub下載最新發行的內容套件](https://github.com/adobe/aem-core-wcm-components/releases/latest) 以及將其安裝在您的AEM環境中。

有數種方法可以自動執行此操作，但在執行個體上快速安裝內容套件的最簡單方式，就是使用套件管理員；請參閱 [安裝套件](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages). 此外，一旦您也執行發佈執行個體後，您需要將該套件復寫至發佈者；請參閱 [複製封裝](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages).

## 建立Proxy元件 {#create-proxy-components}

原因請見 [Proxy元件模式](/help/developing/guidelines.md#proxy-component-pattern) 區段，核心元件不可從內容直接參照。 為避免出現上述情況，這些元件都屬於隱藏的元件群組( `.core-wcm` 或 `.core-wcm-form`)，因此不會直接在編輯器中顯示。

相反地，必須建立網站專用元件，這些元件會定義要向頁面作者顯示的所需元件名稱和群組，並將每個元件參照為其超級型別。 這些網站專用元件有時稱為「代理主機元件」，因為它們不需要包含任何內容，並且主要用於定義用於網站的元件版本。 不過，自訂 [核心元件](/help/developing/customizing.md)，這些Proxy元件在標籤和邏輯自訂方面會發揮重要作用。

因此，針對每個需要用於網站的核心元件，您必須：

1. 在網站的元件資料夾中建立對應的Proxy元件。

   **範例**
下 `/apps/my-site/components` 建立型別的標題節點 `cq:Component`

1. 指向具有超級型別的對應核心元件版本。

   **範例**
新增下列屬性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定義元件的群組、標題及說明（選擇性）。 這些值是專案專屬的值，可指定向作者公開元件的方式。

   **範例**
新增下列屬性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例如，檢視 [WKND網站的標題元件](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml)，這是以這種方式建置的Proxy元件的良好範例。

## 載入核心樣式 {#load-the-core-styles}

1. 如果尚未完成，請建立 [使用者端資源庫](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html) 包含您的網站所需的所有CSS和JS檔案。
1. 在網站的使用者端資料庫上，將相依性新增至可能需要的核心元件。 這是透過新增 `embed` 屬性。

   例如，若要包含所有v1核心元件的使用者端資料庫，則要新增的屬性會是：

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

在移到下一個區段之前，請確定您的Proxy元件和使用者端程式庫已部署到您的AEM環境。

## 允許元件 {#allow-the-components}

下列步驟會在中執行 [範本編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

1. 在範本編輯器中，選取版面容器，然後開啟其原則。
1. 在「允許的元件」清單中，選取先前建立的Proxy元件，這些元件應顯示在指派給它們的元件群組下。 完成後，套用變更。
1. 或者，對於具有設計對話方塊的元件，可以預先設定它們。

就是這樣！在從編輯過的範本建立的頁面中，您現在應該能夠使用新建立的元件。

**閱讀後續章節：**

* [自訂核心元件](/help/developing/customizing.md)  — 瞭解如何樣式化和自訂核心元件。
* [元件指導方針](/help/developing/guidelines.md)  — 瞭解核心元件的實作模式。
