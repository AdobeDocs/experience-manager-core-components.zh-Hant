---
title: 內容片段清單元件
description: 核心元件內容片段清單元件可顯示內容片段的清單。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 0%

---


# 內容片段清單元件{#content-fragment-list-component}

核心元件內容片段清單元件允許顯示[內容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)的清單。

## 使用狀況 {#usage}

核心元件內容片段清單元件允許基於內容片段模型在頁面上包含[內容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)的清單。 這對於建立其他應用程式可輕鬆使用的[無頭內容](https://helpx.adobe.com/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js)特別有用。

* 在[configure dialog](#configure-dialog)中可以選擇清單及其屬性。
* 樣式可套用至[設計對話方塊](#design-dialog)中的元件。

## 版本和相容性{#version-and-compatibility}

目前的內容片段元件版本為v1，此版本於2019年5月隨核心元件2.4.0版推出，並在本檔案中加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容 | 相容 | 相容 |

有關核心元件版本和版本的詳細資訊，請參閱文檔[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗「內容片段清單元件」，並檢視其設定選項的範例以及HTML和JSON輸出，請造訪[元件庫](https://adobe.com/go/aem_cmp_library_cflist)。

## 技術詳細資訊{#technical-details}

有關內容片段清單元件[的最新技術檔案可在GitHub](https://adobe.com/go/aem_cmp_tech_cflist_v1)上找到。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

設定對話方塊可讓內容作者定義要包含清單的內容片段以及這些片段的元素。

### 屬性標籤

**屬性**&#x200B;標籤定義清單中包含哪些內容片段。 這主要是以選取的內容片段模型為基礎，但有其他可用的篩選選項。

![內容片段清單元件的編輯對話框的屬性頁籤](/help/assets/content-fragment-list-properties.png)

* **模型** -清單所依據之內容片段模型的路徑。
   * 預設情況下，定義為&#x200B;**Model Path**&#x200B;的模型的所有內容片段都包括在清單中。
* **父路徑** -應從中構建清單的父路徑。
   * 基於所選&#x200B;**模型路徑**&#x200B;的內容片段將被過濾為指定&#x200B;**父路徑**&#x200B;上的內容片段。
      * 按一下或點選欄位右側的&#x200B;**開啟選擇對話框**&#x200B;按鈕以指定路徑。
* **標籤** -清單中只會包含具有指定標籤的內容片段。
   * 按一下或點選欄位右側的&#x200B;**開啟選擇對話方塊**&#x200B;按鈕，以指定標籤。
   * 按一下或點選選取標籤旁的X以移除標籤。
* **Order By** -內容片段模型的欄位，清單將依此欄位排序
   * 只有文字欄位（包括數值、日期和時間）可供選取。
* **排序順序** -如何按順序按字 **段排** 序
   * 遞增或遞減
* **最大項目** -清單中要顯示的項目數上限
   * 沒有值會傳回所有項目。
* **ID**  —— 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 如果保留空白，則會自動為您產生唯一ID，並透過檢查產生的頁面找到。
   * 如果指定ID，則作者有責任確保其唯一性。
   * 變更ID可能會影響CSS、JS和資料圖層追蹤。

>[!NOTE]
>核心元件2.7.0版中引入了&#x200B;**排序依據**、**排序順序**&#x200B;和&#x200B;**最大項目**&#x200B;選項。

### 元素標籤

依預設，「內容片段模型」的所有元素都會包含在清單中（除非受&#x200B;**最大項目**&#x200B;欄位限制）。 **Elements**&#x200B;標籤允許您僅指定要包含的特定元素。

![內容片段清單元件編輯對話方塊的「元素」索引標籤](/help/assets/content-fragment-list-elements.png)

* **Elements**  —— 只會顯示指定清單中內容片段的元素。
   * 按一下或點選「新增&#x200B;****」按鈕以新增元素。
   * 按一下或點選&#x200B;**Delete**&#x200B;按鈕以移除選取的元素。
   * 拖動&#x200B;**Order**&#x200B;控制代碼以重新排列元素的順序。

## 設計對話框{#design-dialog}

設計對話框允許模板作者定義應用於內容片段清單元件的樣式。
