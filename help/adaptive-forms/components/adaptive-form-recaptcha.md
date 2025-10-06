---
title: 自適應表單核心元件 - Google reCAPTCHA
description: 輕鬆透過 Google reCAPTCHA 服務搭配 AEM Forms 提升表單安全性。說明自適應表單 reCaptcha 的屬性
role: Architect, Developer, Admin, User
exl-id: 2d986b90-e596-4e8f-9a32-0ebced5461c8
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '1325'
ht-degree: 100%

---


# 自適應表單 reCAPTCHA {#google-recaptcha}

CAPTCHA (用於區分電腦和人類的完全自動化公開圖靈測試) 是一種常用於線上交易的程式，以區分人類和自動化程式或機器人。它會提出質詢並評估使用者的回應，以判斷與網站互動的是真人還是機器人。它可防止使用者在測試失敗時繼續操作，並透過防止機器人發佈垃圾郵件或惡意目的來確保線上交易的安全。

AEM Forms as a Cloud Service 支援自適應表單中的 Google reCAPTCHA v2。您可採用此功能在表單提交時提出驗證碼質詢

{{traditional-aem}}

## 用途 {#reasons-to-use-google-recaptcha}


- **防止垃圾郵件和機器人**：使用 reCAPTCHA 的主要原因之一，是防止垃圾郵件提交和惡意機器人大量灌入您的表單。reCAPTCHA 的進階演算法可偵測自動提交表單的嘗試，因此可確保只有合法使用者才能與其互動。

- **增強式安全性**：透過實作 reCAPTCHA，您就可以在自適應表單中新增一層額外的安全性。這有助於保護敏感資訊，並防止惡意使用者利用漏洞。

- **使用者體驗**：雖然驗證碼有時被視為不便，但 reCAPTCHA 的最適化方法意味著大多數使用者都會獲得簡化且易於使用的體驗，而且只需要最少的互動。這有助於在遏制機器人的同時維持良好的使用者體驗。

- **自適應**：reCAPTCHA 的自適應機制會分析使用者行為與互動，以判斷是否為真人。這表示系統會根據使用者為機器人的可能性，調整所呈現的質詢難度。此自適應可減少真實使用者的摩擦，同時維持強大的安全性。

- **減少手動審核**：reCAPTCHA 可大幅減少垃圾郵件提交和機器人產生內容的數量，藉此節省原本用於手動審核和清理的時間和資源。

## 版本和相容性 {#version-and-compatibility}

自適應表單 Google reCAPTCHA 核心元件於 2023 年 8 月作為核心元件「版本」的一部分發行。下表顯示所有支援版本、AEM 相容性以及對應文件的連結：


| 元件版本 | AEM as a Cloud Service |
|--- |--- |
| v1 | 與<br>[ 2.0.4 版](/help/versions.md)及更新版本相容 | 相容 | 相容 |

