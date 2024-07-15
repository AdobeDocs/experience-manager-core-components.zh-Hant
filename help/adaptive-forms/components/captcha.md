---
title: 最適化Forms核心元件 — 表單容器
description: 將最適化表單新增至網頁。
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
exl-id: 1e413ef3-7a6f-41fc-825d-dbe09ebaffe9
source-git-commit: e843ccf5c030cd4f1015e3290347b5799828537a
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 2%

---

# Google reCPATCHA {#google-recaptcha}

CAPTCHA （完全自動化公用圖靈測試來區分電腦和人之間的差異）是一種常用於線上交易的程式，以區分人和自動化程式或機器人。 這會帶來挑戰，並評估使用者的回應，以判斷其是否為人類或機器人與網站互動。 它可防止使用者在測試失敗時繼續進行，並透過防止機器人張貼垃圾郵件或惡意目的來確保線上交易的安全。

AEM Formsas a Cloud Service支援最適化Forms中的Google reCAPTCHA v2。 您可以用它來在表單提交時提出驗證碼質詢

## 使用情況 {#reasons-to-use-google-recaptcha}

- **防止垃圾郵件和機器人**：使用reCAPTCHA的主要原因之一，是防止垃圾郵件提交和惡意機器人淹沒您的表單。 reCAPTCHA的進階演演算法可偵測自動提交表單的嘗試，因此可確保只有合法使用者才能與其互動。

- **增強式安全性**：實作reCAPTCHA後，您就可以在最適化表單中新增一層額外的安全性。 這有助於保護敏感資訊，並防止惡意使用者利用漏洞。

- **使用者體驗**：雖然驗證碼有時被視為不便，但reCAPTCHA的最適化方法意味著大多數使用者都會獲得簡化的、方便使用者的體驗，而且只需要最少的互動。 這有助於在震懾機器人的同時維持良好的使用者體驗。

- **適應性**： reCAPTCHA的適應性機制會分析使用者行為與互動，以判斷是否為人類。 這表示根據使用者成為機器人的可能性，他們面臨的挑戰可能會有所不同。 此適應性可減少真實使用者的摩擦力，同時維持強大的安全性。

- **減少手動稽核**：reCAPTCHA可大幅減少垃圾訊息提交和機器人產生內容的數量，藉此節省原本用於手動稽核和清理的時間和資源。

## 版本和相容性 {#version-and-compatibility}

最適化Forms Google reCAPTCHA核心元件於2023年8月發行，屬於核心元件「版本」的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：


|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service  |
| — | — |
| v1 | 與<br>[版本2.0.4](/help/versions.md)和更新版本相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/versions.md)檔案。

## 技術細節 {#technical-details}

在[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha)的技術檔案中取得最適化Forms Google reCAPTCHA核心元件的最新資訊。 如需開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的Google reCAPTCHA體驗。 您也可以輕鬆定義Google reCAPTCHA選項，以獲得順暢的使用者體驗。

### 基本標籤 {#basic-tab}

- **名稱** — 您可以在表單和規則編輯器中輕鬆識別具有唯一名稱的表單元件，但名稱不得包含空格或特殊字元。

- **標題** — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。

- **隱藏標題** — 選取隱藏元件標題的選項。

- **組態** -

- **型別** -

- **隱藏元件** — 選取選項，以隱藏表單中的元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。

- **停用元件** — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 未提交停用元件的資料。使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

- **唯讀** — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 驗證標籤 {#validation-tab}

- **錯誤訊息** — 此選項可讓您輸入在勾選「**必要**」核取方塊並將表單欄位保留空白時顯示的訊息。

## 另請參閱 {#see-also}

- [建立AEM最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)
- [新增AEM最適化表單至AEM Sites頁面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)
- [將主題套用至AEM最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html)
- [將元件新增至AEM最適化表單](/help/adaptive-forms/introduction.md#adaptive-forms-core-components-components)
- [在AEM最適化表單中使用reCAPTCHA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms.html)
- [產生AEM最適化表單的PDF版本(DoR)](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components.html)
- [翻譯AEM最適化表單](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-aem-translation-workflow-to-localize-adaptive-forms-core-components.html)
- [為最適化表單啟用Adobe Analytics以追蹤表單使用情況](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/services/enable-adobe-analytics-adaptive-form-using-experience-cloud-setup-automation.html)
- [將最適化表單連線至Microsoft SharePoint](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#create-sharepoint-configuration)
- [將最適化表單連線至Microsoft Power Automate](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#microsoft-power-automate)
- [將最適化表單連線至Microsoft OneDrive](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-onedrive)
- [將最適化表單連線至Microsoft Azure Blob儲存體](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-azure-blob-storage)
- [將最適化表單連線至Salesforce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/oauth2-client-credentials-flow-for-server-to-server-integration.html)
- [在AEM最適化表單中使用Adobe Sign](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/use-adobe-sign/working-with-adobe-sign.html)
- [為最適化表單新增地區設定](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components.html)
- [將最適化表單資料傳送到資料庫](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/data-integration.html)
- [將最適化表單資料傳送至REST端點](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-rest-endpoint)
- [將最適化表單資料傳送至AEM Workflow](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#invoke-an-aem-workflow)
- [使用Forms入口網站列出AEM網站上的AEM Adaptive Forms](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-forms-portal.html)

