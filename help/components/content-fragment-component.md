---
title: 內容片段元件
description: 核心元件內容片段元件允許顯示內容片段。
role: Architect, Developer, Admin, User
exl-id: 551ff2a1-f8db-490c-84a3-4255b364fc83
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 2%

---

# 內容片段元件{#content-fragment-component}

核心元件內容片段元件允許顯示 [內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

>[!NOTE]
>
>在核心元件2.4.0版之前，內容片段元件可作為核心元件的擴展，必須單獨下載並明確啟用。

## 使用狀況 {#usage}

核心元件內容片段元件允許包含 [內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 在頁面上。

* 可在 [配置對話框](#configure-dialog)。
* 可以在中定義處理某些影像和網格的資源類型 [設計對話框](#design-dialog)。
* 編輯選項將在 [內容片段編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html)。

## 版本和相容性 {#version-and-compatibility}

內容片段元件的當前版本為v1，該版本於2017年10月隨核心元件1.1.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |

>[!NOTE]
>
>在2.4.0版之前，內容片段元件位於擴展資料夾中。
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>已從2.4.0移動到以下位置。
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>雖然兩者都是v1 ，但從擴展資料夾中使用的任何內容片段元件在升級到2.4.0版或更高版本的核心元件時都需要遷移其相關代理元件以使用新的資源類型。

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗內容片段元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_cf)。

## 技術詳細資訊 {#technical-details}

有關內容片段元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_cf_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義要包括的內容片段和該片段的元素。

### 屬性頁籤 {#properties-tab}

![內容片段元件](/help/assets/content-fragment-edit-properties.png)

* **內容片段**

   * 所需內容片段的路徑
   * 的 **選擇對話框** 可以用來定位碎片

* **顯示模式**
   * **單文本元素**  — 啟用選擇一個多行文本元素並啟用段落控制選項
   * **多元素**  — 允許選擇所選內容片段的一個或多個元素
* **元素**  — 要包括的內容片段的元素
* **變異**  — 要使用的內容片段的哪個變體(預設為 **母版**)

* **段落**

   * **全部**  — 顯示所有段落
   * **範圍**

      * 指定應顯示的段落範圍，用分號分隔
      * 例如 `1;3-5;7;9-*` 包括第1、3至5、7、9至最後段
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

### 段落控制項頁籤 {#paragraph-control-tab}

當 **多元素** 的下界。

![內容片段元件](/help/assets/content-fragment-edit-paragraph.png)

* **段落**  — 允許選擇所有段落或範圍
* **將標題作為自己的段落處理**

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義用於處理混合媒體影像和響應網格的資源類型。

![內容片段元件的「設計」對話框](/help/assets/content-fragment-design.png)

* **內部回應式格線**

   * 用於內部響應網格的Sling資源類型

## Adobe客戶端資料層 {#data-layer}

內容片段元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
