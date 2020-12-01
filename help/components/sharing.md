---
title: 社交分享元件
description: 核心元件社交分享元件是Facebook和Pinterest分享介面工具集。
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 1%

---


# 社交分享元件{#social-sharing-component}

核心元件社交分享元件是Facebook和Pinterest分享介面工具集。

## 使用狀況 {#usage}

社交分享元件會將Facebook和Pinterest分享連結新增至頁面。 它通常包含在頁首或頁尾中。

與其他元件不同，社交共用元件的設定是由範本作者透過[初始頁面屬性](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)和內容作者透過[頁面屬性](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)完成。

## 版本和相容性{#version-and-compatibility}

目前的社交分享元件版本為v1，此版本隨核心元件1.0.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本，以及與元件版本相容的AEM版本。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗社交共用元件，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_sharing)。

### 技術詳細資訊{#technical-details}

有關共用元件[的最新技術文檔可在GitHub](https://adobe.com/go/aem_cmp_tech_sharing_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話框{#edit-dialog}

![共用元件的編輯對話框](/help/assets/sharing-edit.png)

* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

由於共用需要特殊的頁面標題，所以必須在頁面層級啟用任何共用。 因此，對於內容作者，可通過[頁面屬性](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)的共用頁籤提供共用元件的其他編輯選項。

## 設計對話框{#design-dialog}

由於共用需要特殊的頁面標題，所以必須在頁面層級啟用任何共用。 因此，對於模板作者，共用元件的設計選項可通過[初始頁屬性](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)獲得。
