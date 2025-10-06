---
title: 內容片段元件
description: 「核心元件內容片段」元件允許顯示內容片段。
role: Architect, Developer, Admin, User
exl-id: 551ff2a1-f8db-490c-84a3-4255b364fc83
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '659'
ht-degree: 100%

---


# 內容片段元件{#content-fragment-component}

「核心元件內容片段」元件允許顯示[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

>[!NOTE]
>
>在核心元件 2.4.0 版之前，內容片段元件可作為核心元件的擴充功能使用，且必須單獨下載並明確啟用。

{{traditional-aem}}

## 用途 {#usage}

「核心元件內容片段元件」允許在頁面上包含[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

* 可在[設定對話框](#configure-dialog)中選取片段及其屬性。
* 可在[設計對話框](#design-dialog)中定義處理特定影像和格線的資源類型。
* 編輯選項將在[內容片段編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html)中開啟已選取的片段。

## 版本和相容性 {#version-and-compatibility}

內容片段元件的目前版本為 v1，此版本於 2017 年 10 月隨著核心元件 1.1.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v1 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |

>[!NOTE]
>
>在版本 2.4.0 之前，內容片段元件位於擴充功能資料夾中。
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>從 2.4.0 版開始，已移至下列位置。
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>雖然兩者都是 v1，但在升級至發行版本 2.4.0 或更新版本的核心元件時，從擴充功能資料夾使用的任何內容片段元件都必須移轉其相關 Proxy 元件，才能使用新的資源類型。

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「內容片段元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_cf)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_cf_v1)有關內容片段元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義要包含的內容片段和片段元素。

### 屬性索引標籤 {#properties-tab}

![內容片段元件](/help/assets/content-fragment-edit-properties.png)

* **內容片段**

   * 所需內容片段的路徑
   * **選取對話框**&#x200B;可用來尋找片段

* **顯示模式**
   * **單一文字元素** - 啟用選取一個多行文字元素，並啟用段落控制選項
   * **多個元素** - 允許選取一個或多個所選內容片段的元素
* **元素** - 要包含的內容片段的一個或多個元素
* **變化版本** - 要使用的內容片段變化版本 (預設為&#x200B;**主版**)

* **段落**

   * **全部** - 顯示所有段落
   * **範圍**

      * 指定應顯示的段落範圍，並以分號分隔
      * 例如 `1;3-5;7;9-*`，以包含第 1 段、第 3 至第 5 段、第 7 段，以及第 9 至最後一段
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

### 段落控制索引標籤 {#paragraph-control-tab}

選取&#x200B;**多個元素**&#x200B;模式時，此索引標籤無法使用。

![內容片段元件](/help/assets/content-fragment-edit-paragraph.png)

* **段落** - 允許選取所有段落或一個範圍
* **將標題視為單獨段落處理**

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義用於處理混合媒體影像和回應式格線的資源類型。

![內容片段元件的設計對話框](/help/assets/content-fragment-design.png)

* **內部回應式格線**

   * 用於內部回應式格線的 Sling 資源類型

## Adobe Client Data Layer {#data-layer}

「內容片段元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
