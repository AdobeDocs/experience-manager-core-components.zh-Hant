---
title: 標題元件
description: 核心元件標題元件是章節標題元件，具備就地編輯的功能。
role: Architect, Developer, Admin, User
exl-id: 393af72c-549f-4609-afb0-2712f827b549
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 2%

---

# 標題元件{#title-component}

核心元件標題元件是章節標題元件，具備就地編輯的功能。

## 使用狀況 {#usage}

標題元件旨在用作內容區段的標題或標題。 可用的標題層級可由範本作者在 [設計對話方塊](#design-dialog). 內容編輯者可以從 [編輯對話方塊](#edit-dialog). 為了增加便利性，也可以簡單地就地編輯標題文字。

## 版本和相容性 {#version-and-compatibility}

標題元件的目前版本是v3，此版本隨2022年2月的核心元件2.18.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|---|
| v3 | - | 相容 | 相容 |
| [v2](v2/title.md) | 相容 | 相容 | 相容 |
| [v1](v1/title-v1.md) | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗標題元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_title).

### 技術細節 {#technical-details}

有關標題元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_title_v3).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者定義標題文字並選取標題層級。

* **標題**  — 如果留空，則使用頁面標題
* **型別/大小**  — 定義標題的標題層級
* **連結**  — 定義標題將連結到的內容。 這可以是內容頁面的路徑、外部URL或頁面錨點。
* **在新標籤中開啟連結**  — 核取後，連結會在新的瀏覽器分頁中開啟。
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

![標題元件的編輯對話方塊](/help/assets/title-edit.png)

就地編輯器也可用於編輯標題元件的文字。

![就地編輯標題元件](/help/assets/title-edit-inline.png)

### 樣式索引標籤 {#styles-tab-edit}

標題元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling).

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的效果相同。

必須在以下位置為此元件設定樣式： [設計對話方塊](#design-dialog) 讓下拉式功能表可供使用。

![標題元件「編輯」對話方塊的「樣式」索引標籤](/help/assets/title-edit-styles.png)

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義內容作者建立標題元件時具有的預設標題層級。

### 大小索引標籤 {#sizes-tab}

![標題元件的設計對話方塊](/help/assets/title-design.png)

* **允許作者使用的型別/大小**  — 啟用或停用內容作者在使用標題元件時可用的標題型別。
* **預設型別/大小** — 定義內容作者新增標題元件至頁面時，會自動指派的標題型別。
* **停用連結** — 停用標題元件中對連結的支援，以禁止內容作者從標題進行連結。

### 樣式索引標籤 {#styles-tab}

標題元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe使用者端資料層 {#data-layer}

標題元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
