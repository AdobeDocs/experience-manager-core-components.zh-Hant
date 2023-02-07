---
title: 目錄元件
description: 目錄元件會根據頁面內容中的標題建立ToC，讓讀者快速導覽頁面。
role: Architect, Developer, Admin, User
exl-id: 006adde2-ebff-4e74-8e79-325cccd43e8f
source-git-commit: 8beae61676340e8aafaee469018d865ea7ed934e
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 1%

---

# 目錄元件 {#table-of-contents-component}

目錄元件會根據頁面內容中的標題建立ToC，讓讀者快速導覽頁面。

## 使用狀況 {#usage}

「目錄」元件讓網站訪客能根據頁面內容的標題，透過有效產生的ToC快速導覽您的頁面內容。

* ToC在伺服器端產生。
* Dispatcher會完全快取該快取，以便快速傳送。
* 它可與頁面上的所有元件搭配使用，而不只是核心元件。

此 [編輯對話框](#edit-dialog) 可讓內容作者定義要在ToC中使用的標題範圍。 使用 [設計對話](#design-dialog)，當內容作者新增目錄元件至頁面時，範本作者可設定標題的預設值，並根據類別名稱限制ToC中包含的標題。

## 版本與相容性 {#version-and-compatibility}

目前的目錄元件版本為v1，此版本於2022年5月2.20.0版核心元件時推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.5 | AEM as a Cloud Service  |
|---|---|---|
| v1 | 相容 | 相容 |

如需核心元件版本和版本的詳細資訊，請參閱本檔案 [核心元件版本](/help/versions.md).

>[!NOTE]
>
>在AEMas a Cloud Service上，管理員必須啟用元件的篩選器，才能呈現元件的內容。
>
>[請參閱元件的GitHub檔案](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1) 以取得更多資訊。

### 技術詳細資訊 {#technical-details}

目錄元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1).

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 編輯對話方塊 {#edit-dialog}

編輯對話方塊可讓內容作者定義目錄元件應呈現為ToC的標題層級範圍。

![目錄元件的編輯對話框](/help/assets/tableofcontents-edit.png)

**清單類型**  — 此選項定義清單應為項目符號清單還是編號清單。
* **標題開始級別**  — 此選項定義目錄元件應呈現的最高級別標題。
* **標題停止級別**  — 此選項定義目錄元件應呈現的最低級別標題。
* **ID**  — 此選項可控制HTML中和 [資料層](/help/developing/data-layer/overview.md).
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

## 設計對話方塊 {#design-dialog}

使用設計對話框，模板作者可以設定目錄元件標題範圍的預設值，並根據類名限制ToC中包含的標題。

### 屬性標籤 {#properties-tab}

![快速搜索元件的設計對話框](/help/assets/tableofcontents-design.png)

* **限制清單類型**  — 此選項定義元件將生成的清單類型。 選取此選項會限制內容作者選擇其他清單類型的能力。
* **限制開始級別**  — 此選項定義內容作者可為定義ToC而選取的最高標題層級。
* **限制停止級別**  — 此選項定義內容作者可為定義ToC而選擇的最低標題級別。
* **包括類名**  — 如果設定了此選項，則目錄元件將只考慮具有指定類名或包含在指定類名元素中的標題。
   * 點選或按一下 **新增** 表徵圖，添加一個或多個類名。
   * 點選或按一下 **刪除** 表徵圖，將其刪除。
* **忽略類名**  — 如果設定了此選項，則目錄元件將忽略具有指定類名或包含在指定類名的元素中的標題。
   * 點選或按一下 **新增** 表徵圖，添加一個或多個類名。
   * 點選或按一下 **刪除** 表徵圖，將其刪除。

### 樣式標籤 {#styles-tab}

目錄元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

## Adobe用戶端資料層 {#data-layer}

目錄元件支援 [Adobe用戶端資料層。](/help/developing/data-layer/overview.md)
