---
title: 電子郵件宣傳預告元件
description: 電子郵件宣傳預告元件可顯示影像、標題、RTF，以及視需要選擇地連結至其他內容。
role: Architect, Developer, Admin, User
exl-id: d6123b22-7cba-406c-986d-b6f00322d135
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 1%

---


# 電子郵件宣傳預告元件 {#email-teaser-component}

電子郵件宣傳預告元件可顯示影像、標題、RTF，以及視需要選擇地連結至其他內容。

## 使用狀況 {#usage}

電子郵件宣傳預告元件可讓內容作者使用影像、標題或RTF輕鬆建立宣傳，並連結至其他內容或其他動作。

* 範本作者可使用 [設計對話](#design-dialog) 來定義建立動作呼叫和新增連結的選項是否可用，以及停用各種顯示選項。
* 內容作者可使用 [配置對話框](#configure-dialog) 若要設定影像，請定義CTA、設定標題和說明，以及設定個別預告的連結。
* 此 [編輯對話框](image.md#edit-dialog) 的 [電子郵件影像元件](image.md) 可以存取以修改預告影像。

## 版本與相容性 {#version-and-compatibility}

電子郵件宣傳預告元件的目前版本為v1，此版本於2022年10月隨電子郵件核心元件第x版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | 相容 |

## 範例元件輸出 {#sample-component-output}

若要體驗電子郵件宣傳預告元件，並查看其設定選項、HTML和JSON輸出的範例，請造訪 [元件庫。](https://adobe.com/go/aem_cmp_library_email_teaser)

### 技術詳細資訊 {#technical-details}

電子郵件宣傳預告元件的最新技術檔案 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_teaser_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

內容作者可使用設定對話方塊來定義個別預告的屬性。 此外， [編輯對話框](#edit-dialog) 修改預告影像（如果已選取）。

### 連結標籤 {#links-tab}

![電子郵件宣傳預告元件的編輯對話方塊連結索引標籤](/help/email/assets/email-teaser-edit-links.png)

宣傳預告標題、說明和影像可以繼承自連結的內容，或從第一個動作呼叫中連結的內容。 若未指定連結或動作呼叫，則標題、說明和影像將繼承自目前的內容。

* **連結**  — 此檔案會連結至內容、外部URL或錨點。
   * 按一下促銷活動圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。
* **動作呼叫**  — 此選項可連結至多個目的地。
   * 繼承預告標題、說明或影像時，會使用第一個動作呼叫中連結的頁面。
   * 按一下促銷活動圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。

### 文字索引標籤 {#text-tab}

![電子郵件宣傳預告元件的編輯對話方塊文字索引標籤](/help/email/assets/email-teaser-edit-text.png)

* **前置標題**  — 預先標題會顯示在預告標題之前。
* **標題**  — 定義標題，以顯示為預告的標題。
   * 按一下促銷活動圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。
   * **從連結的頁面取得標題**  — 若勾選此選項，標題將會填入連結頁面的標題。
* **說明**  — 定義要顯示為預告子標題的說明。
   * 按一下 **選取Adobe Campaign變數** 圖示以開啟 [選取Adobe Campaign變數](/help/email/campaign-variables.md) 對話方塊，從Adobe Campaign插入動態內容。
   * **從連結的頁面取得說明**  — 若勾選此選項，描述將會填入連結頁面的說明。
* **ID**  — 此選項可控制HTML中元件的唯一標識符。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查產生的內容來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會對CSS造成影響。

### 資產標籤 {#asset-tab}

![電子郵件宣傳預告元件的編輯對話方塊影像索引標籤](/help/email/assets/email-teaser-edit-image.png)

* **從頁面繼承精選影像**  — 使用在連結頁面或目前頁面的頁面屬性中定義的影像（若找不到）。
* **影像資產**  — 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點選 **瀏覽** 從本機檔案系統上傳的選項。
   * 點選或按一下 **清除** 以取消選取目前選取的影像。
   * 點選或按一下 **編輯** to [管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) （在資產編輯器中）。
* **協助工具的替代文字**  — 此欄位可讓您為視覺障礙使用者定義影像說明。
   * **從頁面繼承替代文字**  — 此選項使用 `dc:description` 中繼資料（若未連結任何資產）。
* **不提供替代文本**  — 如果影像純粹是裝飾性的，或未傳達其他資訊至頁面，此選項會標籤要由輔助技術（例如螢幕閱讀器）忽略的影像。

>[!NOTE]
>
>[Dynamic Media功能](image.md#dynamic-media) 目前在Teaser元件中不可用。

### 樣式標籤 {#styles-tab-edit}

Email Teaser元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉式清單選取您要套用至元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須針對此元件在 [設計對話](#design-dialog) 讓索引標籤可用。

## 編輯對話方塊 {#edit-dialog}

電子郵件宣傳預告元件會將影像呈現委派至 [影像元件](image.md). 因此， [編輯對話框](image.md#edit-dialog) 內容作者可使用影像元件來操作預告影像。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者使用此元件時具有的宣傳預告選項。

### Teaser標籤 {#teaser-tab}

![電子郵件宣傳預告元件的設計對話方塊](/help/email/assets/email-teaser-design.png)

* **允許的標題元素**  — 使用下拉式清單定義製作人員可針對預告標題類型選取的標題HTML元素。
* **標題的預設標題元素**  — 預設標題HTML元素，用於預設宣傳的標題類型
* **呼叫動作**
   * **停用呼叫動作**  — 隱藏 **呼叫動作** 內容作者選項
* **元素**
   * **隱藏首頁**  — 隱藏 **前置標題** 內容作者選項
   * **隱藏標題**  — 隱藏 **標題** 內容作者選項
      * 選取 **標題類型** 隱藏
   * **顯示標題類型**
   * **隱藏說明**  — 隱藏 **說明** 內容作者選項
* **影像委派**  — 資訊性顯示，指出Email Teaser委派影像處理的元件。

### 樣式標籤 {#styles-tab}

Email Teaser元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling)
