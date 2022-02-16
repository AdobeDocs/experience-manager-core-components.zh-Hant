---
title: 預告元件(v1)
description: 該預告元件可以顯示影像、標題、富格文本以及可選地連結到其它內容。
role: Architect, Developer, Admin, User
source-git-commit: f8aa86d58ba71ede3c3cd867c45aafff06923325
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 1%

---


# 預告元件(v1) {#teaser-component}

核心元件預告元件可以顯示影像、標題、富格文本，並可選地連結到其他內容。

## 使用狀況 {#usage}

該預告元件允許內容作者使用影像、標題或富格文本容易地建立預告，以進一步內容，並連結到其他內容或其他動作。

模板作者可以使用 [設計對話框](#design-dialog) 定義建立「呼叫操作」和添加連結的選項是否可用以及禁用各種顯示選項。 內容作者可以使用 [配置對話框](#configure-dialog) 要設定影像，請定義CTA、設定標題和說明，以及配置指向單個預告的連結。 的 [編輯對話框](image-v1.md#edit-dialog) 的 [影像元件](image-v1.md) 可訪問以修改預激影像。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了Teaser元件的v1 ，該元件於2018年7月隨核心元件2.1.0版一同推出。

>[!CAUTION]
>
>本文檔介紹預告元件的v1。
>
>有關預告元件當前版本的詳細資訊，請參見 [預告元件](/help/components/teaser.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

要體驗預告元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_teaser)。

### 技術詳細資訊 {#technical-details}

有關預告元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_teaser_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

內容作者可以使用配置對話框來定義單個預告的屬性。 還有 [編輯對話框](#edit-dialog) 修改預激影像。

### 影像 {#image}

![預告元件的編輯對話框影像頁籤](/help/assets/teaser-edit-image.png)

* **影像資產**
   * 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點擊 **瀏覽** 從本地檔案系統上載。
   * 點擊或按一下 **清除** 來取消選擇當前選定的映像。
   * 點擊或按一下 **編輯** 至 [管理資產的格式副本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 的子菜單。

>[!NOTE]
>
>[Dynamic Media特徵](image-v1.md#dynamic-media) 當前在預激元件中不可用。

### 文字 {#text}

![預告元件的編輯對話框文本頁籤](/help/assets/teaser-edit-text.png)

* **前標題**  — 預標題將顯示在預告標題之前。
* **標題**  — 定義要顯示為預告標題的標題。
   * **從連結頁面獲取標題**  — 選中後，標題將填充連結頁面的標題。
* **說明**  — 定義要顯示為預告子標題的說明。
   * **從連結頁面獲取描述**  — 選中後，將使用連結頁面的說明填充說明。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

### 連結和操作 {#links-actions}

![預告元件的編輯對話框連結頁籤](/help/assets/teaser-edit-link.png)

* **連結**  — 應用於預告的連結。 使用路徑瀏覽器選擇連結目標。
* **啟用呼叫操作**  — 選中後，啟用「呼叫到操作」的定義。 清單中的第一個「呼叫到操作」連結用作其他預告元素的連結。

## 編輯對話框 {#edit-dialog}

「預測元件」將影像渲染委託到 [影像元件](image-v1.md)。 因此 [編輯對話框](影像元件的image-v1.md#edit-dialog可用於內容作者操作預告影像。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義內容作者在使用此元件時具有的預告選項。

### 預告頁籤 {#teaser-tab}

![「預測元件」的設計對話框](/help/assets/teaser-design.png)

* **呼叫動作**
   * **禁用呼叫操作**  — 隱藏 **行動要求** 內容作者選項
* **元素**
   * **隱藏前標題**  — 隱藏 **前標題** 內容作者選項
   * **隱藏標題**  — 隱藏 **標題** 內容作者選項
      * 選中時 **標題類型** 隱藏
   * **隱藏說明**  — 隱藏 **說明** 內容作者選項
* **標題類型**  — 定義預告標題使用的H標籤。
* **連結**
   * **不連結影像**  — 選中後，預告影像未連結
   * **不連結標題**  — 選中時，預告標題未連結
* **影像委託**  — 資訊顯示，指示預告委託影像處理的元件。

### 樣式頁籤 {#styles-tab}

預告元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

預告元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
