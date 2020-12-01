---
title: 容器元件
description: 「核心元件容器」元件可讓您在頁面上建立多個其他元件的容器。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 1%

---


# 容器元件{#container-component}

「核心元件容器」元件可讓您在頁面上建立多個其他元件的容器。

## 使用狀況 {#usage}

「核心元件容器」元件可讓您在頁面上建立多個其他元件的容器，並可用來群組其他元件，以及套用共用樣式或版面。

* 可在[configure dialog](#configure-dialog)中選擇容器的屬性。
* 將容器元件新增至頁面時的預設值，可在[設計對話方塊](#design-dialog)中定義。

## 版本和相容性{#version-and-compatibility}

目前的容器元件版本為v1，此版本於2019年6月隨核心元件2.5.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗容器元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_container)。

## 技術詳細資訊{#technical-details}

有關容器元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_container_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

「設定」對話方塊可讓內容作者定義容器項目，以及該項目對頁面訪客的行為和顯示方式。

![容器元件的編輯對話方塊](/help/assets/container-edit.png)

* **配置** -此選項定義容器元件的行為或配置行為。
   * **Simple**  —— 將容器定義為元件的簡單集合
   * **回應式格線** -將容器定義為 [AEM回應式版面](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **背景顏色** -可定義為自由格式的RGB值，或使用檢色器(視配 [置而定)](#background-tab)
* **背景影像** -定義容器的背景顏色，視  [組態而定](#background-tab)
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義使用容器元件的內容作者可用的選項。

### 允許的元件頁籤{#allowed-components-tab}

**允許的元件**&#x200B;標籤用於定義內容作者可將哪些元件新增為容器元件的項目。

當[在範本編輯器中定義版面容器的原則和屬性時，「允許的元件」標籤的運作方式與相同名稱的標籤相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 預設元件頁籤{#default-components-tab}

當容器上放置特定資產類型時，「預設元件」標籤會用來定義要新增至元件的元件，類似於頁面範本[如何定義預設元件。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 回應式設定標籤{#responsive-settings-tab}

![容器元件設計對話方塊的回應式設定標籤](/help/assets/container-design-responsive.png)

* **欄** -定義產生容器格線中的欄數。

### 背景標籤{#background-tab}

![「容器元件」設計對話框的背景標籤](/help/assets/container-design-background.png)

* **背景影像**
   * **啟用背景影像** -選取此選項可讓內容作者為容器定義背景影像。
* **背景色彩**
   * **啟用背景顏色** -選取此選項可讓內容作者為容器定義背景顏色。
   * **僅限色票** -選取此選項，僅允許內容作者從預先定義的容器背景色票中選取。
      * 僅在選擇「啟用背景顏色&#x200B;**」時可用**
* **允許的色票** -定義預先定義的顏色，內容作者可從中選取容器背景顏色
   * 使用&#x200B;**Add**&#x200B;按鈕添加預定義的色板。 新增後，會將一個項目新增至清單，其中包含下列欄：
   * **值** -通過RGB值手動定義顏色
      * 點選或按一下檢色器，可調整個別RGB值或定義十六進位值，以更輕鬆地選取顏色。
   * **刪除** -點選或按一下以刪除色票。
   * **重新排列** -點選或按一下並拖曳以重新排列色票順序。

### 樣式標籤{#styles-tab}

容器元件支援AEM [Style System](/help/get-started/authoring.md#component-styling)。
