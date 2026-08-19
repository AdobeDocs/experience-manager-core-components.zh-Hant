---
title: 快速搜尋元件
description: 快速搜尋元件提供對網站的搜尋功能並顯示搜尋結果，以便訪客能夠搜尋網站並篩選結果，您可以選擇透過語意搜尋切換使用AI支援的語意搜尋。
role: Developer, Admin, User
exl-id: fc40ce1d-e69a-4a40-853e-67a37228271b
TQID: https://experienceleague.adobe.com/wU-3pacdEz9ne8b53-mKJy-XxRdyz2gu4Jvj-yFgGOw
product_v2: id: c45915cf-e157-4af7-a80d-97b905bcb3a5id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: e2c1b6d3-bb7e-4fe8-8c72-f7b403298e91
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: f939ce7498d9ec1901bea4b5fbf631365ba923fa
workflow-type: tm+mt
source-wordcount: 909
ht-degree: 41%

---


# 快速搜尋元件 {#quick-search-component}

「快速搜尋元件」提供網站搜尋功能，並會顯示搜尋結果，讓訪客可輕鬆找到相符的內容並檢視結果。

{{traditional-aem}}

## 用途 {#usage}

「快速搜尋元件」可讓網站訪客搜尋內容、就地檢視結果，並可輕鬆瀏覽至相符的頁面。 當使用者捲動搜尋結果時，則會動態擷取新的結果。

[編輯對話方塊](#edit-dialog)可讓內容作者定義內容樹狀結構中開始搜尋的位置，並可選擇隱藏語意搜尋切換。 範本作者可以使用[設計對話方塊](#design-dialog)，設定內容樹狀結構中搜尋開始位置的預設值、結果集大小上限、搜尋字詞長度下限，以及依預設是否向訪客顯示語意搜尋切換。

## 版本和相容性 {#version-and-compatibility}

快速搜尋元件的目前版本是v3，此版本隨核心元件的[發行版本2.32.0](/help/versions.md)新增選用的語意搜尋切換而推出，本檔案將對此進行說明。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v3 | - | 相容* | 相容* | 相容 |
| [v2](/help/components/v2/quick-search.md) | - | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/quick-search.md) | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 | - | 相容 |

*語意搜尋切換僅適用於AEM as a Cloud Service。

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本。](/help/versions.md)

## 範例元件輸出 {#sample-component-output}

若要體驗快速搜尋元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫。](https://adobe.com/go/aem_cmp_library_search)

## 技術詳細資訊 {#technical-details}

>[!NOTE]
>
>若要保護「搜尋元件」或任何以 AEM 為基礎的應用程式免受 DOS 攻擊，應在較高層級實施，例如透過在 Dispatcher 上使用 `mod_security` 。

在GitHub上可找到有關快速搜尋元件[的最新技術檔案。](https://adobe.com/go/aem_cmp_tech_search_v3)

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件。](/help/developing/overview.md)

## 編輯對話框 {#edit-dialog}

編輯對話方塊可讓內容作者定義內容樹狀結構中開始搜尋的位置，並可選擇隱藏語意搜尋切換按鈕。

![快速搜尋元件的編輯對話框](/help/assets/quick-search-edit-v3.png)

**搜尋根目錄** - 搜尋開始位置的根頁面。 「搜尋根目錄」可以是 Blueprint 主版頁面、語言主版頁面或一般頁面。
* **ID** - 此選項可讓您控制 HTML 和「[資料層](/help/developing/data-layer/overview.md)」中元件的唯一識別碼。
  * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
  * 若已指定 ID，則作者應確保其為唯一識別碼。
  * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。
* **在此執行個體上隱藏語意搜尋切換** — 勾選後，無論[設計對話方塊](#design-dialog)設定為顯示什麼，語意搜尋切換都會隱藏。
  * 取消勾選則使用範本的預設值。
  * 此選項無法強制切換顯示於設計對話方塊隱藏它的位置。

>[!NOTE]
>
>如果&#x200B;**搜尋根目錄**&#x200B;未設定或無法解析，則「快速搜尋」會預設為在目前頁面之下搜尋。

>[!NOTE]
>
>語意搜尋切換只有在環境已設定AEM Content AI時，才會傳回AI支援的結果。 在未設定Content AI的AEM 6.5和AEM 6.5 LTS環境中，使用設計對話方塊](#design-dialog)隱藏切換[，以免訪客使用無法運作的搜尋模式。

## 設計對話框 {#design-dialog}

使用設計對話方塊，範本作者可以設定內容樹狀結構中開始搜尋的位置的預設值，以及結果集大小上限、搜尋字詞長度下限，以及依預設是否向訪客顯示語意搜尋切換。

### 屬性索引標籤 {#properties-tab}

![快速搜尋元件的設計對話框](/help/assets/quick-search-design-v3.png)

* **搜尋根** — 內容作者在內容頁面上放置快速搜尋元件時，搜尋根的預設值
* **結果大小** — 搜尋要求擷取的結果數目上限
* **搜尋字詞最小長度** — 開始搜尋的搜尋字詞最小長度
* **隱藏語意搜尋切換** — 勾選時，[使用方式](#usage)中描述的&#x200B;**語意搜尋**&#x200B;切換預設不會顯示給網站訪客，而且元件的行為類似於[v2 （僅限全文檢索搜尋）元件。](/help/components/v2/quick-search.md)
  * 預設為未勾選。
  * 內容作者也可以在[編輯對話方塊](#edit-dialog)中覆寫個別快速搜尋元件的內容。

>[!NOTE]
>
>語意搜尋切換只有在環境已設定AEM Content AI時，才會傳回AI支援的結果。 在未設定Content AI的AEM 6.5和AEM 6.5 LTS環境中，使用設計對話方塊隱藏切換，以免訪客使用無法運作的搜尋模式。

>[!NOTE]
>
>**結果大小**&#x200B;和&#x200B;**搜尋字詞最小長度**&#x200B;只能在設計模式下設定，因此僅限於範本層級，這表示內容作者無法修改這些值。

>[!CAUTION]
>
>**結果大小**&#x200B;和&#x200B;**搜尋字詞最小長度**&#x200B;如果分別設定得太高或太低，可能會影響效能。

### 樣式索引標籤 {#styles-tab}

「快速搜尋元件」支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
