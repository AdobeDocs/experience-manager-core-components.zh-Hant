---
title: 內容片段清單元件
description: 利用核心元件內容片段清單元件，可顯示內容片段清單。
role: Architect, Developer, Admin, User
exl-id: 0f2295b1-d287-4f72-8ee4-fa98c4850e53
source-git-commit: 395a1669cf3e17f649c23852addc37316b923bfd
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 2%

---

# 內容片段清單元件{#content-fragment-list-component}

核心元件內容片段清單元件允許顯示清單 [內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

## 使用狀況 {#usage}

核心元件內容片段清單元件允許包含清單 [內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 在根據內容片段模式的頁面上。 這在建立時特別有用 [Headless內容](https://helpx.adobe.com/tw/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) 其他應用程式可輕鬆使用的擴充功能。

* 清單及其屬性可在 [設定對話方塊](#configure-dialog).
* 樣式可套用至中的元件 [設計對話方塊](#design-dialog).

## 版本和相容性 {#version-and-compatibility}

內容片段元件的目前版本是v2，此版本隨2022年2月的核心元件2.18.0版的發佈引入，具體說明見本文。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|---|----|---|---|
| v2 | - | 相容 | 相容 |
| [v1](v1/content-fragment-list.md) | 相容 | 相容 | 相容 |

如需核心元件版本和發行版本的詳細資訊，請參閱檔案 [核心元件版本](/help/versions.md).

## 範例元件輸出 {#sample-component-output}

若要體驗內容片段清單元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪 [元件資料庫](https://adobe.com/go/aem_cmp_library_cflist).

## 技術細節 {#technical-details}

有關內容片段清單元件的最新技術檔案 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_cflist_v1).

有關開發核心元件的進一步詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).

## 設定對話方塊 {#configure-dialog}

此設定對話方塊可讓內容作者定義構成清單的內容片段，以及要包含的片段元素。

### 屬性標籤

此 **屬性** 索引標籤會定義清單中包含的內容片段。 這主要是根據選定的內容片段模式，但還有其他可用的篩選選項。

![內容片段清單元件之「編輯」對話方塊的「屬性」索引標籤](/help/assets/content-fragment-list-properties.png)

* **模型**  — 清單所根據的內容片段模式的路徑。
   * 根據預設，模型的所有內容片段定義為 **模型路徑** 包含在清單中。
* **父路徑**  — 應從中建立清單的父路徑。
   * 根據所選的內容片段 **模型路徑** 將會篩選為指定上的專案 **父路徑**.
      * 按一下或點選 **開啟選取範圍對話方塊** 欄位右側的按鈕，指定路徑。
* **標籤**  — 只有具有指定標籤的內容片段會包含在清單中。
   * 按一下或點選 **開啟選取範圍對話方塊** 欄位右側的按鈕，用於指定標籤。
   * 按一下或點選所選標籤旁的X以移除它們。
* **排序方式**  — 清單排序所依據的內容片段模型欄位
   * 只能選取文字欄位（包括數值、日期和時間）。
* **排序順序**  — 清單如何依 **排序方式** 欄位
   * 遞增或遞減
* **專案數量上限**  — 清單中顯示的最大專案數量
   * 沒有值會傳回所有專案。
* **ID**  — 此選項可讓您控制HTML和中的元件唯一識別碼 [資料層](/help/developing/data-layer/overview.md).
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID是唯一的。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

>[!NOTE]
>此 **排序方式**， **排序順序**、和 **專案數量上限** 核心元件2.7.0版中引進了選項。

### 元素標籤

依預設，內容片段模式的所有元素將包含在清單中（除非受到以下限制） **專案數量上限** 欄位)。 此 **元素** tab可讓您僅指定要包含的特定元素。

![內容片段清單元件之「編輯」對話方塊的「元素」索引標籤](/help/assets/content-fragment-list-elements.png)

* **元素**  — 只有指定清單中的內容片段元素會出現。
   * 按一下或點選 **新增** 按鈕來新增元素。
   * 按一下或點選 **刪除** 按鈕以移除選取的元素。
   * 拖曳 **訂購** 操作框可重新排列元素的順序。

### 樣式索引標籤 {#styles-tab-edit}

![內容片段清單元件之「編輯」對話方塊的「樣式」索引標籤](/help/assets/content-fragment-list-styles.png)

內容片段清單元件支援AEM [樣式系統。](/help/get-started/authoring.md#component-styling).

使用下拉式清單，選取要套用至元件的樣式。 在「編輯」對話方塊中所做的選取與從元件工具列中選擇的效果相同。

必須在以下位置為此元件設定樣式： [設計對話方塊](#design-dialog) 讓下拉式功能表可供使用。

## 設計對話方塊 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

內容片段清單元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).
