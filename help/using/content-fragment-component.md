---
title: 內容片段元件
seo-title: 內容片段元件
description: 'null'
seo-description: 核心元件內容片段元件允許顯示內容片段。
uuid: ec807de9-f76c-4850-9ece-c3e439a1d626
contentOwner: 使用者
content-type: 引用
topic-tags: 編寫
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新功能
discoiquuid: f093f58e-9755-4a4f-803a-ab93a50e6870
translation-type: tm+mt
source-git-commit: 548972c65751b594cd62234d4681634a60fa41e2

---


# Content Fragment Component{#content-fragment-component}

The Core Component Content Fragment component allows for the display of a content fragment.[](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html)

>[!NOTE]
>
>Prior to release 2.4.0 of the Core Components, the Content Fragment component was available as an extension to the core components and had to be separately downloaded and explicitly enabled.

## 使用狀況 {#usage}

The Core Component Content Fragment Component allows for the inclusion of a content fragment on a page.[](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html)

* The fragment and its properties can be selected in the configure dialog.[](#configure-dialog)
* Resource types to handle certain images and grids can be defined in the design dialog.[](#design-dialog)
* 編輯選項將在內容片段編輯器中打 [開所選片段](https://helpx.adobe.com/content/help/en/experience-manager/6-5/assets/using/content-fragments.html)。

## 版本與相容性 {#version-and-compatibility}

目前的內容片段元件版本為v1，此版本於2017年10月隨核心元件1.1.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

>[!NOTE]
>
>在2.4.0版之前，內容片段元件位於擴充功能資料夾中。
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>從2.4.0開始，它已移至下列位置。
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>雖然兩者皆為v1，但從擴充功能資料夾使用的任何內容片段元件在升級至核心元件2.4.0版或更新版本時，都需要移轉其相關的代理元件，才能使用新的資源類型。

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗內容片段元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元件 [庫](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)。

## 技術詳細資訊 {#technical-details}

有關內容片段元件的最新技術文 [件可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/contentfragment/v1/contentfragment)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](developing.md)。

## 配置對話框 {#configure-dialog}

The configure dialog allows the content author to define the which content fragment and the elements of that fragment to be included.

![](assets/chlimage_1-87.png)

* **內容片段**

   * 所需內容片段的路徑
   * The Selection Dialog can be used to locate the fragment ****

* **元素** -要包含的內容片段元素
* **Variation - Which variation of the content fragment to use (defaults to Master)******

* **段落**

   * **All - Display all paragraphs**
   * **範圍**

      * 指定應顯示的段落範圍，以分號分隔
      * 例 `1;3-5;7;9-*` 如包括1、3至5、7、9至最後段落

* **將標題當做自己的段落處理**

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義用於處理混合媒體影像和自適應網格的資源類型。

![](assets/chlimage_1-88.png)

* **混合媒體影像類型**

   * 用於呈現混合媒體影像的 Sling 資源類型

* **內部回應式格線**

   * 用於內部回應式格線的Sling資源類型