如需「核心元件」版本和發行版本的詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 技術詳細資訊 {#technical-details}

[GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha) 的技術文件中可找到自適應表單 Google reCAPTCHA 核心元件的最新資訊。如需開發核心元件的更多資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

透過設定對話框，您可以輕鬆自訂訪客的 Google reCAPTCHA 體驗。同樣能夠輕鬆定義 Google reCAPTCHA 選項，以提供順暢無礙的使用者體驗。

### 基本索引標籤 {#basic-tab}

![基本索引標籤](/help/adaptive-forms/assets/recaptcha-basictab.png)

- **名稱** - 在表單和規則編輯器中，您可以使用其唯一名稱輕鬆識別表單元件，但該名稱不得包含空格或特殊字元。

- **標題** - 您可以使用其標題輕鬆識別表單中的元件，預設情況下，標題會顯示在元件上方。若未新增標題，則會顯示該元件的名稱而非標題文字。

- **允許標題使用 RTF 文字** - 此功能可讓使用者格式化純文字標題，整合粗體、斜體、底線文字、各種字型、字體大小、顏色等功能，以及可增強視覺呈現和自訂的其他選項。提供更大的靈活性和創意控制，讓標題在文件、網站或應用程式中脫穎而出。\
  選取**允許標題使用 RTF 文字核取方塊後，即可看到格式選項，以設定元件標題的樣式。若要存取所有可用的格式選項，您可以按一下 ![全螢幕圖示](/help/adaptive-forms/assets/fullscreen-icon.png) 索引標籤。

  ![RTF 文字支援](/help/adaptive-forms/assets/richtext-support-title.png)

- **隱藏標題** - 選取該選項，以隱藏元件標題。
- **標示為未繫結的表單元素**：選取該選項，以設定未連結至任何結構描述的表單欄位。此選項可讓您儲存資料，且無需更新資料來源。還可讓您以自訂方式處理資料，不同於標準資料庫整合。
- **配置設定**：選取包含雲端設定的設定容器，此雲端設定將 AEM Forms 與 Google 的 reCAPTCHA 服務相連。

  >[!NOTE]
  >
  > 請參閱[在基於核心元件的 AEM 自適應表單中使用 Google reCAPTCHA](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/captcha-adaptive-forms-core-components) 一文，了解如何為您的環境建立和設定 Google reCAPTCHA。

- **類型**：選擇此選項以選取 reCAPTCHA 的大小。
   - **一般**：指的是 reCAPTCHA 小工具的標準大型版本，使用者更容易看到，互動更為便利，尤其是在畫面較大的裝置上。
   - **精簡**：指的是 reCAPTCHA 小工具的小型版本。此選項適用於空間有限的情況，例如在行動裝置上或配置密集的網頁版面上。

- **隱藏元件** - 選取該選項，以隱藏表單中的元件。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。這在您需要儲存使用者不需看到或直接變更的資訊時十分有用。

- **停用元件** - 選取該選項以停用元件。一般使用者無法啟動或編輯已停用的元件。未提交停用元件的資料。使用者可以看到欄位的值，但無法修改它。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。

- **唯讀** - 選取該選項，使元件無法編輯。使用者可以看到該欄位的值，但無法修改。元件仍可供其他用途存取，例如將其用於規則編輯器中的計算。

### 驗證索引標籤 {#validation-tab}

![驗證索引標籤](/help/adaptive-forms/assets/recaptcha-validationtab.png)

- **錯誤訊息** - 此選項可讓您輸入訊息，在已勾選&#x200B;**必要**&#x200B;核取方塊且表單欄位留空時顯示。

- **指令碼驗證訊息** - 此選項可讓您輸入訊息，以在指令碼驗證失敗時顯示。

## 設計對話框 {#design-dialog}

設計對話框可用於定義和管理 reCAPTCHA 元件的 CSS 樣式。

### 樣式索引標籤 {#styles-design-tab}

自適應表單 reCAPTCHA 核心元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話框](/help/adaptive-forms/assets/checkbox-style.png)

- **預設 CSS 類別**：您可以為自適應表單 reCAPTCHA 核心元件提供預設 CSS 類別。

- **允許的樣式**：您可以透過提供名稱以及代表該樣式的 CSS 類別，以定義樣式。例如，您可以建立名為「粗體文字」的樣式，並提供 CSS 類別「font-weight: bold」。您可以在自適應表單編輯器中，使用或套用這些樣式至自適應表單。若要套用樣式，請在自適應表單編輯器中選取您要套用樣式的元件，導覽至屬性對話框，然後從&#x200B;**樣式**&#x200B;下拉式清單中選取所需的樣式。如果需要更新或修改樣式，只需返回至設計對話框，更新樣式索引標籤中的樣式，然後儲存變更即可。

### 自訂屬性

![自訂屬性對話框](/help/adaptive-forms/assets/checkbox-customproperties.png)

自訂屬性可讓您使用表單範本，將自訂屬性 (鍵值對) 與自適應表單核心元件建立關聯。自訂屬性會反映在元件的無周邊轉譯屬性區段中。可讓您建立根據自訂屬性值調整的動態表單行為。例如，開發人員可以為行動裝置、桌上型電腦或網頁平台設計各種無周邊表單元件的轉譯，大幅提升各種裝置的使用者體驗。
- **群組名稱**：您可以提供名稱，以識別自訂屬性群組。還可以新增、刪除或重新排列多個自訂屬性群組。新增自訂屬性群組後，您可以看到下列選項：

   - **鍵值對**：按一下每個自訂屬性群組的&#x200B;**新增**&#x200B;按鈕，即可新增多個自訂屬性名稱和自訂屬性值。

   - **刪除**：點選或按一下以刪除自訂屬性名稱和自訂屬性值。

   - **重新排列**：點選或按一下並拖曳以重新排列自訂屬性名稱和自訂屬性值。


## 相關文章 {#related-articles}

{{more-like-this}}

## 另請參閱 {#see-also}

{{see-also}}
