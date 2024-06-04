---
title: 最適化Forms核心元件 — Google reCAPTCHA
description: 透過Google reCAPTCHA服務，使用AEM Forms輕鬆增強表單安全性。 說明最適化表單reCaptcha的屬性
role: Architect, Developer, Admin, User
source-git-commit: 4c510b8fe59f4be6e1b329ee4257ab1b780fbf22
workflow-type: tm+mt
source-wordcount: '1325'
ht-degree: 1%

---


# 自適應表單 reCAPTCHA {#google-recaptcha}

CAPTCHA （完全自動化公用圖靈測試來區分電腦和人類）是一種常用於線上交易的程式，以區分人類和自動化程式或機器人。 這會帶來挑戰，並評估使用者的回應，以判斷其是否為人類或機器人與網站互動。 它可防止使用者在測試失敗時繼續進行，並透過防止機器人張貼垃圾郵件或惡意目的來確保線上交易的安全。

AEM Formsas a Cloud Service支援Adaptive Forms中的Google reCAPTCHA v2。 您可以用它來在表單提交時提出驗證碼質詢

## 使用情況 {#reasons-to-use-google-recaptcha}


- **垃圾郵件和機器人預防**：使用reCAPTCHA的主要原因之一，是防止垃圾訊息提交和惡意機器人淹沒您的表單。 reCAPTCHA的進階演演算法可偵測自動提交表單的嘗試，因此可確保只有合法使用者才能與其互動。

- **增強式安全性**：實作reCAPTCHA後，您可為最適化表單新增額外的安全層。 這有助於保護敏感資訊，並防止惡意使用者利用漏洞。

- **使用者體驗**：雖然驗證碼有時被視為不便，但reCAPTCHA的回應式方法表示大部分使用者都能獲得精簡且方便使用的體驗，只需最少的互動。 這有助於在震懾機器人的同時維持良好的使用者體驗。

- **適應性**： reCAPTCHA的調適性機制會分析使用者行為和互動，以判斷是否為人類。 這表示根據使用者成為機器人的可能性，他們面臨的挑戰可能會有所不同。 此適應性可減少真實使用者的摩擦力，同時維持強大的安全性。

- **減少手動稽核**：reCAPTCHA可大幅減少垃圾訊息提交和機器人產生內容的數量，藉此節省原本用於手動稽核和清理的時間和資源。

## 版本和相容性 {#version-and-compatibility}

最適化Forms Google reCAPTCHA核心元件於2023年8月發行，屬於核心元件「版本」的一部分。 下表顯示所有支援版本、AEM相容性以及對應檔案的連結：


| 元件版本 | AEM as a Cloud Service  |
|--- |--- |
| v1 | 相容於<br>[版本2.0.4](/help/versions.md) 及更新版本 | 相容 | 相容 |

如需核心元件版本的詳細資訊，請參閱 [核心元件版本](/help/versions.md) 檔案。

## 技術細節 {#technical-details}

於的技術檔案中取得最適化Forms Google reCAPTCHA核心元件的最新資訊。 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的Google reCAPTCHA體驗。 您也可以輕鬆定義Google reCAPTCHA選項，以獲得順暢的使用者體驗。

### 基本標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/recaptcha-basictab.png)

- **名稱**  — 在表單和規則編輯器中，您可以使用表單元件的唯一名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

- **標題**  — 您可以使用其Title輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。 如果您未新增標題，則會顯示元件的名稱而非標題文字。

- **允許標題使用RTF文字**  — 此功能可讓使用者格式化純文字標題，並整合如粗體、斜體、底線文字、各種字型、字型大小、顏色，以及其他可增強視覺呈現和自訂的選項。 它提供更大的彈性和創意控制，讓標題在檔案、網站或應用程式中脫穎而出。\
  選取**允許標題使用RTF格式」核取方塊後，格式選項會變成可見，以設定元件標題的樣式。 若要存取所有可用的格式選項，您可以按一下 ![全熒幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png) 標籤。

  ![RTF支援](/help/adaptive-forms/assets/richtext-support-title.png)

- **隱藏標題**  — 選取可隱藏元件標題的選項。
- **標籤為未繫結表單元素**：選取選項以設定未連結至任何結構的表單欄位。 此選項可讓您儲存資料而不更新資料來源。 它也可讓您以自訂方式處理資料，與標準資料庫整合不同。
- **組態設定**：選取包含雲端設定的設定容器，此雲端設定會將AEM Forms與Google的reCAPTCHA服務連線。

  >[!NOTE]
  >
  > 請參閱 [根據核心元件在AEM最適化表單中使用Google reCAPTCHA](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/captcha-adaptive-forms-core-components) 文章，瞭解如何為您的環境建立和設定Google reCAPTCHA。

- **型別**：選取此選項以選取reCAPTCHA的大小。
   - **一般**：是指標準、較大版本的reCAPTCHA Widget，使用者可更輕鬆看得見，與互動，尤其是在熒幕較大的裝置上。
   - **精簡**：指較小版本的reCAPTCHA Widget。 此選項適用於空間有限的情況，例如在行動裝置上或網頁的緊密佈局中。

- **隱藏元件**  — 選取選項，以從表單中隱藏元件。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這將很有用。

- **停用元件**  — 選取選項以停用元件。 一般使用者無法啟動或編輯已停用的元件。 未提交停用元件的資料。使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

- **唯讀**  — 選取選項，讓元件無法編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可於其他用途存取，例如將其用於規則編輯器中的計算。

### 驗證標籤 {#validation-tab}

![驗證標籤](/help/adaptive-forms/assets/recaptcha-validationtab.png)

- **錯誤訊息**  — 此選項可讓您輸入訊息，如果 **必填** 核取方塊，且表單欄位留空。

- **指令碼驗證訊息**  — 此選項可讓您輸入指令碼驗證失敗時顯示的訊息。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可用來定義和管理reCAPTCHA元件的CSS樣式。

### 樣式索引標籤 {#styles-design-tab}

最適化Forms reCAPTCHA核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

![設計對話方塊](/help/adaptive-forms/assets/checkbox-style.png)

- **預設CSS類別**：您可以為最適化Forms reCAPTCHA核心元件提供預設CSS類別。

- **允許的樣式**：您可以提供名稱以及代表樣式的CSS類別來定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight： bold」。 您可以在最適化Forms編輯器中將這些樣式使用或套用至最適化表單。 若要套用樣式，請在最適化Forms編輯器中，選取您要套用樣式的元件，導覽至「屬性」對話方塊，然後從 **樣式** 下拉式清單。 如果您需要更新或修改樣式，只要返回「設計」對話方塊，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話方塊](/help/adaptive-forms/assets/checkbox-customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性（索引鍵/值組）與最適化表單核心元件建立關聯。 自訂屬性會反映在元件Headless轉譯的properties區段中。 它可讓您建立根據自訂屬性值調整的動態表單行為。 例如，開發人員可以為行動、桌上型電腦或Web平台設計各種無頭Forms元件的轉譯，大幅提升各種裝置的使用者體驗。
- **群組名稱**：您可以提供名稱來識別自訂屬性群組。 您可以新增、刪除或重新排列多個自訂屬性群組。 新增自訂屬性群組後，您可以看到下列選項：

   - **索引鍵值配對**：您可以按一下「 」，新增多個自訂屬性名稱和自訂屬性值 **新增** 按鈕來設定每個自訂屬性群組。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳以重新排列自訂屬性名稱和自訂屬性值。


## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
