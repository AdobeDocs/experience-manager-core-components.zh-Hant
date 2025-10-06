---
title: 內容片段清單元件
description: 核心元件內容片段清單元件允許顯示內容片段清單。
role: Architect, Developer, Admin, User
exl-id: 0f2295b1-d287-4f72-8ee4-fa98c4850e53
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '806'
ht-degree: 100%

---


# 內容片段清單元件{#content-fragment-list-component}

核心元件內容片段清單元件允許顯示[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)清單。

{{traditional-aem}}

## 用途 {#usage}

核心元件內容片段清單元件允許在根據內容片段模型的頁面上包含[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)清單。這對於建立可由其他應用程式輕鬆使用的[無周邊內容](https://helpx.adobe.com/tw/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js)尤其有用。

* 可在[設定對話框](#configure-dialog)中選取清單及其屬性。
* 樣式可套用至[設計對話框](#design-dialog)中的元件。

## 版本和相容性 {#version-and-compatibility}

內容片段元件的目前版本為 v2，此版本於 2022 年 2 月隨著核心元件 2.18.0 版發行導入，詳情請參閱本文件。

下表詳細說明該元件的所有支援版本、與元件版本相容的 AEM 版本，以及舊版文件的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|----|---|---|---|
| v2 | - | 相容 | 相容 | 相容 |
| [v1](v1/content-fragment-list.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本和發行版本的進一步詳細資訊，請參閱[核心元件版本](/help/versions.md)文件。

## 範例元件輸出 {#sample-component-output}

若要體驗「內容片段清單元件」，並檢視其設定選項及 HTML 和 JSON 輸出的範例，請造訪「[元件庫](https://adobe.com/go/aem_cmp_library_cflist)」。

## 技術詳細資訊 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_cflist_v1)有關內容片段清單元件的最新技術文件。

如需開發「核心元件」的進一步詳細資訊，請參閱[核心元件開發人員文件](/help/developing/overview.md)。

## 設定對話框 {#configure-dialog}

設定對話框可讓內容作者定義組成清單的內容片段，以及要包含的片段元素。

### 屬性索引標籤

**屬性**&#x200B;索引標籤定義清單中包含的內容片段。這主要是根據所選取的內容片段模型，但還有其他可用的篩選選項。

![內容片段清單元件的編輯對話框屬性索引標籤](/help/assets/content-fragment-list-properties.png)

* **模型** - 清單所根據的內容片段模型的路徑。
   * 預設情況下，定義為&#x200B;**模型路徑**&#x200B;的所有模型內容片段都會包含在清單中。
* **上層路徑** - 應從中建置清單的上層路徑。
   * 根據所選取&#x200B;**模型路徑**&#x200B;的內容片段將篩選為指定&#x200B;**上層路徑**&#x200B;上的內容片段。
      * 按一下或點選欄位右側的&#x200B;**開啟選取對話框**&#x200B;按鈕，以指定路徑。
* **標記** - 清單中只會包含具有指定標記的內容片段。
   * 按一下或點選欄位右側的&#x200B;**開啟選取對話框**&#x200B;按鈕，以指定標記。
   * 按一下或點選所選取標記旁的 X 可將其移除。
* **排序依據** - 清單排序依據的內容片段模型的欄位
   * 只能選取文字欄位 (包括數值、日期和時間)。
* **排序順序** - 清單將依&#x200B;**排序依據**&#x200B;欄位進行排序的方式
   * 升序或降序
* **最大項目數** - 清單中顯示的最大項目數
   * 沒有值時將傳回所有項目。
* **ID** - 此選項可讓您控制 HTML 和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果留空，則會自動產生唯一識別碼，您可以透過檢查得出的頁面找到該 ID。
   * 若已指定 ID，則作者應確保其為唯一識別碼。
   * 變更該 ID 會對 CSS、JS 和「資料層」追蹤造成影響。

>[!NOTE]
>核心元件 2.7.0 版已導入&#x200B;**排序依據**、**排序順序**&#x200B;和&#x200B;**最大項目數**&#x200B;選項。

### 元素索引標籤

預設情況下，內容片段模型的所有元素將會包含在清單中 (除非受到&#x200B;**最大項目數**&#x200B;欄位限制)。**元素**&#x200B;索引標籤允許您僅指定要包含的特定元素。

![內容片段清單元件的編輯對話框元素索引標籤](/help/assets/content-fragment-list-elements.png)

* **元素** - 只會顯示清單中內容片段的指定元素。
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕，以新增新的元素。
   * 點選或按一下&#x200B;**刪除**&#x200B;按鈕，即可移除已選取的元素。
   * 拖曳&#x200B;**順序**&#x200B;控點，以重新排列元素的順序。

### 樣式索引標籤 {#styles-tab-edit}

![內容片段清單元件編輯對話框的樣式索引標籤](/help/assets/content-fragment-list-styles.png)

內容片段清單元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。

使用下拉式清單，選取想要套用至元件的樣式。在編輯對話框中所做的選取，與從元件工具列中選擇具有相同效果。

元件樣式必須在[設計對話框](#design-dialog)中設定，才能使用該下拉式清單。

## 設計對話框 {#design-dialog}

### 樣式索引標籤 {#styles-tab}

內容片段清單元件支援 AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
