---
title: 內容片段元件
description: 核心元件內容片段元件允許顯示內容片段。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 內容片段元件{#content-fragment-component}

核心元件內容片段元件可顯示內容 [片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

>[!NOTE]
>
>在核心元件2.4.0版之前，內容片段元件是核心元件的擴充功能，必須個別下載並明確啟用。

## 使用狀況 {#usage}

核心元件內容片段元件允許在頁面 [上包含內容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 。

* 可在「配置」對話框中選擇該片段及其 [屬性](#configure-dialog)。
* 可在設計對話框中定義用於處理特定影像和網格的 [資源類型](#design-dialog)。
* 編輯選項將在內容片段編輯器中打 [開所選片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html)。

## 版本與相容性 {#version-and-compatibility}

目前的內容片段元件版本為v1，此版本於2017年10月隨核心元件1.1.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM As a Cloud Service |
|--- |--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 | 相容 |

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

如需核心元件版本與版本的詳細資訊，請參閱檔案核 [心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

若要體驗內容片段元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元件 [庫](https://adobe.com/go/aem_cmp_library_cf)。

## 技術詳細資訊 {#technical-details}

有關內容片段元件的最新技術文 [件可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_cf_v1)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

設定對話方塊可讓內容作者定義要包含的內容片段和該片段的元素。

![](/help/assets/chlimage_1-87.png)

* **內容片段**

   * 所需內容片段的路徑
   * 「選 **擇對話框** 」可用於定位片段

* **元素** -要包含的內容片段元素
* **Variation** —— 要使用的內容片段變數(預設為 **Master**)

* **段落**

   * **全部** -顯示所有段落
   * **範圍**

      * 指定應顯示的段落範圍，以分號分隔
      * 例 `1;3-5;7;9-*` 如包括1、3至5、7、9至最後段落

* **將標題當做自己的段落處理**

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義用於處理混合媒體影像和自適應網格的資源類型。

![](/help/assets/chlimage_1-88.png)

* **混合媒體影像類型**

   * 用於呈現混合媒體影像的 Sling 資源類型

* **內部回應式格線**

   * 用於內部回應式格線的Sling資源類型

