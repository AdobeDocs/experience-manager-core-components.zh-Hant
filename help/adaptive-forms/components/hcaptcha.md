---
title: AEM Adaptive Forms中的驗證碼
description: 使用hCaptcha&amp；reg；服務輕鬆增強表單安全性。 內的逐步指南！
feature-set: Experience Manager Sites, Experience Manager Forms
feature: Adaptive Forms, Core Components
role: Architect, Developer, Admin, User
source-git-commit: 9a691fc2aa656f5a96d8cd4b6285e6bd473cdaa4
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 2%

---

# Captcha元件{#hCaptcha-component-adaptive-forms-core-component}

<span class="preview">此功能在早期採用者計畫之下。 您可以從您的官方電子郵件ID寫信到aem-forms-ea@adobe.com ，以加入率先採用者計畫並請求存取該功能。</span>

hCaptcha®服務可保護您的表單免受機器人、垃圾郵件和自動濫用的侵擾。 這會提出核取方塊Widget質詢，並評估使用者回應，以判斷它是人類還是機器人與表單互動。 它可防止使用者在測試失敗時繼續進行，並透過防止機器人張貼垃圾郵件或惡意活動來確保線上交易的安全。

![驗證碼®](/help/adaptive-forms/assets/hCaptcha-challenge.png)

## 使用情況 {#usage}

在表單提交程式中加入hCaptcha挑戰有幾個好處，包括：

- **機器人預防**：可確保表單是由人工提交，減少垃圾郵件和自動化提交。

- **安全性**：它新增一層安全性，可驗證每個表單提交的合法性，並防止惡意攻擊。

- **資料完整性**：藉由防止多次或欺詐性提交，有助於維持透過表單所收集資料的完整性和準確性。

- **使用者驗證**：它可驗證提交表單之使用者的身分，確保只有經過驗證的使用者才能完成機密交易。

- **載入管理**：它可控制表單提交速率，以防止系統在高流量期間發生多載，進而協助管理伺服器載入。

## 技術細節 {#technical-details}

在[GitHub](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/hCaptcha/v1/hCaptcha/README.md)上的技術檔案中取得有關hCaptcha元件的最新資訊。 如需開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

使用[設定對話方塊](#configure-dialog)指定hCaptcha元件的屬性。 設定對話方塊是核心元件的一部分，其建置可讓表單的製作更容易，並提供建立複雜表單的有效方式。

## 版本和相容性 {#version-and-compatibility}


最適化Forms hCaptcha元件於2024年5月發行，是[核心元件3.0.20](https://github.com/adobe/aem-core-forms-components/commit/a4cb97131ffad47137a8f5f173401128a1cf3491)的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service  |
| — | — |
| v1 | 與<br>[版本2.0.4](/help/adaptive-forms/version.md)和更新版本相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/adaptive-forms/version.md)檔案。

## 設定對話方塊 {#configure-dialog}

您可以輕鬆自訂hCaptcha元件的屬性，該元件的「設定」對話方塊具有「基本」標籤和「驗證」標籤，可用於自訂各種屬性。

### 基本標籤 {#basic-tab}

- **[!UICONTROL 名稱]：**&#x200B;指定hCaptcha元件的名稱，您可以在表單和規則編輯器中以唯一名稱輕鬆識別表單元件。
- **[!UICONTROL 標題]：**&#x200B;指定您的hCaptcha元件標題。
- **[!UICONTROL 組態設定]：**&#x200B;選取為hCaptcha®設定的雲端組態。
- **驗證碼大小：**&#x200B;您可以選取hCaptcha®挑戰對話方塊的顯示大小。 使用&#x200B;**[!UICONTROL Compact]**&#x200B;選項可顯示小尺寸，使用&#x200B;**[!UICONTROL Normal]**&#x200B;選項可顯示相對大尺寸的hCaptcha®挑戰對話方塊。<!-- or **[!UICONTROL Invisible]** to validate hCaptcha&reg; without explicitly rendering the checkbox widget on the user interface. -->

  ![hCaptcha基本標籤](/help/adaptive-forms/assets/hcaptcha-basic.png)

### 驗證標籤 {#validation-tab}

- **[!UICONTROL 驗證訊息]：**&#x200B;在表單提交時提供驗證碼驗證的驗證訊息。
- **[!UICONTROL 指令碼驗證訊息]** — 如果指令碼驗證失敗，請使用此選項輸入提示訊息。

  ![hCaptcha驗證標籤](/help/adaptive-forms/assets/hcaptcha-validation-tab.png)

**hCaptcha®是Intuition Machines， Inc.的註冊商標。**

**深入瞭解**&#x200B;其他&#x200B;**驗證碼元件**&#x200B;及其服務，例如：

- [在核心元件的最適化表單中使用hCaptcha](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/integrate-adaptive-forms-hcaptcha-core-components)

- [在Foundation元件的最適化表單中使用hCaptcha](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-hcaptcha)

- [在基礎元件的最適化表單中使用Turnstile驗證碼](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile)

- [在基礎元件的最適化表單中使用Google reCAPTCHA](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/captcha-adaptive-forms-core-components)

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
