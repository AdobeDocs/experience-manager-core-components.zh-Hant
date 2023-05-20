---
title: 電子郵件預告元件
description: 電子郵件預告元件可以顯示影像、標題、富格文本以及可選的指向其他內容的連結。
role: Architect, Developer, Admin, User
exl-id: d6123b22-7cba-406c-986d-b6f00322d135
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 1%

---


# 電子郵件預告元件 {#email-teaser-component}

電子郵件預告元件可以顯示影像、標題、富格文本以及可選的指向其他內容的連結。

## 使用狀況 {#usage}

電子郵件預告元件允許內容作者使用影像、標題或富格文本輕鬆建立預告，並連結到其他內容或其他操作。

* 模板作者可以使用 [設計對話框](#design-dialog) 定義建立「呼叫操作」和添加連結的選項是否可用以及禁用各種顯示選項。
* 內容作者可以使用 [配置對話框](#configure-dialog) 要設定影像，請定義CTA、設定標題和說明，以及配置指向單個預告的連結。
* 的 [編輯對話框](image.md#edit-dialog) 的 [電子郵件映像元件](image.md) 可訪問以修改預激影像。

## 版本和相容性 {#version-and-compatibility}

電子郵件預告元件的當前版本是v1，該版本於2022年10月隨第x版電子郵件核心元件一起推出，本文檔對此進行了說明。

下表詳細說明了元件的所有受支援版本、AEM元件版本與之相容的版本，以及指向早期版本文檔的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | - |

### 技術詳細資訊 {#technical-details}

有關電子郵件預告元件的最新技術文檔 [中。](https://adobe.com/go/aem_cmp_tech_email_teaser_v1)

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔。](/help/developing/overview.md)

## 配置對話框 {#configure-dialog}

內容作者可以使用配置對話框來定義單個預告的屬性。 還有 [編輯對話框](#edit-dialog) 修改預激影像。

### 連結頁籤 {#links-tab}

![電子郵件預告元件的編輯對話框連結頁籤](/help/email/assets/email-teaser-edit-links.png)

預告標題、描述和影像可以從連結的內容或從在第一呼叫操作中連結的內容繼承。 如果既未指定連結也未指定操作呼叫，則標題、說明和影像將從當前內容中繼承。

* **連結**  — 此檔案連結到內容、外部URL或錨點。
   * 按一下「市場活動」表徵圖以開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。
* **行動要求**  — 此選項允許連結到多個目標。
   * 在繼承預告標題、說明或影像時，將使用第一個操作調用中連結的頁面。
   * 按一下「市場活動」表徵圖以開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。

### 文本頁籤 {#text-tab}

![電子郵件預告元件的編輯對話框文本頁籤](/help/email/assets/email-teaser-edit-text.png)

* **前標題**  — 預標題將顯示在預告標題之前。
* **標題**  — 定義要顯示為預告標題的標題。
   * 按一下「市場活動」表徵圖以開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。
   * **從連結頁面獲取標題**  — 選中後，標題將填充連結頁面的標題。
* **說明**  — 定義要顯示為預告子標題的說明。
   * 按一下 **選擇Adobe Campaign變數** 表徵圖以開啟 [選擇Adobe Campaign變數](/help/email/campaign-variables.md) 對話框，插入來自Adobe Campaign的動態內容。
   * **從連結頁面獲取描述**  — 選中後，將使用連結頁面的說明填充說明。
* **ID**  — 此選項允許控制HTML中元件的唯一標識符。
   * 如果留空，則系統會為您自動生成唯一ID，並且可以通過檢查生成的內容來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS。

### 資產標籤 {#asset-tab}

![電子郵件預告元件的編輯對話框影像頁籤](/help/email/assets/email-teaser-edit-image.png)

* **從頁面繼承特色影像**  — 使用連結頁面或當前頁面的頁面屬性中定義的影像（如果找不到）。
* **影像資產**  — 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點擊 **瀏覽** 從本地檔案系統上載。
   * 點擊或按一下 **清除** 來取消選擇當前選定的映像。
   * 點擊或按一下 **編輯** 至 [管理資產的格式副本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 的子菜單。
* **輔助工具的備選文本**  — 此欄位允許您為視力受損的用戶定義影像描述。
   * **從頁面繼承備選文本**  — 此選項使用連結資產值的替代說明 `dc:description` DAM中的元資料，或當前頁的元資料（如果未連結任何資產）。
* **不提供替代文本**  — 此選項標籤要被螢幕閱讀器等輔助技術忽略的影像，在這些情況下，影像純粹是裝飾性的，或者沒有向頁面傳送其他資訊。

>[!NOTE]
>
>[Dynamic Media特徵](image.md#dynamic-media) 當前在預激元件中不可用。

### 樣式頁籤 {#styles-tab-edit}

電子郵件預告元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)

使用下拉框選擇要應用於元件的樣式。 在編輯對話框中所做的選擇與從元件工具欄中選擇的選項具有相同的效果。

必須在 [設計對話框](#design-dialog) 以便該頁籤可用。

## 編輯對話框 {#edit-dialog}

電子郵件預告元件將影像呈現委託給 [影像元件](image.md)。 因此 [編輯對話框](image.md#edit-dialog) 內容作者可以使用「影像元件」來操作預告影像。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者在使用此元件時具有的預告選項。

### 預告頁籤 {#teaser-tab}

![電子郵件預告元件的設計對話框](/help/email/assets/email-teaser-design.png)

* **允許的標題元素**  — 使用下拉框定義作者可以為預告標題類型選擇的標題HTML元素。
* **標題的預設標題元素**  — 用於預告標題類型的預設標題HTML元素
* **呼叫動作**
   * **禁用呼叫操作**  — 隱藏 **行動要求** 內容作者選項
* **元素**
   * **隱藏前標題**  — 隱藏 **前標題** 內容作者選項
   * **隱藏標題**  — 隱藏 **標題** 內容作者選項
      * 選中時 **標題類型** 隱藏
   * **顯示標題類型**
   * **隱藏說明**  — 隱藏 **說明** 內容作者選項
* **影像委託**  — 資訊性顯示，指示電子郵件預告委託影像處理的元件。

### 樣式頁籤 {#styles-tab}

電子郵件預告元件支AEM持 [樣式系統。](/help/get-started/authoring.md#component-styling)
