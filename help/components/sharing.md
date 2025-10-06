---
title: 社交分享元件
description: 核心元件社交分享元件為 Facebook 和 Pinterest 分享小工具。
role: Architect, Developer, Admin, User
exl-id: 8bd53c76-da91-479b-b416-f978682a3d43
index: false
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '377'
ht-degree: 100%

---


# 社交分享元件{#social-sharing-component}

核心元件社交分享元件為 Facebook 和 Pinterest 分享小工具。

>[!NOTE]
>
>社交分享元件已隨著核心元件 [2.18.0 版](/help/versions.md)棄用。

{{traditional-aem}}

## 用途 {#usage}

社交分享元件會將 Facebook 和 Pinterest 分享連結新增至頁面。通常包含在頁首或頁尾。

與其他元件不同，社交分享元件的設定是由範本作者透過[初始頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)完成，以及由內容作者透過[頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=zh-Hant)完成。

## 版本和相容性 {#version-and-compatibility}

社交分享元件的目前版本為 v1，此版本隨著核心元件 1.0.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本，以及與該元件版本相容的 AEM 版本。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | 與 <br>[2.17.4 版](/help/versions.md)及更早版本相容 | 相容 (已棄用) | 相容 (已棄用) | 相容 (已棄用) |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_sharing_v1_tw)有關分享元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

![分享元件的編輯對話框](/help/assets/sharing-edit.png)

* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

由於分享需要特殊的頁首，因此任何分享都必須在頁面層級啟用。因此，對於內容作者，可透過[頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=zh-Hant)的分享索引標籤，使用分享元件的其他編輯選項。

## 設計對話框 {#design-dialog}

由於分享需要特殊的頁首，因此任何分享都必須在頁面層級啟用。因此，對於範本作者，可透過[初始頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)使用分享元件的設計選項。
