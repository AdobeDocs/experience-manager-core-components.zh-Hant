---
title: 內容片段清單元件 (v1)
description: 核心元件內容片段清單元件允許顯示內容片段清單。
role: Architect, Developer, Admin, User
exl-id: 37d6632d-360d-4081-8279-8efbb369a82e
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '694'
ht-degree: 100%

---


# 內容片段清單元件 (v1) {#content-fragment-list-component}

核心元件內容片段清單元件允許顯示[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)清單。

## 用途 {#usage}

核心元件內容片段清單元件允許在根據內容片段模型的頁面上包含[內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)清單。這對於建立可由其他應用程式輕鬆使用的[無周邊內容](https://helpx.adobe.com/tw/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js)尤其有用。

* 可在[設定對話框](#configure-dialog)中選取清單及其屬性。
* 樣式可套用至[設計對話框](#design-dialog)中的元件。

## 版本和相容性 {#version-and-compatibility}

本文件詳細說明「內容片段元件」的 v1 版本，此元件最初隨 2019 年 5 月的「核心元件」2.4.0 版發行導入。

>[!CAUTION]
>
>本文件說明內容片段清單元件 v1。
>
>如需內容片段清單元件目前版本的詳細資訊，請參閱[內容片段清單元件](/help/components/content-fragment-list.md)文件。

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

## 設計對話框 {#design-dialog}

透過設計對話框，範本作者可定義套用至內容片段清單元件的樣式。
