---
title: AEM Adaptive Forms中的驗證碼
description: 使用hCaptcha&reg；服務輕鬆增強表單安全性。 內的逐步指南！
feature-set: Experience Manager Sites, Experience Manager Forms
feature: Adaptive Forms, Core Components
role: Architect, Developer, Admin, User
source-git-commit: 08d44e4db42594fb5aaf33d7d42df6fe19c70f59
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 2%

---

# Captcha元件{#hCaptcha-component-adaptive-forms-core-component}

<span class="preview"> 此功能在早期採用者計畫下。 您可以從您的官方電子郵件ID寫信到aem-forms-ea@adobe.com ，以加入率先採用者計畫並請求存取該功能。 </span>

hCaptcha®服務可保護您的表單免受機器人、垃圾郵件和自動濫用的侵擾。 這會提出核取方塊Widget質詢，並評估使用者回應，以判斷它是人類還是機器人與表單互動。 它可防止使用者在測試失敗時繼續進行，並透過防止機器人張貼垃圾郵件或惡意活動來確保線上交易的安全。

![驗證碼®](/help/adaptive-forms/assets/hCaptcha-challenge.png)

## 使用情況 {#usage}

在表單提交程式中加入hCaptcha挑戰有幾個好處，包括：

- **機器人預防**：這可確保表單是由人工提交，減少垃圾郵件和自動化提交。

- **安全性**：它新增了額外的安全層，可驗證每個表單提交的合法性，並抵禦惡意攻擊。

- **資料完整性**：透過防止多次或欺詐性提交，有助於維持透過表單收集之資料的完整性和準確性。

- **使用者驗證**：它會驗證提交表單之使用者的身分，確保只有已驗證的使用者才能完成敏感交易。

- **載入管理**：它可控制表單提交速率，有助於管理伺服器負載，避免高流量期間系統過載。

## 技術細節 {#technical-details}

在的技術檔案中取得有關驗證碼元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/hCaptcha/v1/hCaptcha/README.md). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

使用「 」指定hCaptcha元件的屬性 [設定對話方塊](#configure-dialog). 設定對話方塊是核心元件的一部分，其建置可讓表單的製作更容易，並提供建立複雜表單的有效方式。

## 版本和相容性 {#version-and-compatibility}


最適化Forms hCaptcha元件於2024年5月發行，是 [核心元件3.0.20](https://github.com/adobe/aem-core-forms-components/commit/a4cb97131ffad47137a8f5f173401128a1cf3491). 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service  |
| — | — |
| v1 | 相容於<br>[版本2.0.4](/help/adaptive-forms/version.md) 及更新版本 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 檔案。

## 設定對話方塊 {#configure-dialog}

您可以輕鬆自訂hCaptcha元件的屬性，該元件的「設定」對話方塊具有「基本」標籤和「驗證」標籤，可用於自訂各種屬性。

### 基本標籤 {#basic-tab}

- **[!UICONTROL 名稱]：** 指定hCaptcha元件的名稱，便可在表單和規則編輯器中以唯一名稱輕鬆識別表單元件。
- **[!UICONTROL 標題]：** 指定hCaptcha元件的標題。
- **[!UICONTROL 組態設定]：** 選取為hCaptcha®設定的雲端設定。
- **驗證碼大小：** 您可以選取hCaptcha®挑戰對話方塊的顯示大小。 使用 **[!UICONTROL 精簡]** 顯示小尺寸和 **[!UICONTROL 一般]** 用於顯示相對較大的hCaptcha®挑戰對話方塊的選項。<!-- or **[!UICONTROL Invisible]** to validate hCaptcha&reg; without explicitly rendering the checkbox widget on the user interface. -->

  ![驗證碼基本標籤](/help/adaptive-forms/assets/hcaptcha-basic.png)

### 驗證標籤 {#validation-tab}

- **[!UICONTROL 驗證訊息]：** 在表單提交時提供驗證碼驗證的驗證訊息。
- **[!UICONTROL 指令碼驗證訊息]**  — 如果指令碼驗證失敗，請使用此選項輸入提示訊息。

  ![驗證碼驗證標籤](/help/adaptive-forms/assets/hcaptcha-validation-tab.png)

**hCaptcha®是Intuation Machines， Inc.的註冊商標。**

**瞭解更多** 關於其他 **驗證碼元件** 及其服務，例如：

- [在最適化表單中使用核心元件的驗證碼](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/integrate-adaptive-forms-hCaptcha-core-components)

- [在Foundation元件適用性表單中使用Captcha](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-hcaptcha)

- [在基礎元件的最適化表單中使用Turnstile驗證碼](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile)

- [在基礎元件的最適化表單中使用Google reCAPTCHA](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/captcha-adaptive-forms-core-components)

## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}