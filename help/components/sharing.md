---
title: 社交分享元件
description: 核心元件社交分享元件是Facebook和Pinterest共用介面工具集。
role: Architect, Developer, Admin, User
exl-id: 8bd53c76-da91-479b-b416-f978682a3d43
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 6%

---

# 社交分享元件{#social-sharing-component}

核心元件社交分享元件是Facebook和Pinterest共用介面工具集。

## 使用狀況 {#usage}

社交分享元件會將Facebook和Pinterest分享連結新增至頁面。 它通常包含在頁首或頁尾中。

與其他元件不同，社交分享元件的設定是由範本作者透過[初始頁面屬性](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)和內容作者透過[頁面屬性](https://docs.adobe.com/content/help/zh-Hant/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)完成。

## 版本與相容性 {#version-and-compatibility}

目前的社交分享元件版本為v1，此版本是隨核心元件1.0.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本，以及與元件版本相容的AEM版本。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗社交分享元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_sharing)。

### 技術詳細資訊 {#technical-details}

如需共用元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_sharing_v1)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 編輯對話方塊 {#edit-dialog}

![共用元件的編輯對話方塊](/help/assets/sharing-edit.png)

* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

因為共用需要特殊的頁面標題，所以必須在頁面層級啟用任何共用。 因此，對於內容作者，可透過共用標籤[頁面屬性](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)提供共用元件的其他編輯選項。

## 設計對話方塊 {#design-dialog}

因為共用需要特殊的頁面標題，所以必須在頁面層級啟用任何共用。 因此，範本作者可透過[初始頁面屬性](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)取得共用元件的設計選項。
