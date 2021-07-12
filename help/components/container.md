---
title: 容器元件
description: 核心元件容器元件可為頁面上的多個其他元件建立容器。
role: Architect, Developer, Admin, User
exl-id: 53c7190d-44cb-42ff-bc1a-483c7875bcf8
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 1%

---

# 容器元件{#container-component}

核心元件容器元件可為頁面上的多個其他元件建立容器。

## 使用狀況 {#usage}

核心元件容器元件允許為頁面上的多個其他元件建立容器，並可用於將其他元件分組和應用通用樣式或佈局。

* 可在[配置對話框](#configure-dialog)中選擇容器的屬性。
* 將容器元件新增至頁面時的預設值，可在[設計對話方塊](#design-dialog)中定義。

## 版本與相容性 {#version-and-compatibility}

容器元件的目前版本為v1，此版本於2019年6月隨核心元件2.5.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗容器元件並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_container)。

## 技術詳細資訊 {#technical-details}

若需容器元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_container_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

「設定」對話方塊可讓內容作者定義容器項目，以及容器項目的行為和顯示方式，供造訪頁面的訪客使用。

![容器元件的編輯對話方塊](/help/assets/container-edit.png)

* **配置**  — 此選項定義容器元件的行為或配置行為。
   * **簡單**  — 將容器定義為元件的簡單集合
   * **回應式格線**  — 將容器定義為 [AEM回應式版面](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **背景顏色**  — 可定義為自由格式RGB值，或使用檢色器，視 [配置而定](#background-tab)
* **背景影像**  — 根據設定定義容器的  [背景顏色](#background-tab)
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義使用容器元件的內容作者可用的選項。

### 「允許的元件」頁簽 {#allowed-components-tab}

**允許的元件**&#x200B;標籤用於定義哪些元件可由內容作者新增為容器元件的項目。

[在模板編輯器中定義佈局容器的策略和屬性時，「允許的元件」頁簽的功能與同名頁簽的功能相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 預設元件頁簽 {#default-components-tab}

「預設元件」索引標籤用於定義將特定資產類型拖放到容器上時，要將哪個元件新增至元件，類似於[在頁面範本](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)上定義預設元件的方式。

### 回應式設定標籤 {#responsive-settings-tab}

![容器元件設計對話方塊的回應式設定標籤](/help/assets/container-design-responsive.png)

* **欄**  — 在產生的容器的格線中定義欄數。

### 背景標籤 {#background-tab}

![「容器元件」設計對話框的背景頁簽](/help/assets/container-design-background.png)

* **背景影像**
   * **啟用背景影像**  — 選取此選項，讓內容作者可定義容器的背景影像。
* **背景色彩**
   * **啟用背景顏色**  — 選取此選項，讓內容作者可定義容器的背景顏色。
   * **僅限色票**  — 選取此選項，僅允許內容作者從預先定義的容器背景顏色色票中選取。
      * 僅當選擇&#x200B;**啟用背景顏色**&#x200B;時可用
* **允許的色票**  — 定義預先定義的顏色，內容作者可從中選取容器背景顏色
   * 使用&#x200B;**Add**&#x200B;按鈕添加預定義的色板。 新增後，會將項目新增至清單，其中包含下列欄：
   * **值**  — 透過RGB值手動定義顏色
      * 點選或按一下檢色器，借由調整個別RGB值或定義十六進位值，更輕鬆地選取顏色。
   * **刪除**  — 點選或按一下以刪除色票。
   * **重新排列**  — 點選或按一下並拖曳以重新排列色票的順序。

### 樣式標籤 {#styles-tab}

容器元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
