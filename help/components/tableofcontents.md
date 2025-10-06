---
title: 目錄元件
description: 目錄元件會根據頁面內容中的標題建立目錄，讓讀者快速瀏覽頁面。
role: Architect, Developer, Admin, User
exl-id: 006adde2-ebff-4e74-8e79-325cccd43e8f
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '762'
ht-degree: 100%

---


# 目錄元件 {#table-of-contents-component}

目錄元件會根據頁面內容中的標題建立目錄，讓讀者快速瀏覽頁面。

{{traditional-aem}}

## 用途 {#usage}

目錄元件根據頁面內容標題有效率地產生目錄，讓網站訪客可快速導覽您的頁面內容。

* 目錄在伺服器端產生。
* Dispatcher 已完全快取該檔案，以便快速傳遞。
* 它適用於頁面上的所有元件，而不僅限於核心元件。

[編輯對話框](#edit-dialog)可讓內容作者定義要在目錄中使用的標題範圍。使用[設計對話框](#design-dialog)，範本作者可以在內容作者新增目錄元件至頁面時，設定標題的預設值，並根據類別名稱限制目錄中包含的標題。

## 版本和相容性 {#version-and-compatibility}

目錄元件的目前版本為 v1，此版本於 2022 年 5 月隨著核心元件 2.20.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

>[!NOTE]
>
>在 AEM as a Cloud Service 上，您的管理員需要啟用元件的篩選器，才能呈現元件的內容。
>
>如需詳細資訊，[請參閱該元件的 GitHub 文件](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1)。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1)有關目錄元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

編輯對話框可讓內容作者定義目錄元件應呈現為目錄的標題層級範圍。

![目錄元件的編輯對話框](/help/assets/tableofcontents-edit.png)

**清單類型** - 此選項定義清單應為項目符號清單或編號清單。
* **標題開始層級** - 此選項會定義目錄元件應呈現的標題最高層級。
* **標題停止層級** - 此選項會定義目錄元件應呈現的最低標題層級。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

## 設計對話框 {#design-dialog}

使用設計對話框，範本作者可以設定目錄元件標題範圍的預設值，並根據類別名稱限制目錄中包含的標題。

### 屬性索引標籤 {#properties-tab}

![快速搜尋元件的設計對話框](/help/assets/tableofcontents-design.png)

* **限制清單類型** - 此選項會定義元件將產生的清單類型。選取此選項會限制內容作者選擇其他清單類型的能力。
* **限制開始層級** - 此選項定義了內容作者可以選擇用於定義目錄的最高標題層級。
* **限制停止層級** - 此選項定義了內容作者可以選擇用於定義目錄的最低標題層級。
* **包含類別名稱** - 如果設定此選項，目錄元件只會考慮具有指定類別名稱或包含在指定類別名稱的元素中的標題。
   * 點選或按一下&#x200B;**新增**&#x200B;圖示以新增一或多個類別名稱。
   * 點選或按一下類別名稱旁的&#x200B;**刪除**&#x200B;圖示可將其刪除。
* **忽略類別名稱** - 如果設定此選項，目錄元件會忽略具有指定類別名稱或包含在指定類別名稱元素中的標題。
   * 點選或按一下&#x200B;**新增**&#x200B;圖示以新增一或多個類別名稱。
   * 點選或按一下類別名稱旁的&#x200B;**刪除**&#x200B;圖示可將其刪除。

### 樣式索引標籤 {#styles-tab}

目錄元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

「目錄元件」支援 [Adobe Client Data Layer。](/help/developing/data-layer/overview.md)
