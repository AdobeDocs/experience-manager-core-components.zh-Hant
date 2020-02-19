---
title: 摘要元件
description: 摘要元件可顯示影像、標題、豐富文字，並可選擇地連結至其他內容。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 摘要元件 {#teaser-component}

核心元件摘要元件可顯示影像、標題、豐富式文字，並可選擇連結至其他內容。

## 使用狀況 {#usage}

「摘要元件」可讓內容作者使用影像、標題或豐富式文字輕鬆建立摘要，以進一步內容，並連結至其他內容或其他動作。

範本作者可使用設 [計對話方塊](#design-dialog) ，定義建立動作呼叫和新增連結的選項是否可用，以及停用各種顯示選項。 內容作者可以使用 [設定對話方塊](#configure-dialog) ，來設定影像、定義CTA、設定標題和說明，以及設定個別摘要的連結。 您可 [以存取影像](image.md#edit-dialog) 元件的編輯對話方塊 [](image.md) ，以修改摘要影像。

## 版本與相容性 {#version-and-compatibility}

摘要元件的目前版本為v1，此版本於2018年7月隨核心元件2.1.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM As a Cloud Service |
|---|---|---|---|---|
| v1 | 相容 | 相容 | 相容 | 相容 |

## 元件輸出示例 {#sample-component-output}

若要體驗Teaser元件，並檢視其設定選項以及HTML和JSON輸出的範例，請造訪元 [件庫](https://adobe.com/go/aem_cmp_library_teaser)。

### 技術詳細資訊 {#technical-details}

有關摘要元件的最新技術文 [件可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_teaser_v1)。

有關開發核心元件的詳細資訊，請參閱核心元 [件開發人員檔案](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

內容作者可以使用設定對話方塊來定義個別摘要的屬性。 如果選取了摘 [要影像](#edit-dialog) ，也會出現編輯對話方塊來修改摘要影像。

### 影像 {#image}

![](/help/assets/screen_shot_2018-07-03at104125.png)

* **影像資產**
   * 從資產瀏覽器中 [拖放資產](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) ，或點選 **** 瀏覽選項，從本機檔案系統上傳。
   * 點選或按一 **下「清除** 」以取消選取目前選取的影像。
   * 點選或按一 **下「編輯** 」, [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 在資產編輯器中管理資產的轉譯。

### 文字 {#text}

![](/help/assets/screen_shot_2018-07-03at104138.png)

* **Title**（標題）定義標題，以顯示為摘要標題。
* **從連結頁面取得標**&#x200B;題勾選後，標題將填入連結頁面的標題。
* **說明**&#x200B;定義要顯示為摘要子標題的說明。
* **從連結頁面取得說**&#x200B;明勾選後，說明將會填入連結頁面的說明。

### 連結與動作 {#links-actions}

![](/help/assets/screen_shot_2018-07-03at104146.png)

* **Link** Link已套用至摘要。 使用路徑瀏覽器來選擇連結目標。
* **啟用「呼叫至動作」**&#x200B;勾選時，啟用「呼叫至動作」的定義。 清單中的第一個「行動要求」連結會用作其他摘要元素的連結。

## Edit Dialog {#edit-dialog}

摘要元件會將影像演算委派至影像 [元件](image.md)。 因此， [內容作者可]以使用「影像元件」的「編輯」對話方塊(image.md#edit-dialog)來控制摘要影像。

## 設計對話框 {#design-dialog}

設計對話方塊可讓範本作者定義內容作者使用此元件時擁有的摘要選項。

### 摘要標籤 {#teaser-tab}

![](/help/assets/screen_shot_2018-07-03at105958.png)

* **呼叫動作**
   * **停用內容作者的**「呼 **叫動作」選項**
* **元素**
   * **隱藏標題**
      * 隱藏內容作 **者的** 「標題」選項
      * 選取「標題類 **型」(Title Type** )後，
   * **隱藏說明**&#x200B;隱藏內容作 **者的「說明** 」選項
* **標題類**&#x200B;型定義摘要標題要使用的H標籤。
* **連結**
   * **不要連結影像選取**&#x200B;時，未連結摘要影像
   * **不要連結標題選取**&#x200B;時，未連結摘要標題

### 樣式標籤 {#styles-tab}

Teaser元件支援AEM [Style系統](/help/get-started/authoring.md#component-styling)。
