---
title: 摘要元件
description: 摘要元件可顯示影像、標題、豐富文字，並可選擇地連結至其他內容。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 2%

---


# 摘要元件{#teaser-component}

核心元件摘要元件可顯示影像、標題、豐富式文字，並可選擇連結至其他內容。

## 使用狀況 {#usage}

「摘要元件」可讓內容作者使用影像、標題或豐富式文字輕鬆建立摘要，以進一步內容，並連結至其他內容或其他動作。

範本作者可使用[設計對話框](#design-dialog)來定義建立動作調用和新增連結的選項是否可用，以及停用各種顯示選項。 內容作者可使用[configure dialog](#configure-dialog)來設定影像、定義CTA、設定標題和說明，以及設定個別摘要的連結。 可以訪問[影像元件](image.md)的[編輯對話框](image.md#edit-dialog)以修改預告影像。

## 版本和相容性{#version-and-compatibility}

摘要元件的目前版本為v1，此版本於2018年7月隨核心元件2.1.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容 | 相容 | 相容 |

## 元件輸出示例{#sample-component-output}

若要體驗Teaser元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_teaser)。

### 技術詳細資訊{#technical-details}

有關Teaser元件[的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

內容作者可以使用設定對話方塊來定義個別摘要的屬性。 此外，還有一個[編輯對話框](#edit-dialog)，用於修改雷射影像（如果已選擇）。

### 影像 {#image}

![摘要元件的編輯對話方塊影像標籤](/help/assets/teaser-edit-image.png)

* **影像資產**
   * 從[資產瀏覽器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)拖放資產，或點選&#x200B;**browse**&#x200B;選項，從本機檔案系統上傳。
   * 點選或按一下&#x200B;**Clear**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下「編輯&#x200B;****」，在資產編輯器中管理資產](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)的轉譯。[

>[!NOTE]
>
>[Dynamic Media](image.md#dynamic-media) 功能目前不適用於摘要元件。

### 文字 {#text}

![摘要元件的編輯對話方塊文字標籤](/help/assets/teaser-edit-text.png)

* **Pretitle**  - Pretitle將顯示在摘要標題之前。
* **Title**  —— 定義標題以顯示為摘要標題。
   * **從連結頁面取得標題** -勾選後，標題將會填入連結頁面的標題。
* **說明** -定義要顯示為摘要子標題的說明。
   * **從連結頁面取得說明** -勾選後，說明將會填入連結頁面的說明。
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

### 連結與動作{#links-actions}

![摘要元件的編輯對話方塊連結標籤](/help/assets/teaser-edit-link.png)

* **連結** -套用至摘要的連結。使用路徑瀏覽器來選擇連結目標。
* **啟用呼叫至動作** -勾選後，啟用呼叫至動作的定義。清單中的第一個「行動要求」連結會用作其他摘要元素的連結。

## 編輯對話框{#edit-dialog}

摘要元件將影像演算委派給[影像元件](image.md)。 因此，內容作者可以使用[編輯對話框](image.md#edit-dialog of the Image Component)來操作摘要影像。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義內容作者使用此元件時擁有的摘要選項。

### 摘要標籤{#teaser-tab}

![摘要元件的設計對話方塊](/help/assets/teaser-design.png)

* **呼叫動作**
   * **停用內容作者的呼叫** -隱藏 **內容作者的** 「呼叫動作」選項
* **元素**
   * **Hide pretitle**  —— 隱藏內容作 **** 者的「Pretitle」（預設標題）選項
   * **隱藏標題** -隱藏內容作 **** 者的標題選項
      * 選擇&#x200B;**標題類型**&#x200B;時隱藏
   * **隱藏說明** -隱藏內容作 **** 者的「說明」選項
* **標題類型** -定義摘要標題要使用的H標籤。
* **連結**
   * **不要連結影像** -選取時，未連結摘要影像
   * **不要連結標題** -選取時，未連結摘要標題
* **影像委派** -資訊顯示，指出摘要委派影像處理的元件。

### 樣式標籤{#styles-tab}

摘要元件支AEM持[樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層{#data-layer}

摘要元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
