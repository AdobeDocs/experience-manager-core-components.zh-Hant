---
title: 內容片段清單元件(v1)
description: 核心元件內容片段清單元件允許顯示內容片段清單。
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 1%

---


# 內容片段清單元件(v1) {#content-fragment-list-component}

核心元件內容片段清單元件允許顯示 [內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

## 使用狀況 {#usage}

核心元件內容片段清單元件允許包含 [內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 基於內容片段模型的頁面。 這對建立 [無頭內容](https://helpx.adobe.com/tw/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) 可供其他應用程式輕鬆使用。

* 可在 [配置對話框](#configure-dialog)。
* 樣式可應用於 [設計對話框](#design-dialog)。

## 版本和相容性 {#version-and-compatibility}

該文檔描述了2019年5月隨核心元件2.4.0版推出的內容片段元件v1。

>[!CAUTION]
>
>本文檔介紹內容片段清單元件的v1。
>
>有關內容片段清單元件的當前版本的詳細資訊，請參見 [內容片段清單元件](/help/components/content-fragment-list.md) 的子菜單。

## 元件輸出示例 {#sample-component-output}

要體驗「內容片段清單」元件，並查看其配置選項示例以及HTML和JSON輸出，請訪問 [元件庫](https://adobe.com/go/aem_cmp_library_cflist)。

## 技術詳細資訊 {#technical-details}

有關內容片段清單元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_cflist_v1)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 配置對話框 {#configure-dialog}

配置對話框允許內容作者定義哪些內容片段包括清單以及要包括的這些片段的元素。

### 屬性頁籤

的 **屬性** 頁籤定義清單中包含的內容片段。 這主要基於選定的內容片段模型，但有其他可用的篩選器選項。

![內容片段清單元件的編輯對話框的屬性頁籤](/help/assets/content-fragment-list-properties.png)

* **模型**  — 清單所基於的內容片段模型的路徑。
   * 預設情況下，模型的所有內容片段定義為 **模型路徑** 清單中。
* **父路徑**  — 應從中生成清單的父路徑。
   * 基於所選內容的內容片段 **模型路徑** 將篩選到指定的 **父路徑**。
      * 按一下或點擊 **開啟選擇對話框** 的子菜單。
* **標籤**  — 清單中將只包含具有指定標籤的內容片段。
   * 按一下或點擊 **開啟選擇對話框** 的子菜單。
   * 按一下或點擊選定標籤旁的X以將其刪除。
* **排序依據**  — 內容片段模型的欄位，按該欄位排序清單
   * 只能選擇文本欄位（包括數字、日期和時間）。
* **排序順序**  — 清單將如何按 **排序依據** 場
   * 升序或降序
* **最大項**  — 要在清單中顯示的最大項目數
   * 沒有值將返回所有項目。
* **ID**  — 此選項允許控制HTML和 [資料層](/help/developing/data-layer/overview.md)。
   * 如果留空，則系統會為您自動生成唯一ID，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

>[!NOTE]
>的 **排序依據**。 **排序順序**, **最大項** 選項隨2.7.0版核心元件一起推出。

### 元素頁籤

預設情況下，「內容片段模型」的所有元素都將包括在清單中(除非受 **最大項** )。 的 **元素** 頁籤允許您僅指定要包括的特定元素。

![內容片段清單元件的編輯對話框的元素頁籤](/help/assets/content-fragment-list-elements.png)

* **元素**  — 將只顯示指定清單中內容片段的元素。
   * 按一下或點擊 **添加** 按鈕
   * 按一下或點擊 **刪除** 按鈕
   * 拖動 **訂單** 控制滑塊以重新排列元素的順序。

## 設計對話框 {#design-dialog}

設計對話框允許模板作者定義應用於內容片段清單元件的樣式。
