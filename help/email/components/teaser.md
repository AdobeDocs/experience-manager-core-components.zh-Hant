---
title: 電子郵件 Teaser 元件
description: 電子郵件 Teaser 元件可顯示影像、標題、RTF 文字，並可選擇性地連結至更多內容。
role: Architect, Developer, Admin, User
exl-id: d6123b22-7cba-406c-986d-b6f00322d135
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: ht
source-wordcount: '1002'
ht-degree: 100%

---


# 電子郵件 Teaser 元件 {#email-teaser-component}

電子郵件 Teaser 元件可顯示影像、標題、RTF 文字，並可選擇性地連結至更多內容。

## 用途 {#usage}

「電子郵件 Teaser 元件」可讓內容作者使用影像、標題或 RTF 文字輕鬆建立 Teaser，並連結至更多內容或其他動作。

* 範本作者可使用[設計對話框](#design-dialog)，定義建立行動號召和新增連結的選項是否可用，以及停用各種顯示選項。
* 內容作者可使用[設定對話框](#configure-dialog)設定影像、定義 CTA、設定標題與說明，並設定個別 Teaser 的連結。
* 透過存取[電子郵件影像元件](image.md)的[編輯對話框](image.md#edit-dialog)，即可修改 Teaser 影像。

## 版本和相容性 {#version-and-compatibility}

電子郵件 Teaser 元件的目前版本為 v1，此版本於 2022 年 10 月隨著電子郵件核心元件 x 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 相容 | - | - |

### 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_teaser_v1)有關電子郵件 Teaser 元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件。](/help/developing/overview.md)

## 設定對話框 {#configure-dialog}

內容作者可以使用設定對話框定義個別 Teaser 的屬性。若已選取 Teaser 影像，同樣可透過[編輯對話框](#edit-dialog)修改。

### 連結索引標籤 {#links-tab}

![電子郵件 Teaser 元件的編輯對話框連結索引標籤](/help/email/assets/email-teaser-edit-links.png)

Teaser 標題、說明和影像可以從所連結的頁面繼承，也可以從第一個行動號召中所連結的頁面繼承。如果連結或行動號召都未指定，則會從當前的頁面繼承標題、說明和影像。

* **連結** - 此檔案連結至內容、外部 URL 或錨點。
   * 按一下行銷活動圖示以開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入來自 Adobe Campaign 的動態內容。
* **行動號召** - 此選項允許連結至多個目標。
   * 繼承 Teaser 標題、說明或影像時，將使用第一個行動號召中所連結的頁面。
   * 按一下行銷活動圖示以開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入來自 Adobe Campaign 的動態內容。

### 文字索引標籤 {#text-tab}

![電子郵件 Teaser 元件的編輯對話框文字索引標籤](/help/email/assets/email-teaser-edit-text.png)

* **前置標題** - 前置標題將顯示在 Teaser 標題之前。
* **標題** - 定義要顯示為 Teaser 標題的標題。
   * 按一下行銷活動圖示以開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入來自 Adobe Campaign 的動態內容。
   * **從連結的頁面取得標題** - 勾選後，標題將填入連結頁面的標題。
* **說明** - 定義要顯示為 Teaser 副標題的說明。
   * 按一下&#x200B;**選取 Adobe Campaign 變數**&#x200B;圖示，開啟[選取 Adobe Campaign 變數](/help/email/campaign-variables.md)對話框，插入 Adobe Campaign 的動態內容。
   * **從連結頁面取得說明** - 勾選後，說明將填入連結頁面的說明。
* **ID** - 此選項允許控制 HTML 中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的內容找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS 產生影響。

### 資產索引標籤 {#asset-tab}

![電子郵件 Teaser 元件的編輯對話框影像索引標籤](/help/email/assets/email-teaser-edit-image.png)

* **從頁面繼承精選影像** - 使用連結頁面的頁面屬性中定義的影像，如果沒有找到，則會使用當前的頁面。
* **影像資產** - 從[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hant)拖曳資產，或點選&#x200B;**瀏覽**&#x200B;選項，以從本機檔案系統上傳。
   * 點選或按一下&#x200B;**「清除」**，取消選取目前選取的影像。
   * 點選或按一下&#x200B;**編輯**，以在 Asset Editor 中[管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=zh-Hant)。
* **協助工具替代文字** - 此欄位可讓您為視障使用者定義影像的說明。
   * **從頁面繼承替代文字** - 此選項會使用 DAM 中 `dc:description` 後設資料所連結資產值的替代說明，若未連結任何資產，則會使用目前頁面的替代說明。
* **不提供替代文字** - 此選項會標記該影像被螢幕助讀程式等輔助技術忽略，適用於影像僅用於裝飾或不向頁面傳達額外資訊的情況。

>[!NOTE]
>
>[Dynamic Media 功能](image.md#dynamic-media)目前無法在 Teaser 元件中使用。

### 樣式索引標籤 {#styles-tab-edit}

電子郵件 Teaser 元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取想要套用至元件的樣式。在編輯對話框中所做的選取，與從元件工具列中選擇具有相同效果。

元件樣式必須在[設計對話框](#design-dialog)中設定，才能使用該索引標籤。

## 編輯對話框 {#edit-dialog}

電子郵件 Teaser 元件將影像轉譯委派給[影像元件](image.md)。因此，內容作者可使用影像元件的[編輯對話框](image.md#edit-dialog)來調整 Teaser 影像。

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義內容作者在使用此元件時具備的 Teaser 選項。

### Teaser 索引標籤 {#teaser-tab}

![電子郵件 Teaser 元件的設計對話框](/help/email/assets/email-teaser-design.png)

* **允許的標題元素** - 使用下拉式清單，定義作者可以選取哪些標題 HTML 元素作為 Teaser 的標題類型。
* **標題的預設標題元素** - 用於 Teaser 標題類型的預設標題 HTML 元素
* **行動號召**
   * **停用行動號召** - 對內容作者隱藏&#x200B;**行動號召**&#x200B;選項
* **元素**
   * **隱藏前置標題** - 對內容作者隱藏「**前置標題**」選項
   * **隱藏標題** - 對內容作者隱藏&#x200B;**標題**&#x200B;選項
      * 選取後，**標題類型**&#x200B;會隱藏
   * **顯示標題類型**
   * **隱藏說明** - 對內容作者隱藏「**說明**」選項
* **影像委派** - 資訊顯示，指示電子郵件 Teaser 要委派影像處理的元件。

### 樣式索引標籤 {#styles-tab}

電子郵件 Teaser 元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
