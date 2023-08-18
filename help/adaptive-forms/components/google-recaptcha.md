---
title: 最適化Forms核心元件 — 表單容器
description: 將最適化表單新增至網頁。
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
source-git-commit: 9a80b453d6a6cf7b347128654d3b5e673a063505
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 1%

---


# Google reCPATCHA {#google-recaptcha}

CAPTCHA （完全自動化公用圖靈測試來區分電腦和人之間的差異）是一種常用於線上交易的程式，以區分人和自動化程式或機器人。 這會帶來挑戰，並評估使用者的回應，以判斷其是否為人類或機器人與網站互動。 它可防止使用者在測試失敗時繼續進行，並透過防止機器人張貼垃圾郵件或惡意目的來確保線上交易的安全。

AEM Formsas a Cloud Service支援Adaptive Forms中的Google reCAPTCHA v2。 您可以用它來在表單提交時提出驗證碼質詢

## 使用狀況 {#reasons-to-use-google-recaptcha}


- **垃圾郵件和機器人預防**：使用reCAPTCHA的主要原因之一，是防止垃圾訊息提交和惡意機器人淹沒您的表單。 reCAPTCHA的進階演演算法可偵測自動提交表單的嘗試，因此可確保只有合法使用者才能與其互動。

- **增強式安全性**：實作reCAPTCHA後，您可為最適化表單新增額外的安全層。 這有助於保護敏感資訊，並防止惡意使用者利用漏洞。

- **使用者體驗**：雖然驗證碼有時被視為不便，但reCAPTCHA的回應式方法表示大部分使用者都能獲得精簡且方便使用的體驗，只需最少的互動。 這有助於在震懾機器人的同時維持良好的使用者體驗。

- **適應性**： reCAPTCHA的調適性機制會分析使用者行為和互動，以判斷是否為人類。 這表示根據使用者成為機器人的可能性，他們面臨的挑戰可能會有所不同。 此適應性可減少真實使用者的摩擦力，同時維持強大的安全性。

- **減少手動稽核**：reCAPTCHA可大幅減少垃圾訊息提交和機器人產生內容的數量，藉此節省原本用於手動稽核和清理的時間和資源。

## 版本和相容性 {#version-and-compatibility}

最適化Forms Google reCAPTCHA核心元件於2023年8月發行，屬於核心元件「版本」的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service  |
| — | --- |
| v1 | 相容於<br>[版本2.0.4](/help/versions.md) 及更新版本 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/versions.md) 檔案。

## 技術細節 {#technical-details}

於的技術檔案中取得最適化Forms Google reCAPTCHA核心元件的最新資訊。 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的Google reCAPTCHA體驗。 您也可以輕鬆定義Google reCAPTCHA選項，以獲得順暢的使用者體驗。

### 基本標籤 {#basic-tab}

- **名稱**  — 在表單和規則編輯器中，您可以使用表單元件的唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

- **標題**  — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。

- **隱藏標題**  — 選取可隱藏元件標題的選項。

- **設定** -

- **類型** -

- **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。

- **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 未提交停用元件的資料。使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

- **唯讀**  — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 驗證標籤 {#validation-tab}

- **錯誤訊息**  — 此選項可讓您輸入訊息，如果 **必填** 核取方塊，且表單欄位留空。

