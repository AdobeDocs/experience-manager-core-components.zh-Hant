---
title: 標題元件
description: 核心元件標題元件是具有就地編輯功能的區段標題元件。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 2%

---


# 標題元件{#title-component}

核心元件標題元件是具有就地編輯功能的區段標題元件。

## 使用狀況 {#usage}

「標題元件」可用作內容區段的標題或標題。 可用標題層級可由範本作者在[設計對話方塊](#design-dialog)中定義。 內容編輯器可從[edit dialog](#edit-dialog)中的可用標題級別進行選擇。 為方便起見，您也可以在原地編輯標題文字。

## 版本和相容性{#version-and-compatibility}

目前版本的標題元件為v2，此版本於2018年1月隨核心元件2.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、元AEM件版本相容的版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v2 | 相容 | 相容 | 相容 |
| [v1](v1/title-v1.md) | 相容 | 相容 | - |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗「標題元件」，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_title)。

### 技術詳細資訊{#technical-details}

有關Title Component [的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_title_v2)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話框{#edit-dialog}

編輯對話方塊可讓內容作者定義標題文字，並選取標題層級。

* **Title**  —— 如果空白，將使用頁面標題
* **類型／大小** -定義標題的標題層級
* **連結** -定義標題將連結至的內容。這可以是內容頁面、外部URL或頁面錨點的路徑。
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

![標題元件的編輯對話方塊](/help/assets/title-edit.png)

>[!NOTE]
>
>核心元件2.2.0版中已引入定義標題連結的功能。

就地編輯器也可用於編輯標題元件的文本。

![就地編輯標題元件](/help/assets/title-edit-inline.png)

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者定義標題元件在內容作者建立時所具有的預設標題層級。

### 大小標籤{#sizes-tab}

![標題元件的設計對話方塊](/help/assets/title-design.png)

* **作者的允許類型／大小** -啟用或停用內容作者使用標題元件時可用的標題類型。
* **預設類型／大小**-定義內容作者將標題元件新增至頁面時會自動指派的標題類型。
* **停用連結**-停用標題元件中連結的支援，以禁止內容作者從標題連結。

>[!NOTE]
>
>核心元件2.2.0版中已引入定義標題連結的功能。

### 樣式標籤{#styles-tab}

標題元件支AEM持[樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層{#data-layer}

標題元件支援[Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
