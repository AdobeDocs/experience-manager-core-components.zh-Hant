---
title: Teaser元件(v1)
description: Teaser元件可顯示影像、標題、RTF文字，並可選擇連結至其他內容。
role: Architect, Developer, Admin, User
exl-id: 48e56938-660a-43e7-9e62-8069283ae73f
source-git-commit: 84e09fa64b3a7ae40ff3ff1a04ea1c7504db29d2
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# Teaser元件(v1) {#teaser-component}

核心元件Teaser元件可顯示影像、標題、RTF文字，並可選擇連結至其他內容。

## 使用狀況 {#usage}

Teaser元件可讓內容作者輕鬆建立Teaser，以使用影像、標題或RTF文字進一步擴充內容，並連結至進一步內容或其他動作。

範本作者可以使用 [設計對話方塊](#design-dialog) 定義是否有建立行動號召和新增連結的選項可用，以及停用各種顯示選項。 內容作者可以使用 [設定對話方塊](#configure-dialog) 若要設定影像、定義CTA、設定標題和說明，以及設定個別Teaser的連結。 此 [編輯對話方塊](image-v1.md#edit-dialog) 的 [影像元件](image-v1.md) 可存取以修改Teaser影像。

## 版本和相容性 {#version-and-compatibility}

本檔案說明Teaser元件v1，此版本隨2018年7月的核心元件發行版本2.1.0的發佈引入。

>[!CAUTION]
>
>本檔案說明Teaser元件v1。
>
>如需目前版本Teaser元件的詳細資訊，請參閱 [Teaser元件](/help/components/teaser.md) 檔案。

## 範例元件輸出 {#sample-component-output}

若要體驗Teaser元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_teaser).

### 技術細節 {#technical-details}

有關Teaser元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_teaser_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

內容作者可以使用設定對話方塊來定義個別Teaser的屬性。 此外， [編輯對話方塊](#edit-dialog) 修改Teaser影像（如果已選取）。

### 影像 {#image}

![Teaser元件的「編輯」對話方塊影像標籤](/help/assets/teaser-edit-image.png)

* **影像資產**
   * 從拖放資產 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點選 **瀏覽** 從本機檔案系統上傳的選項。
   * 點選或按一下 **清除** 以取消選取目前選取的影像。
   * 點選或按一下 **編輯** 至 [管理資產的轉譯](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 在資產編輯器中。

>[!NOTE]
>
>[Dynamic Media功能](image-v1.md#dynamic-media) 目前在Teaser元件中不可用。

### 文字 {#text}

![Teaser元件的編輯對話方塊文字索引標籤](/help/assets/teaser-edit-text.png)

* **前置標題**  — 前置標題顯示在Teaser的標題之前。
* **標題**  — 定義顯示為Teaser大標題的標題。
   * **從連結的頁面取得標題**  — 選取後，標題會填入連結頁面的標題。
* **說明**  — 定義顯示為Teaser子標題的說明。
   * **從連結的頁面取得說明**  — 選取後，系統會使用連結頁面的說明來填入說明。
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

### 連結與動作 {#links-actions}

![Teaser元件的「編輯」對話方塊連結標籤](/help/assets/teaser-edit-link.png)

* **連結**  — 套用至Teaser的連結。 使用路徑瀏覽器來選取連結目標。
* **啟用呼叫動作**  — 勾選後，會啟用呼叫動作的定義。 清單中的第一個行動號召連結會用作其他Teaser元素的連結。

## 編輯對話方塊 {#edit-dialog}

Teaser元件會將影像演算委派給 [影像元件](image-v1.md). 因此， [編輯對話方塊](image-v1.md#edit-dialog) 內容作者可以使用影像元件的來操作Teaser影像。

## 設計對話方塊 {#design-dialog}

「設計」對話方塊可讓範本作者定義內容作者在使用此元件時的Teaser選項。

### Teaser索引標籤 {#teaser-tab}

![Teaser元件的設計對話方塊](/help/assets/teaser-design.png)

* **呼叫動作**
   * **停用呼叫動作**  — 隱藏 **行動號召** 內容作者的選項
* **元素**
   * **隱藏前置標題**  — 隱藏 **前置標題** 內容作者的選項
   * **隱藏標題**  — 隱藏 **標題** 內容作者的選項
      * 選取時 **標題型別** 隱藏
   * **隱藏說明**  — 隱藏 **說明** 內容作者的選項
* **標題型別**  — 定義Teaser標題使用的H標籤。
* **連結**
   * **不要連結影像**  — 選取時，不會連結Teaser影像
   * **不要連結標題**  — 選取時，未連結Teaser標題
* **影像委派**  — 資訊性顯示，指出Teaser將影像處理委派給哪個元件。

### 樣式索引標籤 {#styles-tab}

Teaser元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe使用者端資料層 {#data-layer}

Teaser元件支援 [Adobe使用者端資料層。](/help/developing/data-layer/overview.md)
