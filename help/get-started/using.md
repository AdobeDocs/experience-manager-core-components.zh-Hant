---
title: 使用核心元件
description: 「要在您自己的項目中使用核心元件啟動並運行，需要執行三個步驟：下載和安裝、建立代理元件、載入核心樣式，以及允許模板上的元件。」
role: Architect, Developer, Admin, User
exl-id: ee2d25e4-e2b8-4ecc-a62c-f0066de2bf2d
source-git-commit: 8beae61676340e8aafaee469018d865ea7ed934e
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 2%

---

# 使用核心元件{#using-core-components}

要在您自己的項目中使用核心元件啟動並運行，有四個步驟，這些步驟在以下各節中逐個詳細介紹：

1. [下載並安裝](#download-and-install)
1. [建立代理元件](#create-proxy-components)
1. [載入核心樣式](#load-the-core-styles)
1. [啟用元件](#allow-the-components)

>[!TIP]
>
>有關如何從頭開始使用項目設定、核心元件、可編輯模板、客戶端庫和元件開發的更多說明，可能需要以下多部分教程：\
>[AEM Sites - WKND 教學課程快速入門](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hant)

>[!TIP]
>
>如果使用 [原型AEM計畫，](/help/developing/archetype/overview.md) 核心元件會根據Adobe的最佳實踐建議自動包含在您的項目中。

## 下載並安裝 {#download-and-install}

核心元件背後的驅動思想之一是靈活性。 更經常地發佈新版本的核心元件使Adobe在提供新功能時更加靈活。 開發人員也可以靈活地選擇將哪些元件整合到項目中，以及希望更新這些元件的頻率。 這將導致對核心元件和核心元件AEM進行單獨的發佈過程。

因此，無論您是以雲服AEM務運行還是以內部部署運行，都會確定安裝步驟。

### AEM as a Cloud Service  {#aemaacs}

沒有第一步！ AEMas a Cloud Service自動附帶最新版本的核心元件。 正如AEMaaCS為您提供最新功能AEM一樣，AEMaCS會自動使您瞭解最新版本的核心元件。

在AEMaCS上使用核心元件時，應注意以下幾點：

* 核心元件包含在 `/libs`。
* 如果項目生成管道再次包括核心元件作為日誌的一部分，則該管道將在日誌中生成警告 `/apps` 並將忽略作為項目一部分嵌入的版本。
   * 在即將發佈的版本中，包括核心元件將再次使管道生成失敗。
* 如果您的項目以前在 `/apps`。 [你可能需要調整項目。](/help/developing/overview.md#via-aemaacs)
* 即使核心元件現在 `/libs`，建議不要在 `/apps`。 [代理元件模式](/help/developing/guidelines.md#proxy-component-pattern) 如果需要定制元件的任何方面，則應使用。
* 為了 [目錄元件](/help/components/tableofcontents.md) 要呈現其內容，需要在OSGi中配置篩選器。
   * [請參閱元件的GitHub文檔](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1) 的子菜單。

### AEM6.5和之前版本 {#aem-65}

在生產模式（沒有示例內容）下啟動時，核心元件不是快速啟動的一部分。 所以，你的第一步是 [從GitHub下載最新發佈的內容包](https://github.com/adobe/aem-core-wcm-components/releases/latest) 並安裝到您的環AEM境中。

有幾種方法可以自動執行此操作，但在實例上快速安裝內容包最簡單的方法是使用包管理器；見 [安裝包](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages)。 此外，一旦您的發佈實例也在運行，您需要將該包複製到發佈者；見 [複製包](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages)。

## 建立代理元件 {#create-proxy-components}

由於在 [代理元件模式](/help/developing/guidelines.md#proxy-component-pattern) 部分，核心元件不能從內容中直接引用。 為了避免這種情況，它們都屬於隱藏的元件組( `.core-wcm` 或 `.core-wcm-form`)，這將阻止它們直接出現在編輯器中。

相反，必須建立特定於站點的元件，這些元件定義要顯示給頁面作者的所需元件名稱和組，並將每個元件作為其超級類型引用到核心元件。 這些特定於站點的元件有時稱為「代理元件」，因為它們不需要包含任何元件，並且主要用於定義用於站點的元件的版本。 但是，當自定義 [核心元件](/help/developing/customizing.md)這些代理元件對標籤和邏輯定制起著至關重要的作用。

因此，對於每個希望用於站點的核心元件，必須：

1. 在站點的元件資料夾中建立相應的代理元件。

   **示例**
下 `/apps/my-site/components` 建立類型的標題節點 `cq:Component`

1. 指向具有超類型的相應核心元件版本。

   **示例**
添加以下屬性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定義元件的組、標題和（可選）說明。 這些值特定於項目，並指示元件如何向作者公開。

   **示例**
添加以下屬性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

比如，看看 [WKND站點的標題元件](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml)，這是以這種方式構建的代理元件的一個很好的例子。

## 載入核心樣式 {#load-the-core-styles}

1. 如果尚未完成，請建立 [客戶端庫](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html) 包含站點所需的所有CSS和JS檔案。
1. 在站點的客戶端庫上，將依賴項添加到可能需要的核心元件中。 通過添加 `embed` 屬性。

   例如，要包括所有v1核心元件的客戶端庫，要添加的屬性為：

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

在轉到下一節之前，請確保已將代理元件和客AEM戶端庫部署到您的環境。

## 允許元件 {#allow-the-components}

在 [模板編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)。

1. 在模板編輯器中，選擇佈局容器並開啟其策略。
1. 在「允許的元件」(Allowed Components)清單中，選擇以前建立的代理元件，這些代理元件應顯示在分配給它們的元件組下。 完成後，應用更改。
1. 或者，對於具有設計對話框的元件，可以預配置它們。

就是這樣！在從編輯的模板建立的頁面中，您現在應該可以使用新建立的元件。

**閱讀後續章節：**

* [定制核心元件](/help/developing/customizing.md)  — 學習如何設計和定制核心元件。
* [元件指南](/help/developing/guidelines.md)  — 瞭解核心元件的實施模式。
