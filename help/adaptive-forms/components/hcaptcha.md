---
title: AEM 自適應表單中的 hCaptcha
description: 使用 hCaptcha&reg; 服務輕鬆提升表單安全性。裡面有詳細的逐步指南！
feature-set: Experience Manager Sites, Experience Manager Forms
feature: Adaptive Forms, Core Components
role: Architect, Developer, Admin, User
exl-id: eecb38d5-711e-4dc5-bc19-498e003f37e7
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '583'
ht-degree: 100%

---


# hCaptcha 元件{#hCaptcha-component-adaptive-forms-core-component}

<span class="preview"> 此功能隸屬於早期採用者計劃。您可以使用官方電子郵件 ID 寫信至 aem-forms-ea@adobe.com，以加入早期採用者計劃並要求存取該功能。</span>

hCaptcha® 服務可保護您的表單免受機器人、垃圾郵件和自動化濫用的侵擾。它會利用核取方塊小工具來提出質詢，並評估使用者的回應，以判斷與表單互動的是真人還是機器人。它可防止使用者在測試失敗時繼續操作，並透過防止機器人發佈垃圾郵件或惡意活動來確保線上交易的安全。

![hCaptcha®](/help/adaptive-forms/assets/hCaptcha-challenge.png)

{{traditional-aem}}

## 用途 {#usage}

在表單提交過程中加入 hCaptcha 質詢有多項好處，包括：

- **防止機器人**：可確保表單是由人工提交，減少垃圾郵件和自動化提交。

- **安全性**：它為每次表單提交新增一層額外的安全性，能夠驗證提交的合法性，並防止惡意攻擊。

- **資料完整性**：藉由防止多次或欺騙提交，有助於維持透過表單所收集資料的完整性和準確性。

- **使用者驗證**：它可驗證提交表單之使用者的身分，確保只有經過驗證的使用者才能完成機密交易。

- **載入管理**：它透過控制表單提交速率來協助管理伺服器載入，以防止系統在高流量期間發生過載。

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/hCaptcha/v1/hCaptcha/README.md) 上的技術文件中可取得 hCaptcha 元件的最新相關資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

您可以使用[設定對話框](#configure-dialog)指定 hCaptcha 元件的屬性。設定對話框是核心元件的一部分，其建置可讓表單的製作更容易，並提供高效率建立複雜表單的方法。

## 版本和相容性 {#version-and-compatibility}


自適應表單 hCaptcha 核心元件於 2024 年 5 月作為[核心元件 3.0.20 版](https://github.com/adobe/aem-core-forms-components/commit/a4cb97131ffad47137a8f5f173401128a1cf3491)的一部分發行。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 與<br>[ 2.0.4 版](/help/adaptive-forms/version.md)及更新版本相容 | 相容 | 相容 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)文件。

## 設定對話框 {#configure-dialog}

透過 hCaptcha 元件的設定對話框，其中具備可自訂多種屬性的基本索引標籤和驗證索引標籤，可讓您輕鬆自訂屬性。

### 基本索引標籤 {#basic-tab}

- **[!UICONTROL 名稱]：**&#x200B;指定 hCaptcha 元件名稱，在表單和規則編輯器中，您可以使用其唯一名稱輕鬆識別表單元件。
- **[!UICONTROL 標題]：**&#x200B;指定 hCaptcha 元件的標題。
- **[!UICONTROL 設定]：**&#x200B;選取已設定用於 hCaptcha® 的雲端設定。
- **驗證碼大小：**&#x200B;您可以選取 hCaptcha® 質詢對話框的顯示大小。使用&#x200B;**[!UICONTROL 精簡]**&#x200B;選項可顯示小尺寸，使用&#x200B;**[!UICONTROL 正常]**&#x200B;選項可顯示相對大尺寸的 hCaptcha® 質詢對話框。<!-- or **[!UICONTROL Invisible]** to validate hCaptcha&reg; without explicitly rendering the checkbox widget on the user interface. -->

  ![hCaptcha 基本索引標籤](/help/adaptive-forms/assets/hcaptcha-basic.png)

### 驗證索引標籤 {#validation-tab}

- **[!UICONTROL 驗證訊息]：**&#x200B;在表單提交時提供驗證碼驗證的驗證訊息。
- **[!UICONTROL 指令碼驗證訊息]** - 如果指令碼驗證失敗，請使用此選項輸入提示訊息。

  ![hCaptcha 驗證索引標籤](/help/adaptive-forms/assets/hcaptcha-validation-tab.png)

**hCaptcha® 是 Intuition Machines, Inc. 的註冊商標。**

**深入瞭解**&#x200B;其他&#x200B;**驗證碼元件**&#x200B;及其服務，例如：

- [於核心元件的自適應表單中使用 hCaptcha](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/integrate-adaptive-forms-hcaptcha-core-components)

- [於基礎元件的自適應表單中使用 hCaptcha](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-hcaptcha)

- [於基礎元件的自適應表單中使用 Turnstile 驗證碼](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile)

- [於基礎元件的自適應表單中使用 Google reCAPTCHA](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/captcha-adaptive-forms-core-components)

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
