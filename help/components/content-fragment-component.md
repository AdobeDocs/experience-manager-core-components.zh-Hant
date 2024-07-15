---
title: 內容片段元件
description: 利用核心元件內容片段元件，可顯示內容片段。
role: Architect, Developer, Admin, User
exl-id: 551ff2a1-f8db-490c-84a3-4255b364fc83
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 1%

---

# 內容片段元件{#content-fragment-component}

核心元件內容片段元件允許顯示[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

>[!NOTE]
>
>在核心元件2.4.0版之前，內容片段元件可作為核心元件的擴充功能使用，且必須單獨下載並明確啟用。

## 使用情況 {#usage}

核心元件內容片段元件允許在頁面上包含[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

* 可在[設定對話方塊](#configure-dialog)中選取片段及其屬性。
* 可在[設計對話方塊](#design-dialog)中定義要處理特定影像和網格的資源型別。
* 編輯選項會在[內容片段編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html)中開啟選取的片段。

## 版本和相容性 {#version-and-compatibility}

內容片段元件的目前版本是v1，此版本隨2017年10月的核心元件1.1.0版引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 |

>[!NOTE]
>
>在版本2.4.0之前，內容片段元件位於extensions資料夾中。
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>從2.4.0版開始，已移至下列位置。
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>雖然兩者都是v1，但在升級至發行版本2.4.0或更新版本的核心元件時，從extensions資料夾使用的任何內容片段元件都必須移轉其相關Proxy元件，才能使用新的資源型別。

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗內容片段元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_cf)。

## 技術細節 {#technical-details}

在GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1)上可找到有關內容片段元件[的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義要包含的內容片段及該片段的元素。

### 屬性標籤 {#properties-tab}

![內容片段元件](/help/assets/content-fragment-edit-properties.png)

* **內容片段**

   * 所需內容片段的路徑
   * **選取範圍對話方塊**&#x200B;可用來尋找片段

* **顯示模式**
   * **單一文字元素** — 啟用選取一個多行文字元素並啟用段落控制選項
   * **多個元素** — 允許選取一或多個所選內容片段的元素
* **元素** — 要包含的內容片段的一或多個元素
* **變數** — 要使用的內容片段變數（預設為&#x200B;**Master**）

* **段落**

   * **全部** — 顯示所有段落
   * **範圍**

      * 指定應顯示的段落範圍（以分號分隔）
      * 例如，如果執行個體`1;3-5;7;9-*`包含第一段、第三段到第五段、第七段、第九段到最後一段
* **ID** — 此選項可控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 段落控制標籤 {#paragraph-control-tab}

選取&#x200B;**多個元素**&#x200B;模式時，此索引標籤無法使用。

![內容片段元件](/help/assets/content-fragment-edit-paragraph.png)

* **段落** — 允許選取所有段落或一個範圍
* **將標題處理為它們自己的段落**

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義用於處理混合媒體影像和回應式格線的資源型別。

![內容片段元件](/help/assets/content-fragment-design.png)的「設計」對話方塊

* **內部回應式格線**

   * 用於內部回應式格線的Sling資源型別

## Adobe使用者端資料層 {#data-layer}

內容片段元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
