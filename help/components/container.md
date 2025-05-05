---
title: 容器元件
description: 利用核心元件容器元件，可在頁面上為多個其他元件建立容器。
role: Architect, Developer, Admin, User
exl-id: 53c7190d-44cb-42ff-bc1a-483c7875bcf8
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 1%

---

# 容器元件{#container-component}

利用核心元件容器元件，可在頁面上為多個其他元件建立容器。

## 使用情況 {#usage}

核心元件容器元件可在頁面上為多個其他元件建立容器，並可用於分組其他元件及套用通用樣式或版面。

* 可在[設定對話方塊](#configure-dialog)中選取容器的屬性。
* 將容器元件新增至頁面時的預設值可以在[設計對話方塊](#design-dialog)中定義。

## 版本和相容性 {#version-and-compatibility}

容器元件的目前版本是v1，此版本隨2019年6月的核心元件發行版本2.5.0的發佈引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|--- |--- |---|---|---|
| v1 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗容器元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_container)。

## 技術細節 {#technical-details}

在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_container_v1)上可找到容器元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義容器專案，以及對於頁面的訪客它會如何表現和顯示。

![容器元件](/help/assets/container-edit.png)的編輯對話方塊

* **配置** — 此選項定義容器元件的行為或配置行為。
   * **簡單** — 將容器定義為簡單的元件集合
   * **回應式格線** — 將容器定義為[AEM回應式配置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **背景色彩** — 定義為自由格式的RGB值，或使用檢色器，[視組態而定](#background-tab)
* **背景影像** — 定義容器的背景顏色，[視組態而定](#background-tab)
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義哪些選項可供使用容器元件的內容作者使用。

### 允許的元件標籤 {#allowed-components-tab}

**允許的元件**&#x200B;索引標籤是用來定義哪些元件可由內容作者新增為容器元件的專案。

當[在範本編輯器中定義配置容器的原則與屬性時，「允許的元件」索引標籤的功能與相同名稱的索引標籤相同。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 預設元件標籤 {#default-components-tab}

「預設元件」索引標籤用於定義在特定資產型別放到容器上時，要新增到元件的元件，類似於[如何在頁面範本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)上定義預設元件。

### 回應式設定標籤 {#responsive-settings-tab}

容器元件之設計對話方塊的![回應式設定標籤](/help/assets/container-design-responsive.png)

* **欄** — 定義產生容器的格線中的欄數。

### 背景索引標籤 {#background-tab}

容器元件![&#128279;](/help/assets/container-design-background.png)之設計對話方塊的背景標籤

* **背景影像**
   * **啟用背景影像** — 選取此選項可讓內容作者定義容器的背景影像。
* **背景色彩**
   * **啟用背景顏色** — 選取此選項可讓內容作者定義容器的背景顏色。
   * **僅色票** — 選取此選項，僅允許內容作者從預先定義的色票中選取容器背景顏色。
      * 只有在選取&#x200B;**啟用背景顏色**&#x200B;時可用
* **允許的色票** — 定義內容作者可從中選擇容器背景顏色的預定義顏色
   * 使用&#x200B;**新增**&#x200B;按鈕新增預先定義的色票。 新增專案後，專案會新增到清單中，包含以下欄：
   * **值** — 透過RGB值手動定義顏色
      * 點選或按一下檢色器，即可調整個別RGB值或定義十六進位值，更輕鬆地選取顏色。
   * **刪除** — 點選或按一下以刪除色票。
   * **重新排列** — 點選或按一下並拖曳以重新排列色票。

### 樣式索引標籤 {#styles-tab}

容器元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
