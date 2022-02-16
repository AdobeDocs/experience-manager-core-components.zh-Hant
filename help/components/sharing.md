---
title: 社交共用元件
description: 核心元件社交共用元件是Facebook和Pinterest共用元件。
role: Architect, Developer, Admin, User
exl-id: 8bd53c76-da91-479b-b416-f978682a3d43
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 2%

---

# 社交共用元件{#social-sharing-component}

核心元件社交共用元件是Facebook和Pinterest共用元件。

## 使用狀況 {#usage}

社交共用元件將Facebook和Pinterest共用連結添加到該頁。 它通常包含在頁眉或頁腳中。

與其他元件不同，「社交共用元件」的設定由模板作者通過 [初始頁屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 內容作者通過 [頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)。

## 版本和相容性 {#version-and-compatibility}

當前版本的社會共用元件是v1，它隨核心元件1.0.0版一起推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本AEM以及元件版本與之相容的版本。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v1 | 相容<br>[發行版2.17.4](/help/versions.md) 和 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔 [核心元件版本](/help/versions.md)。

## 元件輸出示例 {#sample-component-output}

要體驗社交共用元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_sharing)。

### 技術詳細資訊 {#technical-details}

有關共用元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_sharing_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

![共用元件的編輯對話框](/help/assets/sharing-edit.png)

* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

由於共用需要特殊的頁眉，因此必須在頁面級別啟用任何共用。 因此，對於內容作者，共用元件的附加編輯選項可通過共用頁籤獲得 [頁屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)。

## 設計對話框 {#design-dialog}

由於共用需要特殊的頁眉，因此必須在頁面級別啟用任何共用。 因此，對於模板作者，共用元件的設計選項可通過 [初始頁屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)。
