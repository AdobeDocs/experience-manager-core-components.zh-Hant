---
title: 內容片段元件
description: 核心元件內容片段元件可顯示內容片段。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 551ff2a1-f8db-490c-84a3-4255b364fc83
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 5%

---

# 內容片段元件{#content-fragment-component}

核心元件內容片段元件允許顯示[內容片段](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

>[!NOTE]
>
>核心元件2.4.0版之前，內容片段元件是核心元件的擴充功能，必須個別下載並明確啟用。

## 使用狀況 {#usage}

核心元件內容片段元件允許在頁面上包含[內容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

* 可在[配置對話框](#configure-dialog)中選擇片段及其屬性。
* 可在[設計對話框](#design-dialog)中定義用於處理某些影像和網格的資源類型。
* 編輯選項將在[內容片段編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html)中開啟所選片段。

## 版本和相容性{#version-and-compatibility}

目前的內容片段元件版本為v1，已於2017年10月隨核心元件1.1.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

>[!NOTE]
>
>在2.4.0版之前，內容片段元件位於擴充功能資料夾中。
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>從2.4.0開始，已移至下列位置。
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>雖然兩者皆為v1，但從擴充功能資料夾使用的任何內容片段元件在升級至核心元件2.4.0版或更新版本時，都需要移轉其相關的代理元件，才能使用新的資源類型。

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗內容片段元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_cf)。

## 技術詳細資訊{#technical-details}

如需內容片段元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

設定對話方塊可讓內容作者定義要包含的內容片段及該片段的元素。

### 屬性頁簽{#properties-tab}

![內容片段元件](/help/assets/content-fragment-edit-properties.png)

* **內容片段**

   * 所需內容片段的路徑
   * **選擇對話框**&#x200B;可用於查找片段

* **顯示模式**
   * **單行文本元素**  — 啟用一個多行文本元素的選擇並啟用段落控制選項
   * **多個元素**  — 允許選取所選內容片段的一或多個元素
* **元素**  — 要包括的內容片段的元素或元素
* **變化**  — 要使用的內容片段變化(預設為 **主版**)

* **段落**

   * **全部**  — 顯示所有段落
   * **範圍**

      * 指定應顯示的段落範圍，以分號分隔
      * 例如`1;3-5;7;9-*`，包括第1、第3至第5、第7和第9至最後段落
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

### 段落控制頁簽{#paragraph-control-tab}

選取&#x200B;**多個元素**&#x200B;模式時，此標籤不可用。

![內容片段元件](/help/assets/content-fragment-edit-paragraph.png)

* **段落**  — 允許選擇所有段落或範圍
* **將標題當作自己的段落處理**

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義用於處理混合媒體影像和回應式格線的資源類型。

![內容片段元件的設計對話方塊](/help/assets/content-fragment-design.png)

* **內部回應式格線**

   * 用於內部回應式格線的Sling資源類型

## Adobe客戶端資料層{#data-layer}

內容片段元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
