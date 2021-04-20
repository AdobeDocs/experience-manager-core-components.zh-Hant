---
title: 內容片段元件
description: 核心元件內容片段元件允許顯示內容片段。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 5%

---


# 內容片段元件{#content-fragment-component}

核心元件內容片段元件允許顯示[內容片段](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

>[!NOTE]
>
>在核心元件2.4.0版之前，內容片段元件是核心元件的擴充功能，必須個別下載並明確啟用。

## 使用狀況 {#usage}

核心元件內容片段元件允許在頁面上包含[內容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

* 可在[configure dialog](#configure-dialog)中選擇該片段及其屬性。
* 可在[設計對話框](#design-dialog)中定義用於處理特定影像和網格的資源類型。
* 編輯選項將在[內容片段編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html)中開啟選定片段。

## 版本和相容性{#version-and-compatibility}

目前的內容片段元件版本為v1，此版本於2017年10月隨核心元件1.1.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
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

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗內容片段元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_cf)。

## 技術詳細資訊{#technical-details}

有關內容片段元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

設定對話方塊可讓內容作者定義要包含的內容片段和該片段的元素。

### 屬性頁籤{#properties-tab}

![內容片段元件](/help/assets/content-fragment-edit-properties.png)

* **內容片段**

   * 所需內容片段的路徑
   * **選擇對話框**&#x200B;可用於定位片段

* **顯示模式**
   * **單一文字元素** -啟用選取一個多行文字元素並啟用段落控制選項
   * **多元素** -允許選擇所選內容片段的一個或多個元素
* **元素** -要包含的內容片段的元素
* **Variation**  —要使用的內容片段變數(預設為 **Master**)

* **段落**

   * **全部** -顯示所有段落
   * **範圍**

      * 指定應顯示的段落範圍，以分號分隔
      * 例如`1;3-5;7;9-*`以包含1、3到5、7和9到最後段落
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

### 段落控制標籤{#paragraph-control-tab}

當選擇&#x200B;**多元素**&#x200B;模式時，此頁籤不可用。

![內容片段元件](/help/assets/content-fragment-edit-paragraph.png)

* **段落** -允許選擇所有段落或範圍
* **將標題當做自己的段落處理**

## 設計對話框{#design-dialog}

設計對話框允許模板作者定義用於處理混合媒體影像和自適應網格的資源類型。

![內容片段元件的設計對話方塊](/help/assets/content-fragment-design.png)

* **內部回應式格線**

   * 用於內部回應式格線的Sling資源類型

## Adobe客戶端資料層{#data-layer}

內容片段元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
