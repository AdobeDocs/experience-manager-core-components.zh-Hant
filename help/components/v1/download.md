---
title: 下載元件(v1)
description: 核心元件下載元件允許在頁面上建立下載選項。
role: Architect, Developer, Admin, User
source-git-commit: f8aa86d58ba71ede3c3cd867c45aafff06923325
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 0%

---


# 下載元件(v1) {#download-component}

核心元件下載元件允許在頁面上建立下載選項。

## 使用狀況 {#usage}

核心元件下載元件允許在頁面上包含下載選項及其關聯資產。

* 可在 [配置對話框](#configure-dialog)。
* 可以在 [設計對話框](#design-dialog)。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了2019年6月隨核心元件2.5.0版一起推出的下載元件v1。

>[!CAUTION]
>
>本文檔介紹下載元件的v1。
>
>For details of the current version of the Download Component, see the [Download Component](/help/components/download.md) document.

## 元件輸出示例 {#sample-component-output}

要體驗下載元件，並查看其配置選項以及HTML和JSON輸出的示例，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_download)。

## 技術詳細資訊 {#technical-details}

有關下載元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_download_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義下載項目及其行為和對頁面訪問者的顯示方式。

![「下載元件的編輯」對話框的「資產」頁籤](/help/assets/download-edit-asset.png)

### 資產標籤 {#asset-tab}

選擇下載資產與 [影像元件](image-v1.md) 同樣利AEM用DAM

* **下載資產**
   * 從 [資產瀏覽器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或點擊 **瀏覽** 從本地檔案系統上載。
   * 點擊或按一下 **清除** 來取消選擇當前選定的映像。
   * 點擊或按一下 **編輯** 至 [管理資產的格式副本](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 的子菜單。

### 屬性頁籤 {#properties-tab}

![下載元件編輯對話框的屬性頁籤](/help/assets/download-edit-properties.png)

* **標題**  — 顯示為下載項的標題
   * **從DAM資產獲取標題**  — 選中後，標題將自動填充DAM資產的標題。
* **說明**  — 顯示為下載項的說明性子標題
   * **從DAM資產獲取說明**  — 選中後，將自動用DAM資產的說明填充說明。
* **操作文本**  — 顯示為下載項的操作文本
   * 從檔案系統上載資產時，此欄位是必需的。
   * **內聯顯示**  — 選擇提供的 **操作文本** 將顯示內聯。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義使用「下載元件」的內容作者可用的選項。

### 屬性頁籤 {#properties-tab-design}

![下載元件的「設計」對話框](/help/assets/download-design.png)

* **允許從檔案系統上載**  — 允許內容作者從其本地檔案系統上載資產作為下載資產。
   * 未選擇預設值。
* **標題類型**  — 用於下載元件標題的HTML元素。
   * 如果未選擇任何值，則預設值為H3。
* **顯示檔案大小**  — 選擇後，資產的檔案大小將顯示在下載元件中。
   * 將選擇預設值。
* **顯示檔案格式**  — 選擇後，資產的檔案格式將顯示在下載元件中。
   * 將選擇預設值。
* **顯示檔案名**  — 選擇後，資產的檔案名將顯示在下載元件中。
   * 將選擇預設值。

### 樣式頁籤 {#styles-tab}

映像元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。
