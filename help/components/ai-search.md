---
title: 內容AI 搜尋元件
description: 內容AI 搜尋元件可為您的網站訪客提供可產生的AI支援搜尋。
role: Developer, Admin, User
product_v2: id: c45915cf-e157-4af7-a80d-97b905bcb3a5id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: e2c1b6d3-bb7e-4fe8-8c72-f7b403298e91
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: e721e8b9469646300432b87d42bfb742aaf5f3fb
workflow-type: tm+mt
source-wordcount: 805
ht-degree: 15%

---


# 內容AI 搜尋元件 {#content-ai-search-component}

內容AI 搜尋元件可為您的網站訪客提供可產生的AI支援搜尋。

{{traditional-aem}}

## 用途 {#usage}

內容AI 搜尋元件可讓訪客直接從頁面搜尋[內容Source](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/contentsources)，並可選擇檢視由人工智慧產生的產生結果摘要。 它將標準全文/語意搜尋方塊與可切換的&#x200B;**顯示AI產生的摘要**&#x200B;面板相結合，該面板由AEM Content AI提供技術支援。

[編輯對話方塊](#edit-dialog)可讓內容作者定義搜尋的內容範圍、搜尋行為和產生式設定。 沒有設計對話方塊，因為範本層級沒有可用的設定。

>[!NOTE]
>
>若要使用內容AI 搜尋元件，您必須擁有Content AI Source的存取權，且您的管理員必須為您的專案啟用該元件。 如需詳細資訊，請參閱檔案[設定內容AI 搜尋元件](/help/developing/ai-search.md)。

## 版本和相容性 {#version-and-compatibility}

內容AI 搜尋元件的目前版本是v1，此版本隨2026年7月的核心元件發行版本2.32.0的發佈引入，說明見本文。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|---|
| v1 | - | - | - | 進行中 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本。](/help/versions.md)

## 範例元件輸出 {#sample-component-output}

若要體驗內容AI 搜尋元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫。](https://adobe.com/go/aem_cmp_library_ai_search)

## 技術詳細資訊 {#technical-details}

在GitHub上可找到有關內容AI 搜尋元件[的最新技術檔案。](https://adobe.com/go/aem_cmp_tech_ai_search_v1)

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件。](/help/developing/overview.md)

## 編輯對話框 {#edit-dialog}

編輯對話方塊可讓內容作者定義搜尋的內容範圍、搜尋行為和產生式設定。 沒有設計對話方塊，因為範本層級沒有可用的設定。

### 內容範圍標籤 {#content-scope}

![編輯對話方塊的內容範圍標籤](/help/assets/content-ai-search-edit-content-scope.png)

* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
  * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
  * 若已指定 ID，則作者應確保其為唯一識別碼。
  * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。
* **內容Source型別** — 此欄位定義內容來源的型別。 選取型別會使用相符的來源填入&#x200B;**內容Source**&#x200B;下拉式清單。
  * **ACQUISITION** — 用於透過抓取/贏取管道索引的公開、匿名存取來源的預設值
  * **AEM_AUTHOR** — 其內容是從AEM作者執行個體擷取的Content-AI端來源
  * **AEM_PUBLISH** — 從AEM發佈執行個體擷取內容的Content-AI端來源
  * **自訂** — 在AEM自己的擷取管道外部註冊的來源
* **內容來源** — 這會定義此元件搜尋的內容Source。
  * 可用專案符合已存在且&#x200B;**可用**&#x200B;的內容來源，也符合&#x200B;**內容Source型別**&#x200B;中設定的型別
  * 如需詳細資訊，請參閱檔案[設定和管理您的Content AI來源](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/contentsources)。

### 搜尋行為標籤 {#search-behavior}

![編輯對話方塊的[搜尋行為]索引標籤](/help/assets/content-ai-search-edit-search-behavior.png)

* **結果配置** — 此選項定義如何向訪客顯示搜尋結果。
  * **卡片** — 此選項會以格線格式顯示結果。
  * **清單** — 此選項會以清單格式顯示結果。
* **結果大小** — 定義每個搜尋要求擷取的結果數目。
  * 預設值為 `12`。
  * 當有其他相符專案可用時，訪客可載入更多結果。
* **預留位置文字** — 這是訪客進入搜尋查詢之前，在空白搜尋輸入欄位中顯示的文字。

### 產生式搜尋標籤 {#generative-search}

![編輯對話方塊的[產生式搜尋]索引標籤](/help/assets/content-ai-search-edit-generative-search.png)

* **向訪客顯示產生式摘要切換** — 取消勾選時，訪客無法變更是否顯示AI摘要。
  * 預設值為啟用。
* **依預設顯示產生摘要** — 此選項會控制AI產生之摘要的訪客對向切換的預設狀態。
  * 預設值為啟用。
* **GenSearch錯誤遞補** — 定義搜尋應該如何行為或錯誤。
  * **只顯示結果（隱藏錯誤）** — 如果發生錯誤，則只顯示傳回的結果，不顯示錯誤和不重試按鈕。 這是預設值。
  * **顯示錯誤並重試** — 如果出現錯誤，請使用重試按鈕顯示錯誤。
  * **僅顯示錯誤訊息** — 如果有錯誤，則僅顯示錯誤訊息，不顯示任何結果。
