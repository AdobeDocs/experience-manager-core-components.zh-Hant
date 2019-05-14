---
title: 內容片段元件
seo-title: 內容片段元件
description: 'null'
seo-description: 核心元件內容片段元件允許顯示內容片段。
uuid: ec807de9-f76 c-4850-9ee-c3 e439 a1 d626
contentOwner: 使用者
content-type: 引用
topic-tags: 製作
products: SG_ PERIENCENCENAGER/CORECOMPonation@-@new
discoiquuid: f093f58e-9755-4a4f-803a-ab93 a50 e6870
translation-type: tm+mt
source-git-commit: 40ce01fdb0f22e3ee3b376a3684a766bd7e7bc11

---


# 內容片段元件{#content-fragment-component}

核心元件內容片段元件允許顯示 [內容片段](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html)。

>[!NOTE]
>
>在核心元件發行2.4.0之前，內容片段元件可作為核心元件的擴充功能，必須個別下載並明確啓用。

## 使用狀況 {#usage}

核心元件內容片段元件可讓您將 [內容片段](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html) 加入頁面中。

* 您可以在 [設定對話方塊中選取片段及其屬性](#configure-dialog)。
* 可在 [設計對話方塊中定義處理特定影像和格線的資源類型](#design-dialog)。
* 編輯選項會在 [內容片段編輯器中開啓選取的片段](https://helpx.adobe.com/content/help/en/experience-manager/6-5/assets/using/content-fragments.html)。

## 版本與相容性 {#version-and-compatibility}

目前版本的內容片段元件是v1，是於2017年10月發行的1.1.0版，現在已於本文中說明。

下表列出元件的所有支援版本、元件版本與元件相容的AEM版本，以及舊版文件的連結。

| 元件版本 | AEM6.3 | AEM6.4 | AEM6.5 |
|--- |--- |--- |---|
| v1 | 相容相容性 | 相容相容性 | 相容相容性 |

如需核心元件版本和版本的詳細資訊，請參閱文件 [核心元件版本](versions.md)。

## 元件輸出範例 {#sample-component-output}

若要體驗內容片段元件，以及查看其組態選項以及HTML和JSON輸出的範例，請造訪 [元件庫](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)。

## 技術細節 {#technical-details}

有關內容片段元件 [的最新技術文件，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/contentfragment/v1/contentfragment)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文件](developing.md)。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義要包含該片段的內容片段和元素。

![](assets/chlimage_1-87.png)

* **內容片段**

   * 所需內容片段的路徑
   * **「選取對話方塊」** 可用來尋找片段

* **元素** -要納入內容片段的元素
* **變數** -要使用的內容片段變化(預設為 **主**)

* **段落**

   * **全部** -顯示所有段落
   * **範圍**

      * 指定應顯示的段落範圍，以分號分隔
      * 例如 `1;3-5;7;9-*` ，將第一個、第三個到第個第個和第個項目包含到最後一個段落中

* **將標題當做自己的段落**

## 設計對話方塊 {#design-dialog}

此設計對話方塊可讓範本作者定義用於處理混合媒體影像和回應式格線的資源類型。

![](assets/chlimage_1-88.png)

* **混合媒體影像類型**

   * 用於呈現混合媒體影像的 Sling 資源類型

* **內部回應式格線**

   * 用於內部回應格線的Sling資源類型