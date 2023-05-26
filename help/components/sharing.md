---
title: 社交分享元件
description: 核心元件社交分享元件是Facebook和Pinterest共用Widget。
role: Architect, Developer, Admin, User
exl-id: 8bd53c76-da91-479b-b416-f978682a3d43
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# 社交分享元件{#social-sharing-component}

核心元件社交分享元件是Facebook和Pinterest共用Widget。

>[!NOTE]
>
>社交共用元件已隨核心元件一起淘汰 [版本2.18.0。](/help/versions.md)

## 使用狀況 {#usage}

社交共用元件會將Facebook和Pinterest共用連結新增至頁面。 它通常包含在頁首或頁尾中。

與其他元件不同，「社交分享」元件的設定由範本作者透過下列方式完成： [初始頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 並由內容作者透過 [頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html).

## 版本和相容性 {#version-and-compatibility}

社交分享元件的目前版本是v1，此版本隨1.0.0版的核心元件引入，說明見本文。

下表詳細說明元件的所有支援版本，以及與元件版本相容的AEM版本。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容於<br>[版本2.17.4](/help/versions.md) 和先前的 | 相容，已棄用 | 相容，已棄用 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

### 技術細節 {#technical-details}

有關共用元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_sharing_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 編輯對話方塊 {#edit-dialog}

![共用元件的編輯對話方塊](/help/assets/sharing-edit.png)

* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

由於共用需要特殊的頁首，因此必須在頁面層級啟用任何共用。 因此，對於內容作者，可透過共用索引標籤使用共用元件的其他編輯選項。 [頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html).

## 設計對話方塊 {#design-dialog}

由於共用需要特殊的頁首，因此必須在頁面層級啟用任何共用。 因此，對於範本作者，共用元件的設計選項可透過 [初始頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).
