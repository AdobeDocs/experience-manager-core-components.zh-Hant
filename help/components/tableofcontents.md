---
title: 目錄元件
description: 目錄元件會根據頁面內容中的標題建立目錄，讓讀者快速瀏覽頁面。
role: Architect, Developer, Admin, User
exl-id: 006adde2-ebff-4e74-8e79-325cccd43e8f
source-git-commit: 8beae61676340e8aafaee469018d865ea7ed934e
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 1%

---

# 目錄元件 {#table-of-contents-component}

目錄元件會根據頁面內容中的標題建立目錄，讓讀者快速瀏覽頁面。

## 使用情況 {#usage}

目錄元件可讓網站訪客透過根據頁面內容標題的高效產生目錄，快速導覽您的頁面內容。

* ToC在伺服器端產生。
* Dispatcher已完全快取該檔案，以便快速傳送。
* 它適用於頁面上的所有元件，而不僅僅是核心元件。

[編輯對話方塊](#edit-dialog)可讓內容作者定義要在ToC中使用的標題範圍。 使用[設計對話方塊](#design-dialog)，範本作者可以在內容作者新增目錄元件至頁面時，設定標題的預設值，並根據類別名稱限制目錄中包含的標題。

## 版本和相容性 {#version-and-compatibility}

目錄元件的目前版本是v1，此版本隨2022年5月的核心元件發行版本2.20.0的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

>[!NOTE]
>
>在AEM as a Cloud Service上，您的管理員需要啟用元件的篩選器，才能呈現元件的內容。
>
>[如需詳細資訊，請參閱元件](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1)的GitHub檔案。

### 技術細節 {#technical-details}

目錄元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1)上找到。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者定義目錄元件應呈現為目錄的標題層級範圍。

![目錄元件的編輯對話方塊](/help/assets/tableofcontents-edit.png)

**清單型別** — 此選項定義清單應為專案符號清單還是編號清單。
* **標題開始層級** — 此選項會定義目錄元件應呈現的標題最高層級。
* **標題停止層級** — 此選項會定義目錄元件應呈現的最低標題層級。
* **ID** — 此選項可控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

## 設計對話方塊 {#design-dialog}

使用設計對話方塊，範本作者可以設定目錄元件標題範圍的預設值，並根據類別名稱限制目錄中包含的標題。

### 屬性標籤 {#properties-tab}

![快速搜尋元件的設計對話方塊](/help/assets/tableofcontents-design.png)

* **限制清單型別** — 此選項會定義元件將產生的清單型別。 選取此選項會限制內容作者選擇其他清單型別的能力。
* **限制開始層級** — 此選項定義了內容作者可以選擇用於定義目錄的最高標題層級。
* **限制停止層級** — 此選項定義了內容作者可以選擇用於定義目錄的最低標題層級。
* **包含類別名稱** — 如果設定此選項，目錄元件只會考慮具有指定類別名稱或包含在指定類別名稱的元素中的標題。
   * 點選或按一下&#x200B;**新增**&#x200B;圖示以新增一或多個類別名稱。
   * 點選或按一下類別名稱旁的&#x200B;**刪除**&#x200B;圖示可將其刪除。
* **忽略類別名稱** — 如果設定此選項，目錄元件會忽略具有指定類別名稱或包含在指定類別名稱元素中的標題。
   * 點選或按一下&#x200B;**新增**&#x200B;圖示以新增一或多個類別名稱。
   * 點選或按一下類別名稱旁的&#x200B;**刪除**&#x200B;圖示可將其刪除。

### 樣式索引標籤 {#styles-tab}

目錄元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe使用者端資料層 {#data-layer}

目錄元件支援[Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
