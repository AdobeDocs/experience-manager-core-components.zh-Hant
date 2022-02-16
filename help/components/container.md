---
title: 容器元件
description: 「核心元件容器」元件允許在頁面上為多個附加元件建立容器。
role: Architect, Developer, Admin, User
exl-id: 53c7190d-44cb-42ff-bc1a-483c7875bcf8
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 1%

---

# 容器元件{#container-component}

「核心元件容器」元件允許在頁面上為多個附加元件建立容器。

## 使用狀況 {#usage}

「核心元件容器」元件允許為頁面上的多個附加元件建立容器，並可用於對其他元件進行分組並應用公共樣式或佈局。

* 可在 [配置對話框](#configure-dialog)。
* 在將容器元件添加到頁面時，可以在 [設計對話框](#design-dialog)。

## 版本和相容性 {#version-and-compatibility}

容器元件的當前版本為v1，該版本於2019年6月隨核心元件2.5.0版一同推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗容器元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_container)。

## 技術詳細資訊 {#technical-details}

有關容器元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_container_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義容器項目及其行為和對頁面訪問者的顯示方式。

![容器元件的編輯對話框](/help/assets/container-edit.png)

* **佈局**  — 此選項定義容器元件的行為或佈局行為。
   * **簡單**  — 將容器定義為元件的簡單集合
   * **響應網格**  — 將容器定義為 [響AEM應佈局](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **背景顏色**  — 可定義為自由格式RGB值或使用拾色器 [取決於配置](#background-tab)
* **背景影像**  — 為容器定義背景顏色，  [取決於配置](#background-tab)
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義使用「容器元件」的內容作者可用的選項。

### 允許的元件頁籤 {#allowed-components-tab}

的 **允許的元件** 頁籤用於定義哪些元件可以由內容作者作為項目添加到容器元件中。

「允許的元件」頁籤的功能與同名的頁籤在 [在模板編輯器中定義佈局容器的策略和屬性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 預設元件頁籤 {#default-components-tab}

「預設元件」頁籤用於定義在容器上放置特定資產類型時將哪個元件添加到元件中，類似於 [如何在頁面模板上定義預設元件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)。

### 響應設定頁籤 {#responsive-settings-tab}

![「容器元件」設計對話框的響應設定頁籤](/help/assets/container-design-responsive.png)

* **列**  — 定義生成容器網格中的列數。

### 背景頁籤 {#background-tab}

![「容器元件」設計對話框的背景頁籤](/help/assets/container-design-background.png)

* **背景影像**
   * **啟用背景影像**  — 選擇此選項可使內容作者為容器定義背景影像。
* **背景色彩**
   * **啟用背景顏色**  — 選擇此選項可使內容作者為容器定義背景顏色。
   * **僅色板**  — 選擇此選項僅允許內容作者從容器背景顏色的預定義顏色色板中進行選擇。
      * 僅在 **啟用背景顏色** 已選中
* **允許的色板**  — 定義內容作者可以從中選擇容器背景顏色的預定義顏色
   * 使用 **添加** 按鈕。 添加後，將向清單中添加一個條目，該清單包含以下列：
   * **值**  — 通過RGB值手動定義顏色
      * 點擊或按一下顏色選取器，通過調整單個RGB值或定義十六進位值，更輕鬆地選擇顏色。
   * **刪除**  — 點擊或按一下以刪除色板。
   * **重新排列**  — 點擊或按一下並拖動以重新排列色板的順序。

### 樣式頁籤 {#styles-tab}

容器元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
