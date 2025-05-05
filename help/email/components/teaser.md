---
title: 電子郵件Teaser元件
description: 電子郵件Teaser元件可以顯示影像、標題、RTF文字，並可選擇連結至更多內容。
role: Architect, Developer, Admin, User
exl-id: d6123b22-7cba-406c-986d-b6f00322d135
source-git-commit: 91969e4956bef1a511b8d588d5290a7999bf86ec
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 0%

---


# 電子郵件Teaser元件 {#email-teaser-component}

電子郵件Teaser元件可以顯示影像、標題、RTF文字，並可選擇連結至更多內容。

## 使用情況 {#usage}

電子郵件Teaser元件可讓內容作者使用影像、標題或RTF文字輕鬆建立Teaser，並連結至其他內容或其他動作。

* 範本作者可以使用[設計對話方塊](#design-dialog)來定義建立行動號召和新增連結的選項是否可用，以及停用各種顯示選項。
* 內容作者可以使用[設定對話方塊](#configure-dialog)來設定影像、定義CTA、設定標題和說明，以及設定個別Teaser的連結。
* 可以存取[電子郵件影像元件](image.md)的[編輯對話方塊](image.md#edit-dialog)來修改Teaser影像。

## 版本和相容性 {#version-and-compatibility}

電子郵件Teaser元件的目前版本是v1，此版本隨2022年10月的電子郵件核心元件發行版本X的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|---|---|---|---|
| v1 | 相容 | - | - |

### 技術細節 {#technical-details}

您可以在GitHub上找到有關電子郵件Teaser元件[的最新技術檔案。](https://adobe.com/go/aem_cmp_tech_email_teaser_v1)

在[核心元件開發人員檔案中可找到有關開發核心元件的進一步詳細資料。](/help/developing/overview.md)

## 設定對話方塊 {#configure-dialog}

內容作者可以使用設定對話方塊來定義個別Teaser的屬性。 如果選取了[編輯對話方塊](#edit-dialog)以修改Teaser影像。

### 連結標籤 {#links-tab}

![電子郵件Teaser元件的編輯對話方塊連結索引標籤](/help/email/assets/email-teaser-edit-links.png)

Teaser標題、說明和影像可以從連結的內容繼承，也可以從第一個call-to-action中連結的內容繼承。 如果未指定連結或call-to-action，則會從目前內容繼承標題、說明和影像。

* **連結** — 此檔案連結到內容、外部URL或錨點。
   * 按一下Campaign圖示以開啟[選取Adobe Campaign變數](/help/email/campaign-variables.md)對話方塊，插入來自Adobe Campaign的動態內容。
* **行動號召** — 此選項可連結至多個目的地。
   * 當繼承Teaser標題、說明或影像時，將使用第一個call-to-action中連結的頁面。
   * 按一下Campaign圖示以開啟[選取Adobe Campaign變數](/help/email/campaign-variables.md)對話方塊，插入來自Adobe Campaign的動態內容。

### 文字索引標籤 {#text-tab}

![電子郵件Teaser元件的編輯對話方塊文字索引標籤](/help/email/assets/email-teaser-edit-text.png)

* **前置標題** — 前置標題會顯示在Teaser的標題之前。
* **標題** — 定義要顯示為Teaser標題的標題。
   * 按一下Campaign圖示以開啟[選取Adobe Campaign變數](/help/email/campaign-variables.md)對話方塊，插入來自Adobe Campaign的動態內容。
   * **從連結的頁面取得標題** — 勾選後，標題會填入連結頁面的標題。
* **描述** — 定義要顯示為Teaser子標題的描述。
   * 按一下&#x200B;**選取Adobe Campaign變數**&#x200B;圖示以開啟[選取Adobe Campaign變數](/help/email/campaign-variables.md)對話方塊，插入來自Adobe Campaign的動態內容。
   * **從連結的頁面取得說明** — 勾選後，說明將會填入連結頁面的說明。
* **ID** — 此選項允許控制HTML中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，但您可在檢查結果內容時找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS造成影響。

### 資產標籤 {#asset-tab}

![電子郵件Teaser元件的編輯對話方塊影像標籤](/help/email/assets/email-teaser-edit-image.png)

* **從頁面**&#x200B;繼承精選影像 — 使用連結頁面的頁面屬性中定義的影像，如果沒有找到，則使用目前頁面。
* **影像資產** — 從[資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hant)拖放資產，或點選&#x200B;**瀏覽**&#x200B;選項，從本機檔案系統上傳。
   * 點選或按一下&#x200B;**清除**&#x200B;以取消選取目前選取的影像。
   * 點選或按一下「**編輯**」以[在Asset Editor中管理資產](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=zh-Hant)的轉譯。
* **協助工具的替代文字** — 此欄位可讓您為視障使用者定義影像的說明。
   * **從頁面**&#x200B;繼承替代文字 — 此選項使用DAM中`dc:description`中繼資料之連結資產值的替代說明，或是使用目前頁面的替代說明（如果未連結資產）。
* **不提供替代文字** — 此選項會將影像標籤為被熒幕閱讀器等輔助技術忽略，以用於影像純粹起裝飾作用或不向頁面傳達額外資訊的情況。

>[!NOTE]
>
>[Dynamic Media功能](image.md#dynamic-media)目前在Teaser元件中無法使用。

### 樣式索引標籤 {#styles-tab-edit}

電子郵件Teaser元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的選取具有相同的效果。

必須在[設計對話方塊](#design-dialog)中為此元件設定樣式，才能使用索引標籤。

## 編輯對話方塊 {#edit-dialog}

電子郵件Teaser元件將影像演算委派給[影像元件](image.md)。 因此，內容作者可以使用影像元件的[編輯對話方塊](image.md#edit-dialog)來處理Teaser影像。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義內容作者在使用此元件時具有的Teaser選項。

### Teaser索引標籤 {#teaser-tab}

![電子郵件Teaser元件的設計對話方塊](/help/email/assets/email-teaser-design.png)

* **允許的標題元素** — 使用下拉式清單來定義作者可以選取哪些標題HTML元素作為Teaser的標題型別。
* **標題的預設標題元素** — 用於Teaser標題型別的預設標題HTML元素
* **行動號召**
   * **停用呼叫動作** — 隱藏內容作者的&#x200B;**呼叫動作**&#x200B;選項
* **元素**
   * **隱藏前置標題** — 隱藏內容作者的&#x200B;**前置標題**&#x200B;選項
   * **隱藏標題** — 隱藏內容作者的&#x200B;**標題**&#x200B;選項
      * 選取時，會隱藏&#x200B;**標題型別**
   * **顯示標題型別**
   * **隱藏描述** — 隱藏內容作者的&#x200B;**描述**&#x200B;選項
* **影像委派** — 資訊性顯示，指出電子郵件Teaser將影像處理委派給哪個元件。

### 樣式索引標籤 {#styles-tab}

電子郵件Teaser元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)
