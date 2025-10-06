---
title: 容器元件
description: 利用核心元件容器元件，可在頁面上為多個其他元件建立容器。
role: Architect, Developer, Admin, User
exl-id: 53c7190d-44cb-42ff-bc1a-483c7875bcf8
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '767'
ht-degree: 100%

---


# 容器元件{#container-component}

利用核心元件容器元件，可在頁面上為多個其他元件建立容器。

{{traditional-aem}}

## 用途 {#usage}

核心元件容器元件可在頁面上為多個其他元件建立容器，並可用於分組其他元件及套用通用樣式或版面。

* 可以在[設定對話框](#configure-dialog)中選取容器的屬性。
* 將容器元件新增至頁面時，可在[設計對話框](#design-dialog)中定義預設值。

## 版本和相容性 {#version-and-compatibility}

容器元件的目前版本為 v1，此版本於 2019 年 6 月隨著核心元件 2.5.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v1 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「容器元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_container)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_container_v1)有關容器元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義容器項目，以及其對頁面訪客的行為與顯示方式。

![容器元件的編輯對話框](/help/assets/container-edit.png)

* **版面** - 此選項定義容器元件的行為或版面行為。
   * **簡單** - 將容器定義為簡單的元件集合
   * **回應式格線** - 將容器定義為 [AEM 回應式版面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **背景顏色** - 透過自由格式的 RGB 值或使用檢色器定義，[視設定而定](#background-tab)
* **背景影像** - 定義容器的背景顏色，[視設定而定](#background-tab)
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可為使用容器元件的內容作者定義可用選項。

### 允許的元件索引標籤 {#allowed-components-tab}

**允許的元件**&#x200B;索引標籤用於定義可供內容作者作為項目新增至容器元件的元件。

[在範本編輯器中定義版面容器的原則與屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)時，允許的元件索引標籤與同名索引標籤的功能相同。

### 預設元件索引標籤 {#default-components-tab}

「預設元件」索引標籤用於定義當特定資產類型放置於容器上時，哪些元件要新增到元件中，類似於[如何在頁面範本上定義預設元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)。

### 回應式設定索引標籤 {#responsive-settings-tab}

![容器元件設計對話框的回應式設定索引標籤](/help/assets/container-design-responsive.png)

* **欄** - 定義產生容器的格線中的欄數。

### 背景索引標籤 {#background-tab}

![容器元件設計對話框的背景索引標籤](/help/assets/container-design-background.png)

* **背景影像**
   * **啟用背景影像** - 選取此選項可讓內容作者定義容器的背景影像。
* **背景顏色**
   * **啟用背景顏色** - 選取此選項可讓內容作者定義容器的背景顏色。
   * **僅色票** - 選取此選項，僅允許內容作者從預先定義的色票中選取容器背景顏色。
      * 只有在選取&#x200B;**啟用背景顏色**&#x200B;時可用
* **允許的色票** - 定義內容作者可從中選擇容器背景顏色的預先定義顏色
   * 使用&#x200B;**新增**&#x200B;按鈕新增預先定義的色票。新增後，就會在清單中新增一個項目，其中包含以下各欄：
   * **值** - 透過 RGB 值手動定義顏色
      * 點選或按一下檢色器，即可調整個別 RGB 值或定義十六進位值，更輕鬆地選取顏色。
   * **刪除** - 點選或按一下，以刪除色票。
   * **重新排列** - 點選或按一下並拖曳，以重新排列色票的順序。

### 樣式索引標籤 {#styles-tab}

容器元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
